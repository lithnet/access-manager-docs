---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Add-AmsGroupMember

## SYNOPSIS
Adds a member to an AMS group

## SYNTAX

```
Add-AmsGroupMember -Id <String> -Devices <Object[]> [<CommonParameters>]
```

## DESCRIPTION
This cmdlet adds an AMS device to an AMS group

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsGroup -Name 'My group' | Add-AmsGroupMember -Devices (Get-AmsDevice -Name 'PC1')
```

This example gets the AMS group named `My group` and pipes it through to the `Add-AmsGroupMember` cmdlet which gets the device named `PC1` to add to the group

## PARAMETERS

### -Devices
A list of device IDs, or device objects, obtained from the `Get-AmsDevice` cmdlet.

```yaml
Type: Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
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

## RELATED LINKS
