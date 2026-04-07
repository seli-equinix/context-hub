---
name: powercli-security-permissions
description: "VMware PowerCLI 13.3 — Roles, permissions, privileges, key providers, TPM, Trust Authority"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,security-permissions,Add-AttestationServiceInfo, Add-EntityDefaultKeyProvider, Add-KeyManagementServer, Add-KeyProviderServiceInfo, Add-TrustAuthorityKeyProviderServer, Add-TrustAuthorityKeyProviderServerCertificate, Complete-VIOAuth2ClientSecretRotation, Export-KeyProvider, Export-Tpm2CACertificate, Export-Tpm2EndorsementKey, Export-TrustAuthorityKeyProviderClientCertificate, Export-TrustAuthorityServicesInfo, Export-TrustedPrincipal, Get-AttestationServiceInfo, Get-KeyManagementServer, Get-KeyProvider, Get-KeyProviderServiceInfo, Get-SecurityInfo, Get-SecurityPolicy, Get-Tpm2EndorsementKey, Get-TrustAuthorityAttestationService, Get-TrustAuthorityKeyProvider, Get-TrustAuthorityKeyProviderClientCertificate, Get-TrustAuthorityKeyProviderClientCertificateCSR, Get-TrustAuthorityKeyProviderServer, Get-TrustAuthorityKeyProviderServerCertificate, Get-TrustAuthorityKeyProviderService, Get-TrustAuthorityPrincipal, Get-TrustAuthorityServicesStatus, Get-TrustAuthorityTpm2AttestationSettings, Get-TrustAuthorityTpm2CACertificate, Get-TrustAuthorityTpm2EndorsementKey, Get-TrustedPrincipal, Get-VDSecurityPolicy, Get-VIAccount, Get-VIOAuth2Client, Get-VIPermission, Get-VIPrivilege, Get-VIPrivilegeReport, Get-VIRole, Get-VTpm, Get-VTpmCertificate, Get-VTpmCSR, Import-KeyProvider, Import-TrustAuthorityServicesInfo, New-TrustAuthorityKeyProvider, New-TrustAuthorityKeyProviderClientCertificate, New-TrustAuthorityKeyProviderClientCertificateCSR, New-TrustAuthorityPrincipal, New-TrustAuthorityTpm2CACertificate, New-TrustAuthorityTpm2EndorsementKey, New-VIOAuth2Client, New-VIPermission, New-VIRole, New-VISamlSecurityContext, New-VTpm, Register-KeyProvider, Remove-AttestationServiceInfo, Remove-EntityDefaultKeyProvider, Remove-KeyManagementServer, Remove-KeyProviderServiceInfo, Remove-TrustAuthorityKeyProvider, Remove-TrustAuthorityKeyProviderServer, Remove-TrustAuthorityKeyProviderServerCertificate, Remove-TrustAuthorityPrincipal, Remove-TrustAuthorityTpm2CACertificate, Remove-TrustAuthorityTpm2EndorsementKey, Remove-VIOAuth2Client, Remove-VIPermission, Remove-VIRole, Remove-VTpm, Set-KeyManagementServer, Set-KeyProvider, Set-SecurityPolicy, Set-TrustAuthorityKeyProvider, Set-TrustAuthorityKeyProviderClientCertificate, Set-TrustAuthorityKeyProviderServerCertificate, Set-TrustAuthorityTpm2AttestationSettings, Set-VDSecurityPolicy, Set-VIOAuth2Client, Set-VIPermission, Set-VIRole, Set-VTpm, Start-VIOAuth2ClientSecretRotation, Unregister-KeyProvider"
---

# VMware PowerCLI — Security & Permissions

Roles, permissions, privileges, key providers, TPM, Trust Authority. Module: VMware.VimAutomation (85 cmdlets).

## Cmdlet Reference (85 cmdlets)

### Add

#### `Add-AttestationServiceInfo`

This cmdlet adds an attestation service information, which comes from the TrustAuthorityAttestationService that runs in the Trust Authority system or its detailed information in the workload vCenter Server system.

**Parameters**: `AttestationService, ServiceAddress, ServiceGroup, TAClusterId, TrustedCA, ServicePort, FilePath, Server`

#### `Add-EntityDefaultKeyProvider`

This cmdlet adds a key provider to entities as default key provider.

**Parameters**: `KeyProvider, Entity, Server`

#### `Add-KeyManagementServer`

This cmdlet adds a key management server to a vCenter Server system.

**Parameters**: `Name, KeyProvider, Address, Port, TrustKeyManagementServer, ProxyAddress, ProxyPort, Username, Password, Credential, Server`

