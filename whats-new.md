# What's new in Lithnet Access Manager v3
Lithnet Access Manager v3 is an exiting new release that sure to revolutionize the way you use LAPS in your organization.

Our flagship feature in v3 is our RapidLAPS passwordless login feature. Using just a QR code, or PIN, you can log into any LAPS-enabled computer, without ever having to type the long and complicated LAPS password. 

The great news is that this feature works, whether you are using Windows LAPS, Microsoft Legacy LAPS, or the Access Manager agent to manage your LAPS passwords.

We've also added support for passphrases, so that if you do have to type in LAPS passwords, they are going to be as easy as possible to use!

## What's new in the Lithnet Access Manager Service

### New features
* Computer name lookup field in the web UI now support autocomplete
* Added support for sending audit events to Splunk
* Upload custom word lists that can be used to generate passphrases
* Manage all agent policies from the AMS server

### Deprecated features
* 

### Removed features
* Entra-registered clients running the Access Manager agent can no longer use Entra authentication. Devices must be be Entra-joined in order to authenticate with the Access Manager server.

### Changed features
* The Lithnet Access Manager Service now requires Microsoft .NET 8.0 (was previously built on Microsoft .NET 6.0 which is EOL in December 2024)

## What's new in the Lithnet Access Manager Agent
The agent now supports passphrases, backing up BitLocker reocvery keys for Windows devices, and enables our new RapidLAPS feature on Windows.

### New features
* Ability to manage the password for an account other than the built-in admin account
* Ability to create a new managed account if it doesn't exist (Windows and MacOS only)
* Ability to backup BitLocker encryption keys (Windows only)
* Ability to generate passphrases 
* MacOS and Linux agents can now use Kerberos authentication to register with the AMS server, removing the need to issue registration keys when these devices are joined to an Acitve Directory domain
* Windows agents can now use Negotiate authentication to register with the AMS server
* Windows agent will now attempt to create its authentication certificate using the computer's TPM, if available

### Removed features
* The Access Manager Agent no longer writes LAPS passwords to Active Directory. All LAPS passwords are saved to the Access Manager server itself.
* The v3 Access Manager Agent can only communicate with a v3 server. Therefore, the Access Manager Server must be upgraded to v3 before upgrading the clients to v3. Note, that v2 agents will continue to work with the v3 server.
* The Access Manager Agent no longer supports using Entra-based authentication for Entra-registered devices. The device must be Entra-joined to be able use Entra authentication.
* Windows 8.1 and Windows Server 2012 are no longer supported. 

### Deprecated features
* The Lithnet Access Manager custom Active Directory schema is no longer used by the agent

### Changed features
* The Lithnet Access Manager Agent for macOS and Linux now requires Microsoft .NET 8.0 (was previously built on Microsoft .NET 6.0 which is EOL in December 2024)
* The Lithnet Access Manager Agent for ARM64 versions of Windows requires .NET Framework 4.8.1
* The Lithnet Access Manager Agent for x86 and x64 versions of Windows requires .NET Framework 4.7.2 or higher
* Group policy is no longer used to manage the Access Manager Agent for Windows. All policy settings are configured via agent policies on the Access Manager Server