---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsLocalAdminPassword

## SYNOPSIS
Gets the local admin password of the specified device

## SYNTAX

### Get password by computer name
```
Get-AmsLocalAdminPassword [-ComputerName] <String> [<CommonParameters>]
```

### Get password by device authority information
```
Get-AmsLocalAdminPassword -AuthorityDeviceId <String> -AuthorityId <String> -AuthorityType <AuthorityType>
 [<CommonParameters>]
```

## DESCRIPTION
This cmdlet gets the local admin password of the specified computer.

Note, this cmdlet is not subject to the authorization rules and audit events. Only AMS administrators can call this cmdlet.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsLocalAdminPassword -ComputerName "PC1"
```

Returns the local admin password for the computer named `PC1`

### Example 2
```powershell
PS C:\> Get-AmsLocalAdminPassword -ComputerName "DEV\SERVER1"
```

Returns the local admin password for the Active Dircetory computer named `SERVER1` int he `DEV` domain

### Example 3
```powershell
PS C:\> Get-AmsDevice -Name "macos12" |  Get-AmsLocalAdminPassword 
```

Returns the local admin password for the AMS-managed computer named `macos12`

## PARAMETERS

### -ComputerName
The name of the computer object. This can be a simple name like `PC1` or a fully qualified name like `DOMAIN\PC1`

```yaml
Type: String
Parameter Sets: Get password by computer name
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthorityDeviceId
The ID of the device

```yaml
Type: String
Parameter Sets: Get password by device authority information
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
Parameter Sets: Get password by device authority information
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
Parameter Sets: Get password by device authority information
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

### None

## OUTPUTS

### Lithnet.AccessManager.PowerShell.PasswordPSObject

## NOTES

## RELATED LINKS
