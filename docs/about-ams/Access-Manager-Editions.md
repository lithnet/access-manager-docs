# Access Manager Editions
## Community Edition
Access Manager Community edition is our core offering, that contains all the features that an organization need to help defend themselves from lateral movement-based attacks. You can provide your users full access to Microsoft LAPS passwords and request just-in-time admin access to computers all from the convenience of their browser.

Community edition is completely free for any organization of any size to use.

## Enterprise Edition
Enterprise edition customers can deploy the Lithnet Access Manager Agent, which enables LAPS support for devices that aren't joined to your Active Directory domain. The agent runs on Windows, macOS, and Linux, and supports Azure Active Directory joined and registered devices.

Enterprise edition also enables additional functionality, such as support for Microsoft Failover Clusters for high availability, and advanced custom authorization rules.

See the [licensing](about-ams/Licensing) page for information on how to trial or purchase an Enterprise Edition license.

## Feature comparison

### Web Interface features
The Access Manager web interface is the main feature of the product that your support staff and end users will be interacting with.

:::{table}
:align: left
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Access to local admin passwords set by the Microsoft LAPS agent | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Access to local admin passwords set by the Lithnet Access Manager Agent <sup>1</sup>| <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
| Access to BitLocker recovery passwords | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Just-in-time access requests for local admin access on computers | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| 'Read aloud' function for passwords (where supported by the browser) | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Phonetic display of passwords | <img src="../images/check2.png" width=20 /> |<img src="../images/check2.png" width=20 /> |
| Access to local admin password history <sup>1</sup> |  <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
| Show the local admin username <sup>1</sup> |  <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
:::

Learn more about [the differences between the Microsoft and Lithnet LAPS Agents](/installation/Choosing-between-the-Microsoft-and-Lithnet-LAPS-agents).

### Common password management features
These features are supported for customers using the Microsoft LAPS agent, as well as the Lithnet Access Manager Agent.

:::{table}
:align: left
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Trigger LAPS password change when the password has been accessed | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
:::

### Lithnet Access Manager Agent password management features 
Enterprise edition customers benefit from the following capabilities when they deploy the Lithnet Access Manager agent to their devices to manage LAPS passwords.

:::{table}
:align: left
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Manage local admin passwords and store them in Active Directory (domain-joined Windows clients only) |  <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
| Manage local admin passwords and store them in AMS |  <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
| Encrypted storage of passwords |  <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
| Retain historical local admin password history |  <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
| Support for domain-joined windows devices | <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
| Support for non-domain joined Windows above clients | <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
| Support for macOS devices (Intel and M1) |  <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
| Support for Azure AD joined Windows 10 and higher devices |  <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
| Support for Azure AD registered Windows 10 and higher devices |  <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
| Support for linux distributions (x64 and arm64) <sup>2</sup> |  <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
:::

### Just-in-time access features
:::{table}
:align: left
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Just-in-time administrative access to Windows computers |<img src="../images/check2.png" width=20 /> |<img src="../images/check2.png" width=20 /> |
:::

### BitLocker features
:::{table}
:align: left
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Read BitLocker recovery passwords from AD | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
:::

### Authentication features
Access Manager supports several authentication mechanisms. You can use a modern authentication provider like Azure AD or Okta to add MFA support to your Access Manager instance.

:::{table}
:align: left
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Support for Integrated Windows Authentication | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Support for OpenID Connect | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Support for WS-Federation | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> | 
| Support for smart-card authentication | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
:::

### Auditing and analytics features
:::{table}
:align: left
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Log events to the Windows event log | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Send audit notifications via webhooks | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Send audit notifications via email | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> | 
| Send audit notifications via custom PowerShell scripts | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> | 
:::

### Infrastructure 
:::{table}
:align: left
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Multi-domain support | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Cross-forest trust support | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Single-server deployments | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Windows Failover Cluster deployments |  <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
| Database support | SQL Express | SQL Express<br>SQL Server Standard or Enterprise | 
:::

### Authorization features
:::{table}
:align: left
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| ACL-based authorization | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Custom PowerShell script-based authorization | | <img src="../images/check2.png" width=20 /> |
| Global rate-limiting on requests | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Import Microsoft LAPS permissions from Active Directory | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Import BitLocker recovery password permissions from Active Directory | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Import local admin permissions from computers | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> | 
| Import permissions from CSV file | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
| Import LAPS permissions from the Lithnet LAPS Web App | <img src="../images/check2.png" width=20 /> | <img src="../images/check2.png" width=20 /> |
:::

### Support
:::{table}
:align: left
| Feature | Community Edition | Enterprise Edition |
| --- | :---: | :---: |
| Community support via GitHub | <img src="../images/check2.png" width=20 /> |  <img src="../images/dash.png" width=15 /> |
| Enterprise support by Lithnet |  <img src="../images/dash.png" width=15 /> | <img src="../images/check2.png" width=20 /> |
:::

1. Requires the use of the Lithnet Access Manager Agent
2. See the page on [supported Linux operating systems](/installation/System-Requirements#Linux requirements) for more details