---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# New-AmsComputerAuthorizationRule

## SYNOPSIS
Creates a new computer authorization rule

## SYNTAX

### Azure AD tenant target authorized by ACL
```
New-AmsComputerAuthorizationRule -AadTenantId <String> [-PrincipalsAllowedLaps <Object[]>]
 [-PrincipalsDeniedLaps <Object[]>] [-PrincipalsAllowedLapsHistory <Object[]>]
 [-PrincipalsDeniedLapsHistory <Object[]>] [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension]
 [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Azure AD tenant target authorized by script
```
New-AmsComputerAuthorizationRule -AadTenantId <String> -AuthorizationScriptPath <String>
 [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension] [-Description <String>]
 [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Azure AD group target authorized by ACL
```
New-AmsComputerAuthorizationRule -AadTenantId <String> -AadGroupId <String> [-PrincipalsAllowedLaps <Object[]>]
 [-PrincipalsDeniedLaps <Object[]>] [-PrincipalsAllowedLapsHistory <Object[]>]
 [-PrincipalsDeniedLapsHistory <Object[]>] [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension]
 [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Azure AD group target authorized by script
```
New-AmsComputerAuthorizationRule -AadTenantId <String> -AadGroupId <String> -AuthorizationScriptPath <String>
 [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension] [-Description <String>]
 [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Azure AD computer target authorized by ACL
```
New-AmsComputerAuthorizationRule -AadTenantId <String> -AadComputerId <String>
 [-PrincipalsAllowedLaps <Object[]>] [-PrincipalsDeniedLaps <Object[]>]
 [-PrincipalsAllowedLapsHistory <Object[]>] [-PrincipalsDeniedLapsHistory <Object[]>]
 [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension] [-Description <String>]
 [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### Azure AD computer target authorized by script
```
New-AmsComputerAuthorizationRule -AadTenantId <String> -AadComputerId <String>
 -AuthorizationScriptPath <String> [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension]
 [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### AD computer target authorized by ACL
```
New-AmsComputerAuthorizationRule -AdComputer <String> [-PrincipalsAllowedJit <Object[]>]
 [-PrincipalsDeniedJit <Object[]>] [-PrincipalsAllowedLaps <Object[]>] [-PrincipalsDeniedLaps <Object[]>]
 [-PrincipalsAllowedLapsHistory <Object[]>] [-PrincipalsDeniedLapsHistory <Object[]>]
 [-PrincipalsAllowedBitLocker <Object[]>] [-PrincipalsDeniedBitLocker <Object[]>] [-JitGroupName <String>]
 [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>]
 [-LapsAllowExtension] [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### AD computer target authorized by script
```
New-AmsComputerAuthorizationRule -AdComputer <String> -AuthorizationScriptPath <String>
 [-JitGroupName <String>] [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension]
 [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension] [-Description <String>]
 [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### AD group target authorized by ACL
```
New-AmsComputerAuthorizationRule -AdGroup <String> [-PrincipalsAllowedJit <Object[]>]
 [-PrincipalsDeniedJit <Object[]>] [-PrincipalsAllowedLaps <Object[]>] [-PrincipalsDeniedLaps <Object[]>]
 [-PrincipalsAllowedLapsHistory <Object[]>] [-PrincipalsDeniedLapsHistory <Object[]>]
 [-PrincipalsAllowedBitLocker <Object[]>] [-PrincipalsDeniedBitLocker <Object[]>] [-JitGroupName <String>]
 [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>]
 [-LapsAllowExtension] [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### AD group target authorized by script
```
New-AmsComputerAuthorizationRule -AdGroup <String> -AuthorizationScriptPath <String> [-JitGroupName <String>]
 [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>]
 [-LapsAllowExtension] [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### AD container target authorized by ACL
```
New-AmsComputerAuthorizationRule -AdContainer <String> [-PrincipalsAllowedJit <Object[]>]
 [-PrincipalsDeniedJit <Object[]>] [-PrincipalsAllowedLaps <Object[]>] [-PrincipalsDeniedLaps <Object[]>]
 [-PrincipalsAllowedLapsHistory <Object[]>] [-PrincipalsDeniedLapsHistory <Object[]>]
 [-PrincipalsAllowedBitLocker <Object[]>] [-PrincipalsDeniedBitLocker <Object[]>] [-JitGroupName <String>]
 [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension] [-LapsMaximumAccessDuration <TimeSpan>]
 [-LapsAllowExtension] [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### AD container target authorized by script
```
New-AmsComputerAuthorizationRule -AdContainer <String> -AuthorizationScriptPath <String>
 [-JitGroupName <String>] [-JitMaximumAccessDuration <TimeSpan>] [-JitAllowExtension]
 [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension] [-Description <String>]
 [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### AMS computer target authorized by ACL
```
New-AmsComputerAuthorizationRule -AmsComputerId <String> [-PrincipalsAllowedLaps <Object[]>]
 [-PrincipalsDeniedLaps <Object[]>] [-PrincipalsAllowedLapsHistory <Object[]>]
 [-PrincipalsDeniedLapsHistory <Object[]>] [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension]
 [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### AMS computer target authorized by script
```
New-AmsComputerAuthorizationRule -AmsComputerId <String> -AuthorizationScriptPath <String>
 [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension] [-Description <String>]
 [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### AMS group target authorized by ACL
```
New-AmsComputerAuthorizationRule -AmsGroupId <String> [-PrincipalsAllowedLaps <Object[]>]
 [-PrincipalsDeniedLaps <Object[]>] [-PrincipalsAllowedLapsHistory <Object[]>]
 [-PrincipalsDeniedLapsHistory <Object[]>] [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension]
 [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

### AMS group target authorized by script
```
New-AmsComputerAuthorizationRule -AmsGroupId <String> -AuthorizationScriptPath <String>
 [-LapsMaximumAccessDuration <TimeSpan>] [-LapsAllowExtension] [-Description <String>]
 [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet creates a new computer authorization rule.

## EXAMPLES

### Example 1
```powershell
PS C:\> $group = Get-AmsGroup -Name "My devices"
PS C:\> New-AmsComputerAuthorizationRule -AmsGroupId $group.Id -PrincipalsAllowedLaps 'DOMAIN\AuthorizedLapsReaders' -LapsMaximumAccessDuration 1:00:00
```

This example creates a new authorization rule, that allows all members of the `DOMAIN\AuthorizedLapsReaders` group to access the LAPS password for all devices in the AMS group named `My devices`, and expires the LAPS password after one hour.

### Example 2
```powershell
PS C:\> New-AmsComputerAuthorizationRule -AadTenantId '2b693132-7e65-4603-b508-910a2b4487c8' -PrincipalsAllowedLaps 'DOMAIN\AuthorizedLapsReaders' -UserRequestReason Required
```

This example creates a new authorization rule, that allows all members of the `DOMAIN\AuthorizedLapsReaders` group to access the LAPS password for all devices in the specified Azure AD tenant, and specifies that the user must provide a reason when requesting access to the LAPS password

### Example 3
```powershell
PS C:\> New-AmsComputerAuthorizationRule -AdContainer 'OU=Devices,DC=domain,DC=local' -PrincipalsAllowedLaps 'DOMAIN\AuthorizedLapsReaders' -NotificationChannelsSuccess 'Email domain admins' -NotificationChannelsFailure 'Email domain admins'
```

This example creates a new authorization rule, that allows all members of the `DOMAIN\AuthorizedLapsReaders` group to access the LAPS password for all devices in the specified Active Directory OU. It also specifies the audit channels to notify on the event a user triggers this rule.

### Example 4
```powershell
PS C:\> New-AmsComputerAuthorizationRule -AdGroup 'DOMAIN\FinanceServers' -PrincipalsAllowedJit 'DOMAIN\FinanceAdmins' -RuleExpiryDate "2025-03-01"
```

This example creates a new authorization rule, that allows all members of the `DOMAIN\FinaanceAdmins` group to JIT into the servers contained within the `FinanceServers` group. The rule is set to expire on 1st March 2025

## PARAMETERS

### -AadComputerId
The object ID of an Azure AD computer

```yaml
Type: String
Parameter Sets: Azure AD computer target authorized by ACL, Azure AD computer target authorized by script
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
Parameter Sets: Azure AD group target authorized by ACL, Azure AD group target authorized by script
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
Parameter Sets: Azure AD tenant target authorized by ACL, Azure AD tenant target authorized by script, Azure AD group target authorized by ACL, Azure AD group target authorized by script, Azure AD computer target authorized by ACL, Azure AD computer target authorized by script
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
Parameter Sets: AD computer target authorized by ACL, AD computer target authorized by script
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
Parameter Sets: AD container target authorized by ACL, AD container target authorized by script
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
Parameter Sets: AD group target authorized by ACL, AD group target authorized by script
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AmsComputerId
The object ID of an AMS-registered computer

```yaml
Type: String
Parameter Sets: AMS computer target authorized by ACL, AMS computer target authorized by script
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
Parameter Sets: AMS group target authorized by ACL, AMS group target authorized by script
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
Parameter Sets: Azure AD tenant target authorized by script, Azure AD group target authorized by script, Azure AD computer target authorized by script, AD computer target authorized by script, AD group target authorized by script, AD container target authorized by script, AMS computer target authorized by script, AMS group target authorized by script
Aliases:

Required: True
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

### -Disabled
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

### -JitAllowExtension
Specifies if the user is allowed to extend their JIT access request before it expires

```yaml
Type: SwitchParameter
Parameter Sets: AD computer target authorized by ACL, AD computer target authorized by script, AD group target authorized by ACL, AD group target authorized by script, AD container target authorized by ACL, AD container target authorized by script
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
Parameter Sets: AD computer target authorized by ACL, AD computer target authorized by script, AD group target authorized by ACL, AD group target authorized by script, AD container target authorized by ACL, AD container target authorized by script
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
Parameter Sets: AD computer target authorized by ACL, AD computer target authorized by script, AD group target authorized by ACL, AD group target authorized by script, AD container target authorized by ACL, AD container target authorized by script
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

### -PrincipalsAllowedBitLocker
The list of principals who are allowed BitLocker access to this computer.

```yaml
Type: Object[]
Parameter Sets: AD computer target authorized by ACL, AD group target authorized by ACL, AD container target authorized by ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalsAllowedJit
The list of principals who are allowed JIT access to this computer.

```yaml
Type: Object[]
Parameter Sets: AD computer target authorized by ACL, AD group target authorized by ACL, AD container target authorized by ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalsAllowedLaps
The list of principals who are allowed LAPS access to this computer.

```yaml
Type: Object[]
Parameter Sets: Azure AD tenant target authorized by ACL, Azure AD group target authorized by ACL, Azure AD computer target authorized by ACL, AD computer target authorized by ACL, AD group target authorized by ACL, AD container target authorized by ACL, AMS computer target authorized by ACL, AMS group target authorized by ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalsAllowedLapsHistory
The list of principals who are allowed LAPS history access to this computer.

```yaml
Type: Object[]
Parameter Sets: Azure AD tenant target authorized by ACL, Azure AD group target authorized by ACL, Azure AD computer target authorized by ACL, AD computer target authorized by ACL, AD group target authorized by ACL, AD container target authorized by ACL, AMS computer target authorized by ACL, AMS group target authorized by ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalsDeniedBitLocker
The list of principals who are not allowed BitLocker access to this computer.

```yaml
Type: Object[]
Parameter Sets: AD computer target authorized by ACL, AD group target authorized by ACL, AD container target authorized by ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalsDeniedJit
The list of principals who are not allowed JIT access to this computer.

```yaml
Type: Object[]
Parameter Sets: AD computer target authorized by ACL, AD group target authorized by ACL, AD container target authorized by ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalsDeniedLaps
The list of principals who are not allowed LAPS access to this computer.

```yaml
Type: Object[]
Parameter Sets: Azure AD tenant target authorized by ACL, Azure AD group target authorized by ACL, Azure AD computer target authorized by ACL, AD computer target authorized by ACL, AD group target authorized by ACL, AD container target authorized by ACL, AMS computer target authorized by ACL, AMS group target authorized by ACL
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalsDeniedLapsHistory
The list of principals who are not allowed LAPS history access to this computer.

```yaml
Type: Object[]
Parameter Sets: Azure AD tenant target authorized by ACL, Azure AD group target authorized by ACL, Azure AD computer target authorized by ACL, AD computer target authorized by ACL, AD group target authorized by ACL, AD container target authorized by ACL, AMS computer target authorized by ACL, AMS group target authorized by ACL
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

### None

## OUTPUTS

### Lithnet.AccessManager.PowerShell.ComputerAuthorizationRulePSObject

## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
