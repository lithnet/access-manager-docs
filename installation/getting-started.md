# Getting started

## About

Lithnet Access Manager consists of two components.

The first is the Lithnet Access Manager Service (AMS). AMS is a web-based interface where users can request various types of access to computers. It's the core service of Access Manager.

The second component is an optional agent, the Access Manager Agent (AMA). You can choose between using the Microsoft LAPS agent, or the Lithnet Access Manager Agent to set LAPS passwords.

This document will guide you through the process for configuring Lithnet Access Manager, and the features you want to use in your environment.

## Installation

You'll need to first install and configure the Access Manager Service application.

[Installing the Access Manager Service](installing-the-access-manager-server/installing-the-access-manager-service.md)

## Choosing the LAPS agent to use

If you plan on providing access to local admin passwords with Access Manager, you'll need to deploy and configure either the Microsoft LAPS agent, or the Lithnet Access Manager agent, to your devices, in order to rotate and store the LAPS passwords.

If you simply want to provide access to LAPS passwords already stored in your Active Directory or Azure Active Directory, then you can skip this step.

You can read more details in our guide for [choosing between the Microsoft and Lithnet LAPS agents](installing-the-access-manager-agent/choosing-between-the-microsoft-and-lithnet-laps-agents.md).

An agent is not required for the other features of AMS, such as just-in-time administrative access and BitLocker recovery password access.

## Configuring features

Once you've installed AMS, you use the following guides to configure specific features as needed.

* [Setting up Microsoft LAPS for Active Directory](../configuration/deploying-features/setting-up-microsoft-laps.md)
* [Setting up Microsoft LAPS for Azure Active Directory](../configuration/deploying-features/setting-up-microsoft-laps-for-aad.md)
* [Setting up Lithnet LAPS](../configuration/deploying-features/setting-up-lithnet-laps/)
* [Setting up JIT access for computers](../configuration/deploying-features/setting-up-jit-access.md)
* [Setting up BitLocker access](../configuration/deploying-features/setting-up-bitlocker-access.md)
* [Setting up JIT access for roles](../configuration/deploying-features/setting-up-jit-for-roles.md)