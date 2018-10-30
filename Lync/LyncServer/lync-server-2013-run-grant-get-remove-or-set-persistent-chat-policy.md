---
title: "Ejecutar, conceder, obtener, quitar o configurar directiva de chat persistente"
TOCTitle: Ejecutar, conceder, obtener, quitar o configurar directiva de chat persistente
ms:assetid: 39ccdbe8-fb3d-47bc-96e2-9486b6d317e0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204810(v=OCS.15)
ms:contentKeyID: 48274961
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ejecutar, conceder, obtener, quitar o configurar directiva de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-01_

Para crear una nueva directiva de Chat persistente

    New-CsPersistentChatPolicy -Identity <XdsIdentity> [-Enable <Switch Parameter>] [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>] [-InMemory <Switch Parameter>]

Para conceder una directiva de Chat persistente

    Grant-CsPersistentChatPolicy -Identity <UserIdParameter> -PolicyName <String> [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Para obtener una directiva de Chat persistente

    Get-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Filter <String>] [-LocalStore <Switch Parameter>]

Para eliminar una directiva de Chat persistente

    Remove-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>]

Para establecer una directiva de Chat persistente

    Set-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Instance < PSObject>]

