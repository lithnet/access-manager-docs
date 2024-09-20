---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsActiveDirectoryJitGroupCreationRule

## SYNOPSIS
The cmdlet retrieves just-in-time Active Directory group creation rules

## SYNTAX

### NoParameters (Default)
```
Get-AmsActiveDirectoryJitGroupCreationRule [<CommonParameters>]
```

### GetById
```
Get-AmsActiveDirectoryJitGroupCreationRule [-Id <String>] [<CommonParameters>]
```

## DESCRIPTION
Use this cmdlet to retrieve the list of just-in-time Active Directory group creation rules, or a specific rule by its unique ID

## EXAMPLES

### Example 1
```
PS C:\>	Get-AmsActiveDirectoryJitGroupCreationRule
```

Using the cmdlet without any parameters will return all the JIT group creation rules

### Example 2
```
PS C:\>	Get-AmsActiveDirectoryJitGroupCreationRule -Id "12345678-1234-1234-1234-123456789012"
```

Using the cmdlet with the -Id parameter will return the JIT group creation rule with the specified ID

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
## OUTPUTS

### Lithnet.AccessManager.PowerShell.AdJitCreationRulePSObject
## NOTES

## RELATED LINKS
