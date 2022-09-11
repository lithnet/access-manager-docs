---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# New-AmsDeviceRegistrationKey

## SYNOPSIS
Creates a new device registration key

## SYNTAX

```
New-AmsDeviceRegistrationKey -Name <String> [-Disable] [-ActivationLimit <Int32>] [-ApprovalRequired]
 [<CommonParameters>]
```

## DESCRIPTION
This cmdlet creates a new device registration key, and optionally allows you to set an activation limit, and specify if device approval is required

## EXAMPLES

### Example 1
```powershell
PS C:\> New-AmsDeviceRegistrationKey -Name "macOS device registration key"
```

Creates a new registration key with the specified name

### Example 2
```powershell
PS C:\> New-AmsDeviceRegistrationKey -Name "macOS device registration key" -ActivationLimit 1
```

Creates a new registration key with the specified name, that can only be used for a single activation

### Example 3
```powershell
PS C:\> New-AmsDeviceRegistrationKey -Name "macOS device registration key" -ActivationLimit 1 -ApprovalRequired
```

Creates a new registration key with the specified name, that can only be used for a single activation, and requires that an AMS administrator approve the device before it can connect to the AMS server

## PARAMETERS

### -ActivationLimit
Specifies the number of times the key can be used

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApprovalRequired
Specifies if administrator approval is required for devices using this key

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

### -Disable
Indicates if the key should be created in a disabled state

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

### -Name
The name of the key

```yaml
Type: String
Parameter Sets: (All)
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

### Lithnet.AccessManager.PowerShell.RegistrationKeyPSObject

## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
