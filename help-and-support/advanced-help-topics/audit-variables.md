# Variables available in audit notification channels
Access Manager provides a comprehensive set of variables you can use in your audit notifications.

See the guides on [PowerShell auditing scripts](audit-scripts.md) and [HTML and JSON audit templates](audit-templates.md) to learn how to use these variables in your audit scripts and templates.

## Global properties
| Property | Format/Type | Description |
| --- | --- | ----- |
| `DateTime` | string | The current date and time, in local server time |
| `DateTimeUtc` | string | The current date and time, in UTC time |

## `Request` element
This group of attributes represents the incoming request

| Property | Format/Type | Description |
| --- | --- | ----- |
| `Request.Target` | string | The name of the target that the user requested access to |
| `Request.TargetType` | `Computer` or `Role` | The type of resource the user requested access to |
| `Request.Reason` | string | The reason that the user provided when requesting access |
| `Request.IPAddress` | IPv4 or IPv6 address string | The IP address of requestor |
| `Request.HostName` | string | The host name of the requestor, if available via reverse DNS lookup |
| `Request.RequestedDuration` | TimeSpan | The requested duration of access |

## `Response` element
This group of attributes represents the result of the access evaluation

| Property | Format/Type | Description |
| --- | --- | ----- |
| `Response.Target` | string | The name of the target that the access request was evaluated against |
| `Response.TargetType` | `Computer` or `Role` | The type of resource that was evaluated |
| `Response.IsSuccess` | `true` or `false` | Indicates if access was granted to the resource |
| `Response.IsFailure` | `true` or `false` | Indicates if access was denied to the resource |
| `Response.IsApproved` | `true` or `false` | Indicates if access was approved to the resource |
| `Response.NotificationChannels` | string | A comma-separated list of audit channels IDs that apply to this access response |
| `Response.MatchedRule` | string | The ID of the authorization rule that was used to make the access decision |
| `Response.MatchedRuleDescription` | string | The 'description' field from the authorization rule that was used to make the access decision |
| `Response.ExpireAfter` | TimeSpan | The duration of time that access was granted for | 
| `Response.Code` | `Success`, `NoMatchingRuleForTarget`, `NoMatchingRuleForUser`, `ExplicitlyDenied`, `UserRateLimitExceeded`, `IpRateLimitExceeded` | The result of the authorization decision. Codes other than `Success` represent an 'access denied' response. | 
| `Response.AccessType` | `None`, `LocalAdminPassword`, `LocalAdminPasswordHistory`, `Jit`, `Bitlocker`, `DeviceLogin`, `DeviceElevation` | The type of access that was granted |
| `Response.AccessTypeDescription` | string | The friendly name of the type of access that was granted |
| `Response.AccessExpiryDate` | DateTime | The date and time when the user's access will expire, expressed in local server time |
| `Response.Message` | string | A user-friendly message describing the outcome of the access decision |
| `Response.WorkflowResult` | `None`, `Approved`, `Rejected`, `Pending` | The approval result of the workflow operation |

## `User` element
This group of attributes represents the user who performed the access request

| Property | Format/Type | Description |
| --- | --- | ----- |
| `User.Username` | string | The `samAccountName` of the user requesting access |
| `User.FullyQualifiedName` | string | The user's username in `domain\username` format |
| `User.DisplayName` | string | The display name of the user |
| `User.Sid` | string | The user's security identifier |
| `User.EmailAddress` | string | The user's email address |

## `Role` element
If the authorization request was for a role, then this property will be populated with information about the role authorization rule 

| Property | Format/Type | Description |
| --- | --- | ----- |
| `Role.Name` | string | The name of the role |
| `Role.Description` | string | The description of the role |
| `Role.MaximumAllowedDuration` | TimeSpan | The maximum amount of time that the user can request for the role according to the authorization rule |

## `Computer` element
If the authorization request was for a computer, then this property will be populated with information about the computer 

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

## `RapidLapsLogin` element
If the authorization request was for workstation login/unlock via *RapidLAPS*, then this property will be populated with information about the *RapidLAPS* login request

| Property | Format/Type | Description |
| --- | --- | ----- |
| `RapidLapsLogin.Type` | string | The type of RapidLAPS request, will always be `Logon` |
| `RapidLapsLogin.DeviceLoginAccountName` | string | The local account used for RapidLAPS login |
| `RapidLapsLogin.UsageScenario` | string | A description of where in the operating system the request occurred from (e.g., `Logon`, `UnlockWorkstation`) |
| `RapidLapsLogin.Responses` | Response[] |  *See below* |
| `RapidLapsLogin.LoggedOnUsers` | LoggedOnUser[] |  *See below* |

## `RapidLapsElevation` element
If the authorization request was for UAC elevation via *RapidLAPS*, then this property will be populated with information about the *RapidLAPS* elevation request

