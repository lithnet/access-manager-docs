---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsComputerAuthorizationRule

## SYNOPSIS
Gets all the computer authorization rules, or a specific computer authorization rule by its ID

## SYNTAX

```
Get-AmsComputerAuthorizationRule [-Id <String>] [<CommonParameters>]
```

## DESCRIPTION
When called without any parameters, this cmdlet returns all the computer authorization rules currently on the server. When the ID parameter is specified, it returns the rule matching that ID.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsComputerAuthorizationRule
```

Returns all the computer authorization rules

### Example 2
```powershell
PS C:\> Get-AmsComputerAuthorizationRule -Id '42d15c63-e17f-4c3c-a61c-b338f9cf3984'
```

Returns the authorization rule specified by the provided ID

## PARAMETERS

### -Id
The unique ID of the rule

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

### Lithnet.AccessManager.PowerShell.ComputerAuthorizationRulePSObject
## NOTES

Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
