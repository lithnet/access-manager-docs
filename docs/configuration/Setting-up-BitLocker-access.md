# Setting up BitLocker access

![!](../images/ui-page-bitlocker.png)

You can access BitLocker recovery passwords using Lithnet Access Manager. No specific configuration is needed, other than delegating permission for the AMS service account to read those passwords from the directory.

From the [BitLocker Page](/help/app-pages/BitLocker-Page), click the `Delegate BitLocker Permissions` button to access a script that will modify the necessary AD permissions to allow the AMS service account to read recovery passwords.

Once directory permissions are granted to the service account, you can assign access to users using [authorization rules](/help/app-pages/Authorization-Page.