| Property | Format/Type | Description |
| --- | --- | ----- |
| `RapidLapsElevation.Type` | string | The type of *RapidLAPS* request, will always be "Elevation" |
| `RapidLapsElevation.DeviceLoginAccountName` | string | The local account used for RapidLAPS elevation |
| `RapidLapsElevation.ComOperationName` | string | The name of the COM operation the user is attempting to elevate (if applicable) |
| `RapidLapsElevation.SessionID` | string | The requesting user's Session ID |
| `RapidLapsElevation.ProcessID` | string | The parent process ID of the elevation (if applicable) |
| `RapidLapsElevation.ProcessName` | string | The parent process name of the elevation (if applicable) |
| `RapidLapsElevation.ElevationType` | string | |
| `RapidLapsElevation.RequesterUsername` | string | The username of the user requesting elevation |
| `RapidLapsElevation.RequesterSid` | string | The security identifier (SID) of the user requesting elevation |
| `RapidLapsElevation.RequesterDisplayName` | string | The display name of the user requesting elevation |
| `RapidLapsElevation.ProductName` | string | The product name of the executable being elevated (if applicable) |
| `RapidLapsElevation.Publisher` | string | The publisher name of the executable being elevated (if applicable) |
| `RapidLapsElevation.FileDescription` | string | The file description of the executable being elevated (if applicable) |
| `RapidLapsElevation.CredUIFlags` | string | The internal flags passed to CredUI (e.g., the credential selector in UAC). [GitHub](https://github.com/lithnet/windows-credential-provider/blob/b010d4ff3f3ff41eac0479e6c8c373907227ad2a/src/Lithnet.CredentialProvider/Enums/CredUIWinFlags.cs) |
| `RapidLapsElevation.ConsentUIFlags` | string | The internal flags passed to ConsentUI (e.g., UAC). For more information, see our `windows-credential-provider` repository on [GitHub](https://github.com/lithnet/windows-credential-provider/blob/b010d4ff3f3ff41eac0479e6c8c373907227ad2a/src/Lithnet.CredentialProvider/Enums/ConsentUIFlags.cs) |
| `RapidLapsElevation.UsageScenario` | string | A description of where in the operating system the request occurred from; will always be "CredUI" |
| `RapidLapsElevation.Responses` | Response[] | *See below* |
| `RapidLapsElevation.LoggedOnUsers` | LoggedOnUser[] | *See below* |
| `RapidLapsElevation.Hashes` | string[] | A list of hashes of the executable the user is attempting to run |
| `RapidLapsElevation.Signature` | Signature | Contains signing information |

### `Signature` data structure
The `RapidLapsElevation.Signature` field contains information about the code signing of the executable run by the user.

| Property | Format/Type | Description |
| --- | --- | ----- |
| `State` | string | The status of the digital signature (e.g. Valid, Invalid, etc.) |
| `Signers` | Signer[] | A list of each code signing certificate used to sign the executable |

#### `Signer` data structure
The `Signer` data structure is used to represent an entity that has digitally singed an executable.

| Property | Format/Type | Description |
| --- | --- | ----- |
| `SignerCertificate` | SignatureCertificate | The certificate used for code signing |
| `CounterSignerCertificates` | SignatureCertificate[] | All countersigner certificates used for code signing |

##### `SignatureCertificate` data structure
The `SignatureCertificate` data structure represents the elements of an *X.509* code signing certificate.

| Property | Format/Type | Description |
| --- | --- | ----- |
| `Thumbprint` | string | The certificate's thumbprint |
| `SerialNumber` | string | The certificate's serial number|
| `Subject` | string | The certificate's subject |
| `DisplayName` | string | The certificate's display name |
| `Issuer` | string | The certificate issuer's distinguished name |
| `IssuerDisplayName` | string | The certificate issuer's display name |
| `NotBefore` | DateTime | The issuance date of the certificate |
| `NotAfter` | DateTime | The expiry date of the certificate |

### `Response` data structure
The `RapidLapsLogin.Responses` and `RapidLapsElevation.Responses` fields contain a list of responses to any prompts defined in the RapidLAPS policy.

| Property | Format/Type | Description |
| --- | --- | ----- |
| `Id` | string | Unique identifier for the prompt message |
| `Label` | string | The human-readable label for the prompt |
| `Type` | string | The type of prompt (e.g., Text, Checkbox, etc.) |
| `Value` | string | The value provided as an answer to the prompt |

### `LoggedOnUser` data structure
The `RapidLapsLogin.LoggedOnUsers` and `RapidLapsElevation.Responses` fields contain a list of users logged into the machine at the time of the request.

| Property | Format/Type | Description |
| --- | --- | ----- |
| `UserName` | string | The user's username |
| `SessionID` | integer | The user's Windows Session ID |
| `IsRemoteSession` | boolean | Indicates if the user was logged in remotely |
