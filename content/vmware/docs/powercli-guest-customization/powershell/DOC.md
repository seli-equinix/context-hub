---
name: powercli-guest-customization
description: "VMware PowerCLI 13.3 — OS customization specifications for automated VM provisioning, NIC mapping, hostname, domain join"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,guest-customization,os-customization,sysprep,kickstart,nic-mapping,Get-OSCustomizationSpec,New-OSCustomizationSpec,Set-OSCustomizationSpec,Remove-OSCustomizationSpec,Get-OSCustomizationNicMapping,New-OSCustomizationNicMapping,Set-OSCustomizationNicMapping,Remove-OSCustomizationNicMapping"
---

# VMware PowerCLI — Guest Customization

## Golden Rule

**OS Customization Specs automate the first-boot configuration of VMs deployed from templates: hostname, domain join, IP address, and SID generation. Without them, every clone is a copy of the template with the same hostname and IP -- causing network conflicts.**

| Task | Cmdlet | Use When | Critical Notes |
|------|--------|----------|----------------|
| List specs | `Get-OSCustomizationSpec` | Audit what specs exist before deploying | Persistent specs are stored on vCenter; NonPersistent are ephemeral |
| Create Linux spec | `New-OSCustomizationSpec -OSType Linux` | Deploying Linux from template | `-Domain` is required; add `-DnsServer` and `-DnsSuffix` |
| Create Windows spec | `New-OSCustomizationSpec -OSType Windows` | Deploying Windows from template | Must specify `-Domain` or `-Workgroup`; `-ChangeSid` is critical |
| Set NIC IP | `New-OSCustomizationNicMapping` | Static IP assignment | Without NIC mapping, guest defaults to DHCP |
| Apply during deploy | `New-VM -OSCustomizationSpec` | Actually using the spec | Spec is applied during first boot after clone |

**Persistent vs NonPersistent:**
- **Persistent**: Saved on vCenter, reusable by name, appears in the GUI
- **NonPersistent**: In-memory only, typically cloned from a persistent spec and modified per-VM for unique IPs

## Scenario: Automated Linux VM Deployment with Static IP

```powershell
# Create a reusable Linux customization spec
New-OSCustomizationSpec -Name "linux-prod" `
    -OSType Linux -Domain "example.com" `
    -DnsServer "10.0.0.10", "10.0.0.11" `
    -DnsSuffix "example.com" `
    -NamingScheme Fixed -NamingPrefix "server" `
    -Description "Production Linux - static IP" `
    -Type Persistent -Server $vcenter

# Add static NIC mapping
$spec = Get-OSCustomizationSpec -Name "linux-prod" -Server $vcenter
New-OSCustomizationNicMapping -OSCustomizationSpec $spec `
    -IpMode UseStaticIp -IpAddress "10.0.100.50" `
    -SubnetMask "255.255.255.0" -DefaultGateway "10.0.100.1" `
    -Dns "10.0.0.10", "10.0.0.11"

# Deploy VM from template using the spec
$template = Get-Template "ubuntu-22.04-base" -Server $vcenter
$ds = Get-Datastore "VMFS-Prod-01" -Server $vcenter
$cluster = Get-Cluster "Production" -Server $vcenter

New-VM -Name "web-prod-05" -Template $template `
    -OSCustomizationSpec $spec -ResourcePool $cluster `
    -Datastore $ds -Location (Get-Folder "Web Servers") -Server $vcenter

Start-VM "web-prod-05" -Server $vcenter
```

## Scenario: Per-VM Unique IP Using NonPersistent Clone

For deploying multiple VMs, clone the spec per-VM and customize the IP.

```powershell
# Clone persistent spec into a non-persistent (ephemeral) copy per VM
$baseSpec = Get-OSCustomizationSpec -Name "linux-prod" -Server $vcenter

$vmConfigs = @(
    @{ Name = "web-01"; IP = "10.0.100.51" },
    @{ Name = "web-02"; IP = "10.0.100.52" },
    @{ Name = "web-03"; IP = "10.0.100.53" }
)

