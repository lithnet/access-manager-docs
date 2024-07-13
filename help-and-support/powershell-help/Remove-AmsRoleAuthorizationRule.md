---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Remove-AmsRoleAuthorizationRule

## SYNOPSIS
Removes a role authorization rule

## SYNTAX

```
Remove-AmsRoleAuthorizationRule [-Id <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet permanently removes a role authorization rule from the server

## EXAMPLES

### Example 1
```powershell
PS C:\> Remove-AmsRoleAuthorizationRule -Id '6d34b2f3-dd28-4dc6-893f-f64f4d099bd6'
```

Removes a role by its known ID

### Example 2
```powershell
PS C:\> Get-AmsRoleAuthorizationRule -Name "My custom role" | Remove-AmsRoleAuthorizationRule
```

Get a role authorization rule by name and removes it

## PARAMETERS

### -Force
Removes the rule without prompting for confirmation

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

### -Id
The unique ID of the rule

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
## OUTPUTS

### System.Void
## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
