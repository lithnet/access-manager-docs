---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Remove-AmsActiveDirectoryJitGroupCreationRule

## SYNOPSIS
Deletes a just-in-time Active Directory group creation rule

## SYNTAX

```
Remove-AmsActiveDirectoryJitGroupCreationRule -Id <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet deletes a just-in-time Active Directory group creation rule by its unique ID

## EXAMPLES

### Example 1
```
PS C:\> Remove-AmsActiveDirectoryJitGroupCreationRule -Id "12345678-1234-1234-1234-123456789012"
```

Deletes the JIT group creation rule with the specified ID

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation

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

Required: True
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

### Lithnet.AccessManager.PowerShell.AdJitCreationRulePSObject
## NOTES

## RELATED LINKS
