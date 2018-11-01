---
title: Administrar salones
TOCTitle: Administrar salones
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48276790
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar salones

 

_**Última modificación del tema:** 2013-02-21_

Para crear un salón nuevo de Servidor de chat persistente

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

> [!IMPORTANT]  
> -PersistentChatPoolFqdn no es necesario si se cumple una de las siguientes acciones:
> <ul>
> <li><p>Hay un solo Grupo de servidores de chat persistente.</p></li>
> <li><p>Proporciona un poolFqdn a la categoría.</p></li>
> <li><p>Proporciona un poolFqdn para agregar un salón.</p></li>
> </ul>


Realizar cambios en una salón existente de Servidor de chat persistente

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

Windows PowerShell: los miembros, administradores y moderadores pueden establecerse de manera simultánea. Deben estar en el subconjunto de AllowedMembers menos DeniedMembers de la categoría de host. Un salón que es type=normal no puede incluir moderadores.

## Crear, obtener, configurar, borrar o quitar un salón

Para crear un salón nuevo

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

Para configurar un salón

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

Para obtener un salón

    Get-CsPersistentChatRoom -Identity <String>

o

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

donde el filtro–solo admita el nombre y la descripción y ayude a buscar salones cuyos nombres o descripciones coincidan con la cadena de la palabra clave. PoolFqdn busca en un determinado Grupo de servidores de chat persistente.

Para borrar un salón y borrar los mensajes de un salón

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

o

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

Para quitar un salón

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

o

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

