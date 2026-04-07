---
name: powercli-guest-customization
description: "VMware PowerCLI 13.3 — OS customization specs, in-guest script execution, file copy"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 2
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,guest-customization,Get-OSCustomizationNicMapping, Get-OSCustomizationSpec, New-OSCustomizationNicMapping, New-OSCustomizationSpec, Remove-OSCustomizationNicMapping, Remove-OSCustomizationSpec, Set-OSCustomizationNicMapping, Set-OSCustomizationSpec"
---

# VMware PowerCLI — Guest Customization

OS customization specs, in-guest script execution, file copy. Module: VMware.VimAutomation (8 cmdlets).

## Get

### `Get-OSCustomizationNicMapping`

**This cmdlet retrieves the configured NIC setting mappings for the specified OS customization specification.**

**Parameters:**

- -OSCustomizationSpec [OSCustomizationSpec[]] (Required) Specifies the OS customization specification for which you want to retrieve the NIC settings mapping.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
$spec1 = Get-OSCustomizationSpec "test"
```
_Retrieves the NIC mappings of the "test" and "test_old" OS customization specifications._

### `Get-OSCustomizationSpec`

**This cmdlet retrieves the OS customization specifications available on a vCenter Server system.**

This cmdlet retrieves the OS customization specifications available on a vCenter Server system. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Id [String[]] (Optional) Specifies the IDs of the OS customization specifications you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the OS customization specifications you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Type [OSCustomizationSpecType] (Optional) Specifis the type of the OS customization specifications you want to retrieve. The valid values are Persistent and NonPersistent.

**Examples:**

```powershell
Get-OSCustomizationSpec "test"
```
_Retrieves from the server the OS customization specification named 'test'._

```powershell
New-VM -Name VM -VMHost Host -Template Template -OSCustomizationSpec $spec
```
_Creates a new virtual machine from a template and configures it using a customization specification._

## New

### `New-OSCustomizationNicMapping`

**This cmdlet adds NIC settings mappings to the specified OS customization specifications.**

This cmdlet adds  NIC settings mappings to the specified OS customization specifications. If the given specification is server-side, it is updated on the server. If it is client-side, the reference that is kept in-memory is updated but the variable that is passed to the cmdlet is not modified.

**Parameters:**

- -AlternateGateway [String] (Optional) Specifies an alternate gateway.
- -DefaultGateway [String] (Optional) Specifies a default gateway.
- -Dns [String[]] (Optional) Specifies a DNS address. This parameter applies only to Windows operating systems.
- -IpAddress [String] (Optional) Specifies an IP address. Using this parameter automatically sets the IpMode parameter to UseStaticIp.
- -IpMode [OSCustomizationIPMode] (Optional) Specifies the IP configuration mode. The valid values are UseDhcp, PromptUser, UseVCApplication, and UseStaticIP.
- -NetworkAdapterMac [String[]] (Optional) Specifies the MAC addresses of the network adapters to which you want to map the new OS customization specifications.
- -OSCustomizationSpec [OSCustomizationSpec] (Required) Specifies the OS customization specification to which you want to add the NIC setting mapping. Passing multiple values to this parameter is obsolete.
- -Position [Int32[]] (Optional) Specifies the position of the NIC to which you want to map the OS customization specification.
- -Ipv6Address [String] (Optional) Specifies an IPv6 address.
- -Ipv6AlternateGateway [String] (Optional) Specifies an alternate IPv6 gateway.
- -Ipv6Gateway [String] (Optional) Specifies the default IPv6 gateway.
- -Ipv6Mode [OSCustomizationIPMode] (Optional) Specifies the IPv6 configuration mode. The valid values are UseDhcp, PromptUser, UseVCApplication, UseStaticIP, UseStatelessIpv6 and UseAutoIpv6.
- -Ipv6Prefix [Int32] (Optional) Specifies the IPv6 prefix.
- -Ipv6VcApplicationArgument [String] (Optional) Specifies a new argument to pass to a vCenter Server application to obtain an IPv6 address.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -SubnetMask [String] (Optional) Specifies a subnet mask.
- -VCApplicationArgument [String] (Optional) Specifies an optional argument you want to pass to the vCenter Server to obtain an IP address.
- -Wins [String[]] (Optional) Specifies WINS servers. This parameter applies only to Windows operating systems.

**Examples:**

```powershell
New-OSCustomizationNicMapping -OSCustomizationSpec $spec -IpMode UseStaticIP -IPAddress 10.0.0.1 -SubnetMask 255.255.255.0 -DefaultGateway 10.0.0.253 -DnsServer 10.0.0.253
```
_Creates a new NIC mapping for the OS customization spec stored in $spec._

### `New-OSCustomizationSpec`

**This cmdlet creates a new OS customization specification.**

This cmdlet creates a new OS customization specification or clones an existing one. If a name is provided, creates and adds the specified customization specification to the server. Otherwise, creates and returns the requested specification object. If the Name parameter is not specified, the OSCustomizationSpec object is not persisted on the server. Either the Domain or the Workgroup parameters should be provided if a Windows specification is created. If a Linux specification is created, the Domain parameter is mandatory. New-OSCustomizationSpec automatically creates a default NIC mapping.

**Parameters:**

- -AdminPassword [String] (Optional) Specifies a new OS administrator's password. This parameter applies only to Windows operating systems. If not specified, the administrator's password is set to blank.
- -AutoLogonCount [Int32] (Optional) Specifies the number of times the virtual machine automatically logs in as administrator without prompting for user credentials. The valid values are in the range between 0 and Int32.MaxValue. Specifying 0 deactivates auto log-on. This parameter applies only to Windows operating systems.
- -ChangeSid [SwitchParameter] (Optional) Indicates that the customization should modify the system security identifier (SID). This parameter applies only to Windows operating systems.
- -CustomizationScript [String] (Optional) Specifies a bash script that runs before and after the customization of the guest operating system. You can use this parameter only for Linux-based operating systems. Use the bash script itself and not the path to it.
- -DeleteAccounts [SwitchParameter] (Optional) Indicates that you want to delete all user accounts. This parameter applies only to Windows operating systems.
- -Description [String] (Optional) Provides a description for the new specification.
- -DnsServer [String[]] (Optional) Specifies the DNS server settings. This parameter applies only to Linux operating systems.
- -DnsSuffix [String[]] (Optional) Specifies the DNS suffix settings. This parameter applies only to Linux operating systems.
- -Domain [String] (Optional) Specifies a domain name.
- -DomainCredentials [PSCredential] (Optional) Specifies the credentials you want to use for domain authentication. This parameter applies only to Windows operating systems.
- -DomainPassword [String] (Optional) Specifies the password you want to use for domain authentication. This parameter applies only to Windows operating systems.
- -DomainUsername [String] (Optional) Specifies the user name you want to use for domain authentication. This parameter applies only to Windows operating systems.
- -FullName [String] (Required) Specifies the administrator's full name. This parameter applies only to Windows operating systems.
- -GuiRunOnce [String[]] (Optional) Specifies a list of commands. These commands run when a user logs in for the first time after the customization completes. This parameter applies only to Windows operating systems.
- -LicenseMaxConnections [Int32] (Optional) Specifies the maximum connections for server license mode. Use this parameter only if the LicenseMode parameter is set to Perserver. This parameter applies only to Windows operating systems.
- -LicenseMode [LicenseMode] (Optional) Specifies the license mode of the Windows 2000/2003 guest operating system. The valid values are Perseat, Perserver, and Notspecified. If Perserver is set, use the LicenseMaxConnection parameter to define the maximum number of connections. This parameter applies only to Windows operating systems.
- -Name [String] (Optional) Specifies a name for the new specification.
- -NamingPrefix [String] (Optional) Depends on the customization naming scheme - Custom, NamingPrefix, or Prefix. If the "Custom" naming scheme is used, NamingPrefix is an optional argument that is passed to the utility for this IP address. The meaning of this field is user-defined in the script. If the "Fixed" naming scheme is used, NamingPrefix should indicate the name of the virtual machine. If the "Prefix" naming scheme is selected, NamingPrefix indicates the prefix to which a unique number is appended.
- -NamingScheme [String] (Optional) Specifies the naming scheme for the virtual machine. The following values are valid:
- -OrgName [String] (Required) Specifies the name of the organization to which the administrator belongs.
- -OSCustomizationSpec [OSCustomizationSpec] (Required) Specifies an OS customization specification that you want to clone.
- -OSType [String] (Optional) Specifies the type of the operating system. The valid values are Linux and Windows.
- -ProductKey [String] (Optional) Specifies the MS product key. If the guest OS version is earlier than Vista, this parameter is required in order to make the customization unattended. For Vista or later, the OS customization is unattended no matter if the ProductKey parameter is set.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -TimeZone [String] (Optional) Specifies the name or ID of the time zone for a Windows guest OS only. Using wildcards is supported. The following time zones are available:
- -Type [OSCustomizationSpecType] (Optional) Specifies the type of the OS customization specification. The valid values are Persistent and NonPersistent.
- -Workgroup [String] (Optional) Specifies a workgroup. This parameter applies only to Windows operating systems.

**Examples:**

```powershell
New-OSCustomizationSpec -Name Spec -OSType Windows -FullName Administrator -OrgName Organization -NamingScheme Fixed -NamingPrefix Computer -ProductKey "xxxx-xxxx" -LicenseMode PerSeat -Workgroup Workgroup -ChangeSid
```
_Generates a new SID for the machine and sets the name of the machine to "Computer"._

```powershell
New-OSCustomizationSpec -Name Spec -OSType Windows -Description "This spec adds a computer in a domain." -FullName Administrator -OrgName Organization -NamingScheme Fixed -NamingPrefix "Computer" -ProductKey "xxxx-xxxx" -LicenseMode Perserver -LicenseMaxConnections 30 -AdminPassword pass -Domain Domain -DomainUsername Root -DomainPassword pass
```
_Creates a customization specification that adds a computer in the domain named "Domain"._

## Remove

### `Remove-OSCustomizationNicMapping`

**This cmdlet removes the specified OS customization NIC mappings.**

**Parameters:**

- -OSCustomizationNicMapping [OSCustomizationNicMapping[]] (Required) Specifies the OSCustomizationNicMapping objects you want to remove.

**Examples:**

```powershell
$nicMapping = Get-OSCustomization MyCustomizationSpec | Get-OSCustomizationNicMapping
```
_Removes the NIC mappings of the specified OS customization spec without asking for confirmation._

### `Remove-OSCustomizationSpec`

**This cmdlet removes the specified OS customization specifications.**

**Parameters:**

- -OSCustomizationSpec [OSCustomizationSpec[]] (Required) Specifies the customization specifications you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-OSCustomizationSpec Spec -Confirm
```
_Removes the Spec OS customization specification from the server._

