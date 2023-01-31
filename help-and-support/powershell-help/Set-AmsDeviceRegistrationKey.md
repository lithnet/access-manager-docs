---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Set-AmsDeviceRegistrationKey

## SYNOPSIS
Sets the properties of a device registration key

## SYNTAX

### None (Default)
```
Set-AmsDeviceRegistrationKey -Id <String> [-Name <String>] [-ActivationLimit <Int32>] [-ResetActivationCount]
 [<CommonParameters>]
```

### EnableApprovalRequired
```
Set-AmsDeviceRegistrationKey -Id <String> [-Name <String>] [-Enable] [-ActivationLimit <Int32>]
 [-ApprovalRequired] [-ResetActivationCount] [<CommonParameters>]
```

### EnableApprovalNotRequired
```
Set-AmsDeviceRegistrationKey -Id <String> [-Name <String>] [-Enable] [-ActivationLimit <Int32>]
 [-ApprovalNotRequired] [-ResetActivationCount] [<CommonParameters>]
```

### DisableApprovalRequired
```
Set-AmsDeviceRegistrationKey -Id <String> [-Name <String>] [-Disable] [-ActivationLimit <Int32>]
 [-ApprovalRequired] [-ResetActivationCount] [<CommonParameters>]
```

### DisableApprovalNotRequired
```
Set-AmsDeviceRegistrationKey -Id <String> [-Name <String>] [-Disable] [-ActivationLimit <Int32>]
 [-ApprovalNotRequired] [-ResetActivationCount] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet allows you to set the properties of a device registration key

## EXAMPLES

### Example 1
```powershell
PS C:\> Set-AmsDeviceRegistrationKey -Id 'b88313dd-fafb-406f-8909-cac0c17c58e3' -Name "My new name" -ResetActivationCount
```

Changes the name of an activation key and resets its activation count

### Example 2
```powershell
PS C:\> Get-AmsDeviceRegistrationKey -Name "Head office device key" | Set-AmsDeviceRegistrationKey -Disable
```

Gets a registration key by its name and disables it.

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

### -ApprovalNotRequired
Specifies that devices can register without additional approval

```yaml
Type: SwitchParameter
Parameter Sets: EnableApprovalNotRequired, DisableApprovalNotRequired
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApprovalRequired
Specifies that administrator approval is required for devices using this key

```yaml
Type: SwitchParameter
Parameter Sets: EnableApprovalRequired, DisableApprovalRequired
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disable
Indicates if the key should be disabled

```yaml
Type: SwitchParameter
Parameter Sets: DisableApprovalRequired, DisableApprovalNotRequired
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enable
Indicates if the key should be enabled

```yaml
Type: SwitchParameter
Parameter Sets: EnableApprovalRequired, EnableApprovalNotRequired
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
The ID of the key

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
The name of the key

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

### -ResetActivationCount
Specifies if the activation count of this key should be reset

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Lithnet.AccessManager.PowerShell.RegistrationKeyPSObject

## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
