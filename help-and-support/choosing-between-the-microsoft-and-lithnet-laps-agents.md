# Choosing between the Microsoft and Lithnet agents for LAPS support

Managing local admin passwords safely and securely relies on having a mechanism to generate and store the local admin passwords. There are three supported agents you can use with Access Manager to manage your device local admin passwords. This guide will help you choose the right option for your environment.

## Option 1: Lithnet Access Manager agent 
Lithnet Access Manager has its own agent that can be used to manage the local admin passwords of your devices. It has full support for encrypted passwords, password history, and is not just supported on Windows, but macOS and Linux as well.

As well as managing LAPS passwords in much the same way as the Microsoft agent, it adds support for backing up BitLocker recovery codes from any Windows device, and enables our new RapidLAPS passwordless LAPS login capability.

Pros
- Supports Windows, macOS, and Linux
- Encrypts all passwords, along with password history support
- Support for "passwordless" elevation and LAPS login with *RapidLAPS* (Windows only)
- Backs up BitLocker recovery keys (Windows only)
- Supports Windows Server 2016 and higher, as well as Windows 10 and higher
- Supports Active Directory joined, Entra ID joined, as well as standalone Windows devices

Cons
- No support for out-of-date operating systems. Only supported on Windows 10 and above and Windows Server 2016 and above

### When should I use the Lithnet Access Manager agent?
- You wish to use the *RapidLAPS* feature on Windows devices.
- You have macOS and Linux devices you want to support
- You have Windows devices not joined to a domain
- You want one LAPS client solution for your entire Windows and non-Windows fleet

{% hint style="info" %}
**Use the *password management* features of the Lithnet Access Manager agent is optional**

For example, if you wish to keep using native Windows LAPS to manage passwords, but want to make use of features such as *RapidLAPS*, the AMS Agent can be configured to not manage passwords.

If the AMS Agent detects that either the *Windows LAPS client* or the *legacy LAPS client* is managing passwords on a device, it will *not* attempt to manage local account passwords (to avoid conflicts).
{% endhint %}

{% hint style="info" %}
**Mix and match!**

It's important to note that you are not restricted to the use of a single LAPS client type in your environment. 

For example, you can use the legacy LAPS client on legacy operating systems, Windows LAPS on modern operating systems, and Access Manager Agent on macOS and Linux devices.

Access Manager Server can read LAPS passwords from any client listed on this page.
{% endhint %}

## Option 2: Legacy LAPS client
Microsoft's tried and true legacy LAPS client provides support for managing LAPS passwords for Active Directory joined devices. It supports a wide range of legacy and modern Windows operating systems.

Pros
- Has the broadest support for OS coverage
- Easy to deploy and configure via group policy

Cons
- Windows only
- Supports Active Directory domain-joined machines only
- Passwords are stored in the directory in plain-text
- Does not store a history of previously used local admin passwords
- Deprecated and no longer being updated by Microsoft

### When should I use legacy LAPS?
- You have an existing deployment of legacy LAPS
- You need to support legacy Windows operating system versions 

## Option 3: Windows LAPS client
In April 2023, Microsoft released LAPS as a built-in Windows feature. This also brought a range of new support for things like password history, encryption, and support for Microsoft Entra joined devices. 

Pros
- Support for both AD and Microsoft Entra joined devices
- Has password history support
- Optionally encrypts passwords stored in Active Directory
- Built into Windows
- Actively supported and developed by Microsoft

Cons
- Windows only
- No support for older operating systems that are still in support. Only supported on Windows 11, Windows Server 2019 and higher, and Windows 10 versions supported as of April 2023.

### When should I use Windows LAPS?
- Your organization has modern Windows operating systems either joined to Microsoft Entra or Active Directory

## Operating system support

The Microsoft agents works only on Windows AD or Microsoft Entra-joined devices. Lithnet Access Manager agent supports a much wider range of operating systems.

