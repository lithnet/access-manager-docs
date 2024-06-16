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
| `Response.NotificationChannels` | string | A comma-separated list of audit channels IDs that apply to this access response |
| `Response.MatchedRule` | string | The ID of the authorization rule that was used to make the access decision |
| `Response.MatchedRuleDescription` | string | The 'description' field from the authorization rule that was used to make the access decision |
| `Response.ExpireAfter` | TimeSpan | The duration of time that access was granted for | 
| `Response.Code` | `Success`, `NoMatchingRuleForTarget`, `NoMatchingRuleForUser`, `ExplicitlyDenied`, `UserRateLimitExceeded`, `IpRateLimitExceeded` | The result of the authorization decision. Codes other than `Success` represent an 'access denied' response. | 
| `Response.AccessType` | `None`, `LocalAdminPassword`, `LocalAdminPasswordHistory`, `Jit`, `Bitlocker` | The type of access that was granted |
| `Response.AccessTypeDescription` | string | The friendly name of the type of access that was granted |
| `Response.AccessExpiryDate` | DateTime | The date and time when the user's access will expire, expressed in local server time |
| `Response.Message` | string | A user-friendly message describing the outcome of the access decision |

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

## RapidLAPS - `DeviceLogin` element
If the authorization request was for workstation login/unlock via *RapidLAPS*, then this property will be populated with information about the *RapidLAPS* login request

| Property | Format/Type | Description |
| --- | --- | ----- |
| `DeviceLogin.Type` | string | The type of *RapidLAPS* request, will always be "Logon" |
| `DeviceLogin.DeviceLoginAccountName` | string | The local account used for RapidLAPS login |
| `DeviceLogin.UsageScenario` | string | A description of where in the operating system the request occured from (e.g., `Logon`, `UnlockWorkstation`) |
| `DeviceLogin.Responses` | Response[] |  *See below* |
| `DeviceLogin.LoggedOnUsers` | LoggedOnUser[] |  *See below* |

### `Response` data structure
The `DeviceLogin.Responses` field contains a list of responses to any prompts defined in the RapidLAPS policy.

| Property | Format/Type | Description |
| --- | --- | ----- |
| `Id` | string | Unique identifier for the prompt message |
| `Label` | string | The human-readable label for the prompt |
| `Type` | string | The type of prompt (e.g., Text, Checkbox, etc.) |
| `Value` | string | The value provided as an answer to the prompt |

### `LoggedOnUser` data structure
The `DeviceLogin.LoggedOnUsers` field contains a list of users logged into the machine at the time of the request.

| Property | Format/Type | Description |
| --- | --- | ----- |
| `UserName` | string | The user's username |
| `SessionID` | int | The user's Windows Session ID |
| `IsRemoteSession` | bool | Indicates if the user was logged in remotely |

## RapidLAPS - `DeviceElevation` element
If the authorization request was for UAC elevation via *RapidLAPS*, then this property will be populated with information about the *RapidLAPS* elevation request

| Property | Format/Type | Description |
| --- | --- | ----- |
| `DeviceElevation.Type` | string | The type of *RapidLAPS* request, will always be "Elevation" |
| `DeviceElevation.DeviceLoginAccountName` | string | The local account used for RapidLAPS elevation |
| `DeviceElevation.ComOperationName` | string | The name of the COM operation the user is attempting to elevate (if applicable) |
| `DeviceElevation.SessionID` | string | The requesting user's Session ID |
| `DeviceElevation.ProcessID` | string | The parent process ID of the elevation (if applicable) |
| `DeviceElevation.ProcessName` | string | The parent process name of the elevation (if applicable) |
| `DeviceElevation.ElevationType` | string | |
| `DeviceElevation.RequesterUsername` | string | The username of the user requesting elevation |
| `DeviceElevation.RequesterSid` | string | The security identifier (SID) of the user requesting elevation |
| `DeviceElevation.RequesterDisplayName` | string | The displau name of the user requesting elevation |
| `DeviceElevation.ProductName` | string | The product name of the executable being elevated (if applicable) |
| `DeviceElevation.Publisher` | string | The publisher name of the executable being elevated (if applicable) |
| `DeviceElevation.FileDescription` | string | The file descrption of the executable being elevated (if applicable) |
| `DeviceElevation.CredUIFlags` | string | The internal flags passed to CredUI (e.g., the credential selector in UAC). [GitHub](https://github.com/lithnet/windows-credential-provider/blob/b010d4ff3f3ff41eac0479e6c8c373907227ad2a/src/Lithnet.CredentialProvider/Enums/CredUIWinFlags.cs) |
| `DeviceElevation.ConsentUIFlags` | string | The internal flags passed to ConsentUI (e.g., UAC). For more information, see our `windows-credential-provider` repository on [GitHub](https://github.com/lithnet/windows-credential-provider/blob/b010d4ff3f3ff41eac0479e6c8c373907227ad2a/src/Lithnet.CredentialProvider/Enums/ConsentUIFlags.cs) |
| `DeviceElevation.UsageScenario` | string | A description of where in the operating system the request occured from; will always be "CredUI" |
| `DeviceElevation.Responses` | Response[] | *See below* |
| `DeviceElevation.LoggedOnUsers` | LoggedOnUser[] | *See below* |
| `DeviceElevation.Hashes` | string[] | A list of hashes of the executable the user is attempting to run |
| `DeviceElevation.Signature` | Signature | Contains signing information |

### `Response` data structure
The `DeviceElevation.Responses` field contains a list of responses to any prompts defined in the RapidLAPS policy.

| Property | Format/Type | Description |
| --- | --- | ----- |
| `Id` | string | Unique identifier for the prompt message |
| `Label` | string | The human-readable label for the prompt |
| `Type` | string | The type of prompt (e.g., Text, Checkbox, etc.) |
| `Value` | string | The value provided as an answer to the prompt |

### `LoggedOnUser` data structure
The `DeviceElevation.LoggedOnUsers` field contains a list of users logged into the machine at the time of the request.

| Property | Format/Type | Description |
| --- | --- | ----- |
| `UserName` | string | The user's username |
| `SessionID` | int | The user's Windows Session ID |
| `IsRemoteSession` | bool | Indicates if the user was logged in remotely |

### `Signature` data structure
The `DeviceElevation.Signature` field contains information about the code signing of the executable run by the user.

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