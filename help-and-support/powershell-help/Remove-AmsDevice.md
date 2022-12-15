---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Remove-AmsDevice

## SYNOPSIS
Removes an AMS device

## SYNTAX

```
Remove-AmsDevice -Id <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet permanently removes a device from the AMS system, and deletes any password history, authentication certificates, and group membership.

## EXAMPLES

### Example 1
```powershell
PS C:\> Remove-AmsDevice -Id '952105e9-e7de-499d-98f5-0133deb31d4a'
```

Removes a device by its known ID

### Example 1
```powershell
PS C:\> Get-AmsDevice -Name "PC1" | Remove-AmsDevice
```

Get a device named `PC1` and permanently deletes it

## PARAMETERS

### -Force
Removes the device without any confirmation prompts

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
The unique ID of the device

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
