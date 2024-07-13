---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# New-AmsRoleAuthorizationRule

## SYNOPSIS
Creates a new role authorization rule

## SYNTAX

```
New-AmsRoleAuthorizationRule -Name <String> -PrincipalsAllowedJit <Object[]> [-PrincipalsDeniedJit <Object[]>]
 -GroupName <String> -MaximumAccessDuration <TimeSpan> [-DefaultAccessDuration <TimeSpan>] [-AllowExtension]
 [-Description <String>] [-RuleExpiryDate <DateTime>] [-Disabled] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [-SiteName <String>] [-DomainControllerName <String>]
 [<CommonParameters>]
```

## DESCRIPTION
This cmdlet creates a new just-in-time access role, and specifies the users who are allowed to claim the role.

Note: The use of this cmdlet requires Access Manager Enterprise Edition

## EXAMPLES

### Example 1
```powershell
PS C:\> New-AmsRoleAuthorizationRule -Name "Rocketship production admin" -GroupName "DOMAIN\Rocketship-Prod-Admins" -MaximumAccessDuration 8:30:00 -PrincipalsAllowedJit "DOMAIN\Rocketship-authorized-admins"
```

Creates a new authorization rule, that allows members of the group \`DOMAIN\Rocketship-authorized-admins\` to become members of the \`DOMAIN\Rocketship-Prod-Admins\` group for a maximum duration of 8 hours and 30 minutes.

## PARAMETERS

### -AllowExtension
Specifies if the user is allowed to extend their access request before it expires

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultAccessDuration
The amount of time the user is offered to access this role by default.
This value cannot be greater than the value defined in MaximumAccessDuration

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

### -Description
A description of the role, as shown to end users

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupName
The name of the group that users will be added to when granted access to this role

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumAccessDuration
The maximum amount of time the user can request access to this role

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the role, as shown to end users

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notes
A custom field to store notes, only visible to AMS administrators

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
A list of channel IDs that should be notified when a user is denied access to this role

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
A list of channel IDs that should be notified when a user is granted access to this role

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

### -PrincipalsAllowedJit
The list of users who are allowed to access this role.
The list can consist of fully qualified usernames (eg domain\user) or SIDs

```yaml
Type: Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalsDeniedJit
The list of users who are not allowed to access this role.
The list can consist of fully qualified usernames (eg domain\user) or SIDs

```yaml
Type: Object[]
Parameter Sets: (All)
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

### -DomainControllerName
The name of a domain controller to use when performing the JIT operation against

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

### -SiteName
The name of the site to use when trying to find a domain controller to perform the JIT operation against

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
## OUTPUTS

### Lithnet.AccessManager.PowerShell.RoleAuthorizationRulePSObject
## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