## Set

### `Set-OSCustomizationNicMapping`

**This cmdlet modifies the provided OS customization NIC mappings.**

This cmdlet modifies the provided OS customization NIC mappings. If the parent spec of the provided NIC mapping is a server-side spec, it is updated on the server. If the parent spec is client-side, the reference that is kept in the memory is updated, but the variable that is passed to the cmdlet is not modified.

**Parameters:**

- -AlternateGateway [String] (Optional) Specifies an alternate gateway.
- -DefaultGateway [String] (Optional) Specifies a default gateway.
- -Dns [String[]] (Optional) Specifies a DNS address. This parameter applies only to Windows operating systems.
- -IpAddress [String] (Optional) Specifies an IP address. Using this parameter automatically sets the IpMode parameter to UseStaticIp.
- -IpMode [OSCustomizationIPMode] (Optional) Specifies the IP configuration mode. The valid values are UseDhcp, PromptUser, UseVCApplication, and UseStaticIP.
- -NetworkAdapterMac [String] (Optional) Specifies the MAC address of the network adapter to which you want to map the OS customization specification.
- -OSCustomizationNicMapping [OSCustomizationNicMapping[]] (Required) Specifies the OS customization NIC mapping you want to configure.
- -Position [Int32] (Optional) Specifies the position of the mapping you want to modify.
- -Ipv6Address [String] (Optional) Specifies an IPv6 address.
- -Ipv6AlternateGateway [String] (Optional) Specifies an alternate IPv6 gateway.
- -Ipv6Gateway [String] (Optional) Specifies the default IPv6 gateway.
- -Ipv6Mode [OSCustomizationIPMode] (Optional) Specifies the IPv6 configuration mode. The valid values are UseDhcp, PromptUser, UseVCApplication, UseStaticIP, UseStatelessIpv6 and UseAutoIpv6.
- -Ipv6Prefix [Int32] (Optional) Specifies the IPv6 prefix.
- -Ipv6VcApplicationArgument [String] (Optional) Specifies a new argument to pass to a vCenter Server application to obtain an IPv6 address.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -SubnetMask [String] (Optional) Specifies a subnet mask.
- -VCApplicationArgument [String] (Optional) Specifies a new argument you want to pass to VCApplication in order to obtain an IP address.
- -Wins [String[]] (Optional) Specifies WINS servers. This parameter applies only to Windows operating systems.

