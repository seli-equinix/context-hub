---
name: powercli-security-permissions
description: "VMware PowerCLI 13.3 — Roles, permissions, privileges, key providers, TPM, Trust Authority"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 2
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,security-permissions,Add-AttestationServiceInfo, Add-EntityDefaultKeyProvider, Add-KeyManagementServer, Add-KeyProviderServiceInfo, Add-TrustAuthorityKeyProviderServer, Add-TrustAuthorityKeyProviderServerCertificate, Complete-VIOAuth2ClientSecretRotation, Export-KeyProvider, Export-Tpm2CACertificate, Export-Tpm2EndorsementKey, Export-TrustAuthorityKeyProviderClientCertificate, Export-TrustAuthorityServicesInfo, Export-TrustedPrincipal, Get-AttestationServiceInfo, Get-KeyManagementServer, Get-KeyProvider, Get-KeyProviderServiceInfo, Get-SecurityInfo, Get-SecurityPolicy, Get-Tpm2EndorsementKey, Get-TrustAuthorityAttestationService, Get-TrustAuthorityKeyProvider, Get-TrustAuthorityKeyProviderClientCertificate, Get-TrustAuthorityKeyProviderClientCertificateCSR, Get-TrustAuthorityKeyProviderServer, Get-TrustAuthorityKeyProviderServerCertificate, Get-TrustAuthorityKeyProviderService, Get-TrustAuthorityPrincipal, Get-TrustAuthorityServicesStatus, Get-TrustAuthorityTpm2AttestationSettings, Get-TrustAuthorityTpm2CACertificate, Get-TrustAuthorityTpm2EndorsementKey, Get-TrustedPrincipal, Get-VDSecurityPolicy, Get-VIAccount, Get-VIOAuth2Client, Get-VIPermission, Get-VIPrivilege, Get-VIPrivilegeReport, Get-VIRole, Get-VTpm, Get-VTpmCertificate, Get-VTpmCSR, Import-KeyProvider, Import-TrustAuthorityServicesInfo, New-TrustAuthorityKeyProvider, New-TrustAuthorityKeyProviderClientCertificate, New-TrustAuthorityKeyProviderClientCertificateCSR, New-TrustAuthorityPrincipal, New-TrustAuthorityTpm2CACertificate, New-TrustAuthorityTpm2EndorsementKey, New-VIOAuth2Client, New-VIPermission, New-VIRole, New-VISamlSecurityContext, New-VTpm, Register-KeyProvider, Remove-AttestationServiceInfo, Remove-EntityDefaultKeyProvider, Remove-KeyManagementServer, Remove-KeyProviderServiceInfo, Remove-TrustAuthorityKeyProvider, Remove-TrustAuthorityKeyProviderServer, Remove-TrustAuthorityKeyProviderServerCertificate, Remove-TrustAuthorityPrincipal, Remove-TrustAuthorityTpm2CACertificate, Remove-TrustAuthorityTpm2EndorsementKey, Remove-VIOAuth2Client, Remove-VIPermission, Remove-VIRole, Remove-VTpm, Set-KeyManagementServer, Set-KeyProvider, Set-SecurityPolicy, Set-TrustAuthorityKeyProvider, Set-TrustAuthorityKeyProviderClientCertificate, Set-TrustAuthorityKeyProviderServerCertificate, Set-TrustAuthorityTpm2AttestationSettings, Set-VDSecurityPolicy, Set-VIOAuth2Client, Set-VIPermission, Set-VIRole, Set-VTpm, Start-VIOAuth2ClientSecretRotation, Unregister-KeyProvider"
---

# VMware PowerCLI — Security & Permissions

Roles, permissions, privileges, key providers, TPM, Trust Authority. Module: VMware.VimAutomation (85 cmdlets).

## Add

### `Add-AttestationServiceInfo`

**This cmdlet adds an attestation service information, which comes from the TrustAuthorityAttestationService that runs in the Trust Authority system or its detailed information in the workload vCenter Server system.**

**Parameters:**

- -AttestationService [TrustAuthorityAttestationService[]] (Required) Specifies the Trust Authority attestation services that you want to retrieve from the Trust Authority system.
- -FilePath [String] (Optional) Specifies a file that stores the X509Chain data you want to use to connect to the Trust Authority attestation service.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -ServiceAddress [String] (Required) Specifies the service address that you want to retrieve from the service address in the Trust Authority attestation service in the Trust Authority system.
- -ServiceGroup [String] (Required) Specifies the service group that you want to retrieve from the service group in the Trust Authority attestation service in the Trust Authority system.
- -ServicePort [Int32] (Optional) Specifies the number of the service port which is retrieved from the service port in the Trust Authority attestation service in the Trust Authority system.
- -TAClusterId [String] (Required) Specifies the Trust Authority cluster ID which you want to retrieve from the Trust Authority cluster ID in the running Trust Authority attestation service in the Trust Authority system.
- -TrustedCA [X509Chain] (Optional) Specifies the Trusted Certificate Authority which you want to retrieve from the Trusted Certificate Authority in the running Trust Authority attestation service in the Trust Authority system.

**Examples:**

```powershell
$attestService = Get-TrustAuthorityAttestationService -Server trustAuthoritySystem
```
_Adds the attestation service information to the workload vCenter Server system by specifying the TrustAuthorityAttesationService objects retrieved from the Trust Authority system._

```powershell
$attestService = Get-TrustAuthorityAttestationService -Server trustAuthoritySystem | select -First 1
```
_Adds the attestation service information to the workload vCenter Server system by specifying detailed information of the TrustAuthorityAttesationService running in the Trust Authority system._

### `Add-EntityDefaultKeyProvider`

**This cmdlet adds a key provider to entities as default key provider.**

**Parameters:**

- -KeyProvider [KeyProvider] (Required) Specifies the key provider you want to add to the entities.
- -Entity [VIObject[]] (Required) Specifies the entities to which you want to add a default key provider. Only the Cluster type and the HostAndCluster type support this operation.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
$cluster  = Get-Cluster -name "MyCluster"
```
_Adds the first key provider to entity "MyCluster" as default key provider._

### `Add-KeyManagementServer`

**This cmdlet adds a key management server to a vCenter Server system.**

**Parameters:**

- -Address [String] (Required) Specifies the address of the Key Management Interoperability Protocol server.
- -Credential [PSCredential] (Optional) Specifies a PSCredential object that contains credentials for authenticating with the key management server.
- -Name [String] (Required) Specifies the name of the Key Management Interoperability Protocol server you want to add.
- -KeyProvider [String] (Required) Specifies the key provider to which you want to add the key management server. This parameter also accepts objects of type KmsCluster through an ArgumentTransformationAttribute object.
- -Password [SecureString] (Optional) Specifies the password you want to use for authenticating with the Key Management Interoperability Protocol server.
- -Port [Int32] (Required) Specifies the port number of the Key Management Interoperability Protocol server.
- -ProxyAddress [String] (Optional) Specifies the address of the proxy server.
- -ProxyPort [Int32] (Optional) Specifies the port number of the proxy server.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustKeyManagementServer [Boolean] (Required) Indicates whether the vCenter Server system can trust the key management server certificate.
- -Username [String] (Optional) Specifies the user name you want to use for authenticating with the Key Management Interoperability Protocol server.

**Examples:**

```powershell
Add-KeyManagementServer -Name 'KMS' -KeyProvider 'KeyProvider' -Address $kmsAddress -Port $kmsPort -ProxyAddress $proxyAddress -ProxyPort $proxyPort -TrustKeyManagementServer $true
```
_Adds the key management server named 'KMS' to the 'KeyProvider' key provider that runs at the $kmsAddress address, $kmsPort port, and trusts the key management server certificate._

### `Add-KeyProviderServiceInfo`

**This cmdlet adds key provider service information, which comes from the Trust Authority key provider service running in the Trust Authority system or its detailed information in the workload vCenter Server system.**

**Parameters:**

- -FilePath [String] (Optional) Specifies a file that stores the X509Chain data that you want to use to connect to the Trust Authority key provider service.
- -KeyProviderService [TrustAuthorityKeyProviderService[]] (Required) Specifies the Trust Authority key provider services that you want to retrieve from the Trust Authority System.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-CIServer cmdlet.
- -ServiceAddress [String] (Required) Specifies the service address which you want to retrieve from the service address in the Trust Authority key provider service in the Trust Authority system.
- -ServiceGroup [String] (Required) Specifies the service group which you want to retrieve from the service group in the Trust Authority key provider service in the Trust Authority system.
- -ServicePort [Int32] (Optional) Specifies the number of the service port which you want to retrieve from the service port in the Trust Authority key provider service in the Trust Authority system.
- -TAClusterId [String] (Required) Specifies the Trust Authority cluster ID which you want to retrieve from the Trust Authority cluster ID in the running Trust Authority key provider service in the Trust Authority system.
- -TrustedCA [X509Chain] (Optional) Specifies the Trusted Certificate Authority that you want to retrieve from the Trusted Certificate Authority in the running Trust Authority key provider service in the Trust Authority system.

**Examples:**

```powershell
$kmxService = Get-TrustAuthorityKeyProviderService -Server trustAuthoritySystem
```
_Adds the key provider service information to the workload vCenter Server system by specifying the TrustAuthorityKeyProviderService objects that you want to retrieve from the Trust Authority system._

```powershell
$kmxService = Get-TrustAuthorityKeyProviderService -Server trustAuthoritySystem | select -First 1
```
_Adds the key provider service information to the workload vCenter Server system by specifying detailed information of the Trust Authority key provider service that runs in the Trust Authority system._

### `Add-TrustAuthorityKeyProviderServer`

**This cmdlet adds a new Trust Authority key provider server to an existing Trust Authority key provider in the Trust Authority system.**

**Parameters:**

- -Address [String] (Required) Specifies the address of the key provider server that you want to add.
- -KeyProvider [TrustAuthorityKeyProvider] (Required) Specifies the Trust Authority key provider to which you want to add a new Trust Authority key provider Server.
- -Name [String] (Optional) Specifies the name of the new Trust Authority key provider server. If it's not specified, the name is the same as the Address parameter.
- -Port [Int32] (Optional) Specifies the number of the port that the Trust Authority key provider server uses to communicate with the Trust Authority key provider.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.

**Examples:**

```powershell
$kp = Get-TrustAuthorityKeyProvider -Name myProvider -TrustAuthorityCluster myCluster
```
_Adds a new Trust Authority key provider server with address 1.1.1.1 to the Trust Authority key provider named myProvider._

### `Add-TrustAuthorityKeyProviderServerCertificate`

**This cmdlet adds the certificate from the Trust Authority key provider server to be trusted by the Trust Authority key provider.**

**Parameters:**

- -Certificate [X509Certificate2[]] (Required) Specifies the certificate to be trusted by the specified Trust Authority key provider.
- -FilePath [String] (Required) Specifies a file that stores the X509Certificate2 data which you want to be trusted by the Trust Authority key provider.
- -KeyProvider [TrustAuthorityKeyProvider] (Required) Specifies the Trust Authority key provider to trust the specified certificate.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -ServerCertificate [TrustAuthorityKeyProviderServerCertificate[]] (Required) Specifies the Trust Authority key provider server certificate that you can trust.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.

**Examples:**

```powershell
$kps = Get-TrustAuthorityKeyProviderServer -KeyProvider myProvider | select -First 1
```
_Adds the $serverCertificate certificate which you can retrieve from the first Trust Authority key Provider server in the Trust Authority key provider named myProvider._

```powershell
$kps = Get-TrustAuthorityKeyProviderServer -KeyProvider myProvider | select -First 1
```
_Adds the certificate which you want to retrieve from the $serverCertificate certificate to be trusted by the Trust Authority key provider myProvider._

## Complete

### `Complete-VIOAuth2ClientSecretRotation`

**Forces an immediate secret rotation for a specific OAuth 2 client.**

Forces an immediate secret rotation for a specific OAuth 2 client. The new secret becomes the current secret of the OAuth 2 client.

**Parameters:**

- -OAuth2Client [OAuth2Client[]] (Optional) Specifies the OAuth 2 client whose secrete rotation you want to force immediately.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
PS C:\> Get-VIOAuth2Client -Id "my-client-id" | Complete-VIOAuth2ClientSecretRotation
```
_Forces an immediate secret rotation for an OAuth 2 client with client ID "my-client-id"._

