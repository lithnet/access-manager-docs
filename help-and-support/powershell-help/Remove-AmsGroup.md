---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Remove-AmsGroup

## SYNOPSIS
Removes an AMS group

## SYNTAX

```
Remove-AmsGroup -Id <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
Permanently removes an AMS group from the system

## EXAMPLES

### Example 1
```powershell
PS C:\> Remove-AmsGroup -Id 'd5e4ccde-454e-4d9b-9310-b0a8a256e150'
```

Removes the group by the specified ID

### Example 2
```powershell
PS C:\> Get-AmsGroup -Name "My group" | Remove-AmsGroup
```

Gets a group by its name, and removes it

## PARAMETERS

### -Force
Removes the group without prompting for confirmation

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
The ID of the group

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

### System.Void
## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