**Examples:**

```powershell
Get-OSCustomizationSpec Spec | Get-OSCustomizationNicMapping | Set-OSCustomizationNicMapping -IpAddress 10.0.0.2
```
_Modifies the IP address of the specified NIC mapping that uses static IP mode._

```powershell
Get-OSCustomizationSpec Spec | Get-OSCustomizationNicMapping | Set-OSCustomizationNicMapping -VcApplicationArgument "subnet2"
```
_Modifies the VCApplication argument of the specified NIC mapping._

```powershell
Get-OSCustomizationSpec Spec | Get-OSCustomizationNicMapping | Set-OSCustomizationNicMapping -IpMode UseStaticIp -IpAddress 10.10.0.1 -SubnetMask 255.255.255.0 -DefaultGateway 10.10.0.1 -AlternateGateway 10.10.0.1 -Dns 10.10.150.1 -PrimaryWins 10.10.150.2
```
_Modifies the attributes of a NIC mapping._

### `Set-OSCustomizationSpec`

**This cmdlet modifies the specified OS customization specification.**

This cmdlet modifies the specified OS customization specification. The specification to be updated is identified by one or both of the Name and Spec parameters. If a Windows specification is to be updated, one of the  Domain and Workgroup parameters must be provided. If a Linux specification is to be updated, the Domain parameter must be provided.

