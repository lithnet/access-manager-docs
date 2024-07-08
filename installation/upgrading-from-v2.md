# Upgrading from Access Manager v2 to v3

## Summary

Upgrading your environment from version 2 to version 3 of Access Manager requires some careful planning has things have changed.

We recommend reviewing the [migration considerations](migration-consideration-from-v2.md) document to understand more about the changes introduced.

{% hint style="warning" %}
#### Upgrade the AMS server before upgrading the AMS agents
The v3 agent can only communicate with a v3 server. Ensure that you upgrade the server to v3, before upgrading the agents to v3.

The v3 server can host both v2 and v3 agents.
{% endhint %}

## Upgrading the Access Manager Server

### Before you upgrade
#### Update your license
If you are an enterprise edition customer, ensure you have your v3 license applied before you perform the upgrade. Contact Lithnet support if you do not have this.

The v3 license is compatible with the v2 server so it can be installed in advance.

You do not need the v3 license to perform the upgrade, however, if you proceed without it, the server will be downgraded to community edition after the update.

### Method 1: In-place upgrade
The in-place upgrade process from Access Manager v2 to v3 is very straight forward. You simply install the new version of AMS over the top, and the application will update the database and relevant configuration settings.

As a best practice precaution, you should take a backup of the server and database before performing the upgrade.

### Method 2: Deploying to a new server, using existing configuration

There is no direct path available for exporting configuration from one server, and importing it into another. 

If you want to migrate configuration from a different server, then you should first install AMSv2 on the new server. Then take a backup of the existing server's database, and restore using the procedure documented in the [backup and restore guide](../help-and-support/advanced-help-topics/backup-and-restore.md).

Once your copy of the server is up and running, then you can perform an in-place upgrade to AMSv3.

## Upgrading the Access Manager Agent

Before deploying the v3 Access Manager agent, you'll need to first update the Access Manager server. The v3 agent can only communicate with a v3 server.

### Create new v3 agent policies
V3 agents require new policies to be created.
View the following guides for configuring your policies for the various supported features

* [Setting up Lithnet LAPS](../configuration/deploying-features/laps/setting-up-lithnet-laps.md)
* [Setting up RapidLAPS](../configuration/deploying-features/rapidlaps/setting-up-rapid-laps.md), 
* [Setting up BitLocker backup](../configuration/deploying-features/fve-backup/setting-up-bitlocker-ams.md) guides.

### Deploy Windows agents
The windows agent can be deployed directly over the top of the existing v2 agent as an in-place upgrade. 

For more information, read the guide on [installing the Access Manager agent on Windows](installing-the-access-manager-agent/installing-the-access-manager-agent-windows.md).

#### Active Directory-joined Windows hosts
Active Directory-joined Windows hosts no longer store their passwords in Active Directory. As such, when upgrading these agents to v3, you must now specify the server name as part of the installation. You can use the following command line to install the agent in Active Directory authentication mode, replacing the server name with your own server.

```
msiexec /i Lithnet.AccessManager.Agent.msi /qn AUTHMODE=1 SERVER=ams.lithnet.local 
```

### Deploy macOS agents
There are no special considerations to make when deploying the macOS agent. 

Follow the steps in the [macOs installation guide](installing-the-access-manager-agent/installing-the-access-manager-agent-macos.md) to install the new agent over the top of the old agent.

### Deploy Linux agents
The Access Manager agent package has been renamed from `LithnetAccessManagerAgent` to `LithnetAccessManagerAgent3` to prevent auto updates to v3 before the server has been upgraded to v3.

The `LithnetAccessManagerAgent3` supersedes the previous agent, and migrates the config, so the upgrade process should be seamless.

For RPM-based distributions, make sure you specify the `--allowerasing` flag.

```shell
# Upgrade the agent (from version 2 to version 3)
sudo dnf install LithnetAccessManagerAgent3 --allowerasing
```

For DEB-based distributions, make sure you specify the `--autoremove` argument flag.
```shell
# Upgrade the agent (from version 2 to version 3)
sudo apt install lithnetaccessmanageragent3 --autoremove
```

Please read the [linux installation guide](installing-the-access-manager-agent/installing-the-access-manager-agent-linux.md) guide for full details.
