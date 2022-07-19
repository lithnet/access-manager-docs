# Variables available in audit notification channels
Access Manager provides a comprehensive set of variables you can use in your audit notifications.

See the guides on [PowerShell auditing scripts](audit-scripts.md) and [HTML and JSON audit templates](audit-templates.md) to learn how to use these variables in your audit scripts and templates.

## Global properties
| Property | Format/Type | Description |
| --- | --- | ----- |
| `DateTime` | string | The current date and time, in local server time |
| `DateTimeUtc` | string | The current date and time, in UTC time |

## Request element
This group of attributes represents the incoming request

| Property | Format/Type | Description |
| --- | --- | ----- |
| `Request.Target` | string | The name of the target that the user requested access to |
| `Request.TargetType` | `Computer` or `Role` | The type of resource the user requested access to |
| `Request.Reason` | string | The reason that the user provided when requesting access |
| `Request.IPAddress` | IPv4 or IPv6 address string | The IP address of requestor |
| `Request.HostName` | string | The host name of the requestor, if available via reverse DNS lookup |
| `Request.RequestedDuration` | TimeSpan | The requested duration of access |

## Response element
This group of attributes represents the result of the access evaluation

| Property | Format/Type | Description |
| --- | --- | ----- |
| `Response.Target` | string | The name of the target that the access request was evaluated against |
| `Response.TargetType` | `Computer` or `Role` | The type of resource that was evaluated |
| `Response.IsSuccess` | `true` or `false` | Indicates if access was granted to the resource |
| `Response.IsFailure` | `true` or `false` | Indicates if access was denied to the resource |
| `Response.NotificationChannels` | string | A comma-separated list of audit channels IDs that apply to this access response |
| `Response.MatchedRule` | string | The ID of the authorization rule that was used to make the access decision |
| `Response.MatchedRuleDescription` | string | The 'description' field from the authorization rule that was used to make the access decision |
| `Response.ExpireAfter` | TimeSpan | The duration of time that access was granted for | 
| `Response.Code` | `Success`, `NoMatchingRuleForTarget`, `NoMatchingRuleForUser`, `ExplicitlyDenied`, `UserRateLimitExceeded`, `IpRateLimitExceeded` | The result of the authorization decision. Codes other than `Success` represent an 'access denied' response. | 
| `Response.AccessType` | `None`, `LocalAdminPassword`, `LocalAdminPasswordHistory`, `Jit`, `Bitlocker` | The type of access that was granted |
| `Response.AccessTypeDescription` | string | The friendly name of the type of access that was granted |
| `Response.AccessExpiryDate` | DateTime | The date and time when the user's access will expire, expressed in local server time |
| `Response.Message` | string | A user-friendly message describing the outcome of the access decision |

## User element
This group of attributes represents the user who performed the access request

| Property | Format/Type | Description |
| --- | --- | ----- |
| `User.Username` | string | The `samAccountName` of the user requesting access |
| `User.FullyQualifiedName` | string | The user's username in `domain\username` format |
| `User.DisplayName` | string | The display name of the user |
| `User.Sid` | string | The user's security identifier |
| `User.EmailAddress` | string | The user's email address |

## Role element
If the authorization request was for a role, then this property will be populated with information about the role authorization rule 

| Property | Format/Type | Description |
| --- | --- | ----- |
| `Role.Name` | string | The name of the role |
| `Role.Description` | string | The description of the role |
| `Role.MaximumAllowedDuration` | TimeSpan | The maximum amount of time that the user can request for the role according to the authorization rule |

## Computer element
If the authorization request for a computer, then this property will be populated with information about the computer 

| Property | Format/Type | Description |
| --- | --- | ----- |
| `Computer.Name` | string | The short name of the computer |
| `Computer.Description` | string | The description of the computer |
| `Computer.FullyQualifiedName` | string | The name of the computer in `domain\computer` format |
| `Computer.DnsHostName` | string | The computer's DNS host name, if known |
| `Computer.DisplayName` | string | The computer's display name |
| `Computer.ObjectId` | string | A unique identifier for the computer |
| `Computer.Sid` | string | The computer's security identifier |
| `Computer.AuthorityType` | `ActiveDirectory`, `AzureActiveDirectory`, `Ams` | The authoritative directory where this computer is located |
| `Computer.AuthorityId` | string | The ID of the authority where the computer is located |
| `Computer.AuthorityDeviceId` | string | The unique ID for the device, specific to the device's authority |