**Parameters:**

- -AdminPassword [String] (Optional) Specifies the new OS administrator's password. This parameter applies only to Windows operating systems.
- -AutoLogonCount [Int32] (Optional) Specifies the number of times the virtual machine should automatically login as an administrator. The valid values are in the range between 0 and Int32.MaxValue. Specifying 0 deactivates auto log-on. This parameter applies only to Windows operating systems.
- -ChangeSID [Boolean] (Optional) Indicates that the customization should modify the system security identifier (SID). This parameter applies only to Windows operating systems.
- -CustomizationScript [String] (Optional) Specifies a bash script that runs before and after the customization of the guest operating system. You can use this parameter only for Linux-based operating systems. Use the bash script itself and not the path to it.
- -DeleteAccounts [Boolean] (Optional) Indicates that you want to delete all user accounts. This parameter applies only to Windows operating systems.
- -Description [String] (Optional) Provides a new description for the specification.
- -DnsServer [String[]] (Optional) Specifies the DNS server. This parameter applies only to Linux operating systems.
- -DnsSuffix [String[]] (Optional) Specifies the DNS suffix. This parameter applies only to Linux operating systems.
- -Domain [String] (Optional) Specifies the domain name.
- -DomainCredentials [PSCredential] (Optional) Specifies credentials for authentication with the specified domain. This parameter applies only to Windows operating systems.
- -DomainPassword [String] (Optional) Specifies a password for authentication with the specified domain. This parameter applies only to Windows operating systems.
- -DomainUsername [String] (Optional) Specifies a username for authentication with the specified domain. This parameter applies only to Windows operating systems.
- -FullName [String] (Optional) Specifies the administrator's full name. This parameter applies only to Windows operating systems.
- -GuiRunOnce [String[]] (Optional) Provides a list of commands to run after first user login. This parameter applies only to Windows operating systems.
- -LicenseMaxConnections [Int32] (Optional) Specifies the maximum connections for server license mode. Use this parameter only if the LicenseMode parameter is set to Perserver. This parameter applies only to Windows operating systems.
- -LicenseMode [LicenseMode] (Optional) Specifies the license mode of the Windows 2000/2003 guest operating system. The valid values are Perseat, Perserver, and NotSpecified. If Perserver is set, use the LicenseMaxConnection parameter to define the maximum number of connections. This parameter applies only to Windows operating systems.
- -Name [String] (Optional) Specifies a new name for the OS customization specification.
- -NamingPrefix [String] (Optional) The behavior of this parameter is related to the customization scheme. If a Custom customization scheme is specified, NamingPrefix is an optional argument that is passed to the utility for this IP address. The value of this field is defined by the user in the script. If a Fixed customization scheme is specified, NamingPrefix should indicate the name of the virtual machine. If a Prefix customization scheme is set, NamingPrefix indicates the prefix to which a unique number is appended.
- -NamingScheme [String] (Optional) Specifies the naming scheme for the virtual machine. The valid values are Custom, Fixed, Prefix, and Vm.
- -NewSpec [OSCustomizationSpec] (Optional) If no other parameters are provided, this parameter specifies a specification from which to retrieve information for the updated specification.
- -OrgName [String] (Optional) Specifies the name of the organization to which the administrator belongs.
- -OSCustomizationSpec [OSCustomizationSpec[]] (Required) Specifies the specification you want to modify.
- -ProductKey [String] (Optional) Specifies the MS product key. If the guest OS version is earlier than Vista, this parameter is required in order to make the customization unattended. For Windows Vista and later, the OS customization is unattended no matter if the ProductKey parameter is set.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -TimeZone [String] (Optional) Specifies the name or ID of the time zone for a Windows guest OS only. Using wildcards is supported. The following time zones are available:
- -Type [OSCustomizationSpecType] (Optional) Sets the type of the OS customization specification. The valid values are Persistent and NonPersistent.
- -Workgroup [String] (Optional) Specifies the workgroup. This parameter applies only to Windows operating systems.

**Examples:**

```powershell
Set-OSCustomizationSpec Spec -Description 'This is a test OS customization specification.'
```
_Updates the description of the Spec OS customization specification._