## Export

### `Export-KeyProvider`

**This cmdlet exports a specified key provider configuration to a specified file. You can use only the NativeKeyProvider type for the KeyProvider parameter.**

**Parameters:**

- -FilePath [String] (Required) Specifies the path to the file where you want to store the given key provider configuration. If the path leads to a folder, the cmdlet creates a file in the folder.
- -Force [SwitchParameter] (Optional) Indicates that the cmdlet overwrites the existing destination files and creates directories to complete the specified file path.
- -KeyProvider [KeyProvider] (Required) Specifies the key providers that you want to backup.
- -Password [SecureString] (Optional) Specifies the password to encrypt the exported configuration.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Export-KeyProvider -KeyProvider mykp -FilePath c:\myfile
```
_Exports the 'mykp' key provider configuration to the specified file c:\myfile._

### `Export-Tpm2CACertificate`

**This cmdlet exports the CA certificate from either the certificate in the specified TPM 2.0 endorsement key or the specified certificate to a file.**

**Parameters:**

- -Certificate [X509Certificate2] (Required) Specifies the certificate from which you can export the CA certificate to a file.
- -FilePath [String] (Required) Specifies the path to the file where you want to export the CA certificate.
- -Force [SwitchParameter] (Optional) Indicates that the cmdlet overwrites the existing destination files and creates directories to complete the specified file path.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Tpm2EndorsementKey [Tpm2EndorsementKey] (Required) Specifies the TPM 2.0 endorsement key that you can use to retrieve the CA certificate.

**Examples:**

```powershell
$tpm2Ek = Get-Tpm2Endorsementkey -VMHost myHost
```
_Exports the CA certificate from the certificate in the $tpm2EK TPM 2.0 endorsement key that you can retrieve from the myHost host to the c:\myfile.zip file._

```powershell
$tpm2Ek = Get-Tpm2Endorsementkey -VMHost myHost
```
_Exports the CA certificate from the specified $tpm2EK.Certificate certificate to the c:\myfile.zip file._

### `Export-Tpm2EndorsementKey`

**This cmdlet exports the TPM 2.0 endorsement key from the TPM 2.0 chip in the specified host. It only works when you connect to the specified host directly by using the Connect-VIServer cmdlet.**

**Parameters:**

- -FilePath [String] (Required) Specifies the path to the file where you want to export the TPM 2.0 endorsement key.
- -Force [SwitchParameter] (Optional) Indicates that the cmdlet overwrites the existing destination files and creates directories to complete the specified file path.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VMHost [VMHost[]] (Required) Specifies the hosts on which you want to export the TPM 2.0 endorsement key from its TPM 2.0 chip.

**Examples:**

```powershell
Connect-VIServer -Server 1.1.1.1 -User myroot -Password mypassword
```
_Exports the TPM 2.0 endorsement key from the TPM 2.0 chip in the 1.1.1.1 host to the c:\mypath file._

### `Export-TrustAuthorityKeyProviderClientCertificate`

**This cmdlet exports the client certificate from the specified Trust Authority key provider to the specified file.**

**Parameters:**

- -FilePath [String] (Required) Specifies the path to the file where you want to export the client certificate of the specified Trust Authority key provider.
- -Force [SwitchParameter] (Optional) Indicates that the cmdlet overwrites the existing destination files and creates directories to complete the specified file path.
- -KeyProvider [TrustAuthorityKeyProvider] (Required) Specifies the Trust Authority key provider from which you can export the client certificate.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.

**Examples:**

```powershell
Export-TrustAuthorityKeyProviderClientCertificate -KeyProvider myProvider -FilePath c:\mypath
```
_Exports the client certificate from the Trust Authority key provider myProvider to the c:\mypath file._

### `Export-TrustAuthorityServicesInfo`

**This cmdlet exports the Trust Authority services information (the Trust Authority attestation service and Trust Authority key provider service) from the specified Trust Authority cluster to the specified file.**

**Parameters:**

- -FilePath [String] (Required) Specifies the path to the file where you want to export the Trust Authority services information from the specified Trust Authority cluster.
- -Force [SwitchParameter] (Optional) Indicates that the cmdlet overwrites the existing destination files and creates directories to complete the specified file path.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Required) Specifies the Trust Authority cluster where you can export the the Trust Authority services information.

**Examples:**

```powershell
Export-TrustAuthorityServicesInfo -TrustAuthorityCluster mycluster -FilePath c:\mypath
```
_Exports the Trust Authority services information (the Trust Authority attestation service and Trust Authority key provider service) from the mycluster Trust Authority Cluster to the c:\mypath file._

### `Export-TrustedPrincipal`

**This cmdlet exports the trusted principal from the single or the specified connected workload vCenter Server system to the specified file.**

**Parameters:**

- -FilePath [String] (Required) Specifies the path to the file where you want to export the trusted principal from the workload vCenter Server system.
- -Force [SwitchParameter] (Optional) Indicates that the cmdlet overwrites the existing destination files and creates directories to complete the specified file path.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Export-TrustedPrincipal -FilePath c:\mypath.
```
_Exports the trusted principal from the connected workload vCenter Server system to the c:\mypath file._

## Get

### `Get-AttestationServiceInfo`

**This cmdlet retrieves the attestation services information configured in the workload vCenter Server system.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the attestation service information you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -ServiceAddress [String[]] (Optional) Specifies the service addresses of the attestation service information you want to retrieve.
- -ServiceGroup [String[]] (Optional) Specifies the service groups of the attestation service information you want to retrieve.
- -ServicePort [Int32] (Optional) Specifies the service port of the attestation service information you want to retrieve. It only works when the ServiceAddress parameter is also specified.
- -TAClusterId [String[]] (Optional) Specifies the Trust Authority cluster IDs of the attestation service information you want to retrieve.

**Examples:**

```powershell
Get-AttestationServiceInfo
```
_Retrieves a list of the available attestation service information configured in the workload vCenter Server system._

### `Get-KeyManagementServer`

**This cmdlet retrieves the key management servers registered on the vCenter Server system.**

This cmdlet retrieves the key management servers registered on the vCenter Server system and can filter the result by name, key provider, key management server address, and ID.

**Parameters:**

- -Address [String[]] (Required) Specifies the IPv4, IPv6, or DNS address of the key management server.
- -Id [String[]] (Required) Specifies the IDs of the key management servers you want to retrieve.
- -Name [String[]] (Optional) Specifies the name or alias of the key management server you want to retrieve.
- -KeyProvider [KeyProvider[]] (Optional) Specifies the list of the key providers by which you want to filter the results.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-KeyManagementServer -Server $myServer
```
_Retrieves all key management servers on the $myServer vCenter Server system._

```powershell
Get-KeyManagementServer -Name 'KMS'
```
_Retrieves a key management server named 'KMS'._

### `Get-KeyProvider`

**This cmdlet retrieves all key providers from the vCenter Server system.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the key providers you want to retrieve.
- -Name [String[]] (Optional) Specifies the name of the key providers you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -Type [KeyProviderType[]] (Optional) Specifies the type of the key providers you want to retrieve.

**Examples:**

```powershell
Get-KeyProvider -Server $myServer
```
_Retrieves all key providers from the $myServer vCenter Server system._

```powershell
Get-KeyProvider -Name 'ThalesCluster'
```
_Retrieves a key provider named 'ThalesCluster'._

```powershell
Get-KeyProvider -Type NativeKeyProvider,TrustedKeyProvider
```
_Retrieves all key providers of the NativeKeyProvider and the TrustedKeyProvider type._

### `Get-KeyProviderServiceInfo`

**This cmdlet retrieves the key provider services information configured in the workload vCenter Server system.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the key provider service information you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -ServiceAddress [String[]] (Optional) Specifies the service addresses of the key provider service information you want to retrieve.
- -ServiceGroup [String[]] (Optional) Specifies the service groups of the key provider service information you want to retrieve.
- -ServicePort [Int32] (Optional) Specifies the service port of the key provider service information you want to retrieve. It only works when the ServiceAddress parameter is also specified.
- -TAClusterId [String[]] (Optional) Specifies the Trust Authority cluster IDs of the key provider service information you want to retrieve.

**Examples:**

```powershell
Get-KeyProviderServiceInfo
```
_Retrieves a list of the available key provider service information configured in the workload vCenter Server system._

### `Get-SecurityInfo`

**This cmdlet retrieves the security information of objects (VirtualMachine, HardDisk or VMHost).**

This cmdlet retrieves the security information of objects. Returns the SecurityInfo instance that corresponds to the specified object.

**Parameters:**

- -Entity [VIObjectCore[]] (Required) Specifies the object to retrieve its security information. Supported objects are VirtualMachine, VMHost and HardDisk.
- -Server [VIServer[]] (Optional) Specifies the connected viserver on which you want to run the cmdlet. If no value is passed to this parameter, the command runs on the default viservers. For more information about default viservers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-SecurityInfo -Entity MyObj*
```
_Retrieves the security information of all the virtual machines and all the VMHosts whose names starting with "MyObj"._

```powershell
Get-VM MyVM | Get-HardDisk | Get-SecurityInfo
```
_Retrieves security information of all disks of 'MyVM' virtual machine._

```powershell
$vmHosts = Get-VMHost
```
_Retrieves security information of all the VMHosts available on the connected servers._

