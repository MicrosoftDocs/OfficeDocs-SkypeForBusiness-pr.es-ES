---
title: 'Lync Server 2013: Habilitar o deshabilitar un salón de chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3ed23319631dd8ab51131fe9a8d7a9099e35d18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Habilitar o deshabilitar un salón de chat en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Si el tema de un salón de chat persistente ya no es relevante, puede deshabilitarlo para hacer que el salón de chat no esté disponible para los usuarios. Cuando un salón de chat está deshabilitado, todos los miembros se desconectan inmediatamente del salón. Después de deshabilitar un salón de chat, los usuarios no pueden volver a unirse o encontrarlo en las búsquedas del salón de chat.

Un administrador de chat persistente puede habilitar más tarde un salón de chat desactivado. Si un salón de chat se encuentra deshabilitado, se conservan su lista de pertenencia y otras opciones de configuración. Si vuelve a habilitar el salón, no es necesario que vuelva a crear la configuración de forma manual.

Si el historial del salón de chat persiste (la persistencia del historial del salón de chat es una configuración opcional en una categoría que se aplica a todas las salas de la categoría; el valor predeterminado es persistir, pero se puede desactivar si se establece la opción **Habilitar historial de chat** en falso), el contenido se conserva cuando el salón de chat está deshabilitado. Pero, dicho contenido no aparecerá en las búsquedas mientras el salón de chat permanezca deshabilitado. Si vuelve a habilitar el salón de chat, los usuarios podrán buscar mensajes publicados antes de que se deshabilitara el salón de chat.

Para obtener detalles sobre cómo deshabilitar y habilitar salones de chat con la interfaz de línea de comandos de Windows PowerShell, consulte "administración de la sala" en [configurar el servidor de chat persistente mediante cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md). Para deshabilitar un salón de chat, use un comando similar a este:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Para habilitar un salón de chat, establece la propiedad disabled en false:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Tenga en cuenta que los salones de chat no se pueden habilitar ni deshabilitar mediante el panel de control de Lync Server.

Para obtener más información sobre cómo configurar salones de chat, consulte [configurar salas en Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación de implementación.

</div>

<span> </span>

</div>

</div>

</div>

