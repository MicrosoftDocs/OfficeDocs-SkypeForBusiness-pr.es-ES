---
title: 'Lync Server 2013: deshabilitar o habilitar un salón de chat'
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
ms.openlocfilehash: 088ea4f3441716efdec748222e9aefeca9643a77
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528967"
---
# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Deshabilitar o habilitar un salón de chat en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Si el tema de un salón de chat persistente ya no es relevante, puede deshabilitarlo para que el salón de chat no esté disponible para los usuarios. Cuando se deshabilita una salón de chat, todos los miembros se desconectan inmediatamente del salón. Después de deshabilitar un salón de chat, los usuarios no pueden unirse a él o encontrarlo en las búsquedas de salones de chat.

Un administrador de chat persistente puede habilitar más adelante un salón de chat deshabilitado. Si un salón de chat está deshabilitado, su lista de pertenencia y otras configuraciones se conservan. Si vuelve a habilitar el salón, necesitará volver a crear manualmente la configuración.

Si el historial del salón de chat persiste (la persistencia del historial del salón de chat es una configuración opcional en una categoría que se aplica a todos los salones de la categoría; la persistencia es el valor predeterminado, pero puede desactivarse configurando la **habilitación del historial del chat** en falso), el contenido se conserva cuando se deshabilita el salón de chat. No obstante, ese contenido no aparecerá en las búsquedas durante el tiempo que el salón de chat permanezca deshabilitado. Si más tarde habilita el salón de chat, los usuarios pueden buscar mensajes que se publicaron antes de que lo deshabilitara.

Para obtener información detallada acerca de la deshabilitación y habilitación de salones de chat mediante la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salones" en [Configuring persistent chat Server by Using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md). Para deshabilitar un salón de chat, usa un comando similar al siguiente:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Para habilitar un salón de chat, establezca la propiedad disabled en false:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Tenga en cuenta que los salones de chat no se pueden habilitar o deshabilitar mediante el panel de control de Lync Server.

Para obtener más información sobre cómo configurar salones de chat, vea [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación sobre implementación.

</div>

<span> </span>

</div>

</div>

</div>