### `Get-SecurityPolicy`

**This cmdlet retrieves the security policy for virtual port groups or the default port security policy for virtual switches.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VirtualPortGroup [VirtualPortGroup[]] (Required) Specifies a virtual port group for which you want to retrieve the security policy.
- -VirtualSwitch [VirtualSwitch[]] (Required) Specifies a virtual switch for which you want to retrieve the default port security policy.

**Examples:**

```powershell
Get-VirtualSwitch "MyVirtualSwitch" | Get-SecurityPolicy
```
_Retrieves the security policy of a virtual switch named "MyVirtualSwitch"._

```powershell
Get-VirtualPortGroup "MyPortgroup" | Get-SecurityPolicy
```
_Retrieves the security policy of a virtual switch port group named "MyPortgroup"._

### `Get-Tpm2EndorsementKey`

**This cmdlet retrieves the TPM 2.0 endorsement key from the TPM 2.0 chip in the specified host. You can use this cmdlet by connecting either directly to an ESXi host or to its vCenter Server system.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VMHost [VMHost[]] (Required) Specifies the hosts on which you want to export the TPM 2.0 endorsement key from the TPM 2.0 chip.
- -VMHostTPM [VMHostTPM[]] (Required) Specifies the TPM from which you want to Get the TPM 2.0 endorsement key.

**Examples:**

```powershell
Connect-VIServer -Server $esxiAddress -User myroot -Password mypassword
```
_Retrieves the TPM 2.0 endorsement key information from the TPM 2.0 chip of the specified host when connected directly to this host._

```powershell
Connect-VIServer -Server $vCenterAddress -User myroot -Password mypassword
```
_Retrieves the TPM 2.0 endorsement key information from the TPM 2.0 chip of the specified host in the connected vCenter._

```powershell
Connect-VIServer -Server $vCenterAddress -User myroot -Password mypassword
```
_Retrieves the TPM 2.0 endorsement key information from the TPM 2.0 chip corresponding to the specified TPM._

### `Get-TrustAuthorityAttestationService`

**This cmdlet retrieves the Trust Authority attestation services from the specified enabled Trust Authority cluster in the Trust Authority vCenter Server system.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -ServiceAddress [String[]] (Optional) Specifies the service addresses of the Trust Authority attestation services you want to retrieve.
- -ServiceGroup [String[]] (Optional) Specifies the service groups of the Trust Authority attestation services you want to retrieve.
- -TrustAuthorityCluster [TrustAuthorityCluster[]] (Optional) Specifies the Trust Autority cluster where you can find the Trust Authority attestation services you want to retrieve.
- -VMHost [VMHost[]] (Optional) Specifies the host from which you can retrieve the Trust Authority attestation services.

**Examples:**

```powershell
Set-TrustAuthorityCluster -TrustAuthorityCluster mycluster -State Enabled
```
_Retrieves the Trust Authority attestation services from the mycluster Trust Authority cluster after you enable it._

### `Get-TrustAuthorityKeyProvider`

**This cmdlet retrieves the Trust Authority key providers from the specified Trust Authority cluster in the Trust Authority vCenter Server system.**

**Parameters:**

- -Name [String[]] (Optional) Specifies the names of the Trust Authority key providers you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster[]] (Required) Specifies the Trust Authority clusters where you can retrieve the Trust Authority key providers.

**Examples:**

```powershell
Get-TrustAuthorityKeyProvider -TrustAuthorityCluster mycluster
```
_Retrieves the Trust Authority key providers from the mycluster Trust Authority cluster in the connected Trust Authority vCenter Server system._

### `Get-TrustAuthorityKeyProviderClientCertificate`

**This cmdlet retrieves the client certificate from the specified Trust Authority key provider in the connected Trust Authority vCenter Server system.**

**Parameters:**

- -KeyProvider [TrustAuthorityKeyProvider[]] (Required) Specifies the Trust Authority key providers from which you want to retrieve the client certificates.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.

**Examples:**

```powershell
Get-TrustAuthorityKeyProviderClientCertificate -KeyProvider myKeyProvider
```
_Retrieves the client certificate from the myKeyProvider Trust Authority key provider._

### `Get-TrustAuthorityKeyProviderClientCertificateCSR`

**This cmdlet retrieves the client certificate Certificate Signing Request (CSR) from the specified Trust Authority key provider in the connected Trust Authority vCenter Server system.**

**Parameters:**

- -KeyProvider [TrustAuthorityKeyProvider[]] (Required) Specifies the Trust Authority key providers from where you want to retrieve the client certificate CSRs.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.

**Examples:**

```powershell
Get-TrustAuthorityKeyProviderClientCertificateCSR -KeyProvider myKeyProvider
```
_Retrieves the client certificate CSR from the Trust Authority myKeyProvider key provider._

### `Get-TrustAuthorityKeyProviderServer`

**This cmdlet retrieves the Trust Authority key provider servers from the specified Trust Authority key providers in the connected Trust Authority vCenter Server system.**

**Parameters:**

- -Address [String[]] (Optional) Specifies the addresses of the Trust Authority key provider server you want to retrieve.
- -KeyProvider [TrustAuthorityKeyProvider[]] (Required) Specifies the Trust Authority key providers from where you want to retrieve the Trust Authority key provider servers.
- -Name [String[]] (Optional) Specifies the names of the Trust Authority key provider server you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.

**Examples:**

```powershell
Get-TrustAuthorityKeyProviderServer -KeyProvider myKeyProvider -Address 1.1.1.1
```
_Retrieves the Trust Authority key provider server with the 1.1.1.1 address from the Trust Authority myKeyProvider key provider._

```powershell
Get-TrustAuthorityKeyProviderServer -KeyProvider myKeyProvider -Name myKmsName
```
_Retrieves the Trust Authority key provider server with name myKmsName from the Trust Authority key provider myKeyProvider._

### `Get-TrustAuthorityKeyProviderServerCertificate`

**This cmdlet retrieves the certificate from the Trust Authority key provider server or the certificate trusted by the specified Trust Authority key provider in the Trust Authority vCenter Server system.**

**Parameters:**

- -KeyProvider [TrustAuthorityKeyProvider[]] (Required) Specifies the Trust Authority key providers from which you want to retrieve the trusted certificates.
- -KeyProviderServer [TrustAuthorityKeyProviderServer[]] (Required) Specifies the Trust Authority key provider servers from which you want to retrieve the certificates.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.

**Examples:**

```powershell
$kmsServer = Get-TrustAuthorityKeyProviderServer -KeyProvider myProvider
```
_Retrieves the certificates from the Trust Authority key provider server in the Trust Authority key provider myProvider._

```powershell
Get-TrustAuthorityKeyProviderServerCertificate -KeyProvider myProvider
```
_Retrieves the certificates that are trusted by the Trust Authority key provider myProvider._

### `Get-TrustAuthorityKeyProviderService`

**This cmdlet retrieves the Trust Authority key provider services from the specified enabled Trust Authority cluster in the Trust Authority vCenter Server system.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -ServiceAddress [String[]] (Optional) Specifies the service addresses of the Trust Authority key provider services you want to retrieve.
- -ServiceGroup [String[]] (Optional) Specifies the service groups of the Trust Authority key provider services you want to retrieve.
- -TrustAuthorityCluster [TrustAuthorityCluster[]] (Optional) Specifies the Trust Autority clusters from which you want to retrieve the Trust Authority key provider services.
- -VMHost [VMHost[]] (Optional) Specifies the hosts from which you want to retrieve the Trust Authority key provider services.

**Examples:**

```powershell
Set-TrustAuthorityCluster -TrustAuthorityCluster mycluster -State Enabled
```
_Retrieves the Trust Authority key provider services from the Trust Authority mycluster cluster after you enable it._

### `Get-TrustAuthorityPrincipal`

**This cmdlet retrieves the Trust Authority principals from the specified Trust Authority clusters in the Trust Authority vCenter Server system.**

**Parameters:**

- -Domain [String] (Optional) Specifies the domain of the Trust Authority principals you want to retrieve. It only works together with the Name parameter.
- -Id [String[]] (Required) Specifies the IDs of the Trust Authority principals you want to retrieve.
- -Issuer [String[]] (Optional) Specifies the issuers of the Trust Authority principals you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the Trust Authority principals you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster[]] (Required) Specifies the Trust Authority clusters from where you want to retrieve the Trust Authority principals.

**Examples:**

```powershell
Get-TrustAuthorityPrincipal -TrustAuthorityCluster mycluster -Name myprincipal
```
_Retrieves the Trust Authority principal with name myprincipal from the Trust Authority cluster mycluster._

### `Get-TrustAuthorityServicesStatus`

**This cmdlet retrieves the Trust Authority services status from the specified Trust Authority clusters in the connected Trust Authority vCenter Server system.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster[]] (Required) Specifies the Trust Authority clusters from which you want to retrieve the Trust Authority services status.

**Examples:**

```powershell
Get-TrustAuthorityServicesStatus -TrustAuthorityCluster mycluster
```
_Retrieves the Trust Authority services status from the Trust Authority cluster mycluster._

### `Get-TrustAuthorityTpm2AttestationSettings`

**This cmdlet retrieves the Trust Authority TPM 2.0 attestation settings from the specified Trust Authority clusters in the connected Trust Auhtority vCenter Server system.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster[]] (Required) Specifies the Trust Authority clusters from which you want to retrieve the Trust Authority TPM 2.0 attestation settings.

**Examples:**

```powershell
Get-TrustAuthorityTpm2AttestationSettings -TrustAuthorityCluster mycluster
```
_Retrieves the Trust Authority TPM 2.0 attestation settings from the Trust Authority cluster mycluster._

### `Get-TrustAuthorityTpm2CACertificate`

**This cmdlet retrieves the Trust Authority TPM 2.0 Certificate Authority (CA) certificates from the specified Trust Authority clusters in the Trust Authority vCenter Server system.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the Trust Authority TPM 2.0 CA certificates you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the Trust Authority TPM 2.0 CA certificates you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster[]] (Required) Specifies the Trust Authority clusters from which you want to retrieve the Trust Authority TPM 2.0 CA certificates.

**Examples:**

```powershell
Get-TrustAuthorityTpm2CACertificate -TrustAuthorityCluster mycluster
```
_Retrieves the Trust Authority TPM 2.0 CA certificates from the Trust Authority cluster mycluster._

### `Get-TrustAuthorityTpm2EndorsementKey`

**This cmdlet retrieves the Trust Authority TPM 2.0 endorsement keys from the specified Trust Authority clusters in the Trust Authority vCenter Server system.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the Trust Authority TPM 2.0 endorsement keys you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the Trust Authority TPM 2.0 endorsement keys you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster[]] (Required) Specifies the Trust Authority clusters from which you want to retrieve the Trust Authority TPM 2.0 endorsement keys.