#### `Add-KeyProviderServiceInfo`

This cmdlet adds key provider service information, which comes from the Trust Authority key provider service running in the Trust Authority system or its detailed information in the workload vCenter Server system.

**Parameters**: `KeyProviderService, ServiceAddress, ServiceGroup, TAClusterId, TrustedCA, ServicePort, FilePath, Server`

#### `Add-TrustAuthorityKeyProviderServer`

This cmdlet adds a new Trust Authority key provider server to an existing Trust Authority key provider in the Trust Authority system.

**Parameters**: `TrustAuthorityCluster, KeyProvider, Address, Name, Port, Server`

#### `Add-TrustAuthorityKeyProviderServerCertificate`

This cmdlet adds the certificate from the Trust Authority key provider server to be trusted by the Trust Authority key provider.

**Parameters**: `TrustAuthorityCluster, KeyProvider, Certificate, FilePath, ServerCertificate, Server`

### Complete

#### `Complete-VIOAuth2ClientSecretRotation`

Forces an immediate secret rotation for a specific OAuth 2 client.

**Parameters**: `OAuth2Client, Server`

### Export

#### `Export-KeyProvider`

This cmdlet exports a specified key provider configuration to a specified file. You can use only the NativeKeyProvider type for the KeyProvider parameter.

**Parameters**: `KeyProvider, FilePath, Password, Force, Server`

#### `Export-Tpm2CACertificate`

This cmdlet exports the CA certificate from either the certificate in the specified TPM 2.0 endorsement key or the specified certificate to a file.

**Parameters**: `Tpm2EndorsementKey, Certificate, FilePath, Force, RunAsync`

#### `Export-Tpm2EndorsementKey`

This cmdlet exports the TPM 2.0 endorsement key from the TPM 2.0 chip in the specified host. It only works when you connect to the specified host directly by using the Connect-VIServer cmdlet.

**Parameters**: `VMHost, FilePath, Force, Server`

#### `Export-TrustAuthorityKeyProviderClientCertificate`

This cmdlet exports the client certificate from the specified Trust Authority key provider to the specified file.

**Parameters**: `TrustAuthorityCluster, KeyProvider, FilePath, Force, Server`

#### `Export-TrustAuthorityServicesInfo`

This cmdlet exports the Trust Authority services information (the Trust Authority attestation service and Trust Authority key provider service) from the specified Trust Authority cluster to the specified file.

**Parameters**: `TrustAuthorityCluster, FilePath, Force, Server`

#### `Export-TrustedPrincipal`

This cmdlet exports the trusted principal from the single or the specified connected workload vCenter Server system to the specified file.

**Parameters**: `Server, FilePath, Force`

### Get

#### `Get-AttestationServiceInfo`

This cmdlet retrieves the attestation services information configured in the workload vCenter Server system.

**Parameters**: `ServiceAddress, ServiceGroup, ServicePort, TAClusterId, Id, Server`

#### `Get-KeyManagementServer`

This cmdlet retrieves the key management servers registered on the vCenter Server system.

**Parameters**: `Name, KeyProvider, Address, Id, Server`

#### `Get-KeyProvider`

This cmdlet retrieves all key providers from the vCenter Server system.

**Parameters**: `Name, Id, Type, Server`

#### `Get-KeyProviderServiceInfo`

This cmdlet retrieves the key provider services information configured in the workload vCenter Server system.

**Parameters**: `ServiceAddress, ServiceGroup, ServicePort, TAClusterId, Id, Server`

#### `Get-SecurityInfo`

This cmdlet retrieves the security information of objects (VirtualMachine, HardDisk or VMHost).

**Parameters**: `Entity, Server`

#### `Get-SecurityPolicy`

This cmdlet retrieves the security policy for virtual port groups or the default port security policy for virtual switches.

**Parameters**: `VirtualSwitch, VirtualPortGroup, Server`

#### `Get-Tpm2EndorsementKey`

This cmdlet retrieves the TPM 2.0 endorsement key from the TPM 2.0 chip in the specified host. You can use this cmdlet by connecting either directly to an ESXi host or to its vCenter Server system.

**Parameters**: `VMHost, VMHostTPM, Server`

#### `Get-TrustAuthorityAttestationService`

This cmdlet retrieves the Trust Authority attestation services from the specified enabled Trust Authority cluster in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, VMHost, ServiceAddress, ServiceGroup, Server`

#### `Get-TrustAuthorityKeyProvider`

This cmdlet retrieves the Trust Authority key providers from the specified Trust Authority cluster in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, Name, Server`

#### `Get-TrustAuthorityKeyProviderClientCertificate`

