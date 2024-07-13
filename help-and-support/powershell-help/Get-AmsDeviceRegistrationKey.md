---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsDeviceRegistrationKey

## SYNOPSIS
Get AMS device registration keys

## SYNTAX

### GetByName (Default)
```
Get-AmsDeviceRegistrationKey [[-Name] <String>] [<CommonParameters>]
```

### GetById
```
Get-AmsDeviceRegistrationKey -Id <String> [<CommonParameters>]
```

### GetByKey
```
Get-AmsDeviceRegistrationKey -Key <String> [<CommonParameters>]
```

## DESCRIPTION
This cmdlet allows you to retrieve a device registration key by name, ID, or the key itself.
When used without parameters, it will return all registration keys.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsDeviceRegistrationKey
```

Returns all registration keys

### Example 2
```powershell
PS C:\> Get-AmsDeviceRegistrationKey -Key XXXXXXXXXXXXXXXXXXXXXXXXX
```

Returns the registration key object that is represented by the specified key value

### Example 3
```powershell
PS C:\> Get-AmsDeviceRegistrationKey -Name 'Linux key'
```

Returns the registration key object that is represented by the specified name

### Example 4
```powershell
PS C:\> Get-AmsDeviceRegistrationKey -Id 'd54bdb4b-75de-4114-b2c7-305320222b9e'
```

Returns the registration key object that is represented by the specified ID

## PARAMETERS

### -Id
The ID of the key

```yaml
Type: String
Parameter Sets: GetById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Key
The key value

```yaml
Type: String
Parameter Sets: GetByKey
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the key

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

### System.String
## OUTPUTS

### Lithnet.AccessManager.PowerShell.RegistrationKeyPSObject
## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
