# Choosing between the Microsoft and Lithnet agents for LAPS support

Managing local admin passwords safely and securely relies on having a mechanism to generate and store the local admin passwords. There are three supported agents you can use with Access Manager to manage your device local admin passwords. This guide will help you choose the right option for your environment.

## Option 1: Legacy LAPS client
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

## Option 2: Windows LAPS client
In April 2023, Microsoft released LAPS as a built-in Windows feature. This also brought a range of new support for things like password history, encryption, and support for Azure AD joined devices. 

Pros
- Support for both AD and Azure AD joined devices
- Has password history support
- Optionally encrypts passwords stored in Active Directory
- Built into Windows
- Actively supported and developed by Microsoft

Cons
- Windows only
- No support for older operating systems that are still in support. Only supported on Windows 11, Windows Server 2019 and higher, and Windows 10 versions supported as of April 2023.

### When should I use Windows LAPS?
- Your organization has modern Windows operating systems either joined to Azure AD or Active Directory

## Option 3: Lithnet Access Manager agent 
Lithnet Access Manager has its own agent that can be used to managing the local admin passwords of your devices. It has full support for encrypted passwords, password history, and is not just supported on Windows, but macOS and Linux as well.

Pros
- Supports Windows, macOS, and Linux
- Encrypts all passwords
- Has password history support
- Supports Windows Server 2012 R2 and higher, as well as Windows 8.1 and higher
- Supports domain joined, Azure AD-joined, as well as standalone Windows devices

Cons
- No support for out-of-date operating systems. Only supported on Windows 8.1 and above and Windows Server 2012 R2 and above

### When should I use the Lithnet Access Manager agent?
- You have macOS and Linux devices you want to support
- You have Windows devices not joined to a domain
- You want fully encrypted local admin passwords in all scenarios
- You want one LAPS client solution for your entire Windows and non-Windows fleet

{% hint style="info" %}
Note, that you are not restricted to the use of a single LAPS client type in your environment. 

For example, you can use the legacy LAPS client on legacy operating systems, Windows LAPS on modern operating systems, and Access Manager Agent on macOS and Linux devices.

Access Manager Server can read LAPS passwords from any client listed on this page.
{% endhint %}

## Operating system support

The Microsoft agents works only on Windows AD or Azure AD-joined devices. Lithnet Access Manager agent supports a much wider range of operating systems.

| Operating system    |   Microsoft Legacy LAPS Agent  |  Microsoft Windows LAPS Agent  |   Lithnet Access Manager Agent   |
| --- | --- | --- | --- |
|  Windows Vista, Windows 7 and Windows 8 |   ![](../../images/check3.png)  |  ![](../../images/dash.png)  |   ![](../../images/dash.png)  |
| Windows 8.1  |   ![](../../images/check3.png)  |  ![](../../images/dash.png)  |   ![](../../images/check3.png)  |
|  Windows 10  |   ![](../../images/check3.png)  |  ![](../../images/check3.png)  |   ![](../../images/check3.png)  |
| Windows 11 and higher |  ![](../../images/check3.png)  |    ![](../../images/check3.png)   |   ![](../../images/check3.png)  |
| Windows Server 2012 R2  |   ![](../../images/check3.png)  |  ![](../../images/dash.png)  |   ![](../../images/check3.png)  |
| Windows Server 2016 |   ![](../../images/check3.png)  |  ![](../../images/dash.png)  |   ![](../../images/check3.png)  |
| Windows Server 2019 and higher  |   ![](../../images/check3.png)  |    ![](../../images/check3.png)   |   ![](../../images/check3.png)  |
| Linux     |  ![](../../images/dash.png)  |  ![](../../images/dash.png)  |   ![](../../images/check3.png)  |
| macOS     |  ![](../../images/dash.png)  |  ![](../../images/dash.png)  |   ![](../../images/check3.png)  |

## Supported join types
| Join type | Microsoft Legacy LAPS Agent | Microsoft Windows LAPS Agent | Lithnet Access Manager Agent |
| --- | --- |--- |--- |
| Active Directory joined devices |   ![](../../images/check3.png) |   ![](../../images/check3.png) |   ![](../../images/check3.png) |
| Azure Active Directory joined devices | ![](../../images/dash.png) |   ![](../../images/check3.png) |   ![](../../images/check3.png) |
| Azure Active Directory registered devices | ![](../../images/dash.png) |   ![](../../images/dash.png) |   ![](../../images/check3.png) |
| Non-domain joined devices (workgroup) | ![](../../images/dash.png) | ![](../../images/dash.png) |   ![](../../images/check3.png) |

## Feature comparison

| Feature     |   Microsoft Legacy LAPS Agent  |  Microsoft Windows LAPS Agent  |  Lithnet Access Manager Agent   |
| --- | --- | --- | --- |
| Regularly rotates the local admin password  |   ![](../../images/check3.png)  |    ![](../../images/check3.png) |    ![](../../images/check3.png)  |
| Requires a custom schema for AD password storage   |   ![](../../images/check3.png)  |    ![](../../images/check3.png)  |   ![](../../images/check3.png) 1 |
| Stores a history of previous local admin passwords |  ![](../../images/dash.png) |    ![](../../images/check3.png)  |    ![](../../images/check3.png)  |
| Stores passwords in plain-text  |   ![](../../images/check3.png)  |  ![](../../images/dash.png) 3 |  ![](../../images/dash.png) 2  |
| Encrypts passwords    |  ![](../../images/dash.png)  | ![](../../images/check3.png)  |    ![](../../images/check3.png)  |   
| Write passwords to Active Directory  |   ![](../../images/check3.png)  |    ![](../../images/check3.png)   |   ![](../../images/check3.png)  |
| Write passwords to Azure Active Directory  |![](../../images/dash.png)  |    ![](../../images/check3.png)   |![](../../images/dash.png) |
| Write passwords to the AMS server  |  ![](../../images/dash.png)  |  ![](../../images/dash.png)  |   ![](../../images/check3.png)  |

_1. Custom schema is only required if using the agent on domain-joined devices. Schema is not required when using the agent on non-windows or non-domain-joined devices_

_2. Access Manager agent can store unencrypted passwords in the Microsoft LAPS attributes when in compatibility mode (applies to domain-joined Windows devices only)_

_3. Windows LAPS can store passwords in plain text if configured_

## Compatibility with password retrieval solutions

| | Legacy LAPS thick client | Windows LAPS AD property pages | Windows LAPS PowerShell | Azure Portal | Access Manager Service|
| --- | --- | --- | --- | --- | --- |
| Microsoft Legacy LAPS passwords stored in AD | ![](../../images/check3.png)  | ![](../../images/check3.png) | ![](../../images/check3.png)  | ![](../../images/dash.png) | ![](../../images/check3.png) | 
| Microsoft Windows LAPS passwords stored in AD |![](../../images/dash.png) | ![](../../images/check3.png)| ![](../../images/check3.png)  | ![](../../images/dash.png) |  ![](../../images/check3.png)  |
| Microsoft Windows LAPS passwords stored in Azure AD |![](../../images/dash.png) | ![](../../images/dash.png)  | ![](../../images/check3.png)  | ![](../../images/check3.png)  |  ![](../../images/check3.png)  |
| Access Manager Agent passwords |   ![](../../images/dash.png)  |  ![](../../images/dash.png)  |![](../../images/dash.png)  |  ![](../../images/dash.png)  |   ![](../../images/check3.png)  |


