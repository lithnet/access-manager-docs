# Event IDs used in Access Manager

## Access Manager Server
| Event ID | Severity | Description |
| --- | --- | --- |
| 2000 | Informational | A user has requested access to a computer |
| 2001 | Informational | A user has been added to a local SAM group |
| 2002 | Informational | A user has been removed from a local SAM group |
| 2003 | Informational | The JIT worker service has created a new group |
| 2004 | Informational | The JIT worker service has deleted a group |
| 2005 | Informational | The JIT worker service has created a new dynamic group |
| 2006 | Informational | The JIT worker service has deleted a dynamic group |
| 2007 | Informational | JIT access has been granted to a user via PAM|
| 2008 | Informational | JIT access has been revoked from a user via PAM |
| 2009 | Informational | A user has requested access to a role |
| 2010 | Informational | JIT access has been granted to a user via the scheduler|
| 2011 | Informational | JIT access has been revoked from a user via the scheduler|
| 2012 | Informational | The JIT scheduler determined that the user no longer exists |
| 2013 | Informational | The JIT scheduler determined that the group no longer exists |
| 2101 | Informational | A computer authorization rule has been added |
| 2102 | Informational | A computer authorization rule has been deleted |
| 2103 | Informational | A computer authorization rule has been modified |
| 2104 | Informational | A role authorization rule has been added |
| 2105 | Informational | A role authorization rule has been deleted |
| 2106 | Informational | A role authorization rule has been modified |
| 2200 | Informational | The database does not exist |
| 2201 | Informational | The database has been created |
| 2202 | Informational | Database upgrade is required |
| 2203 | Informational | The database is being deleted |
| 2204 | Informational | The database has been deleted |
| 2205 | Informational | Database upgrade check is in progress |
| 2206 | Informational | Database upgrade has been completed |
| 2207 | Informational | Database upgrade is not required |
| 2300 | Informational | The master key has been exported |
| 3000 | Audit Success | A user has been authenticated |
| 3001 | Audit Success | Access to the computer's current local admin password has been granted |
| 3002 | Audit Success | Access to the computer's password history has been granted |
| 3003 | Audit Success | JIT access to a computer has been granted |
| 3004 | Audit Success | BitLocker access to a computer has been granted |
| 3005 | Audit Success | JIT access to a role has been granted |
| 4000 | Errors | SSO identity not found |
| 4001 | Errors | Computer not found in directory |
| 4002 | Errors | LAPS password not present |
| 4003 | Errors | Computer name is ambiguous |
| 4004 | Errors | A user request reason was required but it was not provided |
| 4006 | Errors | User certificate identity not found |
| 4008 | Errors | User certificate validation error |
| 4009 | Errors | Identity discovery error |
| 4010 | Errors | Computer discovery error |
| 4011 | Errors | No LAPS password history is available |
| 4012 | Errors | Authorization failed because there were no rules that matched for the specific user |
| 4013 | Errors | Authorization failed because there were no rules that matched for the requested computer |
| 4014 | Errors | Authorization failed |
| 4015 | Errors | Authorization was explicitly denied |
| 4016 | Errors | Authorization failed because a mandatory audit event failed to be delivered |
| 4017 | Errors | The IP-based rate limit was exceeded |
| 4018 | Errors | The user-based rate limit was exceeded |
| 4019 | Errors | BitLocker keys were not present for the specified computer |
| 4020 | Errors | Authorization failed because the rate limit was exceeded |
| 4021 | Errors | The search request returned too many results |
| 5001 | Errors | Failed to add a user to a local SAM group |
| 5002 | Errors | Failed to remove a user from a local SAM group |
| 5003 | Errors | Invalid certificate - invalid or unsupported URI scheme |
| 5004 | Errors | Unexpected error |
| 5005 | Errors | Error loading template resource |
| 5006 | Errors | Notification channel delivery error |
| 5007 | Errors | Unhandled error in background task |
| 5008 | Errors | Error processing an authorization rule |
| 5009 | Errors | JIT rollback is in progress |
| 5010 | Errors | JIT rollback failed |
| 5011 | Errors | JIT error |
| 5012 | Errors | An error occured in the pre-authorization process |
| 5013 | Errors | LAPS password history error |
| 5014 | Errors | LAPS password error |
| 5015 | Errors | Authorization error |
| 5016 | Errors | Application is not configured |
| 5017 | Errors | Certificate trust chain parsing issue |
| 5018 | Errors | Error looking up target directory |
| 5019 | Errors | Error creating authorization context |
| 5020 | Errors | Authorization context fallback |
| 5021 | Errors | Authorization context server cannot connect |
| 5022 | Errors | Invalid response from PowerShell security descriptor generator |
| 5023 | Errors | DN parse error |
| 5024 | Errors | Unexpected error in JIT worker |
| 5025 | Errors | Failed to create JIT worker group |
| 5026 | Errors | Failed to delete JIT worker group |
| 5027 | Errors | JIT worker USN fallback |
| 5028 | Errors | JIT dynamic group has invalid domain |
| 5029 | Errors | External authentication provider error |
| 5030 | Errors | Error processing authentication provider response |
| 5031 | Errors | Error looking up authentication directory |
| 5032 | Errors | Access denied by external authentication provider |
| 5033 | Errors | Certificate authentication access denied |
| 5034 | Errors | Certificate authentication error |
| 5035 | Errors | BitLocker key access error |
| 5036 | Errors | Error reading resource |
| 5037 | Errors | Error importing certificate |
| 5038 | Errors | Error exporting certificate |
| 5039 | Errors | The certificate could not be synchronized because the private key was not exportable |
| 5040 | Errors | Database upgrade error |
| 5041 | Errors | Database upgrade warning |
| 5042 | Errors | Database upgrade info |
| 5048 | Errors | Failed to check for new version |
| 5049 | Errors | Failed to check certificate expiry |
| 5050 | Errors | API is not enabled |
| 5051 | Errors | Database backup job failed |
| 5052 | Errors | Database initialization failed |
| 5053 | Errors | The scheduler failed to remove JIT membership |
| 5054 | Errors | The scheduler abandoned the membership removal job |
| 5055 | Errors | Password retrieval restricted by license |
| 5056 | Errors | Database maintenance job failed |
| 5057 | Errors | JIT worker job failed |
| 5058 | Errors | Certificate authentication failed because no certificate was presented |

