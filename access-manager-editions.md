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
| Access to plain-text local admin passwords set by the legacy Microsoft LAPS agent ('AdmPwd' attributes)  | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Access to plain-text local admin passwords set by the new Microsoft LAPS agent ('msLAPS' attributes)  | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Access to encrypted local admin passwords set by the new Microsoft LAPS agent ('msLAPS' attributes)  | ![](/images/dash.png) | <img src="/images/green_circle_tick.png" data-size="line"> |
| Access to encrypted local admin passwords set by the Lithnet Access Manager Agent <sup>1</sup>  | ![](/images/dash.png)  | <img src="/images/green_circle_tick.png" data-size="line"> |
| Access to BitLocker recovery passwords   | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Just-in-time administrative access to Windows computers | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Just-in-time access to custom roles   | ![](/images/dash.png) | <img src="/images/green_circle_tick.png" data-size="line"> |
| 'Read aloud' function for passwords (where supported by the browser)   | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Phonetic display of passwords   | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Access to local admin password history <sup>1</sup> | ![](/images/dash.png) | <img src="/images/green_circle_tick.png" data-size="line"> |
| Show the local admin username <sup>1</sup> | ![](/images/dash.png) | <img src="/images/green_circle_tick.png" data-size="line"> |
| Trigger LAPS password change when the password has been accessed | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |

Learn more about [the differences between the Microsoft and Lithnet LAPS Agents](installation/installing-the-access-manager-agent/choosing-between-the-microsoft-and-lithnet-laps-agents.md).

### Lithnet Access Manager Agent password management features

Enterprise edition customers benefit from the following capabilities when they deploy the Lithnet Access Manager agent to their devices to manage LAPS passwords.

| Feature |   Community Edition   |   Enterprise Edition  |
| ---------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Manage local admin passwords of domain-joined devices and store them in Active Directory (domain-joined Windows clients only) | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Manage local admin passwords of non domain-joined devices and store them in the Access Manager database   | Limited to 100 devices   | <img src="/images/green_circle_tick.png" data-size="line"> |
| Encrypted storage of passwords  | ![](/images/dash.png)  | <img src="/images/green_circle_tick.png" data-size="line"> |
| Retain historical local admin password history | ![](/images/dash.png)  | <img src="/images/green_circle_tick.png" data-size="line"> |
| Support for domain-joined Windows devices   | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Support for non-domain joined Windows clients  | Limited to 100 devices   | <img src="/images/green_circle_tick.png" data-size="line"> |
| Support for macOS devices (Intel and arm64) | Limited to 100 devices   | <img src="/images/green_circle_tick.png" data-size="line"> |
| Support for Azure AD joined Windows 10 and higher devices  | Limited to 100 devices   | <img src="/images/green_circle_tick.png" data-size="line"> |
| Support for Azure AD registered Windows 10 and higher devices | Limited to 100 devices   | <img src="/images/green_circle_tick.png" data-size="line"> |
| Support for Linux distributions (x64, arm64, arm32) <sup>2</sup> | Limited to 100 devices   | <img src="/images/green_circle_tick.png" data-size="line"> |

### Just-in-time access features

| Feature |   Community Edition   |   Enterprise Edition  |
| ------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Just-in-time administrative access to Windows computers | <img src="/images/green_circle_tick.png" data-size="line"> |<img src="/images/green_circle_tick.png" data-size="line"> |
| Just-in-time access to Active Directory role-based groups   | Limited to 3 roles | <img src="/images/green_circle_tick.png" data-size="line"> |

### BitLocker features

| Feature  |   Community Edition   |   Enterprise Edition  |
| ----------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Read BitLocker recovery passwords from AD | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |

### Authentication features

Access Manager supports several authentication mechanisms. You can use a modern authentication provider like Azure AD or Okta to add MFA support to your Access Manager instance.

| Feature   |   Community Edition   |   Enterprise Edition  |
| --------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Support for Integrated Windows Authentication | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Support for OpenID Connect  | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Support for WS-Federation   | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Support for smart-card authentication   | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |

### Auditing features

| Feature   |   Community Edition   |   Enterprise Edition  |
| ------------------------------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Log events to the Windows event log  | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Send audit notifications via webhooks   | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Send audit notifications via email   | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Send audit notifications via custom PowerShell scripts | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |

### Infrastructure

| Feature   |   Community Edition   |   Enterprise Edition  |
| ------------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Multi-domain support  | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Cross-forest trust support  | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Single-server deployments   | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Windows Failover cluster deployments | ![](/images/dash.png) | <img src="/images/green_circle_tick.png" data-size="line"> |
| Load-balanced deployments   | ![](/images/dash.png) | <img src="/images/green_circle_tick.png" data-size="line"> |

### Authorization features

| Feature  |   Community Edition   |   Enterprise Edition  |
| -------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| ACL-based authorization | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Custom PowerShell script-based authorization | ![](/images/dash.png) | <img src="/images/green_circle_tick.png" data-size="line"> |
| Global rate-limiting on requests | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Import Microsoft LAPS permissions from Active Directory  | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Import BitLocker recovery password permissions from Active Directory | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Import local admin permissions from computers   | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Import permissions from CSV file | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Import LAPS permissions from the Lithnet LAPS Web App | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |

### Configuration management features

| Feature  |   Community Edition   |   Enterprise Edition  |
| -------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Manage AMS groups from the UI | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Manage AMS groups from PowerShell | ![](/images/dash.png) | <img src="/images/green_circle_tick.png" data-size="line"> |
| Manage AMS devices from the UI | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Manage AMS devices from PowerShell | ![](/images/dash.png) | <img src="/images/green_circle_tick.png" data-size="line"> |
| Manage AMS registration keys from the UI | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Manage AMS registration keys from PowerShell | ![](/images/dash.png) | <img src="/images/green_circle_tick.png" data-size="line"> |
| Create and modify authorization rules using the UI | <img src="/images/green_circle_tick.png" data-size="line"> | <img src="/images/green_circle_tick.png" data-size="line"> |
| Create and modify authorization rules using PowerShell | ![](/images/dash.png) | <img src="/images/green_circle_tick.png" data-size="line"> |

### Support

| Feature  |   Community Edition   |   Enterprise Edition  |
| ----------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Community support via GitHub  | <img src="/images/green_circle_tick.png" data-size="line"> |  ![](/images/dash.png)  |
| Enterprise support by Lithnet |  ![](images/dash.png)  | <img src="/images/green_circle_tick.png" data-size="line"> |

1. Requires the use of the Lithnet Access Manager Agent
2. See the page on [supported Linux operating systems](installation/system-requirements.md) for more details
