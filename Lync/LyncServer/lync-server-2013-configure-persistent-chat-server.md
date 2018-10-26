---
title: 'Lync Server 2013: Configurar el servidor de chat persistente'
TOCTitle: Configurar el servidor de chat persistente
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48275894
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar el servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

Para crear una nueva configuración del Chat persistente

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Para obtener la configuración de Chat persistente

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

Para quitar una configuración de Chat persistente

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

Para establecer una configuración de Chat persistente

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

En Lync Server 2013, todo el tráfico del servicio web es compatible con el Lync Server 2013, Servidores front-end. Por lo tanto, la dirección de gcweb01 en Servidor de chat persistente no es necesaria. Aún admitimos el acceso a servicios web internos, ya que seguimos proporcionando el servicio de carga y descarga de archivos únicamente para el sitio web *interno* ; (no para el sitio web *externo* para usuarios remotos).