| Operating system    |   Microsoft Legacy LAPS Agent  |  Microsoft Windows LAPS Agent  |   Lithnet Access Manager Agent   |
| --- | --- | --- | --- |
|  Windows Vista, Windows 7 and Windows 8 |   ![](../images/check3.png)  |  ![](../images/dash.png)  |   ![](../images/dash.png)  |
| Windows 8.1  |   ![](../images/check3.png)  |  ![](../images/dash.png)  | ![](../images/dash.png)  |
|  Windows 10  |   ![](../images/check3.png)  |  ![](../images/check3.png)  |   ![](../images/check3.png)  |
| Windows 11 and higher |  ![](../images/check3.png)  |    ![](../images/check3.png)   |   ![](../images/check3.png)  |
| Windows Server 2012 R2  |   ![](../images/check3.png)  |  ![](../images/dash.png)  |  ![](../images/dash.png)   |
| Windows Server 2016 |   ![](../images/check3.png)  |  ![](../images/dash.png)  |   ![](../images/check3.png)  |
| Windows Server 2019 and higher  |   ![](../images/check3.png)  |    ![](../images/check3.png)   |   ![](../images/check3.png)  |
| macOS<sup>\[1\]</sup> |  ![](../images/dash.png)  |  ![](../images/dash.png)  |   ![](../images/check3.png)  |
| Linux<sup>\[1\]</sup> |  ![](../images/dash.png)  |  ![](../images/dash.png)  |   ![](../images/check3.png)  |

_1. See the [downloads page](../installation/downloads.md) for detailed operating system support for macOS and Linux agents._

## Supported join types
| Join type | Microsoft Legacy LAPS Agent | Microsoft Windows LAPS Agent | Lithnet Access Manager Agent |
| --- | --- |--- |--- |
| Active Directory joined devices |   ![](../images/check3.png) |   ![](../images/check3.png) |   ![](../images/check3.png) |
| Entra ID joined devices | ![](../images/dash.png) |   ![](../images/check3.png) |   ![](../images/check3.png) |
| Non-domain joined devices (workgroup) | ![](../images/dash.png) | ![](../images/dash.png) |   ![](../images/check3.png) |

## Feature comparison

| Feature     |   Microsoft Legacy LAPS Agent  |  Microsoft Windows LAPS Agent  |  Lithnet Access Manager Agent   |
| --- | --- | --- | --- |
| Regularly rotates the local admin password  |   ![](../images/check3.png)  |    ![](../images/check3.png) |    ![](../images/check3.png)  |
| Stores a history of previous local admin passwords |  ![](../images/dash.png) |    ![](../images/check3.png)  |    ![](../images/check3.png)  |
| Stores passwords in plain-text  |   ![](../images/check3.png)  |  ![](../images/dash.png) 1 |  ![](../images/dash.png)  |
| Encrypts passwords    |  ![](../images/dash.png)  | ![](../images/check3.png)  |    ![](../images/check3.png)  |   
| Writes passwords to Active Directory |   ![](../images/check3.png)  |    ![](../images/check3.png) |   ![](../images/dash.png) |
| Write passwords to Entra ID |![](../images/dash.png)  |    ![](../images/check3.png)   |![](../images/dash.png) |
| Write passwords to the AMS server  |  ![](../images/dash.png)  |  ![](../images/dash.png)  |   ![](../images/check3.png)  |
| Backups up BitLocker recovery keys to AMS  |  ![](../images/dash.png)  |  ![](../images/dash.png)  |   ![](../images/check3.png)  |
| Enables passwordless login and elevation via RapidLAPS  |  ![](../images/dash.png)  |  ![](../images/dash.png)  |   ![](../images/check3.png)  |

_1. Windows LAPS can store passwords in plain text if configured_

## Compatibility with password retrieval solutions

| | Legacy LAPS thick client | Windows LAPS AD property pages | Windows LAPS PowerShell | Entra Admin Portal | Access Manager Service|
| --- | --- | --- | --- | --- | --- |
| Microsoft Legacy LAPS passwords stored in AD | ![](../images/check3.png)  | ![](../images/check3.png) | ![](../images/check3.png)  | ![](../images/dash.png) | ![](../images/check3.png) | 
| Microsoft Windows LAPS passwords stored in AD |![](../images/dash.png) | ![](../images/check3.png)| ![](../images/check3.png)  | ![](../images/dash.png) |  ![](../images/check3.png)  |
| Microsoft Windows LAPS passwords stored in Microsoft Entra |![](../images/dash.png) | ![](../images/dash.png)  | ![](../images/check3.png)  | ![](../images/check3.png)  |  ![](../images/check3.png)  |
| Access Manager Agent passwords |   ![](../images/dash.png)  |  ![](../images/dash.png)  |![](../images/dash.png)  |  ![](../images/dash.png)  |   ![](../images/check3.png)  |