This cmdlet retrieves the client certificate from the specified Trust Authority key provider in the connected Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, KeyProvider, Server`

#### `Get-TrustAuthorityKeyProviderClientCertificateCSR`

This cmdlet retrieves the client certificate Certificate Signing Request (CSR) from the specified Trust Authority key provider in the connected Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, KeyProvider, Server`

#### `Get-TrustAuthorityKeyProviderServer`

This cmdlet retrieves the Trust Authority key provider servers from the specified Trust Authority key providers in the connected Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, KeyProvider, Name, Address, Server`

#### `Get-TrustAuthorityKeyProviderServerCertificate`

This cmdlet retrieves the certificate from the Trust Authority key provider server or the certificate trusted by the specified Trust Authority key provider in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, KeyProviderServer, KeyProvider, Server`

#### `Get-TrustAuthorityKeyProviderService`

This cmdlet retrieves the Trust Authority key provider services from the specified enabled Trust Authority cluster in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, VMHost, ServiceAddress, ServiceGroup, Server`

#### `Get-TrustAuthorityPrincipal`

This cmdlet retrieves the Trust Authority principals from the specified Trust Authority clusters in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, Domain, Issuer, Name, Id, Server`

#### `Get-TrustAuthorityServicesStatus`

This cmdlet retrieves the Trust Authority services status from the specified Trust Authority clusters in the connected Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, Server`

#### `Get-TrustAuthorityTpm2AttestationSettings`

This cmdlet retrieves the Trust Authority TPM 2.0 attestation settings from the specified Trust Authority clusters in the connected Trust Auhtority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, Server`

#### `Get-TrustAuthorityTpm2CACertificate`

This cmdlet retrieves the Trust Authority TPM 2.0 Certificate Authority (CA) certificates from the specified Trust Authority clusters in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, Name, Id, Server`

#### `Get-TrustAuthorityTpm2EndorsementKey`

This cmdlet retrieves the Trust Authority TPM 2.0 endorsement keys from the specified Trust Authority clusters in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, Name, Id, Server`

#### `Get-TrustedPrincipal`

This cmdlet retrieves the trusted principals from the connected workload vCenter Server system.

**Parameters**: `Server`

#### `Get-VDSecurityPolicy`

This cmdlet retrieves the security policy for distributed ports.

**Parameters**: `VDPortgroup, VDSwitch, VDPort, Server`

#### `Get-VIAccount`

This cmdlet retrieves the accounts from the ESX/ESXi or vCenter Server.

**Parameters**: `Group, User, Id, Domain, Name, Server`

#### `Get-VIOAuth2Client`

This cmdlet retrieves the OAuth2 clients available on a vCenter Server system.

**Parameters**: `Id, Name, Server`

#### `Get-VIPermission`

This cmdlet retrieves the permissions defined on the specified inventory objects.

**Parameters**: `Entity, Principal, Server`

```powershell
Get-VIPermission -Entity (Get-Datacenter "DC1") | Select-Object Principal, Role, Propagate
```

#### `Get-VIPrivilege`

This cmdlet retrieves the privilege groups and items for the provided servers.

**Parameters**: `PrivilegeGroup, PrivilegeItem, Name, Role, Group, Id, Server`

#### `Get-VIPrivilegeReport`

This cmdlet records the privilege checks that occur for the specified sessions during the execution of a specified script block.

**Parameters**: `ScriptBlock, Server`

#### `Get-VIRole`

This cmdlet retrieves all roles defined on the provided servers.

**Parameters**: `Name, Id, Server`

#### `Get-VTpm`

This cmdlet retrieves the virtual TPM (vTPM) devices available on the given virtual machines.

**Parameters**: `VM, Id, Server`

#### `Get-VTpmCSR`

This cmdlet retrieves the certficate signing requests (CSR) from the given vTPM devices.

**Parameters**: `VTpm, CSRType`

#### `Get-VTpmCertificate`

This cmdlet retrieves the certificate information from the given vTPM devices.

**Parameters**: `VTpm, CSRType`

### Import

#### `Import-KeyProvider`

This cmdlet imports a key provider from a specified configuration file.

**Parameters**: `FilePath, Password, TpmRequired, DryRun, Server`

#### `Import-TrustAuthorityServicesInfo`

This cmdlet imports the Trust Authority services information (Trust Authority attestation service and Trust Authority key provider service) from the specified file to the workload vCenter Server system.

**Parameters**: `FilePath, Server`

### New

#### `New-TrustAuthorityKeyProvider`

