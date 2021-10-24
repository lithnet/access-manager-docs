# Getting started

## About
Lithnet Access Manager consists of two components.

The first is the Lithnet Access Manager Service (AMS). AMS is a web-based interface where users can request various types of access to computers. It's the core service of Access Manager.

The second component is an optional agent, available to Enterprise Edition customers, the Access Manager Agent (AMA). You can choose between using the Microsoft LAPS agent, or the Lithnet Access Manager Agent to set LAPS passwords. 

This document will guide you through the process for configuring Lithnet Access Manager, and the features you want to use in your environment.

## Installation
You'll need to first install and configure the Access Manager Service application. 

[Installing the Access Manager Service]installation/(Installing-the-Access-Manager-Service)

## Choosing the agent to use
Once you've installed AMS, you need to decide if you need to deploy the Microsoft LAPS agent, or the Lithnet Access Manager agent. Use the following table below to map the capabilities you want to use with the agent you need to deploy.

| Feature | Microsoft LAPS Agent | Lithnet Access Manager Agent |
| --- | --- | --- |
| Write local admin password to Active Directory | ✔ | ✔ |
| Write local admin password to the AMS database | ❌ | ✔ |
| Support for Windows 8.1 or higher domain-joined devices | ✔ | ✔ |
| Support for Windows 8.1 or higher non-domain-joined devices | ❌ | ✔ |
| Support for Windows 10 or higher Azure AD-joined devices | ❌ | ✔ |
| Support for Windows 10 or higher Azure AD-registered devices | ❌ | ✔ |
| Support for Linux | ❌ | ✔ |
| Support for macOS | ❌ | ✔ |
| Encrypt stored local admin passwords | ❌ | ✔ |
| Store a history of previous local admin passwords | ❌ | ✔ |

AMS is fully compatible with Microsoft LAPS. To learn more, read the guide on [Choosing between the Microsoft and Lithnet LAPS agents](Choosing-between-the-Microsoft-and-Lithnet-LAPS-agents.md). 

An agent is not required for the just-in-time and BitLocker features of AMS.

## Configuring features
Once you've installed AMS, you use the following guides to configure specific features as needed.
- [Setting up Microsoft LAPS](/installation/Setting-up-Microsoft-LAPS)
- [Setting up password encryption and history](/installation/Setting-up-password-encryption-and-history)
- [Setting up JIT access](/installation/Setting-up-JIT-access)
- [Setting up BitLocker access](/installation/Setting-up-BitLocker-access)
