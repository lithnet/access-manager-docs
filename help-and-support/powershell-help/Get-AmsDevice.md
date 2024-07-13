---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsDevice

## SYNOPSIS
Gets AMS registered devices

## SYNTAX

### GetByName (Default)
```
Get-AmsDevice [[-Name] <String>] [-ApprovalState <ApprovalState>] [<CommonParameters>]
```

### GetById
```
Get-AmsDevice -Id <String> [-ApprovalState <ApprovalState>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet retrieves AMS devices from the server.
It can retrieve individual devices by name, by ID, and approval state.
When used without parameters, it will return all AMS devices

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsDevice
```

Returns all AMS registered devices

### Example 2
```powershell
PS C:\> Get-AmsDevice -Name "PC1"
```

Returns the AMS device named \`PC1\`

### Example 3
```powershell
PS C:\> Get-AmsDevice -ApprovalState Pending
```

Returns all AMS registered devices that are currently pending approval

### Example 4
```powershell
PS C:\> Get-AmsDevice -Id '800e470e-2af1-482c-a596-da730b075933'
```

Returns the AMS device with the specified ID

## PARAMETERS

### -ApprovalState
Returns only devices matching the specified approval state

```yaml
Type: ApprovalState
Parameter Sets: (All)
Aliases:
Accepted values: Pending, Approved, Rejected

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
Parameter Sets: GetById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the device

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
## OUTPUTS

### Lithnet.AccessManager.PowerShell.DevicePSObject
## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
