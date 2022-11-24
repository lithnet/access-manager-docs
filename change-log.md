# Change log

## v1.1.2021 25th November 2022
### New features
- None

### Issues fixed
- Fixes an issue where certificate/smart-card authentication was not working on the Access Manager Service after upgrading from v1.0

## v1.1.1011 17th November 2022
### Access Manager Service
This is an update to Lithnet Access Manager Server to update the .NET runtime from .NET Core 3.1 to .NET 6 in advance of the [EOL date of .NET Core 3.1 on 13th December 2022](https://dotnet.microsoft.com/en-us/platform/support/policy/dotnet-core).

All users should update their Access Manager Server installations to v1.1 before this date in order to ensure they continue to receive security updates for .NET from Microsoft

Note, this only applies to the Access Manager Service. The Access Manager agent is built using .NET Framework 4 which is not EOL.

There are no new features or fixes in this version

## v1.0.7941
This is a minor servicing release of Lithnet Access Manager.

### New features
- Adds information to the event log on which DC was used to perform the JIT group operation
- Adds support for accessing computers with an underscore in their name (#140)

### Issues fixed
- Fixes an issue where a memory leak may occur in the JIT worker service
- Fixes an issue where computers located in an OU containing a forward slash character could not be accessed
- Fixes an issue where expiry dates shown to the user were in the server time zone, rather than the browsers time zone
