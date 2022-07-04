# Choosing between the Microsoft and Lithnet agents for LAPS support

Managing local admin passwords safely and securely relies on having a mechanism to generate and store the local admin passwords, and a way for trusted users to access them.

Microsoft provides the Microsoft LAPS agent for generating and storing passwords in the directory, and the Microsoft LAPS client for accessing them.

Lithnet Access Manager also has an agent for generating and storing passwords in a directory, and a client for accessing them. The Access Manager Agent (AMA), can be used in place of the Microsoft LAPS agent to generate and store local admin passwords. The Access Manager Service (AMS) is a web-based service for accessing local admin passwords that is fully compatible with passwords set by the Microsoft LAPS agent.

This guide will outline the feature differences between these products, and help you make a decision that is right for your environment.

## Operating system support

The Microsoft LAPS agent works only on Windows AD domain-joined devices. Lithnet Access Manager agent supports a much wider range of operating systems and scenarios.

| Feature                                                      |                       Microsoft LAPS Agent                       |                   Lithnet Access Manager Agent                   |
| ------------------------------------------------------------ | :--------------------------------------------------------------: | :--------------------------------------------------------------: |
| Write local admin password to Active Directory               | <img src="../../docs/images/check2.png" alt="" data-size="line"> | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Write local admin password to the AMS database               |                  ![](../../docs/images/dash.png)                 | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Support for Windows 8.1 or higher domain-joined devices      | <img src="../../docs/images/check2.png" alt="" data-size="line"> | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Support for Windows 8.1 or higher non-domain-joined devices  |                  ![](../../docs/images/dash.png)                 | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Support for Windows 10 or higher Azure AD-joined devices     |                  ![](../../docs/images/dash.png)                 | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Support for Windows 10 or higher Azure AD-registered devices |                  ![](../../docs/images/dash.png)                 | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Support for Linux                                            |                  ![](../../docs/images/dash.png)                 | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Support for macOS                                            |                  ![](../../docs/images/dash.png)                 | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Encrypt stored local admin passwords                         |                  ![](../../docs/images/dash.png)                 | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Store a history of previous local admin passwords            |                  ![](../../docs/images/dash.png)                 | <img src="../../docs/images/check2.png" alt="" data-size="line"> |

## Accessing local admin passwords

Lithnet Access Manager provides an alternative to the LAPS client by offering web-based access to Microsoft LAPS passwords in a more accessible and secure way. It offers an array of features not present in the native Microsoft offering, and significantly improves the usability and security of accessing LAPS passwords in your environment.

### Feature comparison between the Microsoft LAPS client and the Lithnet Access Manager Service

| Feature                                                                |                       Microsoft LAPS Client                       |                  Lithnet Access Manager Service                  |
| ---------------------------------------------------------------------- | :---------------------------------------------------------------: | :--------------------------------------------------------------: |
| Allows access to Microsoft LAPS plain-text passwords                   |  <img src="../../docs/images/check2.png" alt="" data-size="line"> | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Allows access to Lithnet Access Manager Agent encrypted passwords      |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Supports accessing passwords over cross-forest trusts                  |  <img src="../../docs/images/check2.png" alt="" data-size="line"> | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Static permissions via ACLs                                            |  <img src="../../docs/images/check2.png" alt="" data-size="line"> | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Dynamic permissions via PowerShell scripts                             |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Allows basic audit information to be captured                          | <img src="../../docs/images/check2.png" alt="" data-size="line">1 | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Allows detailed audit information to be captured                       |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Log audit events to Windows event log                                  | <img src="../../docs/images/check2.png" alt="" data-size="line">2 | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Log audit events to a file                                             |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Send audit events via email                                            |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Send audit events via a webhook                                        |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Send audit events via PowerShell                                       |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Web-based access                                                       |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Mobile-device friendly                                                 |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Access from non-Windows devices                                        |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Allows modern authentication and multifactor authentication            |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Per-user and per-IP rate-limiting to prevent password harvesting       |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Restrict directory access to the passwords to a single service account |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Access passwords for non-domain-joined Windows devices                 |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Access passwords for non-Windows devices (macOS, Linux)                |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Access passwords for Azure AD devices                                  |                  ![](../../docs/images/dash.png)                  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |

_1. Enabling auditing of access to Microsoft LAPS passwords requires enabling directory object auditing_

_2. LAPS events can be lost in a sea of other directory-related audit events_

The Access Manager Service is designed to take the pain away from desktop and server admins who have to use feature-limited tools to access these passwords. It also puts control in the hands of LAPS administrators and makes sure they can easily control who has access to the local admin passwords and keeps robust and detailed records of access events. It's the next generation of our trusted and proven [Lithnet LAPS Web App](https://github.com/lithnet/laps-web).

## Generating and storing local admin passwords

Lithnet Access Manager has its own agent you can deploy to computers to manage the admin password. It behaves in much the same way as the Microsoft LAPS agent with a few important differences.

The first difference is that all passwords generated by the Access Manager Agent are encrypted before they are stored. The second is that the Access Manager Agent can be configured to record previous password history as well. This helps in scenarios where a computer is restored from a backup or rolled back from a snapshot.

For devices that are domain-joined, the Access Manager Agent stores them in the AD itself. For non-domain joined devices, the passwords are stored in the AMS directory.

### Feature comparison between the Microsoft LAPS agent and the Lithnet Access Manager Agent

| Feature                                            |                       Microsoft LAPS Agent                       |                    Lithnet Access Manager Agent                   |
| -------------------------------------------------- | :--------------------------------------------------------------: | :---------------------------------------------------------------: |
| Regularly rotates the local admin password         | <img src="../../docs/images/check2.png" alt="" data-size="line"> |  <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Requires a custom AD schema                        | <img src="../../docs/images/check2.png" alt="" data-size="line"> | <img src="../../docs/images/check2.png" alt="" data-size="line">1 |
| Stores a history of previous local admin passwords |                  ![](../../docs/images/dash.png)                 |  <img src="../../docs/images/check2.png" alt="" data-size="line"> |
| Stores passwords in plain-text                     | <img src="../../docs/images/check2.png" alt="" data-size="line"> |                 ![](../../docs/images/dash.png) 2                 |
| Encrypts passwords                                 |                  ![](../../docs/images/dash.png)                 |  <img src="../../docs/images/check2.png" alt="" data-size="line"> |

_1. Custom schema is only required if using the agent on domain-joined devices. Schema is not required when using the agent on non-windows or non-domain-joined devices_

_2. Access Manager agent can store unencrypted passwords in the Microsoft LAPS attributes when in compatibility mode (applies to domain-joined Windows devices only)_

### Compatibility

You can use the Access Manager Service with the Microsoft LAPS agent without having to deploy the Access Manager Agent. However, if you deploy the Access Manager Agent, you'll need to use the Access Manager Service.

|                        |                  Microsoft LAPS Agent Passwords                  |                  Access Manager Agent Passwords                  |
| ---------------------- | :--------------------------------------------------------------: | :--------------------------------------------------------------: |
| Microsoft LAPS Client  | <img src="../../docs/images/check2.png" alt="" data-size="line"> |                  ![](../../docs/images/dash.png)                 |
| Access Manager Service | <img src="../../docs/images/check2.png" alt="" data-size="line"> | <img src="../../docs/images/check2.png" alt="" data-size="line"> |
