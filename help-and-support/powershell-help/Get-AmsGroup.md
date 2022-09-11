---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsGroup

## SYNOPSIS
Gets AMS groups

## SYNTAX

### GetByName (Default)
```
Get-AmsGroup [[-Name] <String>] [<CommonParameters>]
```

### GetBySid
```
Get-AmsGroup -SecurityIdentifier <String> [<CommonParameters>]
```

### GetById
```
Get-AmsGroup -Id <String> [<CommonParameters>]
```

## DESCRIPTION
This cmdlet gets AMS groups by their name, SID, or ID value. When used without parameters, it returns all AMS groups

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsGroup
```

Gets all AMS groups

### Example 2
```powershell
PS C:\> Get-AmsGroup -Id 'ccf95e2b-e9c0-49b4-b810-c959d5e49e06'
```

Gets the AMS group by the specified ID

### Example 3
```powershell
PS C:\> Get-AmsGroup -SecurityIdentifier 'S-1-4096-2-1'
```

Gets the AMS group by the specified SID

### Example 4
```powershell
PS C:\> Get-AmsGroup -Name 'All linux devices'
```

Gets the AMS group by the specified name

## PARAMETERS

### -Id
The ID of the group

```yaml
Type: String
Parameter Sets: GetById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the group

```yaml
Type: String
Parameter Sets: GetByName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityIdentifier
The security identifier of the group

```yaml
Type: String
Parameter Sets: GetBySid
Aliases:

Required: True
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

### Lithnet.AccessManager.PowerShell.GroupPSObject

## NOTES

## RELATED LINKS
