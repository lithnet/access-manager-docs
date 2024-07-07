# Setting up access to BitLocker recovery keys
The Access Manager service allows you to retrieve BitLocker recovery keys through the same friendly web interface used to access LAPS passwords.

AMS can retrieve passwords that are stored natively in Active Directory by Windows.
Unfortunately, Microsoft does not allow a way for Access Manager to retrieve BitLocker recovery passwords stored in Entra ID.

However, you can deploy the Access Manager Agent to *any* Windows device, and use it to backup the BitLocker recovery keys to the Access Manager server itself.

* [Setup access to BitLocker recovery passwords stored in Active Directory](setting-up-bitlocker-ad.md)
* [Setup BitLocker recovery key backup and access using the Access Manager Agent](setting-up-bitlocker-ams.md)