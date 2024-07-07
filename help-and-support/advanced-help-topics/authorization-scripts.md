# Script-based authorization

![](../../images/badge-enterprise-edition-rocket.svg) Script-based authorization is an [Enterprise edition feature](../../access-manager-editions.md)

If you'd like to make dynamic authorization decisions, outside the static ACL model, you can utilize a PowerShell script to do this.

Access Manager can call a script that contains a function called `Get-AuthorizationResponse` that takes a user, computer, and logger as input parameters. From there you can make a decision on what the user should be allowed or denied access to, or choose to not make an authorization decision at all.

Access Manager uses the response you provide to create a dynamic ACL for the user, and includes it in the access evaluation of all applicable targets.

## Example script

```PowerShell
function Get-AuthorizationResponse {
	param(
		$User,
		$Computer
	)
	Write-Information  "We're in PowerShell!"
	Write-Information "Checking if $($User.MsDsPrincipalName) is allowed access to $($Computer.MsDsPrincipalName)"

	# Create an object to hold our authorization decisions
	# Set IsAllowed to true to allow access, or set IsDenied to explicitly deny access, or leave both as false if no decision was made. This will allow other rules to be evaluated.
	$Response = [PSCustomObject]@{
		IsLocalAdminPasswordAllowed = $false
		IsLocalAdminPasswordDenied = $false
		IsLocalAdminPasswordHistoryAllowed = $false
		IsLocalAdminPasswordHistoryDenied = $false
		IsJitAllowed = $false
		IsJitDenied = $false
		IsBitLockerAllowed = $false
		IsBitLockerDenied = $false
		IsRapidLapsLoginAllowed = $false
		IsRapidLapsLoginDenied = $false
		IsRapidLapsElevationAllowed = $false
		IsRapidLapsElevationDenied = $false
	}

	# Return the authorization response to Access Manager to process
	Write-Output $Response;
}
```

## Logging information

You can use the Write-Information, Write-Warning, Write-Verbose cmdlets to write to the AMS log file and document your authorization decisions. Note that if you use Write-Error, or if an exception is thrown and not handled, the authorization evaluation for the entire access request will fail.

## Performance

Be aware of performance when writing external authorization scripts. From the user's perspective, they will be waiting in the browser while the access evaluation takes place. If you have a slow script, or lots of scripts, this wait time may seem excessive.

Scripts that take longer than 30 seconds to complete will be terminated by Access Manager, and the user's authorization request will fail.

### `$user` object

The user object has the following properties you can access

| Property Name | Type | Description |
| --- | --- | --- |
| `Description` | string | The value of the description field in active directory, if present |
| `DisplayName` | string | The display name of the user |
| `DistinguishedName` | string | The DN of the user from Active Directory |
| `EmailAddress` | string | The user's email address (e.g. `user@domain.com`) |
| `GivenName` | string | The user's given name |
| `Guid` | Guid | The object GUID from the directory object |
| `MsDsPrincipalName` | string | The NT4-style name of the user (e.g. `DOMAIN\user`) |
| `SamAccountName` | string | The samAccountName of the user (e.g. `user`) |
| `Sid` | string | The Security Identifier of the user (e.g. `S-1-5-x`) |
| `Surname` | string | The user's surname |
| `UserPrincipalName` | string | The user's UPN (e.g. `user@domain.local`) |

### `$computer` object

The computer object has the following properties you can access

| Property Name | Type | Description |
| --- | --- | --- |
| `Description` | string | The value of the description field in active directory, if present |
| `DisplayName` | string | The display name of the computer |
| `DnsHostName` | string | The user's email address (e.g. `user@domain.com`) |
| `AuthorityId` | string | The identifier that represents the authority ID that manages the computer |
| `AuthorityDeviceId` | string | An identifier, specific to the authority type, that uniquely represents the computer object |
| `AuthorityType` | `ActiveDirectory`, `AzureActiveDirectory`, `Ams` | The type of authority that manages the computer |
| `FullyQualifiedName` | string | The fully qualified name of the computer.  (e.g. `DOMAIN\PC1$`) |
| `Name` | string | The name of the computer (e.g. `PC1`) |
| `ObjectId` | string | The computer's unique AMS object ID |

If the computer is an Active Directory-joined computer, then the following additional properties may be available
| Property Name | Type | Description |
| --- | --- | --- |
| `DistinguishedName` | string | The DN of the user from Active Directory |
| `Guid` | Guid | The object GUID from the directory object |
| `MsDsPrincipalName` | string | The NT4-style name of the computer (e.g. `DOMAIN\PC1$`) |
| `SamAccountName` | string | The samAccountName of the computer (e.g. `PC1`) |
| `Sid` | string | The Security Identifier of the computer (e.g. `S-1-5-x`) |

