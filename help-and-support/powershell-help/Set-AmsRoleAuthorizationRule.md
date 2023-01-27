---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Set-AmsRoleAuthorizationRule

## SYNOPSIS
Configures a role authorization rule

## SYNTAX

```
Set-AmsRoleAuthorizationRule [-Id] <String> [-Name <String>] [-AddPrincipalsAllowedJit <Object[]>]
 [-RemovePrincipalsAllowedJit <Object[]>] [-AddPrincipalsDeniedJit <Object[]>]
 [-RemovePrincipalsDeniedJit <Object[]>] [-GroupName <String>] [-MaximumAccessDuration <TimeSpan>]
 [-DefaultAccessDuration <TimeSpan>] [-AllowExtension <Boolean>] [-Description <String>]
 [-RuleExpiryDate <DateTime>] [-Enabled <Boolean>] [-Notes <String>]
 [-UserRequestReasonRequirement <AuditReasonFieldState>] [-NotificationChannelsSuccess <String[]>]
 [-NotificationChannelsFailure <String[]>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet allows you to change properties on role authorization rules

## EXAMPLES

### Example 1
```powershell
PS C:\> Set-AmsRoleAuthorizationRule -Id 'a984d40c-8b22-4009-83ac-f38b7b341cc4' -Name "My new role name"
```

Renames a role

### Example 2
```powershell
PS C:\> Set-AmsRoleAuthorizationRule -Id 'a984d40c-8b22-4009-83ac-f38b7b341cc4' -AddPrincipalsAllowedJit "DOMAIN\user1"
```

Adds `Domain\user1` to the list of users who are allowed to access this role

### Example 3
```powershell
PS C:\> Get-AmsRoleAuthorizationRule -Name "My role" | Set-AmsRoleAuthorizationRule -AddPrincipalsDeniedJit "DOMAIN\user1"
```

Get a rule by its name, and adds `Domain\user1` to the list of users who are denied to access this role

### Example 4
```powershell
PS C:\> Get-AmsRoleAuthorizationRule -Name "My role" | Set-AmsRoleAuthorizationRule -Enabled:$false
```

Get a rule by its name, and disables it


## PARAMETERS

### -AddPrincipalsAllowedJit
A list of usernames or SIDs to add to the list of users who are allowed to access this role

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

### -AddPrincipalsDeniedJit
A list of usernames or SIDs to add to the list of users who are not allowed to access this role

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

### -AllowExtension
Specifies if the user is allowed to extend their access request before it expires

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

### -Enabled
Indicates if the rule should be enabled

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupName
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

### -Id
The ID of the role to edit

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaximumAccessDuration
The maximum amount of time the user can request access to this role

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

### -Name
The name of the role, as shown to end users

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

### -RemovePrincipalsAllowedJit
A list of usernames or SIDs to remove from the list of users who are allowed to access this role

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

### -RemovePrincipalsDeniedJit
A list of usernames or SIDs to remove from the list of users who are not allowed to access this role

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Lithnet.AccessManager.PowerShell.RoleAuthorizationRulePSObject

## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS