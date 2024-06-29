# Access Manager Editions

## Community Edition

Access Manager Community edition is our core offering, that contains all the features that an organization need to help defend themselves from lateral movement-based attacks. You can provide your users full access to Microsoft LAPS passwords and request just-in-time admin access to computers all from the convenience of their browser.

Community edition is completely free for any organization of any size to use.

## Enterprise Edition

Enterprise edition customers can deploy the Lithnet Access Manager Agent, which enables LAPS support for devices that aren't joined to your Active Directory domain. The agent runs on Windows, macOS, and Linux, and supports Azure Active Directory joined and registered devices.

Enterprise edition also enables additional functionality, such as support for high availability, and advanced custom authorization rules.

See the [licensing](licensing.md) page for information on how to trial or purchase an Enterprise Edition license.

## Feature comparison

### Web Interface features

The Access Manager web interface is the main feature of the product that your support staff and end users will be interacting with.

| Feature |   Community Edition   |   Enterprise Edition  |
| ------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Access to local admin passwords set by the legacy Microsoft LAPS agent | ![](/images/check3.png) | ![](/images/check3.png) |
| Access to local admin passwords set by the new Microsoft Windows LAPS agent  | ![](/images/check3.png) | ![](/images/check3.png) |
| Access to local admin passwords set by the Lithnet Access Manager Agent <sup>1</sup>  | ![](/images/check3.png) | ![](/images/check3.png) |
| Access to BitLocker recovery passwords   | ![](/images/check3.png) | ![](/images/check3.png) |
| Just-in-time administrative access to Windows computers | ![](/images/check3.png) | ![](/images/check3.png) |
| Just-in-time access to custom roles   | Limited to 3 roles | ![](/images/check3.png) |
| 'Read aloud' function for passwords (where supported by the browser)   | ![](/images/check3.png) | ![](/images/check3.png) |
| Phonetic display of passwords   | ![](/images/check3.png) | ![](/images/check3.png) |
| Access to local admin password history <sup>3</sup> | ![](/images/dash.png) | ![](/images/check3.png) |
| Show the local admin username <sup>3</sup> | ![](/images/dash.png) | ![](/images/check3.png) |
| Trigger LAPS password change when the password has been accessed <sup>4 | ![](/images/check3.png) | ![](/images/check3.png) |

Learn more about [the differences between the Microsoft and Lithnet LAPS Agents](installation/installing-the-access-manager-agent/choosing-between-the-microsoft-and-lithnet-laps-agents.md).

### Lithnet Access Manager Agent password management features

Enterprise edition customers benefit from the following capabilities when they deploy the Lithnet Access Manager agent to their devices to manage LAPS passwords.

| Feature |   Community Edition   |   Enterprise Edition  |
| ---------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Manage local admin passwords of domain-joined devices and store them in Active Directory (domain-joined Windows clients only) | ![](/images/check3.png) | ![](/images/check3.png) |
| Manage local admin passwords of non domain-joined devices and store them in the Access Manager database   | Limited to 100 devices   | ![](/images/check3.png) |
| Encrypted storage of passwords  | ![](/images/dash.png)  | ![](/images/check3.png) |
| Retain historical local admin password history | ![](/images/dash.png)  |  ![](/images/check3.png) |
| Support for domain-joined Windows devices   |![](/images/check3.png) | ![](/images/check3.png) |
| Support for non-domain joined Windows clients  | Limited to 100 devices   | ![](/images/check3.png) |
| Support for macOS devices (Intel and arm64) | Limited to 100 devices   | ![](/images/check3.png) |
| Support for Microsoft Entra-joined Windows 10 and higher devices  | Limited to 100 devices   | ![](/images/check3.png) |
| Support for Linux distributions (x64, arm64, arm32) <sup>2</sup> | Limited to 100 devices   | ![](/images/check3.png) |

### Just-in-time access features

| Feature |   Community Edition   |   Enterprise Edition  |
| ------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Just-in-time administrative access to Windows computers | ![](/images/check3.png) |![](/images/check3.png) |
| Just-in-time access to Active Directory role-based groups   | Limited to 3 roles | ![](/images/check3.png) |

### BitLocker features

| Feature  |   Community Edition   |   Enterprise Edition  |
| ----------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Read BitLocker recovery passwords from AD | ![](/images/check3.png) | ![](/images/check3.png) |

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

### Infrastructure

| Feature   |   Community Edition   |   Enterprise Edition  |
| ------------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Multi-domain support  | ![](/images/check3.png) | ![](/images/check3.png) |
| Cross-forest trust support  | ![](/images/check3.png) | ![](/images/check3.png) |
| Single-server deployments   | ![](/images/check3.png) | ![](/images/check3.png) |
| Windows Failover cluster deployments | ![](/images/dash.png) | ![](/images/check3.png) |
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
| Import LAPS permissions from the Lithnet LAPS Web App | ![](/images/check3.png) | ![](/images/check3.png) |

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
| Community support via GitHub  | ![](/images/check3.png) |  ![](/images/dash.png)  |
| Enterprise support by Lithnet |  ![](images/dash.png)  | ![](/images/check3.png) |

1. Requires the use of the Lithnet Access Manager Agent
2. See the page on [supported Linux operating systems](installation/system-requirements.md) for more details
3. Requires the use of the Lithnet Access Manager Agent or the Microsoft Windows LAPS client
4. Not supported when using the Microsoft Windows LAPS client and storing the password in Microsoft Entra
