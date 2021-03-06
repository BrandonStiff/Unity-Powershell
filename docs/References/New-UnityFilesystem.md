---
external help file: Unity-Powershell-help.xml
online version: https://github.com/equelin/Unity-Powershell
schema: 2.0.0
---

# New-UnityFilesystem

## SYNOPSIS
Creates a Unity Filesystem.

## SYNTAX

```
New-UnityFilesystem [-session <Object>] [-Name] <String[]> [-Description <String>] [-snapSchedule <String>]
 [-isSnapSchedulePaused <Boolean>] -Pool <String> -nasServer <String>
 -supportedProtocols <FSSupportedProtocolEnum> [-isFLREnabled <String>] [-isThinEnabled <String>]
 -Size <UInt64> [-hostIOSize <HostIOSizeEnum>] [-isCacheDisabled <Boolean>] [-accessPolicy <AccessPolicyEnum>]
 [-poolFullPolicy <ResourcePoolFullPolicyEnum>] [-tieringPolicy <TieringPolicyEnum>]
 [-isCIFSSyncWritesEnabled <Boolean>] [-isCIFSOpLocksEnabled <Boolean>] [-isCIFSNotifyOnWriteEnabled <Boolean>]
 [-isCIFSNotifyOnAccessEnabled <Boolean>] [-cifsNotifyOnChangeDirDepth <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Creates a Unity Filesystem.
You need to have an active session with the array.

## EXAMPLES

### -------------------------- EXEMPLE 1 --------------------------
```
New-UnityFilesystem -Name 'FS01' -Pool 'pool_1' -Size 10GB -nasServer 'nas_1' -supportedProtocols 'CIFS'
```

Create CIFS filesystem named 'FS01' on pool 'pool_1' and with a size of '10GB' bytes

## PARAMETERS

### -session
Specify an UnitySession Object.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: ($global:DefaultUnitySession | where-object {$_.IsConnected -eq $true})
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Filesystem Name

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Description
Filesystem Description

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

### -snapSchedule
ID of a protection schedule to apply to the filesystem

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

### -isSnapSchedulePaused
Is assigned snapshot schedule is paused ?
(Default is false)

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pool
Filesystem Pool ID

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

### -nasServer
Filesystem nasServer ID

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

### -supportedProtocols
Filesystem supported protocols

```yaml
Type: FSSupportedProtocolEnum
Parameter Sets: (All)
Aliases: 
Accepted values: NFS, CIFS, Multiprotocol

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -isFLREnabled
Indicates whether File Level Retention (FLR) is enabled for the file system

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -isThinEnabled
Indicates whether to enable thin provisioning for file system.
Default is $True

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -Size
Filesystem Size

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -hostIOSize
Typical write I/O size from the host to the file system

```yaml
Type: HostIOSizeEnum
Parameter Sets: (All)
Aliases: 
Accepted values: General_8K, Exchange2007, Oracle, SQLServer, VMwareHorizon, SAP, General_16K, General_32K, Exchange2010, Exchange2013, SharePoint, General_64K

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -isCacheDisabled
Indicates whether caching is disabled

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -accessPolicy
Access policy

```yaml
Type: AccessPolicyEnum
Parameter Sets: (All)
Aliases: 
Accepted values: Native, Unix, Windows

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -poolFullPolicy
Behavior to follow when pool is full and a write to this filesystem is attempted

```yaml
Type: ResourcePoolFullPolicyEnum
Parameter Sets: (All)
Aliases: 
Accepted values: Delete_All_Snaps, Fail_Writes

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -tieringPolicy
Filesystem tiering policy

```yaml
Type: TieringPolicyEnum
Parameter Sets: (All)
Aliases: 
Accepted values: Autotier_High, Autotier, Highest, Lowest, No_Data_Movement, Mixed

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -isCIFSSyncWritesEnabled
Indicates whether the CIFS synchronous writes option is enabled for the file system

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -isCIFSOpLocksEnabled
Indicates whether opportunistic file locks are enabled for the file system

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -isCIFSNotifyOnWriteEnabled
Indicates whether the system generates a notification when the file system is written to

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -isCIFSNotifyOnAccessEnabled
Indicates whether the system generates a notification when a user accesses the file system

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -cifsNotifyOnChangeDirDepth
Indicates the lowest directory level to which the enabled notifications apply, if any

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Indicate that the cmdlet is run only to display the changes that would be made and actually no objects are modified.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
If the value is $true, indicates that the cmdlet asks for confirmation before running.
If the value is $false, the cmdlet runs without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Written by Erwan Quelin under MIT licence - https://github.com/equelin/Unity-Powershell/blob/master/LICENSE

## RELATED LINKS

[https://github.com/equelin/Unity-Powershell](https://github.com/equelin/Unity-Powershell)

