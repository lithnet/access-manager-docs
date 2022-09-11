---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Set-AmsComputerAuthorizationRule

## SYNOPSIS
Sets the properties of an AMS authorization rule

## SYNTAX

### None (Default)
```
Set-AmsComputerAuthorizationRule -Id <String> [-JitGroupName <String>] [-JitMaximumAccessDuration <TimeSpan>]
 [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension] [-Description <String>]
 [-RuleExpiryDate <DateTime>] [-Disable] [-Enable] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Set the rule target to an Azure AD tenant
```
Set-AmsComputerAuthorizationRule -Id <String> -AadTenantId <String> [-JitGroupName <String>]
 [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>]
 [-LapsAllowExtension] [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disable] [-Enable]
 [-Notes <String>] [-UserRequestReasonRequirement <AuditReasonFieldState>]
 [-NotificationChannelsSuccess <String[]>] [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Set the rule target to an Azure AD group
```
Set-AmsComputerAuthorizationRule -Id <String> -AadTenantId <String> -AadGroupId <String>
 [-JitGroupName <String>] [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension]
 [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension] [-Description <String>]
 [-RuleExpiryDate <DateTime>] [-Disable] [-Enable] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Set the rule target to an Azure AD computer
```
Set-AmsComputerAuthorizationRule -Id <String> -AadTenantId <String> -AadComputerId <String>
 [-JitGroupName <String>] [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension]
 [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension] [-Description <String>]
 [-RuleExpiryDate <DateTime>] [-Disable] [-Enable] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Set the rule target to an AD computer
```
Set-AmsComputerAuthorizationRule -Id <String> -AdComputer <String> [-JitGroupName <String>]
 [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>]
 [-LapsAllowExtension] [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disable] [-Enable]
 [-Notes <String>] [-UserRequestReasonRequirement <AuditReasonFieldState>]
 [-NotificationChannelsSuccess <String[]>] [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Set the rule target to an AD group
```
Set-AmsComputerAuthorizationRule -Id <String> -AdGroup <String> [-JitGroupName <String>]
 [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>]
 [-LapsAllowExtension] [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disable] [-Enable]
 [-Notes <String>] [-UserRequestReasonRequirement <AuditReasonFieldState>]
 [-NotificationChannelsSuccess <String[]>] [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Set the rule target to an AD container
```
Set-AmsComputerAuthorizationRule -Id <String> -AdContainer <String> [-JitGroupName <String>]
 [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>]
 [-LapsAllowExtension] [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disable] [-Enable]
 [-Notes <String>] [-UserRequestReasonRequirement <AuditReasonFieldState>]
 [-NotificationChannelsSuccess <String[]>] [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Set the rule target to an AMS computer
```
Set-AmsComputerAuthorizationRule -Id <String> -AmsComputerId <String> [-JitGroupName <String>]
 [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>]
 [-LapsAllowExtension] [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disable] [-Enable]
 [-Notes <String>] [-UserRequestReasonRequirement <AuditReasonFieldState>]
 [-NotificationChannelsSuccess <String[]>] [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Set the rule target to an AMS group
```
Set-AmsComputerAuthorizationRule -Id <String> -AmsGroupId <String> [-JitGroupName <String>]
 [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>]
 [-LapsAllowExtension] [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disable] [-Enable]
 [-Notes <String>] [-UserRequestReasonRequirement <AuditReasonFieldState>]
 [-NotificationChannelsSuccess <String[]>] [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Modify the rule ACL
```
Set-AmsComputerAuthorizationRule -Id <String> [-AddPrincipalsAllowedJit <Object[]>]
 [-RemovePrincipalsAllowedJit <Object[]>] [-AddPrincipalsDeniedJit <Object[]>]
 [-RemovePrincipalsDeniedJit <Object[]>] [-AddPrincipalsAllowedLaps <Object[]>]
 [-RemovePrincipalsAllowedLaps <Object[]>] [-AddPrincipalsDeniedLaps <Object[]>]
 [-RemovePrincipalsDeniedLaps <Object[]>] [-AddPrincipalsAllowedLapsHistory <Object[]>]
 [-RemovePrincipalsAllowedLapsHistory <Object[]>] [-AddPrincipalsDeniedLapsHistory <Object[]>]
 [-RemovePrincipalsDeniedLapsHistory <Object[]>] [-AddPrincipalsAllowedBitLocker <Object[]>]
 [-RemovePrincipalsAllowedBitLocker <Object[]>] [-AddPrincipalsDeniedBitLocker <Object[]>]
 [-RemovePrincipalsDeniedBitLocker <Object[]>] [-JitGroupName <String>] [-JitMaximumAccessDuration <TimeSpan>]
 [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension] [-Description <String>]
 [-RuleExpiryDate <DateTime>] [-Disable] [-Enable] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Modify the rule authorization script
```
Set-AmsComputerAuthorizationRule -Id <String> [-AuthorizationScriptPath <String>] [-JitGroupName <String>]
 [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>]
 [-LapsAllowExtension] [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disable] [-Enable]
 [-Notes <String>] [-UserRequestReasonRequirement <AuditReasonFieldState>]
 [-NotificationChannelsSuccess <String[]>] [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet allows you to modify the properties of an authorization rule, such as updating the target of the rule, adding and removing authorized users, and configuring LAPS and JIT settings.

## EXAMPLES

### Example 1
```powershell
PS C:\> Set-AmsComputerAuthorizationRule -Id '8a2ac32c-3fe8-478f-9550-9e6630d8f07a' -AddPrincipalsAllowedJit 'DOMAIN\user1'
```

Adds the specified principal to the list of allowed JIT users

### Example 2
```powershell
PS C:\> Set-AmsComputerAuthorizationRule -Id '8a2ac32c-3fe8-478f-9550-9e6630d8f07a' -AuthorizationScriptPath "C:\scripts\authz.ps1"
```

Updates the rule to use the specified authorization script


### Example 3
```powershell
PS C:\> Set-AmsComputerAuthorizationRule -Id '8a2ac32c-3fe8-478f-9550-9e6630d8f07a' -AdGroup "DOMAIN\AccountingServers"
```

Targets the rule to the `AccountingServers` AD group



## PARAMETERS

### -AadComputerId
The object ID of an Azure AD computer

```yaml
Type: String
Parameter Sets: Set the rule target to an Azure AD computer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AadGroupId
The object ID of an Azure AD group

```yaml
Type: String
Parameter Sets: Set the rule target to an Azure AD group
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AadTenantId
The tenant ID of a registered Azure AD tenant

```yaml
Type: String
Parameter Sets: Set the rule target to an Azure AD tenant, Set the rule target to an Azure AD group, Set the rule target to an Azure AD computer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdComputer
The fully qualified name or SID of an Active Directory computer

```yaml
Type: String
Parameter Sets: Set the rule target to an AD computer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdContainer
The DN of an Active Directory container object such as an organizational unit

```yaml
Type: String
Parameter Sets: Set the rule target to an AD container
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdGroup
The fully qualified name or SID of an Active Directory group

```yaml
Type: String
Parameter Sets: Set the rule target to an AD group
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddPrincipalsAllowedBitLocker
Principals to add to the allow BitLocker access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddPrincipalsAllowedJit
Principals to add to the allow JIT access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddPrincipalsAllowedLaps
Principals to add to the allow LAPS access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddPrincipalsAllowedLapsHistory
Principals to add to the allow LAPS history access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddPrincipalsDeniedBitLocker
Principals to add to the deny BitLocker access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddPrincipalsDeniedJit
Principals to add to the deny JIT access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddPrincipalsDeniedLaps
Principals to add to the deny LAPS access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddPrincipalsDeniedLapsHistory
Principals to add to the deny LAPS history access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AmsComputerId
The object ID of an AMS-registered computer

```yaml
Type: String
Parameter Sets: Set the rule target to an AMS computer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AmsGroupId
The SID of an AMS group

```yaml
Type: String
Parameter Sets: Set the rule target to an AMS group
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthorizationScriptPath
The path to the authorization script to import

```yaml
Type: String
Parameter Sets: Modify the rule authorization script
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
A description of the rule

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disable
Indicates if the rule should be disabled

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enable
Indicates if the rule should be enabled

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
The unique ID of the rule

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JitAllowExtension
Specifies if the user is allowed to extend their JIT access request before it expires

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JitGroupName
The name of the group that users will be added to when granted access to this role

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JitMaximumAccessDuration
The maximum amount of time the user can request access to this computer via JIT

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LapsAllowExtension
Specifies if the user is allowed to extend their LAPS access request before it expires

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LapsMaximumAccessDuration
The maximum amount of time the user can request access to this computer's LAPS password before it is changed

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notes
A custom field to store notes

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotificationChannelsFailure
A list of channel IDs or names that should be notified when a user is denied access by this rule

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotificationChannelsSuccess
A list of channel IDs or names that should be notified when a user is granted access by this rule

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePrincipalsAllowedBitLocker
Principals to remove from the allow BitLocker access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePrincipalsAllowedJit
Principals to remove from the allow JIT access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePrincipalsAllowedLaps
Principals to remove from the allow LAPS access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePrincipalsAllowedLapsHistory
Principals to remove from the allow LAPS history access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePrincipalsDeniedBitLocker
Principals to remove from the deny BitLocker access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePrincipalsDeniedJit
Principals to remove from the deny JIT access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePrincipalsDeniedLaps
Principals to remove from the deny LAPS access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePrincipalsDeniedLapsHistory
Principals to remove from the deny LAPS history access list

```yaml
Type: Object[]
Parameter Sets: Modify the rule ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleExpiryDate
A date and time when this rule will expire, expressed in local time

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRequestReasonRequirement
Specifies if the user must provide a reason for the request, if they can optionally provide a reason, or are not prompted at all for a reason

```yaml
Type: AuditReasonFieldState
Parameter Sets: (All)
Aliases:
Accepted values: Hidden, Optional, Required

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Lithnet.AccessManager.PowerShell.ComputerAuthorizationRulePSObject

## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