**Examples:**

```powershell
Get-TrustAuthorityTpm2EndorsementKey -TrustAuthorityCluster mycluster
```
_Retrieves the Trust Authority TPM 2.0 endorsement keys from the Trust Authority cluster mycluster._

### `Get-TrustedPrincipal`

**This cmdlet retrieves the trusted principals from the connected workload vCenter Server system.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-TrustedPrincipal
```
_Retrieves the trusted principals from the connected workload vCenter Server system._

### `Get-VDSecurityPolicy`

**This cmdlet retrieves the security policy for distributed ports.**

This cmdlet retrieves the security policy for distributed ports. For distributed port group and vSphere distributed switch parameter sets, the default port policy at the distributed port group or switch level is retrieved.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDPort [VDPort[]] (Required) Specifies the distributed ports for which you want to retrieve the security policy.
- -VDPortgroup [VDPortgroup[]] (Required) Specifies a distributed port group for which you want to retrieve the default security policy.
- -VDSwitch [VDSwitch[]] (Required) Specifies a vSphere distributed switch for which you want to retrieve the default security policy.

**Examples:**

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDSecurityPolicy
```
_Retrieves the security policy of a vSphere distributed switch named "MyVDSwitch"._

```powershell
Get-VDPortgroup "MyVDPortgroup" | Get-VDPort -Key 4 | Get-VDSecurityPolicy
```
_Retrieves the security policies of a specific port inside a distributed port group named "MyVDPortgroup"._

### `Get-VIAccount`

**This cmdlet retrieves the accounts from the ESX/ESXi or vCenter Server.**

This cmdlet retrieves the accounts from the ESX/ESXi or vCenter Server. The Group and User switch parameters let you retrieve group and user accounts. By default, the cmdlet lists only user accounts. If the Domain parameter is specified, the cmdlet retrieves only the accounts on the specified AD domain. Otherwise, only local accounts are listed.

**Parameters:**

- -Domain [String] (Optional) Specifies AD domains to search for accounts.
- -Group [SwitchParameter] (Optional) Specifies that you want to retrieve only group accounts.
- -Id [String[]] (Optional) Specifies the IDs of the accounts you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the accounts you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -User [SwitchParameter] (Optional) Specifies that you want to retrieve only user accounts.

**Examples:**

```powershell
Get-VIAccount -Id Administrator
```
_Retrieve accounts by Id._

```powershell
Get-VIAccount -Group
```
_Retrieve all group accounts._

```powershell
Get-VIAccount -Id Administrator -Domain "MSDomain"
```
_Get all VIAccounts for specified ID and Domain._

### `Get-VIOAuth2Client`

**This cmdlet retrieves the OAuth2 clients available on a vCenter Server system.**

**Parameters:**

- -Id [String[]] (Optional) Filters the OAuth2 clients by ID.
- -Name [String[]] (Optional) Filters the OAuth2 clients by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VIOauth2Client -Name "MyOAuth2Client*"
```
_Retrieves all OAuth2 clients with names that start with "MyOAuth2Client"._

```powershell
Get-VIOauth2Client -Id "MyOAuth2Client1"
```
_Retrieves OAuth2 client with ID "MyOAuth2Client1"_

### `Get-VIPermission`

**This cmdlet retrieves the permissions defined on the specified inventory objects.**

This cmdlet retrieves the permissions defined on the specified inventory objects. If no inventory objects are specified, the cmdlet retrieves all permissions available on the server.

**Parameters:**

- -Entity [VIObject[]] (Optional) Specifies the inventory items for which you want to retrieve permissions.
- -Principal [VIAccount[]] (Optional) Specifies the users and groups for which you want to retrieve permissions.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VIPermission -Entity (Get-Datacenter) -Principal Administrator
```
_Retrieves the permissions of the Administrator user on the provided datacenters._

### `Get-VIPrivilege`

**This cmdlet retrieves the privilege groups and items for the provided servers.**

**Parameters:**

- -Group [PrivilegeGroup[]] (Required) Specifies the privilege group whose items you want to retrieve.
- -Id [String[]] (Optional) Specifies the IDs of the privileges you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the privileges you want to retrieve.
- -PrivilegeGroup [SwitchParameter] (Optional) Indicates that you want to retrieve only the privilege groups and not the privilege items in them.
- -PrivilegeItem [SwitchParameter] (Optional) Indicates that you want to retrieve only the privilege items and not the privilege groups.
- -Role [Role[]] (Required) Specifies the roles whose privileges you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VIPrivilege -Name "Host*"
```
_Retrieves all privileges with names that start with "Host"._

```powershell
Get-VIPrivilege -PrivilegeGroup
```
_Retrieves all privilege groups._

### `Get-VIPrivilegeReport`

**This cmdlet records the privilege checks that occur for the specified sessions during the execution of a specified script block.**

This cmdlet records the privilege checks that occur for the specified sessions during the execution of a specified script block. The vCenter Server systems on which the script block is executed must be managed within the script block.

**Parameters:**

- -ScriptBlock [ScriptBlock] (Required) Specifies the script block to be executed to collect required privileges. The vCenter Server systems on which the script block is executed must be managed within the script block.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to collect a privilege report. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
PS C:\> $scriptBlock = {
```
_First, retrieves privilege checks from the connected vCenter Server systems. Then, enhances the report with the VIObjects retrieved from the EntityMoRef property of the retrieved PrivilegeCheck objects, when there is an equivalent high-level object available in PowerCLI._

### `Get-VIRole`

**This cmdlet retrieves all roles defined on the provided servers.**

**Parameters:**

- -Id [String[]] (Optional) Specifies the IDs of the roles you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the roles you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VIRole -Server $server -Name "Admin*"
```
_Retrieves all roles on the specified server with names that start with "Admin"._

### `Get-VTpm`

**This cmdlet retrieves the virtual TPM (vTPM) devices available on the given virtual machines.**

This cmdlet retrieves the virtual TPM (vTPM) devices available on the given virtual machines. This cmdlet returns vTPM devices that correspond to the filter criteria specified by the provided parameters.

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the vTPM device that you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines from which you want to retrieve the vTPM device.

**Examples:**

```powershell
$vm = Get-VM "MyVM"
```
_Retrieves the vTPM device of the virtual machine named "MyVM"._

### `Get-VTpmCSR`

**This cmdlet retrieves the certficate signing requests (CSR) from the given vTPM devices.**

This cmdlet retrieves the certficate signing requests (CSR) from the given vTPM devices. You can retrive the certificate signing request from the given vTPM devices by specifying the vTPM device and the certificate signing request type (CSRType): RSA, ECC, or All. By default, the certificate signing request type (CSRType) is All.

**Parameters:**

- -CSRType [CSRType] (Optional) Specifies the signing request type. The valid values are: All, ECC, RSA.
- -VTpm [VTpm[]] (Required) Specifies the vTPM device from which you want to retrieve the certificate signing request information.

**Examples:**

```powershell
Get-VTpm -VM MyVM | Get-VTpmCSR
```
_Retrieves all the certificate signing request information from the vTPM device of the virtual machine named "MyVM"._

```powershell
Get-VTpm -VM MyVM | Get-VTpmCSR -CSRType ECC
```
_Retrieves the certificate signing request information, whose encryption algorithm is ECC, from the vTPM device of the virtual machine named "MyVM"._

### `Get-VTpmCertificate`

**This cmdlet retrieves the certificate information from the given vTPM devices.**

This cmdlet retrieves the certificate information from the given vTPM devices. You can retrive the certificate information from the given vTPM devices by specifying the vTPM device and the certificate signing request type (CSRType): RSA, ECC, or All. By default, the certificate signing request type (CSRType) is All.

**Parameters:**

- -CSRType [CSRType] (Optional) Specifies the signing request type of the certificate. The valid values are All, ECC, and RSA.
- -VTpm [VTpm[]] (Required) Specifies the vTPM device from which you want to retrieve the certificate information.

**Examples:**

```powershell
Get-VTpm -VM MyVM | Get-VTpmCertificate
```
_Retrieves all the certificate information from the vTPM device of the virtual machine named "MyVM"._

```powershell
Get-VTpm -VM MyVM | Get-VTpmCertificate -CSRType ECC
```
_Retrieves the certificate information, whose encryption algorithm is ECC, from the vTPM device of the virtual machine named "MyVM"._

## Import

### `Import-KeyProvider`

**This cmdlet imports a key provider from a specified configuration file.**

**Parameters:**

- -DryRun [SwitchParameter] (Optional) Specifies to perform a trial import without actually creating a key provider.
- -FilePath [String] (Required) Specifies the configuration file you want to import.
- -Password [SecureString] (Optional) Specifies the password to decrypt the configuration file you want to import.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TpmRequired [SwitchParameter] (Optional) Specifies whether the key provider should be restricted to hosts with TPM 2.0 capability.

**Examples:**

```powershell
Import-KeyProvider -FilePath c:\myfile
```
_Creates a key provider by importing the configuration from the specified file c:\myfile._

```powershell
Import-KeyProvider -FilePath c:\myfile -DryRun
```
_Performs a trial import without actually creating a key provider from the specified file c:\myfile._

### `Import-TrustAuthorityServicesInfo`

**This cmdlet imports the Trust Authority services information (Trust Authority attestation service and Trust Authority key provider service) from the specified file to the workload vCenter Server system.**

**Parameters:**

- -FilePath [String] (Required) Specifies the path to the file where you want to import the Trust Authority services information.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Import-TrustAuthorityServicesInfo -FilePath c:\mypath
```
_Imports the Trust Authority services information in the c:\mypath file to the connected workload vCenter Server system._

## New

### `New-TrustAuthorityKeyProvider`

**This cmdlet creates a new Trust Authority key provider in the Trust Authority vCenter Server system.**

**Parameters:**

- -ConnectionTimeOutSeconds [Int64] (Optional) Specifies the timeout in seconds for the connection between the Trust Authority key provider and the KMIP servers.
- -Description [String] (Optional) Specifies the description of the Trust Authority key provider.
- -KmipServerAddress [String] (Required) Specifies the first KMIP server address in the Trust Authority key provider.
- -KmipServerName [String] (Optional) Specifies the name of the first KMIP server in the Trust Authority key provider.
- -KmipServerPassword [SecureString] (Optional) Specifies the password of the first KMIP server in the Trust Authority key provider.
- -KmipServerPort [Int32] (Optional) Specifies the port number of the first KMIP server in the Trust Authority key provider.
- -KmipServerUsername [String] (Optional) Specifies the user name of the first KMIP server in the Trust Authority key provider.
- -MasterKeyId [String] (Required) This parameter is deprecated and scheduled for removal. Use the PrimaryKeyId parameter instead.
- -Name [String] (Required) Specifies the name of the Trust Authority key provider.
- -ProxyAddress [String] (Optional) Specifies the proxy address of the Trust Authority key provider that you want to use to connect to the KMIP servers.
- -ProxyPort [Int32] (Optional) Specifies the proxy port number of the Trust Authority key provider that you use to connect to the KMIP servers. It works with the ProxyAddress parameter.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is given to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Required) Specifies the Trust Authority cluster in which you want to create the Trust Authority key provider.
- -PrimaryKeyId [String] (Required) Specifies the primary key ID of the Trust Authority key provider that you want to use from the KMIP servers.

