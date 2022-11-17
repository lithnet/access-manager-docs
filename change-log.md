# Change log

## v2.0.9376 18th November 2022
- [FIX] Fixes an issue where the service incorrectly goes into recovery mode when the November 2022 Windows updates are applied to a DC and the [known issue](https://support.microsoft.com/en-us/topic/kb5021131-how-to-manage-the-kerberos-protocol-changes-related-to-cve-2022-37966-fd837ac3-cdec-4e76-a6ec-86e67501407d#knownissues5021131) regarding RC4 is in play. Not the service will instead just terminate with a message that domain connectivity is not available.

## v2.0.9375 15th November 2022
- [FIX] Fixes an issue where the service installer may fail on a non-english language Windows system
- [FIX] Fixes an issue where the New-AmsComputerAuthorizationRule and Set-AmsComputerAuthorizationRule report an error

## v2.0.9373 10th November 2022
### Access Manager Service
- [SECURITY FIX] Updates the SQL client libraries to resolve [CVE 2022-41064](https://github.com/dotnet/announcements/issues/239)

## v2.0.9371 7th November 2022
- Initial release of v2. Review the [what's new in v2 article](./whats-new.md) to learn about the major changes since Access Manager v1