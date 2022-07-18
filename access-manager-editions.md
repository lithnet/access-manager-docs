# Access Manager Editions?!?

## Community Edition

Access Manager Community edition is our core offering, that contains all the features that an organization need to help defend themselves from lateral movement-based attacks. You can provide your users full access to Microsoft LAPS passwords and request just-in-time admin access to computers all from the convenience of their browser..

Community edition is completely free for any organization of any size to use.

## Enterprise Edition

Enterprise edition customers can deploy the Lithnet Access Manager Agent, which enables LAPS support for devices that aren't joined to your Active Directory domain. The agent runs on Windows, macOS, and Linux, and supports Azure Active Directory joined and registered devices.

Enterprise edition also enables additional functionality, such as support for Microsoft Failover Clusters for high availability, and advanced custom authorization rules.

See the[ licensing ](licensing.md)page for information on how to trial or purchase an Enterprise Edition license.

## Feature comparison

### Web Interface features

The Access Manager web interface is the main feature of the product that your support staff and end users will be interacting with.

| Feature                                                                   |                        Community Edition                       |                       Enterprise Edition                       |
| ------------------------------------------------------------------------- | :------------------------------------------------------------: | :------------------------------------------------------------: |
| Access to local admin passwords set by the Microsoft LAPS agent           | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Access to local admin passwords set by the Lithnet Access Manager Agent 1 |                  ![](.gitbook/assets/dash.png)                 | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Access to BitLocker recovery passwords                                    | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Just-in-time access requests for local admin access on computers          | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| 'Read aloud' function for passwords (where supported by the browser)      | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Phonetic display of passwords                                             | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Access to local admin password history 1                                  |                  ![](.gitbook/assets/dash.png)                 | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Show the local admin username 1                                           |                  ![](.gitbook/assets/dash.png)                 | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| :::                                                                       |                                                                |                                                                |

Learn more about [the differences between the Microsoft and Lithnet LAPS Agents](installation/installing-the-access-manager-agent/choosing-between-the-microsoft-and-lithnet-laps-agents.md).

### Common password management features

These features are supported for customers using the Microsoft LAPS agent, as well as the Lithnet Access Manager Agent.



| Feature                                                          |                        Community Edition                       |                       Enterprise Edition                       |
| ---------------------------------------------------------------- | :------------------------------------------------------------: | :------------------------------------------------------------: |
| Trigger LAPS password change when the password has been accessed | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| :::                                                              |                                                                |                                                                |

### Lithnet Access Manager Agent password management features

Enterprise edition customers benefit from the following capabilities when they deploy the Lithnet Access Manager agent to their devices to manage LAPS passwords.



| Feature                                                                                              |       Community Edition       |                       Enterprise Edition                       |
| ---------------------------------------------------------------------------------------------------- | :---------------------------: | :------------------------------------------------------------: |
| Manage local admin passwords and store them in Active Directory (domain-joined Windows clients only) | ![](.gitbook/assets/dash.png) | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Manage local admin passwords and store them in AMS                                                   | ![](.gitbook/assets/dash.png) | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Encrypted storage of passwords                                                                       | ![](.gitbook/assets/dash.png) | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Retain historical local admin password history                                                       | ![](.gitbook/assets/dash.png) | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Support for domain-joined windows devices                                                            | ![](.gitbook/assets/dash.png) | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Support for non-domain joined Windows above clients                                                  | ![](.gitbook/assets/dash.png) | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Support for macOS devices (Intel and M1)                                                             | ![](.gitbook/assets/dash.png) | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Support for Azure AD joined Windows 10 and higher devices                                            | ![](.gitbook/assets/dash.png) | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Support for Azure AD registered Windows 10 and higher devices                                        | ![](.gitbook/assets/dash.png) | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Support for linux distributions (x64 and arm64) 2                                                    | ![](.gitbook/assets/dash.png) | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| :::                                                                                                  |                               |                                                                |

### Just-in-time access features



| Feature                                                 |                        Community Edition                       |                       Enterprise Edition                       |
| ------------------------------------------------------- | :------------------------------------------------------------: | :------------------------------------------------------------: |
| Just-in-time administrative access to Windows computers | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| :::                                                     |                                                                |                                                                |

### BitLocker features



| Feature                                   |                        Community Edition                       |                       Enterprise Edition                       |
| ----------------------------------------- | :------------------------------------------------------------: | :------------------------------------------------------------: |
| Read BitLocker recovery passwords from AD | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| :::                                       |                                                                |                                                                |

### Authentication features

Access Manager supports several authentication mechanisms. You can use a modern authentication provider like Azure AD or Okta to add MFA support to your Access Manager instance.



| Feature                                       |                        Community Edition                       |                       Enterprise Edition                       |
| --------------------------------------------- | :------------------------------------------------------------: | :------------------------------------------------------------: |
| Support for Integrated Windows Authentication | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Support for OpenID Connect                    | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Support for WS-Federation                     | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Support for smart-card authentication         | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| :::                                           |                                                                |                                                                |

### Auditing and analytics features



| Feature                                                |                        Community Edition                       |                       Enterprise Edition                       |
| ------------------------------------------------------ | :------------------------------------------------------------: | :------------------------------------------------------------: |
| Log events to the Windows event log                    | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Send audit notifications via webhooks                  | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Send audit notifications via email                     | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Send audit notifications via custom PowerShell scripts | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| :::                                                    |                                                                |                                                                |

### Infrastructure



| Feature                              |                        Community Edition                       |                       Enterprise Edition                       |
| ------------------------------------ | :------------------------------------------------------------: | :------------------------------------------------------------: |
| Multi-domain support                 | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Cross-forest trust support           | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Single-server deployments            | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Windows Failover Cluster deployments |                  ![](.gitbook/assets/dash.png)                 | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Database support                     |                           SQL Express                          |     <p>SQL Express<br>SQL Server Standard or Enterprise</p>    |
| :::                                  |                                                                |                                                                |

### Authorization features



| Feature                                                              |                        Community Edition                       |                       Enterprise Edition                       |
| -------------------------------------------------------------------- | :------------------------------------------------------------: | :------------------------------------------------------------: |
| ACL-based authorization                                              | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Custom PowerShell script-based authorization                         |                                                                | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Global rate-limiting on requests                                     | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Import Microsoft LAPS permissions from Active Directory              | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Import BitLocker recovery password permissions from Active Directory | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Import local admin permissions from computers                        | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Import permissions from CSV file                                     | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| Import LAPS permissions from the Lithnet LAPS Web App                | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |

### Support

| Feature                       |                        Community Edition                       |                       Enterprise Edition                       |
| ----------------------------- | :------------------------------------------------------------: | :------------------------------------------------------------: |
| Community support via GitHub  | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |                  ![](.gitbook/assets/dash.png)                 |
| Enterprise support by Lithnet |                  ![](.gitbook/assets/dash.png)                 | <img src=".gitbook/assets/check2.png" alt="" data-size="line"> |
| :::                           |                                                                |                                                                |

1. Requires the use of the Lithnet Access Manager Agent
2. See the page on [supported Linux operating systems](installation/system-requirements.md) for more details
