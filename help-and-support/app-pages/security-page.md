# Security page

![](../../images/ui-page-security.png)

## Service administration
### AMS administrators group
The AMS administrators group are able to manage the AMS service. They are able to edit configuration using the UI, as well as connect and execute PowerShell commands against the server.

### Encryption support
This section shows if DPAPI-NG encryption is supported on this server and in this domain. DPAPI-NG encryption support is mandatory for environments with multiple servers in a farm.

DPAPI-NG support requires at least one domain controller in the domain running Windows Server 2012 R2, and a [KDS root key](https://docs.microsoft.com/en-us/windows-server/security/group-managed-service-accounts/create-the-key-distribution-services-kds-root-key) must have been generated in the domain.

### Master key recovery password
All secrets in the database are protected by the AMS server master key. This is used to encrypt server-side secrets and private keys. Without the master key, AMS will be unable to decode settings and stored passwords, and will fail to start. A master key recovery password allows you to recover the master key in the event the server is unable to decrypt it on its own. Generate a recovery password, and store it in a safe place.

Note, that each time you generate a new recovery password, you invalidate the previous password. Only one recovery password can be active at a time.

If the server is unable to access it's master key, and no recovery password is available, there are no recovery options for the server. You will need to rebuild the environment from scratch.