foreach ($cfg in $vmConfigs) {
    # Clone spec (NonPersistent = in-memory, no server-side conflict)
    $tempSpec = New-OSCustomizationSpec -OSCustomizationSpec $baseSpec `
        -Name "temp-$($cfg.Name)" -Type NonPersistent

    # Update hostname and NIC IP
    Set-OSCustomizationSpec -OSCustomizationSpec $tempSpec `
        -NamingScheme Fixed -NamingPrefix $cfg.Name

    Get-OSCustomizationNicMapping -OSCustomizationSpec $tempSpec |
        Set-OSCustomizationNicMapping -IpMode UseStaticIp `
            -IpAddress $cfg.IP -SubnetMask "255.255.255.0" `
            -DefaultGateway "10.0.100.1"

    # Deploy
    New-VM -Name $cfg.Name -Template $template `
        -OSCustomizationSpec $tempSpec -ResourcePool $cluster `
        -Datastore $ds -Server $vcenter
}
```

## Scenario: Windows Domain Join with SID Regeneration

```powershell
New-OSCustomizationSpec -Name "win-domain-join" `
    -OSType Windows -FullName "Administrator" -OrgName "Contoso" `
    -NamingScheme Prefix -NamingPrefix "WS-" `
    -Domain "contoso.com" `
    -DomainUsername "svc-vmjoin" -DomainPassword "JoinPassword!" `
    -ChangeSid `
    -TimeZone "035" `
    -AdminPassword "InitialP@ss1" `
    -LicenseMode PerSeat `
    -Type Persistent -Server $vcenter

# Set NIC to DHCP (common for Windows domain environments)
$spec = Get-OSCustomizationSpec "win-domain-join" -Server $vcenter
New-OSCustomizationNicMapping -OSCustomizationSpec $spec -IpMode UseDhcp
```

CRITICAL: `-ChangeSid` is essential for Windows. Without it, cloned VMs share the same SID, which breaks Active Directory trust relationships and causes authentication failures.

## Common Mistakes

### Mistake 1: Forgetting -ChangeSid on Windows Specs

```powershell
# WRONG -- Cloned VMs have duplicate SIDs
New-OSCustomizationSpec -Name "win-spec" -OSType Windows `
    -FullName "Admin" -OrgName "Corp" -Workgroup "WORKGROUP"
# Every VM deployed from this spec has the SAME Windows SID

# CORRECT -- Always use -ChangeSid for Windows
New-OSCustomizationSpec -Name "win-spec" -OSType Windows `
    -FullName "Admin" -OrgName "Corp" -Workgroup "WORKGROUP" -ChangeSid
```

### Mistake 2: No NIC Mapping Means DHCP by Default

```powershell
# WRONG -- Create spec but forget NIC mapping, guest gets random DHCP address
New-OSCustomizationSpec -Name "linux-static" -OSType Linux -Domain "example.com"
# VM boots with DHCP -- not the static IP you expected

# CORRECT -- Always add NIC mapping for static IP environments
$spec = Get-OSCustomizationSpec "linux-static"
New-OSCustomizationNicMapping -OSCustomizationSpec $spec `
    -IpMode UseStaticIp -IpAddress "10.0.100.50" `
    -SubnetMask "255.255.255.0" -DefaultGateway "10.0.100.1"
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-OSCustomizationSpec` | List specs | `-Name`, `-Type` (Persistent/NonPersistent), `-Server` |
| `New-OSCustomizationSpec` | Create spec | `-Name`, `-OSType` (Linux/Windows), `-Domain`, `-NamingScheme`, `-ChangeSid`, `-Type` |
| `New-OSCustomizationSpec` (clone) | Clone existing spec | `-OSCustomizationSpec` (source), `-Name`, `-Type NonPersistent` |
| `Set-OSCustomizationSpec` | Modify spec | `-NamingScheme`, `-Domain`, `-DnsServer`, `-Description` |
| `Remove-OSCustomizationSpec` | Delete spec | `-OSCustomizationSpec` |
| `Get-OSCustomizationNicMapping` | List NIC mappings | `-OSCustomizationSpec` |
| `New-OSCustomizationNicMapping` | Add NIC mapping | `-OSCustomizationSpec`, `-IpMode`, `-IpAddress`, `-SubnetMask`, `-DefaultGateway`, `-Dns` |
| `Set-OSCustomizationNicMapping` | Modify NIC mapping | `-IpMode`, `-IpAddress`, `-SubnetMask`, `-DefaultGateway` |
| `Remove-OSCustomizationNicMapping` | Delete NIC mapping | `-OSCustomizationNicMapping` |