**Examples:**

```powershell
New-TrustAuthorityKeyProvider -TrustAuthorityCluster mycluster -Name mykp -PrimaryKeyId 1 -KmipServerAddress 1.1.1.1
```
_Creates a new Trust Authority key provider in the Trust Authority cluster mycluster with the mykp and primarykeyId 1 names for all the Key Management Interoperability Protocol (KMIP) servers in this key provider. Adds KMIP server with the 1.1.1.1 address to the key provider._

### `New-TrustAuthorityKeyProviderClientCertificate`

**This cmdlet creates a client certificate for the specified Trust Authority key provider in the Trust Authority vCenter Server system.**

**Parameters:**

- -KeyProvider [TrustAuthorityKeyProvider] (Required) Specifies the Trust Authority key provider for which you want to generate a client certificate.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.

**Examples:**

```powershell
New-TrustAuthorityKeyProviderClientCertificate -KeyProvider mykp
```
_Creates the client certificate for the Trust Authority key provider mykp._

### `New-TrustAuthorityKeyProviderClientCertificateCSR`

**This cmdlet creates the client certificate Certificate Signing Request (CSR) for the specified Trust Authority key providers in the Trust Authority vCenter Server system.**

**Parameters:**

- -KeyProvider [TrustAuthorityKeyProvider] (Required) Specifies the Trust Authority key provider for which you want to generate the client certificate CSR.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.

**Examples:**

```powershell
New-TrustAuthorityKeyProviderClientCertificateCSR -KeyProvider mykp
```
_Creates the client certificate CSR for the Trust Authority key provider mykp._

### `New-TrustAuthorityPrincipal`

**This cmdlet creates a new Trust Authority principal in the specified Trust Authority cluster in the Trust Authority vCenter Server system.**

**Parameters:**

- -CertificateChain [X509Chain[]] (Required) Specifies the certificate chain of the trusted principal in the workload vCenter Server system to create a Trust Authority principal.
- -Domain [String] (Required) Specifies the domain of the trusted principal in the workload vCenter Server system to create a Trust Authority principal.
- -FilePath [String] (Required) Specifies the file including the trusted principal in the workload vCenter Server system to create the Trust Authority principal.
- -Issuer [String] (Required) Specifies the issuer of the trusted principal in the workload vCenter Server system to create a Trust Authority principal.
- -Name [String] (Required) Specifies the name of the trusted principal in the workload vCenter Server system to create a Trust Authority principal.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Required) Specifies the Trust Authority cluster in which you want to create the Trust Authority principal.
- -TrustedPrincipal [TrustedPrincipal] (Required) Specifies the trusted principal in the workload vCenter Server system to create a Trust Authority principal.
- -Type [PrincipalType] (Optional) Specifies the type of the trusted principal in the workload vCenter Server system to create a Trust Authority principal.

**Examples:**

```powershell
$trustedPrincipal = Get-TrustedPrincipal -Server workloadSystem
```
_Creates the Trust Authority principal in the Trust Authority cluster mycluster from the trusted principal object $trustedPrincipal. You can retrieve the trusted principal object from the connected workload vCenter Server system workloadSystem._

```powershell
Export-TrustedPrincipal -Server workloadSystem -FilePath c:\mypath
```
_Exports the trusted principal object from the connected workload vCenter Server system workloadSystem to the c:\mypath file. Creates the Trust Authority principal in the Trust Authority cluster mycluster from the c:\mypath file._

```powershell
$trustedPrincipal = Get-TrustedPrincipal -Server workloadSystem
```
_Creates a Trust Authority principal in the Trust Authority cluster mycluster from each property of the trusted principal object. You can retrieve the Trusted principal object from the connected workload vCenter Server system workloadSystem._

### `New-TrustAuthorityTpm2CACertificate`

**This cmdlet creates a new Trust Authority TPM 2.0 Certificate Authority (CA) certificate in the specified Trust Authority Cluster in the Trust Authority vCenter Server system.**

This cmdlet creates a new Trust Authority TPM 2.0 CA certificate in the specified Trust Authority cluster in the Trust Authority vCenter Server system.

**Parameters:**

- -CertificateChain [X509Chain] (Required) Specifies the TPM 2.0 chip's CA certificate chain that you want to use to create a Trust Authority TPM 2.0 CA certificate.
- -FilePath [String] (Required) Specifies the file where you can find the CA certificates. The file can be in a .crt or .zip format. If the file is in a .zip format, you should name the .crt files in the .zip package as <file>-00.crt, <file>-01.crt... <file>-09.crt. Use the Export-Tpm2CACertificate cmdlet to download the CA certificates from the given TPM 2.0 chip's certificate.
- -Name [String] (Optional) Specifies the name of the Trust Authority TPM 2.0 CA certificate that you want to create. If it's not specified, the name is the subject key identifier of the certificate which is the leaf-most certificate in the certificate chain.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Required) Specifies the Trust Authority cluster in which you want to create a new Trust Authority TPM 2.0 CA certificate.

**Examples:**

```powershell
New-TrustAuthorityTpm2CACertificate -TrustAuthorityCluster mycluster -CertificateChain $x509chain
```
_Creates a new Trust Authority TPM 2.0 CA certificate in the Trust Authority cluster mycluster from the given $x509Chain certificate chain._

```powershell
New-TrustAuthorityTpm2CACertificate -TrustAuthorityCluster mycluster -FilePath c:\mypath
```
_Creates a new Trust Authority TPM 2.0 CA certificate in the Trust Authority cluster mycluster from the specified c:\mypath file. The file can be in a .crt or .zip format._

### `New-TrustAuthorityTpm2EndorsementKey`

**This cmdlet creates a new Trust Authority TPM 2.0 endorsement key in the specified Trust Authority cluster in the Trust Authority vCenter Server system.**

**Parameters:**

- -Certificate [X509Certificate2] (Optional) Specifies the certificate of the TPM 2.0 device from a workload virtual machine host server that you want to use to create a Trust Authority TPM 2.0 endorsement key object in Trust Autority vCenter Server system.
- -CertificateFile [String] (Optional) Specifies the certificate file where you can find the TPM 2.0 device's certificate.
- -FilePath [String] (Required) Specifies the file where you can find the TPM 2.0 endorsement key.
- -Name [String] (Required) Specifies the name of the new Trust Authority TPM 2.0 endorsement key that you want to create.
- -PublicKey [SecureString] (Optional) Specifies the TPM 2.0 device's public key in PEM format.
- -PublicKeyFile [String] (Optional) Specifies the file where you can find the TPM 2.0 device's public key.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -Tpm2EndorsementKey [Tpm2EndorsementKey[]] (Required) Specifies the TPM 2.0 endorsement key of the TPM 2.0 device from a workload virtual machine host server that you can use to create Trust Authority TPM 2.0 endorsement key object in the Trust Autority vCenter Server system.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Required) Specifies the Trust Authority cluster in which you want to create a new Trust Authority TPM 2.0 endorsementKey object.

**Examples:**

```powershell
Connect-VIServer -Server 1.1.1.1 -User root -Password mypasswd
```
_Creates a Trust Authority TPM 2.0 endorsement key in the Trust Authority cluster mycluster from the TPM 2.0 endorsement key object $tpm2Ek. You can retrieve the TPM 2.0 endorsement key object from the connected workload virtual machine host server 1.1.1.1._

```powershell
Connect-VIServer -Server 1.1.1.1 -User root -Password mypasswd
```
_Creates a Trust Authority TPM 2.0 endorsement key in the Trust Authority cluster mycluster from the c:\mypath file. You can export the TPM 2.0 endorsement key object from the connected workload virtual machine host server 1.1.1.1._

```powershell
Connect-VIServer -Server 1.1.1.1 -User root -Password mypasswd
```
_Creates a Trust Authority TPM 2.0 endorsement key with the mytpm2Ek name in the Trust Authority cluster mycluster from each property of the Tpm2EndorsementKey object. You can retrieve the TPM 2.0 endorsement key object from the connected workload virtual machine host server 1.1.1.1._

### `New-VIOAuth2Client`

**Creates a new OAuth2 client registration with the VMware Identity Broker.**

Creates a new OAuth2 client registration with the vCenter Identity Broker. The VMware Identity Broker is an OAuth2 relay that is used by client applications to authenticate with vCenter using OAuth2.

**Parameters:**

- -AccessTokenTimeToLiveMinutes [Int32] (Optional) How long in minutes new access tokens issued to this client should live.
- -ClientId [String] (Required) OAuth 2.0 Client identifier that the client uses to identify itself during the OAuth 2.0 exchanges. The client ID must contain only alphanumeric (A-Z, a-z, 0-9), period (.), underscore (_), hyphen (-) and at sign (@) characters.
- -GrantTypes [String[]] (Required) Specifies a list of OAuth 2.0 Access Grant Types that are enabled in this OAuth 2.0 Client.
- -Name [String] (Optional) Specifies the user-friendly name that you set for this OAuth 2.0 client.
- -PkceEnforced [Boolean] (Optional) Specifies whether PKCE is enforced for the OAuth2 client. If not specified, the value is 'false'.
- -PostLogoutRedirectUris [String[]] (Optional) Specifies a list of absolute URLs to the OAuth2 Relaying Party. When a logout occurs, the Auth2 Relaying Party might request that the User Agent of the End-User is redirected to one of these absolute URLs. These URLs must contain the https scheme and can also have a port, path, and some query parameters. However, the URLs may also contain the http scheme, provided that the Client Type is confidential. To skip the check for a particular URL section, you can substitute a wildcard character with any string.
- -PublicClient [Boolean] (Optional) Specifies whether the OAuth 2.0 client is public or not. A public client is one that does not have a secret. If not specified, the value is 'false'.
- -RedirectUris [String[]] (Optional) Specifies a list of absolute URIs of application endpoints that are allowed to receive the authorization code and access token.  The redirect URI sent by the application as part of the Authorization Code Grant Oauth 2.0 flow is verified against this list.  A Wildcard can be substituted for any string to skip the check for a particular URL section. The field is required if GrantTypes parameter contain an "authorization_code" grant type.
- -RefreshTokenIdleTimeToLiveMinutes [Int32] (Optional) Specifies how long in minutes new refresh tokens issued to this client should live.  Only applicable and mandatory if the GrantTypes parameter includes "refresh_token".
- -RefreshTokenTimeToLiveMinutes [Int32] (Optional) Specifies how long in minutes new refresh tokens issued to this client can be idle. Only applicable and mandatory if GrantTypes includes "refresh_token". Its value should be less than the refresh token TTL value (specified by the parameter RefreshTokenIdleTimeToLiveMinutes).
- -RuleSetNames [String[]] (Optional) Specifies a list of built in rule set names to associate this client with.  Each ruleset, allows the client to call a specific set of tenant APIs.
- -Scope [String[]] (Required) Specifies a list of access request scopes that are allowed by this OAuth 2.0 Client.
- -Secret [SecureString] (Optional) Specifies the OAuth 2.0 Client secret.
- -SecretTimeToLiveInMinutes [Int32] (Optional) Specifies after what time in minutes the secret must be rotated.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
PS C:\> New-VIOAuth2Client `
```
_Creates a registration for a public OAuth 2.0 client with the specified client ID, scopes, grant types, and redirect URL. The OAuth2 client must implement the Proof Key for Code Exchange (PKCE) protocol to be registered._

