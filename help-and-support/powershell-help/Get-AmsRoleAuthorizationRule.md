---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsRoleAuthorizationRule

## SYNOPSIS
Gets all the role authorization rules, or a specific role authorization rule by its ID

## SYNTAX

### NoParameters (Default)
```
Get-AmsRoleAuthorizationRule [<CommonParameters>]
```

### GetByName
```
Get-AmsRoleAuthorizationRule [-Name <String>] [<CommonParameters>]
```

### GetById
```
Get-AmsRoleAuthorizationRule [-Id <String>] [<CommonParameters>]
```

## DESCRIPTION
When called without any parameters, this cmdlet returns all the role authorization rules currently on the server.
When the ID parameter is specified, it returns the rule matching that ID.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsRoleAuthorizationRule
```

Returns all the role authorization rules on the server

### Example 2
```powershell
PS C:\> Get-AmsRoleAuthorizationRule -Name "My custom role"
```

Returns the role authorization rule with the name \`My custom role\`

### Example 3
```powershell
PS C:\> Get-AmsRoleAuthorizationRule -Id "941f158c-3f88-4665-be37-217c2841b718"
```

Returns the role authorization rule with the specified ID

## PARAMETERS

### -Id
The unique ID of the rule

```yaml
Type: String
Parameter Sets: GetById
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the rule

```yaml
Type: String
Parameter Sets: GetByName
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