## Agent
| Event ID | Description |
| --- | --- |
| 1000 | The agent has started |
| 1001 | The agent has been disabled |
| 1002 | The LAPS agent is currently disabled |
| 1020 | The LAPS agent has been enabled |
| 1004 | The LAPS agent cannot run because it is running on a domain controller |
| 1006 | An unexpected exception occurred in the LAPS process |
| 1007 | An unexpected exception occurred in the agent |
| 1008 | The LAPS agent is not configured |
| 1009 | There was a conflict between the Access Manager Agent and the Windows LAPS agent. Only one may be active at any one time |
| 1010 | The password has expired |
| 1011 | Password has been set on the LAPS attribute |
| 1012 | Password has been set on the Access Manager attribute |
| 1013 | Password has been changed |
| 1014 | Failure in password expiry check |
| 1015 | Failure in password change |
| 1017 | LAPS conflict has been resolved |
| 1018 | No password change required |
| 1019 | UWF (Unified Write Filter) has been enabled |
| 2001 | Error in server connection |
| 2002 | Server credentials are not recognized |
| 2003 | No server is configured |
| 2004 | AADR (Azure Active Directory Registration) registration is not allowed |
| 2005 | AMS registration has been rejected |
| 2006 | AMS registration information is missing |
| 2007 | AD certificate private key is not available |
| 2008 | Impersonation failure |
| 2009 | AMS registration failed due to an invalid registration key |
| 2010 | Failed to enable the account |
| 2011 | Failed to reset the agent |
| 2012 | Server certificate has expired |
| 2013 | Server certificate hostname mismatch |
| 2014 | Server certificate validation failed |
| 3001 | Registration is not ready |
| 3002 | No suitable AAD (Azure Active Directory) tenant found |
| 4001 | AMS registration is pending |
| 4002 | AMS registration has been approved |
| 4003 | AMS registration is starting |
| 4004 | Secondary credentials have been registered |
| 4005 | Agent reset has been completed |
