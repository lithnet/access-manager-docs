# What's new in Lithnet Access Manager v3
Lithnet Access Manager v3 - the latest major release of Access Manager - is an exciting new release that's sure to revolutionize the way you use LAPS in your organization!

Some highlights include:

{% hint style="info" %}
__RapidLAPS passwordless login__

Have you ever had to communicate a LAPS password over the phone? Are you tired of having to type in a complicated LAPS password over and over again, just to install some software?

With *RapidLAPS*, using just a QR code, or PIN, you can log into any LAPS-enabled computer, without ever having to type a long and complicated password! *RapidLAPS* integrates into the Windows lock screen and UAC prompts, allowing you to speed up the LAPS process wherever you use local admin accounts!

The great news is that this feature works, whether you are using Windows LAPS, Microsoft Legacy LAPS, or the Access Manager agent to manage your LAPS passwords.
{% endhint %}

{% hint style="info" %}
__Passphrases for LAPS__

This release adds support for generating passphrases for LAPS passwords.

With passphrases, even if you do have to type in LAPS passwords, they're going to be as easy as possible to use!

You can import wordlists for any language, ensuring you can support users in all localizations.
{% endhint %}

{% hint style="info" %}
__Unified policy management__

AMS Agent settings are now unified across all supported client operating systems.

You can target policies at AMS, Active Directory and Entra ID groups, organsational units and devices.

Active Directory-joined devices can now be managed by, and backup their local administrator passwords to the AMS server directly. Devices can now use Kerberos authentication to register with the AMS server, removing the need to issue registration keys when devices are joined to an Active Directory domain.

This means that wherever your devices are, or the directory they're tied to - managing LAPS configuration is as seamless as possible!
{% endhint %}

## What's new in the Lithnet Access Manager Service

### New features
* Active Directory-joined devices can now be managed by, and backup their local administrator passwords to the AMS server directly.
* AMS Agent policies can now be configured directly in the UI, unified across all supported client operating systems
  * Policies can be targeted at AMS, Active Directory and Entra ID groups, organsational units and devices.
* Added autocompletion support to the computer search box in the Web UI
* Added support for custom help messages presented to users in the event of an authorization error
* Added support for delivering JSON-formatted auditing events to Splunk
* Added support for custom word lists that can be used to generate passphrases
* Added support for 'automatic JIT access group creation' rules to assign a Unix-style 'gidNumber' attribute to created groups

### Deprecated features
* 

### Removed features
* Entra-registered clients running the Access Manager agent can no longer use Entra authentication. Devices must be be Entra-joined in order to authenticate with the Access Manager server.
  * *Note*: Entra ID-registered devices can still register with AMS via *registration tokens*.

### Changed features
* The Lithnet Access Manager Service now requires Microsoft .NET 8.0 (was previously built on Microsoft .NET 6.0 which is EOL in December 2024)

## What's new in the Lithnet Access Manager Agent
The agent now supports passphrases, backing up BitLocker reocvery keys for Windows devices, and enables our new RapidLAPS feature on Windows.

### New features
* RapidLAPS login and elevation - login with the AMS managed
  * Using just a QR code, or PIN, you can log into any LAPS-enabled computer, without ever having to type a long and complicated LAPS password.
  * Provides a [credential provider](https://learn.microsoft.com/en-us/windows/win32/secauthn/credential-providers-in-windows) which can be used for workstation unlock, and at UAC prompts.
  * *Note*: Windows only
* Password management updates
    * Ability to generate passphrases for local administrator accounts.
    * Ability to manage the password for an account other than the built-in administrator account.
    * Ability to create a new local managed account if it doesn't already exist.
        * *Note*: Windows and MacOS only
    * Ability to backup BitLocker encryption keys to AMS.
        * *Note*: Windows only
* Devices can now use Kerberos authentication to register with the AMS server, removing the need to issue registration keys when devices are joined to an Active Directory domain.
  * Windows agents can can now use Kerberos and NTLM ([disabled by default](https://learn.microsoft.com/en-us/windows/whats-new/deprecated-features#deprecated-features)) authentication to register with the AMS server.
  * MacOS and Linux agents can now use Kerberos authentication to register with the AMS server.

* Windows devices will now attempt to create AMS authentication certificates protected by the computer's TPM, if available

### Removed features
* The Access Manager Agent no longer writes LAPS passwords to Active Directory. All LAPS passwords are saved to the Access Manager server itself.
* The v3 Access Manager Agent can only communicate with a v3 server. Therefore, the Access Manager Server must be upgraded to v3 before upgrading the clients to v3. Note, that v2 agents will continue to work with the v3 server.
* The Access Manager Agent no longer supports using Entra-based authentication for Entra-registered devices. The device must be Entra-joined to be able use Entra authentication.
* Windows 8.1 and Windows Server 2012 are no longer supported. 

### Deprecated features
* The Lithnet Access Manager custom Active Directory schema is no longer used by the agent

### Changed features
* The Lithnet Access Manager Agent for macOS and Linux now requires Microsoft .NET 8.0
  * The agent was previously built on Microsoft .NET 6.0, which is EOL in December 2024
* The Lithnet Access Manager Agent for ARM64 versions of Windows requires .NET Framework 4.8.1
* The Lithnet Access Manager Agent for x86 and x64 versions of Windows requires .NET Framework 4.7.2 or higher
* Group Policy is no longer used to manage the Access Manager Agent for Windows. All policy settings are configured via agent policies on the Access Manager Server