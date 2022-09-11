---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Set-AmsDevice

## SYNOPSIS
Sets the properties of an AMS device

## SYNTAX

### Approve
```
Set-AmsDevice -Id <String> [-Approve] [<CommonParameters>]
```

### Reject
```
Set-AmsDevice -Id <String> [-Reject] [-Force] [<CommonParameters>]
```

### Enable
```
Set-AmsDevice -Id <String> [-Enable] [<CommonParameters>]
```

### Disable
```
Set-AmsDevice -Id <String> [-Disable] [<CommonParameters>]
```

### ExpirePassword
```
Set-AmsDevice -Id <String> [-ExpirePassword] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet allows you to approve, reject, enable, disable or expire a device's password.

## EXAMPLES

### Example 1
```powershell
PS C:\> Set-AmsDevice -Id '10e051a4-6f08-4ac1-9fa5-2d62297137c8' -Approve
```

Approves a device by its ID


### Example 2
```powershell
PS C:\> Get-AmsDevice -Name 'PC1' |  Set-AmsDevice -Reject
```

Gets a device by its name and rejects it


## PARAMETERS

### -Approve
Approves the device's registration request

```yaml
Type: SwitchParameter
Parameter Sets: Approve
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disable
Disables the device, preventing it from communicating with AMS

```yaml
Type: SwitchParameter
Parameter Sets: Disable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enable
Enables the device, allowing it to communicate with AMS

```yaml
Type: SwitchParameter
Parameter Sets: Enable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpirePassword
Indicates that the current password for the device should be marked as expired

```yaml
Type: SwitchParameter
Parameter Sets: ExpirePassword
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Rejects the device without prompting for confirmation

```yaml
Type: SwitchParameter
Parameter Sets: Reject
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

### -Reject
Rejects the device's registration request

```yaml
Type: SwitchParameter
Parameter Sets: Reject
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

### System.String

## OUTPUTS

### Lithnet.AccessManager.PowerShell.DevicePSObject

## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