```powershell
PS C:\> New-VIOAuth2Client `
```
_Creates a registration for a public OAuth 2.0 client with the specified client ID, scopes, grant types, and redirect URL. The OAuth2 client must implement the Proof Key for Code Exchange (PKCE) protocol to be registered._

```powershell
PS C:\> New-VIOAuth2Client `
```
_If the user needs to use PowerCLI to authenticate using OAuth2, PowerCLI must be registered as an OAuth2 public client._

### `New-VIPermission`

**This cmdlet creates new permissions on the specified inventory objects for the provided users and groups in the role.**

This cmdlet creates new permissions on the specified inventory objects for the provided users and groups in the role. By default, new permissions are propagated down the hierarchy to sub-entities. You cannot create new permissions for the following objects: - direct child folders of a datacenter

**Parameters:**

- -Entity [VIObject] (Required) Specifies the inventory objects for which you want to create new permissions. Passing multiple values to this parameter is obsolete.
- -Principal [VIAccount] (Required) Specifies users and groups to which you want to apply the new permissions. If you specify principal names by using the "domain\name" syntax, wildcards are not supported. Passing multiple values to this parameter is obsolete.
- -Propagate [Boolean] (Optional) Indicates that you want to propagate the new permissions to the child inventory objects.
- -Role [Role] (Required) Specifies the roles for which you want to create new permissions.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
New-VIRole -Name Role -Server $server -Privilege (Get-VIPrivilege -PrivilegeGroup)
```
_Creates a permission on the provided server for a role with the specified privileges._

### `New-VIRole`

**This cmdlet creates a new role on the specified servers and applies the provided privileges.**

**Parameters:**

- -Name [String] (Required) Specifies a name for the new role.
- -Privilege [Privilege[]] (Optional) Specifies the privileges you want to apply to the new role.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
New-VIRole -Name Role -Privilege (Get-VIPrivilege -PrivilegeGroup)
```
_Creates a new role with the provided group privileges._

### `New-VISamlSecurityContext`

**Creates an SAML2 security context object that can be used to authenticate a user with any VMware vCenter Server services.**

**Parameters:**

- -IgnoreSslValidationErrors [SwitchParameter] (Optional) If specified, any errors with the SSL certificate of the server will be ignored.
- -OAuthSecurityContext [OAuth2SecurityContext] (Required) Specifies the OAuth2 security context from an authentication server that the vCenter Server instance is configured to trust.
- -Port [Int32] (Optional) Specifies the port where the vCenter vAPI Endpoint is listening on. The default is 443.
- -VCenterServer [String] (Required) Specifies the IP address or the DNS name of the vSphere server that authenticates the user.

**Examples:**

```powershell
$oauthCtx = New-VcsOAuthSecurityContext -ApiToken "a3f35067-80b5-44f0-a0bc-e19f2bc17fb7"
```
_Creates an SAML2 security context object by authenticating the user with an OAuth2 security context from the VMware Cloud Services authentication server. This SAML2 security context can be used to authenticate the user to any vCenter Server services running in the VMware Cloud on AWS._

### `New-VTpm`

**This cmdlet creates a new vTPM device on the specified virtual machine.**

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VM [VirtualMachine] (Required) Specifies the virtual machine to which you want to add the vTPM device.

**Examples:**

```powershell
Get-VM MyVM | New-VTpm
```
_Adds a new vTPM device to the virtual machine named "MyVM"._

## Register

### `Register-KeyProvider`

**This cmdlet registers a trusted key provider in the workload vCenter Server system which you can use for encryption operations.**

**Parameters:**

- -KeyProvider [KeyProvider[]] (Required) Specifies the key provider that you want to register. If the given key provider's type is KeyProvider, the cmdlet fails.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
$kp = Get-KeyProvider | Where-Object {$_.Type -eq 'TrustedKeyProvider'}
```
_Registers all trusted key providers in the connected workload vCenter Server system._

## Remove

### `Remove-AttestationServiceInfo`

**This cmdlet removes the specified attestation services information from the workload vCenter Server system.**

**Parameters:**

- -AttestationServiceInfo [AttestationServiceInfo[]] (Required) Specifies the attestation services information you want to remove.

**Examples:**

```powershell
$attest = Get-AttestationServiceInfo
```
_Removes the attestation services information configured in the connected workload vCenter Server system._

### `Remove-EntityDefaultKeyProvider`

**This cmdlet removes the default key provider from the specified entities.**

**Parameters:**

- -Entity [VIObject[]] (Required) Specifies the entities from which you want to remove the deault key provider.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
$cluster = Get-Cluster -Name "MyCluster"
```
_Removes the default key provider from the "MyCluster" entity._

### `Remove-KeyManagementServer`

**This cmdlet removes the specified key management servers from the vCenter Server systems.**

**Parameters:**

- -KeyManagementServer [KeyManagementServer[]] (Required) Specifies the key management server list you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-KeyManagementServer $kms -Confirm:$false
```
_Removes the $kms key management server without asking for confirmation._

### `Remove-KeyProviderServiceInfo`

**This cmdlet removes the specified key provider services information from the workload vCenter Server system.**

**Parameters:**

- -KeyProviderServiceInfo [KeyProviderServiceInfo[]] (Required) Specifies the key provider services information that you want to remove.

**Examples:**

```powershell
$kmxd = Get-KeyProviderServiceInfo
```
_Removes the key provider services information configured in the connected workload vCenter Server system._

### `Remove-TrustAuthorityKeyProvider`

**This cmdlet removes the specified Trust Authority key providers from the Trust Authority vCenter Server system.**

**Parameters:**

- -KeyProvider [TrustAuthorityKeyProvider[]] (Required) Specifies the Trust Authority key providers that you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.

**Examples:**

```powershell
Remove-TrustAuthorityKeyProvider -KeyProvider mykp
```
_Removes the Trust Authority key provider mykp from the connected Trust Authority vCenter Server system._

### `Remove-TrustAuthorityKeyProviderServer`

**This cmdlet removes the specified Trust Authority key provider servers from their location in the Trust Authority vCenter Server system.**

**Parameters:**

- -KeyProviderServer [TrustAuthorityKeyProviderServer[]] (Required) Specifies the Trust Authority key provider servers that you want to remove. You cannot remove all Trust Authority key provider servers from a Trust Authority key provider. A Trust Authority key provider requires at least 1 Trust Authority key provider server.

**Examples:**

```powershell
$kmipServer = Get-TrustAuthorityKeyProviderServer -KeyProvider mykp | select -Last 1
```
_Removes the last Trust Authority key provider server from the mykp Trust Authority key provider._

### `Remove-TrustAuthorityKeyProviderServerCertificate`

**This cmdlet removes the specified Trust Authority key provider server certificates from their location. The certificate is no longer trusted by the Trust Authority key provider in the Trust Authority vCenter Server system.**

**Parameters:**

- -ServerCertificate [TrustAuthorityKeyProviderServerCertificate[]] (Required) Specifies the server certificates that you no longer want to be trusted.

**Examples:**

```powershell
$servercert = Get-TrustAuthorityKeyProviderServerCertificate -KeyProvider mykp | select -First 1
```
_Removes the first trusted server certificate from the mykp Trust Authority key provider._

### `Remove-TrustAuthorityPrincipal`

**This cmdlet removes the Trust Authority principals from their location in the Trust Authority vCenter Server system.**

**Parameters:**

- -TrustAuthorityPrincipal [TrustAuthorityPrincipal[]] (Required) Specifies the Trust Authority principals that you want to remove.

**Examples:**

```powershell
$principals = Get-TrustAuthorityPrincipal -TrustAuthorityCluster mycluster
```
_Removes the Trust Authority principals from the mycluster Trust Authority cluster._

### `Remove-TrustAuthorityTpm2CACertificate`

**This cmdlet removes the Trust Authority TPM 2.0 certificate authority (CA) certificates from the Trust Authority cluster in the Trust Authority vCenter Server system.**

**Parameters:**

- -Tpm2CACertificate [TrustAuthorityTpm2CACertificate[]] (Required) Specifies the Trust Authority TPM 2.0 CA certificates that you want to remove.

**Examples:**

```powershell
$cacerts = Get-TrustAuthorityTpm2CACertificate -TrustAuthorityCluster mycluster
```
_Removes the Trust Authority TPM 2.0 CA certificates from the mycluster Trust Authority cluster._

### `Remove-TrustAuthorityTpm2EndorsementKey`

**This cmdlet removes the Trust Authority TPM 2.0 endorsement keys from the Trust Authority cluster in the Trust Authority vCenter Server system.**

**Parameters:**

- -Tpm2EndorsementKey [TrustAuthorityTpm2EndorsementKey[]] (Required) Specifies the Trust Authority TPM 2.0 endorsement keys that you want to remove.

**Examples:**

```powershell
$tpm2Eks = Get-TrustAuthorityTpm2EndorsementKey -TrustAuthorityCluster mycluster
```
_Removes the Trust Authority TPM 2.0 endorsement keys from the Trust Authority cluster mycluster._

### `Remove-VIOAuth2Client`

**Deletes a registration for a specified OAuth2 client from the VMware Identity Broker.**

**Parameters:**

- -OAuth2Client [OAuth2Client[]] (Optional) Specifies the registrations that must be removed.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
PS C:\> Get-VIOAuth2Client -Id "my-ouath2-client" | Remove-VIOAuth2Client
```
_Deletes the registration with ID "my-ouath2-client"._

```powershell
PS C:\> Remove-VIOAuth2Client -OAuth2Client "my-client-*"
```
_Deletes the registrations with names that start with the string "my-client-"._

### `Remove-VIPermission`

**This cmdlet removes the specified permissions.**

**Parameters:**

- -Permission [Permission[]] (Required) Specifies the permissions you want to remove.