This cmdlet creates a new Trust Authority key provider in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, Name, MasterKeyId, PrimaryKeyId, Description, KmipServerName, KmipServerAddress, KmipServerPort, ProxyAddress, ProxyPort, KmipServerUsername, KmipServerPassword` (+2 more)

#### `New-TrustAuthorityKeyProviderClientCertificate`

This cmdlet creates a client certificate for the specified Trust Authority key provider in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, KeyProvider, Server`

#### `New-TrustAuthorityKeyProviderClientCertificateCSR`

This cmdlet creates the client certificate Certificate Signing Request (CSR) for the specified Trust Authority key providers in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, KeyProvider, Server`

#### `New-TrustAuthorityPrincipal`

This cmdlet creates a new Trust Authority principal in the specified Trust Authority cluster in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, TrustedPrincipal, FilePath, Name, Domain, Issuer, CertificateChain, Type, Server`

#### `New-TrustAuthorityTpm2CACertificate`

This cmdlet creates a new Trust Authority TPM 2.0 Certificate Authority (CA) certificate in the specified Trust Authority Cluster in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, CertificateChain, Name, FilePath, Server`

#### `New-TrustAuthorityTpm2EndorsementKey`

This cmdlet creates a new Trust Authority TPM 2.0 endorsement key in the specified Trust Authority cluster in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, Tpm2EndorsementKey, Certificate, CertificateFile, Name, PublicKey, PublicKeyFile, FilePath, Server`

#### `New-VIOAuth2Client`

Creates a new OAuth2 client registration with the VMware Identity Broker.

**Parameters**: `ClientId, Name, Secret, Scope, AccessTokenTimeToLiveMinutes, RefreshTokenTimeToLiveMinutes, RefreshTokenIdleTimeToLiveMinutes, SecretTimeToLiveInMinutes, GrantTypes, RedirectUris, PostLogoutRedirectUris, RuleSetNames` (+3 more)

#### `New-VIPermission`

This cmdlet creates new permissions on the specified inventory objects for the provided users and groups in the role.

**Parameters**: `Entity, Principal, Role, Propagate, Server`

#### `New-VIRole`

This cmdlet creates a new role on the specified servers and applies the provided privileges.

**Parameters**: `Name, Privilege, Server`

#### `New-VISamlSecurityContext`

Creates an SAML2 security context object that can be used to authenticate a user with any VMware vCenter Server services.

**Parameters**: `VCenterServer, Port, IgnoreSslValidationErrors, OAuthSecurityContext`

#### `New-VTpm`

This cmdlet creates a new vTPM device on the specified virtual machine.

**Parameters**: `VM, Server, RunAsync`

### Register

#### `Register-KeyProvider`

This cmdlet registers a trusted key provider in the workload vCenter Server system which you can use for encryption operations.

**Parameters**: `KeyProvider, Server`

### Remove

#### `Remove-AttestationServiceInfo`

This cmdlet removes the specified attestation services information from the workload vCenter Server system.

**Parameters**: `AttestationServiceInfo`

#### `Remove-EntityDefaultKeyProvider`

This cmdlet removes the default key provider from the specified entities.

**Parameters**: `Entity, Server`

#### `Remove-KeyManagementServer`

This cmdlet removes the specified key management servers from the vCenter Server systems.

**Parameters**: `KeyManagementServer, Server`

#### `Remove-KeyProviderServiceInfo`

This cmdlet removes the specified key provider services information from the workload vCenter Server system.

**Parameters**: `KeyProviderServiceInfo`

#### `Remove-TrustAuthorityKeyProvider`

This cmdlet removes the specified Trust Authority key providers from the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, KeyProvider, Server`

#### `Remove-TrustAuthorityKeyProviderServer`

This cmdlet removes the specified Trust Authority key provider servers from their location in the Trust Authority vCenter Server system.

**Parameters**: `KeyProviderServer`

#### `Remove-TrustAuthorityKeyProviderServerCertificate`

This cmdlet removes the specified Trust Authority key provider server certificates from their location. The certificate is no longer trusted by the Trust Authority key provider in the Trust Authority vCenter Server system.

**Parameters**: `ServerCertificate`

#### `Remove-TrustAuthorityPrincipal`

This cmdlet removes the Trust Authority principals from their location in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityPrincipal`

#### `Remove-TrustAuthorityTpm2CACertificate`

This cmdlet removes the Trust Authority TPM 2.0 certificate authority (CA) certificates from the Trust Authority cluster in the Trust Authority vCenter Server system.

**Parameters**: `Tpm2CACertificate`

#### `Remove-TrustAuthorityTpm2EndorsementKey`

This cmdlet removes the Trust Authority TPM 2.0 endorsement keys from the Trust Authority cluster in the Trust Authority vCenter Server system.

