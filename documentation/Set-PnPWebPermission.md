---
Module Name: 
title: Set-PnPWebPermission
schema: 2.0.0
applicable: SharePoint Online
external help file: PnP.PowerShell.dll-Help.xml
online version: https://pnp.github.io/powershell/cmdlets/Set-PnPWebPermission.html
---
 
# Set-PnPWebPermission

## SYNOPSIS
Sets a web permissions

## SYNTAX

```powershell
Set-PnPWebPermission -Group <GroupPipeBind> [-Identity <WebPipeBind>] [-AddRole <String[]>] [-RemoveRole <String[]>]
```

```powershell
Set-PnPWebPermission -User <String> [-Identity <WebPipeBind>]  [-AddRole <String[]>] [-RemoveRole <String[]>]
```


## DESCRIPTION
This cmdlet adds permissions to a user or a group or removes permissions from a user or a group.

## EXAMPLES

### EXAMPLE 1
```powershell
Set-PnPWebPermission -User "user@contoso.com" -AddRole "Contribute"
```

Adds the "Contribute" permission role to the specified user in the current web.

### EXAMPLE 2
```powershell
Set-PnPWebPermission -Group "Project Managers" -AddRole "Contribute"
```

Adds the "Contribute" permission role to the "Project Managers" group in the current web.

### EXAMPLE 3
```powershell
Set-PnPWebPermission -Identity projectA -User "user@contoso.com" -AddRole "Contribute"
```

Adds the "Contribute" permission role to the user "user@contoso.com" in the subweb of the current web with site relative url "projectA"

### EXAMPLE 4
```powershell
Set-PnPWebPermission -User "user@contoso.com" -AddRole "Custom Role 1","Custom Role 2"
```

Adds the specified permission roles to the user "user@contoso.com" in the current web

## PARAMETERS

### -User
The name of the user.

```yaml
Type: String
Parameter Sets: Set user permissions

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Group
The name of the group.

```yaml
Type: String
Parameter Sets: Set group permissions

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddRole
The name of the permission level to add to the specified user or group.

```yaml
Type: String[]
Parameter Sets: (All)

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveRole
The name of the permission level to remove from the specified user or group.

```yaml
Type: String[]
Parameter Sets: (All)

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
The guid or site relative url of the web to use

```yaml
Type: Guid
Parameter Sets: (All)

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


## RELATED LINKS

[Microsoft 365 Patterns and Practices](https://aka.ms/m365pnp)

