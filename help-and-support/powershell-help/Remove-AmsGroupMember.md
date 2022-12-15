---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Remove-AmsGroupMember

## SYNOPSIS
Removes one or more members of an AMS group

## SYNTAX

```
Remove-AmsGroupMember -Id <String> [-Devices <Object[]>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet removes one or more members from a group

## EXAMPLES

### Example 1
```powershell
PS C:\> Remove-AmsGroupMember -Id '0c1ecad4-3581-42c5-8501-22f13559e418' -Devices '0b5cffd6-d22f-49d7-b5e2-4631997a7416'
```

Removes a device by its ID from a group by its ID

### Example 2
```powershell
PS C:\> Remove-AmsGroupMember -Id '0c1ecad4-3581-42c5-8501-22f13559e418'
```

Removes all members of the group

### Example 3
```powershell
PS C:\> Get-AmsGroup -Name "My group" | Remove-AmsGroupMember -Devices '0b5cffd6-d22f-49d7-b5e2-4631997a7416'
```

Gets a group by name, and removes a specific member by its known ID

### Example 4
```powershell
PS C:\> Get-AmsGroup -Name "My group" | Remove-AmsGroupMember -Devices (Get-AmsDevice -Name 'PC1')
```

Gets a group by name, and removes a specific member by retrieving the object by its name

## PARAMETERS

### -Devices
A list of IDs or device objects to remove from the group

```yaml
Type: Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
When removing all members from the group, this parameter indicates that the members should be removed without any confirmation prompt

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
