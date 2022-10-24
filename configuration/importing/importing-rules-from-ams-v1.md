# Importing rules from Access Manager v1

If you had Access Manager v1 installed, you can migrate your computer authorization rules to v2 using the import wizard.

## Open the import wizard

Using the Lithnet Access Manager Configuration Tool, navigate to the `Authorization rules/Computers` page, and click `Import authorization rules...`

![](../../images/ui-page-authorization-rules-computers.png)

## Select the import type

Select the AMS v1 import type, and click `Next`

![](../../images/ui-page-import-type-v1.png)

## Select the config path

Specify the path to the `config` folder. This folder is usually located at `C:\Program Files\Lithnet\Access Manager Service\config` in your v1 installation, unless you changed the path at install time. You can copy the contents of this folder locally from another server. This folder must contain the `appsettings.json` file, as well the `audit-templates` and `scripts` folders. 

![](../../images/ui-page-import-v1-folder.png)

## Review discovery results

Once the discovery process has completed, you can review the proposed rules before committing them to the authorization store.

![](../../images/ui-page-import-results-v1.png)

### Merge settings

When a new rule is discovered for a target (computer, group or container) that matches the target of an existing rule, Access Manager will just add the new permissions to the existing rule, rather than create a new rule. You can control this behavior with by unselecting the corresponding checkbox.

When merging rules, settings from the _existing rule_ are retained when a conflict is found. For example, if an existing rule is configured to expire LAPS passwords after one hour, and the new rule is configured to expire them after two hours, then the settings from the existing rule are retained. You can alter this behavior by selecting the appropriate checkbox.

### Discovery issues

If any issues are found during the discovery process, a `Discovery issues` section is shown. You can export this list to a CSV file and review the issues before proceeding with the import.

### Discovered rules

The `discovered rules` section shows the proposed rules that Access Manager will create. You can add, edit and delete these rules before finalizing the import. The `effective access` tool can be used to test the proposed rules, and ensure the right users have access to the computers you expect.

### Complete the import

When you have completed your review, and are happy with the proposed rules, click `Import` to merge them into the authorization store.
