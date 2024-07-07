# Setup up LAPS

Lithnet Access Manager provides two distinct LAPS capabilities

## Web-based access to LAPS passwords managed by Microsoft LAPS
If you have Microsoft LAPS deployed (either the legacy LAPS or the new Windows LAPS), you can simply user access to those LAPS passwords using the Access Manager Service. AMS allows you to provide a highly secure, mobile friendly, consistent user interface, for accessing LAPS passwords across you organization, no matter what tool you use to manage them.

* [Setting up access to Microsoft LAPS passwords stored in Active Directory](setting-up-microsoft-laps.md)
* [Setting up access to Microsoft LAPS passwords stored in Microsoft Entra ID](setting-up-microsoft-laps-for-aad.md)

## Universal LAPS access and passphrase support with Lithnet LAPS
Access Manager comes with an agent that can manage LAPS passwords in place of the Microsoft agent. Lithnet LAPS gives you the option of using much more friendly passphrases, instead of long and complicated passwords. It also works in places that Microsoft LAPS does not. We have full support for Windows devices that are domain joined, Entra-joined, or even stand alone. We also support managing the root password on macOS and Linux devices.

* [Setting up Lithnet LAPS](setting-up-lithnet-laps.md)

## Go one better than LAPS
However, you can go one better again, and do away with having to touch LAPS passwords in your environment entirely! Check out our RapidLAPS functionality for a fully passwordless LAPS experience.

* [Setting up Lithnet RapidLAPS](../rapidlaps/setting-up-rapid-laps.md)