---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsLocalAdminPasswordHistory

## SYNOPSIS
Gets the local admin password history of the specified device

## SYNTAX

```
Get-AmsLocalAdminPasswordHistory [-ComputerName] <String> [<CommonParameters>]
```

## DESCRIPTION
This cmdlet gets the local admin password history of the specified computer.

Note, this cmdlet is not subject to the authorization rules and audit events. Only AMS administrators can call this cmdlet.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsLocalAdminPasswordHistory -ComputerName 'PC1'
```

Returns the local admin password history for the computer named `PC1`

## PARAMETERS

### -ComputerName
The name of the computer object. This can be a simple name like `PC1` or a fully qualified name like `DOMAIN\PC1`

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Lithnet.AccessManager.PowerShell.PasswordPSObject

## NOTES

## RELATED LINKS
