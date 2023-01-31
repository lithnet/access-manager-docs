---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Set-AmsGroup

## SYNOPSIS
Sets the properties of an AMS group

## SYNTAX

```
Set-AmsGroup -Id <String> [-Name <String>] [-Description <String>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet allows you to set the name and description of an AMS group

## EXAMPLES

### Example 1
```powershell
PS C:\> Set-AmsGroup -Id '0a6e38fc-6039-494a-8bc5-7e023fff8838' -Name 'New group name'
```

Set the name of an existing AMS group to a new name

### Example 2
```powershell
PS C:\> Get-AmsGroup -Name "My group" | Set-AmsGroup -Description 'My group description'
```

Get an existing AMS group by name and changes its description

## PARAMETERS

### -Description
The description of the group

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

### -Name
The name of the group

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

### System.String

## OUTPUTS

### Lithnet.AccessManager.PowerShell.GroupPSObject

## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
