# Access Manager Editions

Access Manager comes in two product editions. A free community edition, that provides key protections from lateral movement-based attacks, and enterprise edition, which allows organizations to take full advantage of the security and usability enhancements provided by the Access Manager solution.

## Enterprise Edition

Enterprise edition unlocks the full potential of Access Manager. From fully customizing the user experience, to providing advanced authorization and auditing integrations it's the ultimate solution for organizations who want the best protections against lateral movement, and the best user experiences for support staff.

Enterprise edition customers can deploy the Access Manager agent to their Windows, macOS and Linux devices and move away from difficult to use passwords, to easy to remember passphrases.

On Windows, our RapidLAPS feature means your support staff will never have to touch a LAPS password ever again, and use a PIN or QR-code based login instead.

Enterprise edition also enables additional functionality, such as support for high availability, and advanced custom authorization rules.

See the [licensing](licensing.md) page for information on how to trial or purchase an Enterprise Edition license.

## Community Edition

Access Manager Community edition is our core offering, that contains the key features that an organization need to help defend themselves from lateral movement-based attacks. You can provide your users full access to Microsoft LAPS passwords and request just-in-time admin access to computers, all from the convenience of their browser.

Community edition allows the deployment of the Access Manager agent to up to 100 devices.

Community edition is completely free for any organization of any size to use, however no formal support is provided by Lithnet.

## Feature comparison

### Web app features

The Access Manager web app is the main feature of the product that your support staff and end users will be interacting with.

| Feature |   Community Edition   |   Enterprise Edition  |
| ------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Access to local admin passwords set by the legacy Microsoft LAPS agent | ![](/images/check3.png) | ![](/images/check3.png) |
| Access to local admin passwords set by the new Microsoft Windows LAPS agent  | ![](/images/check3.png) | ![](/images/check3.png) |
| Access to local admin passwords and passphrases set by the Lithnet Access Manager Agent | ![](/images/check3.png) | ![](/images/check3.png) |
| Access to BitLocker recovery passwords   | ![](/images/check3.png) | ![](/images/check3.png) |
| Just-in-time administrative access to Windows computers | ![](/images/check3.png) | ![](/images/check3.png) |
| Just-in-time access to custom roles   | Limited to 3 roles | ![](/images/check3.png) |
|Review and approve RapidLAPS login and elevation requests   | ![](/images/check3.png) | ![](/images/check3.png) |
| 'Read aloud' function for passwords (where supported by the browser)   | ![](/images/check3.png) | ![](/images/check3.png) |
| Phonetic display of passwords   | ![](/images/check3.png) | ![](/images/check3.png) |
| Access to local admin password history <sup>3</sup> | ![](/images/dash.png) | ![](/images/check3.png) |
| Show the local admin username <sup>3</sup> | ![](/images/dash.png) | ![](/images/check3.png) |
| Trigger LAPS password change when the password has been accessed <sup>4 | ![](/images/check3.png) | ![](/images/check3.png) |
| Customize and brand the web app user interface | ![](/images/dash.png) | ![](/images/check3.png) |


### Lithnet Access Manager Agent features

Access Manager comes with its own agent which enables RapidLAPS, support for passphrase-based LAPS passwords, and BitLocker recovery key backup.

Community edition customers can deploy up to 100 agents in their environment. 

| Feature |   Community Edition   |   Enterprise Edition  |
| ---------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Manage local admin passwords | Limited to 100 devices  | ![](/images/check3.png) |
| Generate passphrases for LAPS passwords | Limited to 100 devices  | ![](/images/check3.png) |
| Retain historical local admin password history | ![](/images/dash.png)  |  ![](/images/check3.png) |
| Backup BitLocker recovery keys <sup>5</sup> | Limited to 100 devices  | ![](/images/check3.png) |
|  Passwordless login via RapidLAPS <sup>5</sup> | Limited to 100 devices  | ![](/images/check3.png) |
|  Passwordless elevation via RapidLAPS <sup>5</sup> | Limited to 100 devices  | ![](/images/check3.png) |
| Support for domain-joined Windows devices   | Limited to 100 devices  | ![](/images/check3.png) |
| Support for non-domain joined Windows clients  | Limited to 100 devices   | ![](/images/check3.png) |
| Support for macOS devices (Intel and arm64) | Limited to 100 devices   | ![](/images/check3.png) |
| Support for Microsoft Entra-joined Windows 10 and higher devices  | Limited to 100 devices   | ![](/images/check3.png) |
| Support for Linux distributions (x64, arm64) <sup>2</sup> | Limited to 100 devices   | ![](/images/check3.png) |

### Just-in-time access features

