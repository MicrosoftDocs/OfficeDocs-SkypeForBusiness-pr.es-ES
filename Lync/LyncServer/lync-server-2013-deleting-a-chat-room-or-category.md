---
title: 'Lync Server 2013: Eliminar un salón de chat o una categoría'
TOCTitle: Eliminar un salón de chat o una categoría
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48276350
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar un salón de chat o una categoría en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Los salones de Chat persistente se pueden eliminar. Si tiene un salón de chat que ya no se usa, puede deshabilitarlo. Para más información, vea [Habilitar o deshabilitar un salón de chat en Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Un administrador de Chat persistente puede consultar los salones de chat deshabilitados, y puede depurar periódicamente y eliminar de forma definitiva los salones de chat con el cmdlet **Remove-CsPersistentChatRoom** de Windows PowerShell.

Las categorías se pueden eliminar. Pero para eliminar una categoría, primero debe eliminar todos los salones de chat incluidos en ella o mover los salones de chat a una nueva categoría, y dejar esa categoría vacía para su eliminación. El Servidor de chat persistente no permite eliminar una categoría que contiene salones de chat. Para más información, vea [Mover un salón de chat de una categoría a otra en Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Para más información sobre cómo eliminar categorías vacías con la Interfaz de la línea de comandos Windows PowerShell, vea "Administrar salones" en [Configuración del servidor de chat persistente con cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para más información sobre salones y categorías de chat, vea [Configurar salones en Lync Server 2013](lync-server-2013-configure-rooms.md) y [Configurar categorías en Lync Server 2013](lync-server-2013-configure-categories.md) en la documentación sobre implementación.

