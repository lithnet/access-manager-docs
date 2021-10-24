# Access Manager Editions
Access Manager comes in two editions - Community and Enterprise.

## Community Edition
Access Manager Community edition is our core offering, that contains all the features that an organization need to help defend themselves from lateral movement-based attacks. You can provide your users full access to Microsoft LAPS passwords and request just-in-time admin access to computers all from the convenience of their browser.

Community edition is completely free for any organization of any size to use.

:::{note}
This text is **standard** _Markdown_
:::

:::{admonition} This *is* also **Markdown**
:class: warning

This text is **standard** _Markdown_
:::

## Enterprise Edition
 Enterprise edition customers can deploy the Lithnet Access Manager Agent, which enables LAPS support for devices that aren't joined to your Active Directory domain. The agent runs on Windows, macOS, and Linux, and supports Azure Active Directory joined and registered devices.

Enterprise edition also enables additional functionality, such as support for Microsoft Failover Clusters for high availability, and advanced custom authorization rules.

See the [[licensing]] page for information on how to trial or purchase an Enterprise Edition license.

## **Feature comparison**
---

### Web Interface features
The Access Manager web interface is the main feature of the product that your support staff and end users will be interacting with.


:::{table}
:align: left

| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Access to local admin passwords set by the Microsoft LAPS agent | ✔ | ✔ |
| Access to local admin passwords set by the Lithnet Access Manager Agent <sup>1</sup>|  | ✔ |
| Access to BitLocker recovery passwords | ✔ | ✔ |
| Just-in-time access requests for local admin access on computers | ✔ | ✔ |
| 'Read aloud' function for passwords (where supported by the browser) | ✔ | ✔ |
| Phonetic display of passwords | ✔ | ✔ |
| Access to local admin password history <sup>1</sup> |  | ✔ |
| Show the local admin username <sup>1</sup> |  | ✔ |
:::

### Common password management features
These features are support for customers using the Microsoft LAPS agent, as well as the Lithnet Access Manager Agent.
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Trigger LAPS password change when the password has been accessed | ✔ | ✔ |

### Lithnet Access Manager Agent password management features 
Enterprise edition customer benefit from the following capabilities when they deploy the Lithnet Access Manager agent to their devices to manage LAPS passwords.
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Manage local admin passwords and store them in Active Directory (domain-joined Windows clients only) |  | ✔ |
| Manage local admin passwords and store them in AMS |  | ✔ |
| Encrypted storage of passwords |  | ✔ |
| Retain historical local admin password history |  | ✔ |
| Support for domain-joined windows devices | | ✔ |
| Support for non-domain joined Windows above clients | | ✔ |
| Support for macOS devices (Intel and M1) |  | ✔ |
| Support for Azure AD joined Windows 10 and higher devices |  | ✔ |
| Support for Azure AD registered Windows 10 and higher devices |  | ✔ |
| Support for linux distributions (x64 and arm64) <sup>2</sup> | | ✔ |

### Just-in-time access features
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Just-in-time administrative access to Windows computers | ✔ | ✔ |

### BitLocker features
:::{table}
:align: left
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Read BitLocker recovery passwords from AD | ✔ | ✔ |
:::

### Authentication features
Access Manager supports many different authentication mechanisms. Use a modern authentication provider like Azure AD or Okta to add MFA support to your Access Manager instance.
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Support for Integrated Windows Authentication | ✔ | ✔ |
| Support for OpenID Connect | ✔ | ✔ |
| Support for WS-Federation | ✔ | ✔ | 
| Support for smart-card authentication | ✔ | ✔ |

### Auditing and analytics features
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Log events to the Windows event log | ✔ | ✔ |
| Send audit notifications via webhooks | ✔ | ✔ |
| Send audit notifications via email | ✔ | ✔ | 
| Send audit notifications via custom PowerShell scripts | ✔ | ✔ | 

### Infrastructure 
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Multi-domain support | ✔ | ✔ |
| Cross-forest trust support | ✔ | ✔ |
| Single-server deployments | ✔ | ✔ |
| Windows Failover Cluster deployments |  | ✔ |
| Database support | SQL Express  | SQL Express<br>SQL Server Standard or Enterprise | 

### Authorization features
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| ACL-based authorization | ✔ | ✔ |
| Custom PowerShell script-based authorization | | ✔ |
| Global rate-limiting on requests | ✔ | ✔ |
| Import Microsoft LAPS permissions from Active Directory | ✔ | ✔ |
| Import BitLocker recovery password permissions from Active Directory | ✔ | ✔ |
| Import local admin permissions from computers | ✔ | ✔ | 
| Import permissions from CSV file | ✔ | ✔ |
| Import LAPS permissions from the Lithnet LAPS Web App | ✔ | ✔ |

### Support
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Community support via GitHub | ✔ |  |
| Enterprise support by Lithnet |  | ✔ |

1. Requires the use of the Lithnet Access Manager Agent
2. See the page on [[linux support]] for more details