| Feature |   Community Edition   |   Enterprise Edition  |
| ------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Just-in-time administrative access to Windows computers | ![](/images/check3.png) |![](/images/check3.png) |
| Just-in-time access to Active Directory role-based groups   | Limited to 3 roles | ![](/images/check3.png) |

### BitLocker features

| Feature  |   Community Edition   |   Enterprise Edition  |
| ----------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Read BitLocker recovery passwords from AD | ![](/images/check3.png) | ![](/images/check3.png) |
| Read BitLocker recovery passwords from non-AD joined devices <sup>1</sup>| Limited to 100 devices | ![](/images/check3.png) |

### Authentication features

Access Manager supports several authentication mechanisms. You can use a modern authentication provider like Microsoft Entra ID or Okta to add MFA support to your Access Manager instance.

| Feature   |   Community Edition   |   Enterprise Edition  |
| --------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Support for Integrated Windows Authentication | ![](/images/check3.png) | ![](/images/check3.png) |
| Support for OpenID Connect  | ![](/images/check3.png) | ![](/images/check3.png) |
| Support for WS-Federation   | ![](/images/check3.png) | ![](/images/check3.png) |
| Support for smart-card authentication   | ![](/images/check3.png) | ![](/images/check3.png) |

### Auditing features

| Feature   |   Community Edition   |   Enterprise Edition  |
| ------------------------------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Log events to the Windows event log  | ![](/images/check3.png) | ![](/images/check3.png) |
| Send audit notifications via webhooks   | ![](/images/check3.png) | ![](/images/check3.png) |
| Send audit notifications via email   | ![](/images/check3.png) | ![](/images/check3.png) |
| Send audit notifications via custom PowerShell scripts | ![](/images/check3.png) | ![](/images/check3.png) |
| Send audit notifications to Splunk HEC | ![](/images/dash.png) | ![](/images/check3.png) |

### Infrastructure

| Feature   |   Community Edition   |   Enterprise Edition  |
| ------------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Multi-domain support  | ![](/images/check3.png) | ![](/images/check3.png) |
| Cross-forest trust support  | ![](/images/check3.png) | ![](/images/check3.png) |
| Single-server deployments   | ![](/images/check3.png) | ![](/images/check3.png) |
| Load-balanced deployments   | ![](/images/dash.png) | ![](/images/check3.png) |

### Authorization features

| Feature  |   Community Edition   |   Enterprise Edition  |
| -------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| ACL-based authorization | ![](/images/check3.png) | ![](/images/check3.png) |
| Custom PowerShell script-based authorization | ![](/images/dash.png) | ![](/images/check3.png) |
| Global rate-limiting on requests | ![](/images/check3.png) | ![](/images/check3.png) |
| Import Microsoft LAPS permissions from Active Directory  | ![](/images/check3.png) | ![](/images/check3.png) |
| Import BitLocker recovery password permissions from Active Directory | ![](/images/check3.png) | ![](/images/check3.png) |
| Import local admin permissions from computers   | ![](/images/check3.png) | ![](/images/check3.png) |
| Import permissions from CSV file | ![](/images/check3.png) | ![](/images/check3.png) |

### Configuration management features

| Feature  |   Community Edition   |   Enterprise Edition  |
| -------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Manage AMS groups from the UI | ![](/images/check3.png) | ![](/images/check3.png) |
| Manage AMS groups from PowerShell | ![](/images/dash.png) | ![](/images/check3.png) |
| Manage AMS devices from the UI | ![](/images/check3.png) | ![](/images/check3.png) |
| Manage AMS devices from PowerShell | ![](/images/dash.png) | ![](/images/check3.png) |
| Manage AMS registration keys from the UI | ![](/images/check3.png) | ![](/images/check3.png) |
| Manage AMS registration keys from PowerShell | ![](/images/dash.png) | ![](/images/check3.png) |
| Create and modify authorization rules using the UI | ![](/images/check3.png) | ![](/images/check3.png) |
| Create and modify authorization rules using PowerShell | ![](/images/dash.png) | ![](/images/check3.png) |

### Support

| Feature  |   Community Edition   |   Enterprise Edition  |
| ----------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Enterprise support by Lithnet |  ![](images/dash.png)  | ![](/images/check3.png) |

1. Requires the use of the Lithnet Access Manager Agent
2. See the page on [supported Linux operating systems](installation/system-requirements.md) for more details
3. Requires the use of the Lithnet Access Manager Agent or the Microsoft Windows LAPS client
4. Not supported when using the Microsoft Windows LAPS client and storing the password in Microsoft Entra
5. Current supported on Windows devices only