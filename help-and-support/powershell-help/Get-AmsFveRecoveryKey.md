---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsFveRecoveryKey

## SYNOPSIS
Gets the full-volume encryption keys of the specified device

## SYNTAX

### Get full-volume encryption keys by computer name (Default)
```
Get-AmsFveRecoveryKey [-ComputerName] <String> [<CommonParameters>]
```

### Get full-volume encryption keys by device authority information
```
Get-AmsFveRecoveryKey -AuthorityDeviceId <String> -AuthorityId <String> -AuthorityType <AuthorityType>
 [<CommonParameters>]
```

## DESCRIPTION
This cmdlet gets the full-volume encryption keys (e.g., BitLocker keys) of the specified computer.

Note, this cmdlet is not subject to the authorization rules and audit events. Only AMS administrators can call this cmdlet.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsFveRecoveryKey -ComputerName "PC1"
```

Returns the full-volume encryption keys for the computer named `PC1`

### Example 2
```powershell
PS C:\> Get-AmsFveRecoveryKey -ComputerName "DEV\SERVER1"
```

Returns the full-volume encryption keys for the Active Dircetory computer named `SERVER1` int he `DEV` domain

### Example 3
```powershell
PS C:\> Get-AmsDevice -Name "macos12" |  Get-AmsFveRecoveryKey
```

Returns the full-volume encryption keys for the AMS-managed computer named `macos12`

## PARAMETERS

### -AuthorityDeviceId
The ID of the device

```yaml
Type: String
Parameter Sets: Get full-volume encryption keys by device authority information
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthorityId
The device's Authority

```yaml
Type: String
Parameter Sets: Get full-volume encryption keys by device authority information
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthorityType
The authority type

```yaml
Type: AuthorityType
Parameter Sets: Get full-volume encryption keys by device authority information
Aliases:
Accepted values: None, ActiveDirectory, AzureActiveDirectory, Ams

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
The name of the computer object. This can be a simple name like `PC1` or a fully qualified name like `DOMAIN\PC1`

```yaml
Type: String
Parameter Sets: Get full-volume encryption keys by computer name
Aliases:

Required: True
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

### Lithnet.AccessManager.PowerShell.FveRecoveryKeyPSObject

## NOTES

## RELATED LINKS