**Examples:**

```powershell
Remove-VIPermission -Permission $permission -Confirm:$false
```
_Removes the $permission permission without asking for confirmation._

### `Remove-VIRole`

**This cmdlet removes the specified roles.**

This cmdlet removes the specified roles. To remove a role that is associated with a permission, you need to set the Force parameter to $true.

**Parameters:**

- -Force [SwitchParameter] (Optional) Indicates that you want to remove the role even if it is associated with a permission.
- -Role [Role[]] (Required) Specifies the roles you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VIRole -Server $server -Name "Customer*" | Remove-VIRole
```
_Removes the roles with names that start with  "Customer"._

### `Remove-VTpm`

**This cmdlet removes the specified vTPM devices.**

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -VTpm [VTpm[]] (Required) Specifies the vTPM devices that you want to remove.

**Examples:**

```powershell
$myVm = Get-VM MyVM
```
_Removes the vTPM device from the virtual machine named 'MyVM'._

```powershell
$vtpm = Get-VTpm -VM "MyVM"
```
_Removes the vTPM device from the virtual machine named "MyVM"._

## Set

### `Set-KeyManagementServer`

**This cmdlet configures the settings of the key management server.**

**Parameters:**

- -Address [String] (Optional) Specifies the new address of the key management server.
- -Credential [PSCredential] (Optional) Specifies a PSCredential object that contains credentials for authenticating with the key management server.
- -KeyManagementServer [KeyManagementServer[]] (Required) Specifies the key management servers you want to configure.
- -Password [SecureString] (Optional) Specifies the new password you want to use for authenticating with the Key Management Interoperability Protocol server. If you want to unset the password, set the value to an empty string.
- -Port [Int32] (Optional) Specifies the new port number of the key management server.
- -ProxyAddress [String] (Optional) Specifies the new address of the proxy server. If you want to unset the address, set the value to an empty string.
- -ProxyPort [Int32] (Optional) Specifies the new port number of the proxy server. If you want to unset the port number, set the value to -1.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -TrustKeyManagementServer [Boolean] (Optional) Indicates whether the vCenter Server system can trust the key management server certificate. Revoking trust of the key management server is not supported.
- -Username [String] (Optional) Specifies the new user name you want to use for authenticating with the Key Management Interoperability Protocol server. If you want to unset the user name, set the value to an empty string.

**Examples:**

```powershell
Set-KeyManagementServer -KeyManagementServer $kms -Address $newKmsAddress -Port $newKmsPort
```
_Updates the $kms key management server with $newKmsAddress as the new key management server address and $newKmsPort as the new key management server port._

```powershell
Set-KeyManagementServer -KeyManagementServer $kms -Name 'NewName'
```
_Renames the $kms key management server to 'NewName'._

### `Set-KeyProvider`

**This cmdlet modifies the settings of the specified key provider.**

**Parameters:**

- -KeyProvider [KeyProvider] (Required) Specifies the key provider you want to modify.
- -KmsProvidedClientCertificate [String] (Optional) Specifies the certificate provided by the key management server and its private key. Either this parameter or the KmsProvidedClientCertificateFilePath parameter should be specified.
- -KmsProvidedClientCertificateFilePath [String] (Optional) Specifies the file path to the certificate file provided by the key management server. Either this parameter or the KmsProvidedClientCertificate parameter should be specified.
- -KmsProvidedPrivateKey [SecureString] (Optional) Specifies the private key for the key provider, if it is provided by the key management server. Either this parameter or the KmsProvidedPrivateKeyFilePath parameter should be specified.
- -KmsProvidedPrivateKeyFilePath [String] (Optional) Specifies the private key file path provided by the key management server. Either this parameter or the KmsProvidedPrivateKey parameter should be specified.
- -KmsSignedClientCertificate [String] (Optional) Uploads the key management server-signed client certificate for the key provider. The server uses the certificate for authentication with the key management server in the key provider. Either this parameter or the KmsSignedClientCertificateFilePath parameter should be specified.
- -KmsSignedClientCertificateFilePath [String] (Optional) Specifies the file path to the certificate file signed by the key management server. Either this parameter or the KmsSignedClientCertificate parameter should be specified.
- -SelfSignedClientCertificate [String] (Optional) Specifies the self-signed certificate for the key provider. The server uses the certificate for authentication with the key management server in the key provider. Either this parameter or the SelfSignedClientCertificateFilePath parameter should be specified.
- -SelfSignedClientCertificateFilePath [String] (Optional) Specifies the file path to the self-signed certificate. Either this parameter or the SelfSignedClientCertificate parameter should be specified.
- -DefaultForSystem [SwitchParameter] (Optional) Specifies the key provider you want to use as the vCenter Server system default key provider.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -KeyId [Guid] (Required) Specifies the key ID of the key provider you want to set. You can use this parameter only with key providers of the NativeKeyProvider type.

**Examples:**

```powershell
Set-KeyProvider -KeyProvider $keyProvider -SelfSignedClientCertificate $certificate -DefaultForSystem
```
_Updates the client certificate with the $certificate self-signed certificate and marks the $keyProvider key provider as the system default key provider._

```powershell
Set-KeyProvider -KeyProvider $keyProvider -KmsProvidedClientCertificate $certificate -KmsProvidedPrivateKey $privateKey
```
_Updates the client certificate and its private key with $certificate and $privateKey for the $keyProvider key provider._

### `Set-SecurityPolicy`

**This cmdlet modifies the security policy for virtual port groups or the default port security policy for virtual switches.**

This cmdlet modifies the security policy for virtual port groups or the default port security policy for virtual switches. Specifying a parameter automatically changes the parameter's Inherited setting to 'false'. Specifying the parameter's Inherited setting as 'true' automatically applies the switch level security policy to the parameter.

**Parameters:**

- -AllowPromiscuous [Boolean] (Optional) Specifies whether promiscuous mode is enabled for the corresponding virtual port group or switch.
- -AllowPromiscuousInherited [Boolean] (Optional) Specifies whether the AllowPromiscuous setting is inherited from the parent virtual switch.
- -ForgedTransmits [Boolean] (Optional) Specifies whether forged transmits are enabled for the corresponding virtual port group or switch.
- -ForgedTransmitsInherited [Boolean] (Optional) Specifies whether the ForgedTransmits setting is inherited from the parent virtual switch.
- -MacChanges [Boolean] (Optional) Specifies whether MAC address changes are enabled for the corresponding virtual port group or switch.
- -MacChangesInherited [Boolean] (Optional) Specifies whether the MacChanges setting is inherited from the parent virtual switch.
- -VirtualPortGroupPolicy [VirtualPortgroupSecurityPolicy[]] (Required) Specifies the virtual port group security policy that you want to configure.
- -VirtualSwitchPolicy [VirtualSwitchSecurityPolicy[]] (Required) Specifies the virtual switch security policy that you want to configure.

**Examples:**

```powershell
Get-VirtualSwitch -Name "MyVirtualSwitch" | Get-SecurityPolicy | Set-SecurityPolicy -MacChanges $false
```
_Retrieves a virtual switch named "MyVirtualSwitch" and updates its security policy to forbid MAC address changes._

```powershell
Get-VirtualPortgroup -Name "MyVirtualPortGroup" | Get-SecurityPolicy | Set-SecurityPolicy -ForgedTransmitsInherited $true
```
_Retrieves a virtual port group named "MyVirtualPortGroup" and updates the security policy to inherit the setting value for controlling outbound frames filtering by MAC address from its parent._

### `Set-TrustAuthorityKeyProvider`

**This cmdlet modifies the Trust Authority key providers with the specified properties in the Trust Authority vCenter Server system.**

**Parameters:**

- -ConnectionTimeoutSeconds [Int64] (Optional) Specifies the timeout in seconds of the connection between the Trust Authority key provider and the Trust Authority key provider server.
- -Description [String] (Optional) Specifies the description you want to set to the Trust Authority key provider.
- -KeyProvider [TrustAuthorityKeyProvider] (Required) Specifies the Trust Authority key provider that you want to modify.
- -KmipServerPassword [SecureString] (Required) Specifies the new password that you can use to connect to the KMIP servers from the Trust Authority key provider.
- -KmipServerUsername [String] (Optional) Specifies the new user name that you can use to connect to the KMIP servers from the Trust Authority key provider.
- -MasterKeyId [String] (Optional) This parameter is deprecated and scheduled for removal. Use the PrimaryKeyId parameter instead.
- -ProxyAddress [String] (Optional) Specifies the new proxy address of the Trust Authority key provider that you can use to connect to the KMIP servers.
- -ProxyPort [Int32] (Optional) Specifies the new porxy port number of the Trust Authority key provider that you can use to connect to the KMIP servers. This parameter works with the ProxyAddress parameter.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is given to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.
- -Type [KmsType] (Optional) Specifies the new type of the Trust Authority key provider servers.
- -PrimaryKeyId [String] (Optional) Specifies the new primary key ID of the Trust Authority key provider that you want to use from the KMIP servers.

**Examples:**

```powershell
Set-TrustAuthorityKeyProvider -KeyProvider mykp -KmipServerUsername root
```
_Sets the user name of the Key Management Interoperability Protocol (KMIP) servers in the mykp Trust Authority key provider._

```powershell
Set-TrustAuthorityKeyProvider -KeyProvider mykp -KmipServerPassword mypassword
```
_Sets the password of the KMIP servers in the mykp Trust Authority key provider._

### `Set-TrustAuthorityKeyProviderClientCertificate`

**This cmdlet updates the client certificate of the specified Trust Authority key providers in the Trust Authority vCenter Server system.**

**Parameters:**

- -Certificate [X509Certificate2] (Required) Specifies the certificate that you want to update to the Trust Authority key provider.
- -CertificateFilePath [String] (Required) Specifies the file with the certificate that you want to update to the Trust Authority key provider.
- -KeyProvider [TrustAuthorityKeyProvider[]] (Required) Specifies the Trust Authority key providers that you want to modify.
- -PrivateKey [SecureString] (Optional) Specifies the private key part of the certificate that you want to update to the Trust Authority key provider.
- -PrivateKeyFilePath [String] (Optional) Specifies the file with the private key part of the certificate that you want to update to the Trust Authority key provider.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.

**Examples:**

```powershell
Set-TrustAuthorityKeyProviderClientCertificate -KeyProvider mykp -Certificate $mycert -Privatekey $mycertKey
```
_Updates the client certificate of the Trust Authority key provider mykp with the given certificate $mycert and its private key $mycertKey._

### `Set-TrustAuthorityKeyProviderServerCertificate`

**This cmdlet updates the trusted server certificates of the specified Trust Authority key providers in the Trust Authority vCenter Server system.**

**Parameters:**

- -Certificate [X509Certificate2[]] (Required) Specifies the certificates that you can trust.
- -KeyProvider [TrustAuthorityKeyProvider] (Required) Specifies the Trust Authority key provider that you want to modify.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Optional) Specifies the Trust Authority cluster where the Trust Authority key provider resides.

**Examples:**

```powershell
$kmipServers = Get-TrustAuthorityKeyProvider -Name "myprovider" -TrustAuthorityCluster "mycluster" | Get-TrustAuthorityKeyProviderServer
```
_Indicates that the Trust Authority key provider myprovider can trust the certificates of the Trust Authority key provider servers in it._

### `Set-TrustAuthorityTpm2AttestationSettings`

**This cmdlet modifies the Trust Authority TPM 2.0 attestation settings of the Trust Authority cluster in the Trust Authority vCenter Server system.**

**Parameters:**

- -RequireCertificateValidation [SwitchParameter] (Optional) Updates the specified Trust Authority TPM 2.0 attestation settings to require the TPM 2.0 certificate authority (CA) certificate validation.
- -RequireEndorsementKey [SwitchParameter] (Optional) Updates the specified Trust Authority TPM 2.0 attestation settings to require the TPM 2.0 endorsement key validation.
- -Tpm2AttestationSettings [TrustAuthorityTpm2AttestationSettings] (Required) Specifies the Trust Authority TPM 2.0 attestation settings that you want to modify.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Required) Specifies the Trust Authority cluster where you want to modify the Trust Authority TPM 2.0 attestation settings.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
$tpm2Settings = Get-TrustAuthorityTpm2AttestationSettings -TrustAuthorityCluster mycluster
```
_Modifies the Trust Authority TPM 2.0 attestation settings in the Trust Authority Cluster mycluster. The CertificateValidation and EndorsementKey parameters are required._

