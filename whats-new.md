# What's new in Lithnet Access Manager v3
Lithnet Access Manager v3 - the latest major release of Access Manager - is an exciting new release that's sure to revolutionize the way you use LAPS in your organization!

## RapidLAPS passwordless login
We've made typing in long and complicated LAPS passwords a thing of the past!

Have you ever had to communicate a LAPS password over the phone? Are you tired of having to type in a complicated LAPS password over and over again, just to install some software?

With *RapidLAPS*, using just a QR code, or PIN, you can log into any LAPS-enabled computer, with the managed LAPS account, without ever having to type the LAPS password!

*RapidLAPS* integrates into the Windows lock screen and admin elevation prompts, allowing you to speed up the LAPS process wherever you use local admin accounts!

The great news is that this feature works, whether you are using Windows LAPS, legacy LAPS, or the Access Manager agent to manage your LAPS passwords.

## Passphrases for LAPS
In the scenarios where RapidLAPS isn't available or can't be used, we can still simply the process for users by using passphrases instead of randomly generated complex passwords.

Passphrases are available on all operating systems that support the Access Manager agent, configurable by custom policy that even lets you have full control of the word lists used to generate them.

So even if you do have to type in LAPS passwords, they're going to be as easy as possible to use!

## Unified policy management

AMS Agent settings are now unified across all supported client operating systems; you can target policies at AMS, Active Directory and Entra ID groups, organizational units and devices.

Active Directory-joined devices can now be managed by, and backup their local administrator passwords to the AMS server directly.

Windows, macOs, and Linux devices can now use Windows authentication to register with the AMS server, removing the need to issue registration keys when devices are joined to an Active Directory domain.

This means that wherever your devices are, or the directory they're tied to - managing LAPS configuration is as seamless as possible!

## What's new in the Lithnet Access Manager Service

### New features
* Active Directory-joined devices can now be managed by, and backup their local administrator passwords to the AMS server directly.
* AMS Agent policies can now be configured directly in the UI, unified across all supported client operating systems
  * Policies can be targeted at AMS, Active Directory and Entra ID groups, organizational units and devices.
* Added autocompletion support to the computer search box in the Web UI
* Added support for custom help messages presented to users in the event of an authorization error
* Added support for delivering JSON-formatted auditing events to Splunk HEC
* Added support for custom word lists that can be used to generate passphrases
* Added support for 'automatic JIT access group creation' rules to assign a Unix-style 'gidNumber' attribute to created groups

### Deprecated features
* Retrieval of Lithnet encrypted LAPS passwords from Active Directory. 

### Removed features
* Entra-registered clients running the Access Manager agent can no longer use Entra authentication. Devices must be Entra-joined in order to authenticate with the Access Manager server.
  * *Note*: Entra ID-registered devices can still register with AMS via *registration tokens*.

### Changed features
* The Lithnet Access Manager Service now requires Microsoft .NET 8.0 

## What's new in the Lithnet Access Manager Agent
The agent now supports passphrases, backing up BitLocker recovery keys for Windows devices, and enables our new RapidLAPS feature on Windows.

### New features
* RapidLAPS login and elevation 
* Password management updates
    * Ability to generate passphrases for local administrator accounts.
    * Ability to manage the password for an account other than the built-in administrator account.
    * Ability to create a new local managed account if it doesn't already exist.
        * *Note*: Windows and MacOS only
    * Ability to backup BitLocker encryption keys to AMS.
        * *Note*: Windows only
* Devices can now use Windows authentication to register with the AMS server, removing the need to issue registration keys when devices are joined to an Active Directory domain.
* Windows devices will now attempt to create AMS authentication certificates protected by the computer's TPM, if available

### Removed features
* The Access Manager Agent no longer writes LAPS passwords to Active Directory. All LAPS passwords are saved to the Access Manager server itself.
* The v3 Access Manager Agent can only communicate with a v3 server. Therefore, the Access Manager Server must be upgraded to v3 before upgrading the clients to v3. Note, that v2 agents will continue to work with the v3 server.
* The Access Manager Agent no longer supports using Entra-based authentication for Entra-registered devices. The device must be Entra-joined to be able use Entra authentication.
* Windows 8.1 and Windows Server 2012 are no longer supported. 
* Support for agents running on ARM32-based Linux operating systems is no longer available

### Deprecated features
* The Lithnet Access Manager custom Active Directory schema is no longer used by the agent

### Changed features
* The Lithnet Access Manager Agent for macOS and Linux now requires Microsoft .NET 8.0
* The Lithnet Access Manager Agent for ARM64 versions of Windows requires .NET Framework 4.8.1
* The Lithnet Access Manager Agent for x86 and x64 versions of Windows requires .NET Framework 4.7.2 or higher
* Group Policy is no longer used to manage the Access Manager Agent for Windows. All policy settings are configured via agent policies on the Access Manager Server