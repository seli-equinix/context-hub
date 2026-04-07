---
name: powercli-guest-customization
description: "VMware PowerCLI 13.3 — OS customization specs, in-guest script execution, file copy"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,guest-customization,Get-OSCustomizationNicMapping, Get-OSCustomizationSpec, New-OSCustomizationNicMapping, New-OSCustomizationSpec, Remove-OSCustomizationNicMapping, Remove-OSCustomizationSpec, Set-OSCustomizationNicMapping, Set-OSCustomizationSpec"
---

# VMware PowerCLI — Guest Customization

OS customization specs, in-guest script execution, file copy. Module: VMware.VimAutomation (8 cmdlets).

## Cmdlet Reference (8 cmdlets)

### Get

#### `Get-OSCustomizationNicMapping`

This cmdlet retrieves the configured NIC setting mappings for the specified OS customization specification.

**Parameters**: `OSCustomizationSpec, Server`

#### `Get-OSCustomizationSpec`

This cmdlet retrieves the OS customization specifications available on a vCenter Server system.

**Parameters**: `Server, Name, Id, Type`

### New

#### `New-OSCustomizationNicMapping`

This cmdlet adds NIC settings mappings to the specified OS customization specifications.

**Parameters**: `OSCustomizationSpec, NetworkAdapterMac, Position, Server, IpMode, VCApplicationArgument, IpAddress, SubnetMask, Ipv6Prefix, Ipv6Address, Ipv6Mode, Ipv6VcApplicationArgument` (+6 more)

#### `New-OSCustomizationSpec`

This cmdlet creates a new OS customization specification.

**Parameters**: `OSCustomizationSpec, FullName, OrgName, OSType, ChangeSid, DeleteAccounts, Server, Name, Type, DnsServer, DnsSuffix, GuiRunOnce` (+15 more)

### Remove

#### `Remove-OSCustomizationNicMapping`

This cmdlet removes the specified OS customization NIC mappings.

**Parameters**: `OSCustomizationNicMapping`

#### `Remove-OSCustomizationSpec`

This cmdlet removes the specified OS customization specifications.

**Parameters**: `OSCustomizationSpec, Server`

### Set

#### `Set-OSCustomizationNicMapping`

This cmdlet modifies the provided OS customization NIC mappings.

**Parameters**: `OSCustomizationNicMapping, NetworkAdapterMac, Position, Server, IpMode, VCApplicationArgument, IpAddress, SubnetMask, Ipv6Prefix, Ipv6Address, Ipv6Mode, Ipv6VcApplicationArgument` (+6 more)

#### `Set-OSCustomizationSpec`

This cmdlet modifies the specified OS customization specification.

**Parameters**: `FullName, OrgName, ChangeSID, DeleteAccounts, OSCustomizationSpec, NewSpec, Type, Server, Name, DnsServer, DnsSuffix, GuiRunOnce` (+15 more)