### `Set-VDSecurityPolicy`

**This cmdlet modifies the security policy for distributed ports.**

This cmdlet modifies the security policy for distributed ports or the default port policy at port group or switch level (depending on the input policy).

**Parameters:**

- -AllowPromiscuous [Boolean] (Optional) Specifies whether promiscuous mode is enabled for the corresponding distributed port, port group, or switch.
- -AllowPromiscuousInherited [Boolean] (Optional) Specifies whether the AllowPromiscuous setting is inherited from a parent object, such as a distributed port group or switch.
- -ForgedTransmits [Boolean] (Optional) Specifies whether forged transmits are enabled for the corresponding distributed port, port group, or switch.
- -ForgedTransmitsInherited [Boolean] (Optional) Specifies whether the ForgedTransmits setting is inherited from a parent object, such as a distributed port group or switch.
- -MacChanges [Boolean] (Optional) Specifies whether MAC address changes are enabled for the corresponding distributed port, port group, or switch.
- -MacChangesInherited [Boolean] (Optional) Specifies whether the MacChanges setting is inherited from a parent object, such as a distributed port group or switch.
- -Policy [SecurityPolicy[]] (Required) Specifies the security policy that you want to configure.

**Examples:**

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDSecurityPolicy | Set-VDSecurityPolicy -MacChanges $true
```
_Retrieves a vSphere distributed switch named "MyVDSwitch" and updates its security policy to allow MAC address changes._

```powershell
Get-VDPortgroup "MyVDPortgroup" | Get-VDSecurityPolicy | Set-VDSecurityPolicy -ForgedTransmitsInherited $true
```
_Retrieves a distributed port group named "MyVDPortgroup" and updates the security policy to inherit the setting value for controlling outbound frames filtering by MAC address from its parent._

### `Set-VIOAuth2Client`

**Updates the configuration of the OAuth2 client registered with the VMware Identity Broker.**

Updates the configuration of the OAuth2 client registered with the VMware Identity Broker. The VMware Identity Broker is an OAuth2 relay that is used by client applications to authenticate with vCenter using OAuth2.

**Parameters:**

- -AccessTokenTimeToLiveMinutes [Int32] (Optional) How long in minutes new access tokens issued to this client should live.
- -GrantTypes [String[]] (Optional) A list of OAuth 2.0 Access Grant Types that are enabled in this OAuth 2.0 Client.
- -Name [String] (Optional) The user-friendly name that you set for this OAuth 2.0 client.
- -OAuth2Client [OAuth2Client[]] (Optional) Specifies the OAuth 2 clients whose configuration you want to modify.
- -PkceEnforced [Boolean] (Optional) Indicates whether PKCE is enforced for the OAuth2 client.
- -PostLogoutRedirectUris [String[]] (Optional) The OAuth2 Relaying Party provides a list of absolute URLs with the PostLogoutRedirectUris parameter. When a logout occurs, the Auth2 Relaying Party might request that the User Agent of the End-User is redirected to one of these absolute URLs. These URLs must contain the https scheme and can also have a port, path, and some query parameters. However, the URLs may also contain the http scheme, provided that the Client Type is confidential. To skip the check for a particular URL section, you can substitute a wildcard character with any string.
- -RedirectUris [String[]] (Optional) Specifies a list of absolute URIs of application endpoints that are allowed to receive the authorization code and access token. The redirect URI sent by the application as part of the Authorization Code Grant Oauth 2.0 flow is verified against this list. The "*" character can be used as a wildcard character to be substituted for any string to skip the check for a particular URL section. The field is required if GrantTypes parameter contain an "authorization_code" grant type.
- -RefreshTokenIdleTimeToLiveMinutes [Int32] (Optional) Specifies how long in minutes new refresh tokens issued to this client should live. Only applicable and mandatory if the GrantTypes parameter includes ?refresh_token?.
- -RefreshTokenTimeToLiveMinutes [Int32] (Optional) How long in minutes new refresh tokens issued to this client can be idle. Only applicable and mandatory if GrantTypes includes ?refresh_token?. Its value should be less than the refresh token TTL value (specified by the parameter RefreshTokenIdleTimeToLiveMinutes).
- -RuleSetNames [String[]] (Optional) Specifies a list of built-in rule set names to associate this client with. Each ruleset, allows the client to call a specific set of tenant APIs.
- -Scope [String[]] (Optional) A list of access request scopes that are allowed by this OAuth 2.0 Client.
- -Secret [SecureString] (Optional) Specifies the OAuth 2.0 Client secret. For additional security, the stored secret will not be returned by the Get-VIOAuth2Client and this command output.
- -SecretTimeToLiveInMinutes [Int32] (Optional) Specifies after what time in minutes the secret must be rotated.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
PS C:\> $x = Get-VIOAuth2Client -Id "my-client"
```
_Changes the -AccessTokenTimeToLiveMinutes configuration setting of the OAuth 2.0 client with ID "my-client" to 31. This change indicates that the registered OAuth 2.0 client will have its access tokens valid for 31 minutes._

```powershell
PS C:\> Set-VIOAuth2Client -OAuth2Client "My Client Name" -Secret "123456"
```
_Changes the current secret of the OAuth 2.0 client with user-friendly name "My Client Name" to "123456"._

### `Set-VIPermission`

**This cmdlet modifies the properties of the specified permissions.**

This cmdlet modifies the properties of the specified permissions. The cmdlet can change the role and define whether the permission propagates down the hierarchy to child inventory objects.

**Parameters:**

- -Permission [Permission[]] (Required) Specifies the permissions you want to modify.
- -Propagate [Boolean] (Optional) Indicates that you want to propagate the new permissions to the child inventory objects.
- -Role [Role] (Optional) Specifies a new role for the permissions.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Set-VIPermission -Permission $permission -Role Role -Propagate:$false
```
_Changes the Propagate property of the $permission permission to $false._

### `Set-VIRole`

**This cmdlet modifies the privileges of the provided roles.**

**Parameters:**

- -AddPrivilege [Privilege[]] (Optional) Specifies privileges and privilege groups you want to add to the provided roles.
- -Name [String] (Optional) Provides a new name for the provided role.
- -RemovePrivilege [Privilege[]] (Optional) Specifies privileges or privilege groups you want to remove from the provided roles.
- -Role [Role[]] (Required) Specifies the roles you want to modify.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Set-VIRole -Role Role -AddPrivilege (Get-VIPrivilege -Name 'Create Datacenter')
```
_Adds the "Create Datacenter" privilege to the Role role._

### `Set-VTpm`

**This cmdlet modifies the properties of the specified vTPM device.**

This cmdlet modifies the properties of the specified vTPM device. You can change the certificate of the specified vTPM device by specifying the new certificate in an X509Certificate2 object or in a file.

**Parameters:**

- -CertFilePath [String] (Required) Specifies the certificate file where the certificate string that you want to set to the specified vTPM device resides.
- -Certificate [X509Certificate2] (Required) Specifies the certificate object that you want to set to the specified vTPM device.
- -VTpm [VTpm] (Required) Specifies the vTPM device that you want to configure.

**Examples:**

```powershell
Get-VTpm -VM 'MyVM' | Set-VTpm -CertFilePath 'C:\MyCertFile.cert'
```
_Changes the certificate of the vTPM device in a virtual machine named 'MyVM' with the new certificate in the 'C:\MyCertFile.cert' file._

## Start

### `Start-VIOAuth2ClientSecretRotation`

**Initiates a rotation of the secret of an OAuth 2 client.**

Initiates a rotation of the secret of an OAuth 2 client. While the rotation process is running, both the old and the new client secret will be valid. To complete the rotation manually, use the Complete-VIOAuth2ClientSecretRotation command, or specify a time period after which the secret rotation must start automatically.

**Parameters:**

- -OAuth2Client [OAuth2Client[]] (Optional) Specifies the OAuth 2 clients whose client secret you want to rotate.
- -PrimarySecretAutoRetireDurationInMinutes [Int32] (Optional) Sets how long, in minutes, before the primary secret is automatically retired. The default value is 1 day. The maximum value is 7 days.
- -SecondarySecret [SecureString] (Required) Specifies an alternative secret to the client primary secret that will replace the existing primary secret when the secret rotation ends.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
PS C:\> Get-VIOAuth2Client -Id "my-client-id" | Start-VIOAuth2ClientSecretRotation `
```
_Initiates a rotation of the secret for the OAuth 2 client with client ID "my-client-id". For the next 100 minutes the current client secret and the new secret "my-secondary-secret" will be valid for this client. After 100 minutes or if you manually complete the rotation process using the Complete-VIOAuth2ClientSecretRotation command, the only valid client secret will be "my-secondary-secret"._

## Unregister

### `Unregister-KeyProvider`

**This cmdlet unregisters the specified key provider from the workload vCenter Server system. For a trusted key provider, you cannot use it in encryption operations. For a standard key provider, you can remove it from the workload vCenter Server system.**

**Parameters:**

- -KeyProvider [KeyProvider[]] (Required) Specifies the key providers that you want to unregister or remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Unregister-KeyProvider -KeyProvider mykp
```
_Unregisters the key provider mykp from the connected workload vCenter Server system._
