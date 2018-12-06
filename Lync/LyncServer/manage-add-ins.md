---
title: Administrar complementos
TOCTitle: Administrar complementos
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48276467
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar complementos

 

_**Última modificación del tema:** 2012-10-06_

Para crear un nuevo complemento Servidor de chat persistente

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

## Crear obtener, configurar o quitar un complemento

Para crear un nuevo complemento

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

> [!IMPORTANT]  
> PersistentChatPoolFqdn &lt;String&gt; es necesario solo si hay más de un Grupo de servidores de chat persistente.



Para obtener un complemento

    Get-CsPersistentChatAddin -Identity <String>]

o

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

Para configurar un complemento

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

o

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

Para quitar un complemento

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

o

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