**Parameters**: `Tpm2EndorsementKey`

#### `Remove-VIOAuth2Client`

Deletes a registration for a specified OAuth2 client from the VMware Identity Broker.

**Parameters**: `OAuth2Client, Server`

#### `Remove-VIPermission`

This cmdlet removes the specified permissions.

**Parameters**: `Permission`

#### `Remove-VIRole`

This cmdlet removes the specified roles.

**Parameters**: `Role, Force, Server`

#### `Remove-VTpm`

This cmdlet removes the specified vTPM devices.

**Parameters**: `VTpm, RunAsync`

### Set

#### `Set-KeyManagementServer`

This cmdlet configures the settings of the key management server.

**Parameters**: `KeyManagementServer, Address, Port, TrustKeyManagementServer, ProxyAddress, ProxyPort, Username, Password, Credential, Server`

#### `Set-KeyProvider`

This cmdlet modifies the settings of the specified key provider.

**Parameters**: `KeyProvider, DefaultForSystem, SelfSignedClientCertificate, SelfSignedClientCertificateFilePath, KmsSignedClientCertificate, KmsSignedClientCertificateFilePath, KmsProvidedClientCertificate, KmsProvidedClientCertificateFilePath, KmsProvidedPrivateKey, KmsProvidedPrivateKeyFilePath, KeyId, Server`

#### `Set-SecurityPolicy`

This cmdlet modifies the security policy for virtual port groups or the default port security policy for virtual switches.

**Parameters**: `VirtualSwitchPolicy, VirtualPortGroupPolicy, AllowPromiscuousInherited, ForgedTransmitsInherited, MacChangesInherited, AllowPromiscuous, ForgedTransmits, MacChanges`

#### `Set-TrustAuthorityKeyProvider`

This cmdlet modifies the Trust Authority key providers with the specified properties in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, KeyProvider, ConnectionTimeoutSeconds, Description, KmipServerUsername, ProxyAddress, ProxyPort, MasterKeyId, PrimaryKeyId, Type, KmipServerPassword, Server`

#### `Set-TrustAuthorityKeyProviderClientCertificate`

This cmdlet updates the client certificate of the specified Trust Authority key providers in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, KeyProvider, Certificate, PrivateKey, CertificateFilePath, PrivateKeyFilePath, Server`

#### `Set-TrustAuthorityKeyProviderServerCertificate`

This cmdlet updates the trusted server certificates of the specified Trust Authority key providers in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, KeyProvider, Certificate, Server`

#### `Set-TrustAuthorityTpm2AttestationSettings`

This cmdlet modifies the Trust Authority TPM 2.0 attestation settings of the Trust Authority cluster in the Trust Authority vCenter Server system.

**Parameters**: `Tpm2AttestationSettings, TrustAuthorityCluster, RequireCertificateValidation, RequireEndorsementKey, Server`

#### `Set-VDSecurityPolicy`

This cmdlet modifies the security policy for distributed ports.

**Parameters**: `Policy, AllowPromiscuous, AllowPromiscuousInherited, ForgedTransmits, ForgedTransmitsInherited, MacChanges, MacChangesInherited`

#### `Set-VIOAuth2Client`

Updates the configuration of the OAuth2 client registered with the VMware Identity Broker.

**Parameters**: `OAuth2Client, AccessTokenTimeToLiveMinutes, Name, PostLogoutRedirectUris, PkceEnforced, GrantTypes, RedirectUris, RefreshTokenIdleTimeToLiveMinutes, RefreshTokenTimeToLiveMinutes, RuleSetNames, Scope, Secret` (+2 more)

#### `Set-VIPermission`

This cmdlet modifies the properties of the specified permissions.

**Parameters**: `Permission, Role, Propagate, Server`

#### `Set-VIRole`

This cmdlet modifies the privileges of the provided roles.

**Parameters**: `Role, Name, AddPrivilege, RemovePrivilege, Server`

#### `Set-VTpm`

This cmdlet modifies the properties of the specified vTPM device.

**Parameters**: `VTpm, Certificate, CertFilePath`

### Start

#### `Start-VIOAuth2ClientSecretRotation`

Initiates a rotation of the secret of an OAuth 2 client.

**Parameters**: `OAuth2Client, PrimarySecretAutoRetireDurationInMinutes, SecondarySecret, Server`

### Unregister

#### `Unregister-KeyProvider`

This cmdlet unregisters the specified key provider from the workload vCenter Server system. For a trusted key provider, you cannot use it in encryption operations. For a standard key provider, you can remove it from the workload vCenter Server system.

**Parameters**: `KeyProvider, Server`
