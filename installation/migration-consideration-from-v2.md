# Migration considerations for migrating from Access Manager v2 to v3

Upgrading your environment from version 2 to version 3 of Access Manager requires some careful planning as things have changed.

## Access Manager Server

### Enterprise edition license key update required
If you are an Access Manager *enterprise edition* customer, you will require a new license key to support AMSv3.

Existing *enterprise edition* customers should contact [Lithnet support](https://lithnet.io/support) to obtain an AMSv3 license prior to upgrading if they have no already done so.

### Community edition no longer allows web app customization
Access Manager v2 allowed *community edition* users to customize some elements of the web app such as branding and custom logo use.

In Access Manager v3, customization of the web app is now an *enterprise edition* feature.

Community edition users upgrading from v2 to v3 will revert to the default settings of the web app.

### Audit template updates
In order to support accurate logging of audit events in line with new features such as RapidLAPS, the event log template has been replaced with a new version. If you have customized the event log template, you'll need to reapply your customizations after the upgrade. The old event log template will be backed up to the Access Manager app path under the `migration-backups` folder.

Updated versions of the slack, teams, and email templates are provided for use in the `templates` folder of the application install directory. These are not applied by default.

### Agent policies
Agent policies from Access Manager v2 will be imported as "Legacy agent v2 policies". They will continue to work as they do today. 

However, before deploying v3 agents, you'll need to create v3 agent policies, as the legacy v2 agent policies are not used by the new agent. 

This will allow you to leverage new features such as RapidLAPS, passphrases, and BitLocker recovery key backup.

Policies are now set per operating system type, as each operating system has different feature sets available to it.

See the guides for [configuring Lithnet LAPS](../configuration/deploying-features/laps/setting-up-lithnet-laps.md) to set up new password policies that are compatible with V3 agents.

You can also set up new features that the v3 agent unlocks by following the [configuring RapidLAPS](../configuration/deploying-features/rapidlaps/setting-up-rapid-laps.md), and [configuring BitLocker backup](../configuration/deploying-features/fve-backup/setting-up-bitlocker-ams.md) guides.

### SPN migration required when using Windows authentication for users
When user authentication was configured to use integrated windows authentication, Access Manager v2 employed the use of kernel-mode authentication. This required that the SPN for the web site be registered against the AMS computer object.

In AMSv3, the Access Manager service uses user-mode authentication, and as such, the SPN must be moved to the AMS service account. The [migration guide](upgrading-from-v2.md) provides the steps required to do this.

## Access Manager Agent

{% hint style="warning" %}
#### Upgrade the AMS server before upgrading the AMS agents
The v3 agent can only communicate with a v3 server. Ensure that you upgrade the server to v3, before upgrading the agents to v3.

The v3 server can host both v2 and v3 agents.
{% endhint %}

### Access Manager Agent no longer supports writing passwords to the Active Directory custom schema
When a v2 agent is installed on a host that was joined to an Active Directory domain, it writes LAPS passwords to a set of custom schema attributes in Active Directory. The v3 agent no longer writes to these Active Directory attributes, and instead, stores its password directly in the AMS server.

When upgrading these agents to v3, you must now specify the server name as part of the installation.

For more information, read the guide on [installing the Access Manager agent on Windows](installing-the-access-manager-agent/installing-the-access-manager-agent-windows.md)

### Group policy is no longer used to configure password management of Windows-based agents
The password policy settings configured for the v2 agent via group policy are no longer used by the v3 agent. The v3 agent uses policies configured on the AMS server.

See the guides for [configuring Lithnet LAPS](../configuration/deploying-features/laps/setting-up-lithnet-laps.md) to set up new password policies that are compatible with V3 agents.

### The package name for the Linux agent has changed

The Access Manager agent package has been renamed from `LithnetAccessManagerAgent` to `LithnetAccessManagerAgent3` to prevent auto updates to v3 before the server has been upgraded to v3.

The `LithnetAccessManagerAgent3` supersedes the previous agent, and migrates the config, so the upgrade process should be seamless.

Please read the [Linux installation guide](installing-the-access-manager-agent/installing-the-access-manager-agent-linux.md) guide for full details.

### ARM32 packages are no longer available
Due to an incompatibility with [.NET 8 and ARM32](https://github.com/dotnet/core/discussions/9285), Lithnet is currently unable to provide an ARM32 agent for Access Manager v3. You can continue to use the v2 agent on these devices, and upgrade your server to v3. Advanced features, such as passphrases will not be available on these devices, and they will remain managed by legacy AMSv2 policies.