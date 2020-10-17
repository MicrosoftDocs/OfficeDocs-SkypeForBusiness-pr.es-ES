---
title: 'Lync Server 2013: deshabilitar o habilitar un salón de chat'
description: 'Lync Server 2013: deshabilitar o habilitar un salón de chat.'
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
ms.openlocfilehash: 9b81ce2614cebcf554c0390369068d8fd8b8f932
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568156"
---
# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="903c3-103">Deshabilitar o habilitar un salón de chat en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="903c3-103">Disabling or enabling a chat room in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="903c3-104">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="903c3-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="903c3-105">Si el tema de un salón de chat persistente ya no es relevante, puede deshabilitarlo para que el salón de chat no esté disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="903c3-105">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="903c3-106">Cuando se deshabilita una salón de chat, todos los miembros se desconectan inmediatamente del salón.</span><span class="sxs-lookup"><span data-stu-id="903c3-106">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="903c3-107">Después de deshabilitar un salón de chat, los usuarios no pueden unirse a él o encontrarlo en las búsquedas de salones de chat.</span><span class="sxs-lookup"><span data-stu-id="903c3-107">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="903c3-108">Un administrador de chat persistente puede habilitar más adelante un salón de chat deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="903c3-108">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="903c3-109">Si un salón de chat está deshabilitado, su lista de pertenencia y otras configuraciones se conservan.</span><span class="sxs-lookup"><span data-stu-id="903c3-109">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="903c3-110">Si vuelve a habilitar el salón, necesitará volver a crear manualmente la configuración.</span><span class="sxs-lookup"><span data-stu-id="903c3-110">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="903c3-p103">Si el historial del salón de chat persiste (la persistencia del historial del salón de chat es una configuración opcional en una categoría que se aplica a todos los salones de la categoría; la persistencia es el valor predeterminado, pero puede desactivarse configurando la **habilitación del historial del chat** en falso), el contenido se conserva cuando se deshabilita el salón de chat. No obstante, ese contenido no aparecerá en las búsquedas durante el tiempo que el salón de chat permanezca deshabilitado. Si más tarde habilita el salón de chat, los usuarios pueden buscar mensajes que se publicaron antes de que lo deshabilitara.</span><span class="sxs-lookup"><span data-stu-id="903c3-p103">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled. However, that content will not appear in searches during the time that the chat room remains in a disabled state. If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="903c3-114">Para obtener información detallada acerca de la deshabilitación y habilitación de salones de chat mediante la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salones" en [Configuring persistent chat Server by Using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="903c3-114">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="903c3-115">Para deshabilitar un salón de chat, usa un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="903c3-115">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="903c3-116">Para habilitar un salón de chat, establezca la propiedad disabled en false:</span><span class="sxs-lookup"><span data-stu-id="903c3-116">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="903c3-117">Tenga en cuenta que los salones de chat no se pueden habilitar o deshabilitar mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="903c3-117">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="903c3-118">Para obtener más información sobre cómo configurar salones de chat, vea [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="903c3-118">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

