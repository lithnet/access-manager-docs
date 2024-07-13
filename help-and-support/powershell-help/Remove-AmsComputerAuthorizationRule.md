---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Remove-AmsComputerAuthorizationRule

## SYNOPSIS
Removes a computer authorization rule

## SYNTAX

```
Remove-AmsComputerAuthorizationRule [-Id <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet permanently removes a computer authorization rule from the system

## EXAMPLES

### Example 1
```powershell
PS C:\> Remove-AmsComputerAuthorizationRule -Id '832a1b2c-a673-4e70-82cd-59c16675203e'
```

Removes the authorization rule specified by the ID

## PARAMETERS

### -Force
Removes the rule without confirmation

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
