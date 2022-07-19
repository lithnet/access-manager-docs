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

If you plan on providing access to local admin passwords with Access Manager, you'll need to deploy either the Microsoft LAPS agent, or the Lithnet Access Manager agent, to your devices, in order to rotate and store the LAPS passwords.

If you simply want to provide access to LAPS passwords already stored in your Active Directory, then you can skip this step.

If you are deploying LAPS in an Active Directory only environment, we recommend deploying Microsoft's LAPS agent.

If you want to support advanced scenarios such as Azure AD joined and registered devices, standalone Windows devices, macOS, or Linux devices, you'll need to deploy the Lithnet Access Manager Agent.

You can read more details in our guide for [choosing between the Microsoft and Lithnet LAPS agents](installing-the-access-manager-agent/choosing-between-the-microsoft-and-lithnet-laps-agents.md).

An agent is not required for the other features of AMS, such as just-in-time administrative access and BitLocker recovery password access.

## Configuring features

Once you've installed AMS, you use the following guides to configure specific features as needed.

* [Setting up Microsoft LAPS](../configuration/deploying-features/setting-up-microsoft-laps.md)
* [Setting up Lithnet LAPS](../configuration/deploying-features/setting-up-lithnet-laps/)
* [Setting up JIT access for computers](../configuration/deploying-features/setting-up-jit-access.md)
* [Setting up BitLocker access](../configuration/deploying-features/setting-up-bitlocker-access.md)
* [Setting up JIT access for roles](../configuration/deploying-features/setting-up-jit-for-roles.md)