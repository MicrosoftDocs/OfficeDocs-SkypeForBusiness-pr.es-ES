---
title: Administrar categorías
TOCTitle: Administrar categorías
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48274584
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar categorías

 

_**Última modificación del tema:** 2012-10-06_

Para crear una nueva categoría de Servidor de chat persistente

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

> [!IMPORTANT]  
> PersistentChatPoolFqdn es necesario solo si hay más de un Grupo de servidores de chat persistente.



Para realizar cambios en la categoría de Servidor de chat persistente existente

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

Windows PowerShell: pueden establecer simultáneamente AllowedMembers, DeniedMembers y Creators. Creators debería ser el subconjunto de AllowedMembers menos DeniedMembers. También puede establecer las propiedades de una categoría al mismo tiempo que los miembros y los creadores.

## Crear, obtener, establecer o quitar una categoría

Para crear una nueva categoría

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

Para obtener una categoría

    Get-CsPersistentChatCategory -Identity <String>

o

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

Para establecer una categoría

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

o

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

Para quitar una categoría

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

o

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

