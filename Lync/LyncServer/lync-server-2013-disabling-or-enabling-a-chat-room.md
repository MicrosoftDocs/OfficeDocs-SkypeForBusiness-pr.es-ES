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

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="fd64e-102">Habilitar o deshabilitar un salón de chat en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd64e-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd64e-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="fd64e-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="fd64e-104">Si el tema de un salón de chat persistente ya no es relevante, puede deshabilitarlo para hacer que el salón de chat no esté disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fd64e-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="fd64e-105">Cuando un salón de chat está deshabilitado, todos los miembros se desconectan inmediatamente del salón.</span><span class="sxs-lookup"><span data-stu-id="fd64e-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="fd64e-106">Después de deshabilitar un salón de chat, los usuarios no pueden volver a unirse o encontrarlo en las búsquedas del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="fd64e-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="fd64e-107">Un administrador de chat persistente puede habilitar más tarde un salón de chat desactivado.</span><span class="sxs-lookup"><span data-stu-id="fd64e-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="fd64e-108">Si un salón de chat se encuentra deshabilitado, se conservan su lista de pertenencia y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="fd64e-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="fd64e-109">Si vuelve a habilitar el salón, no es necesario que vuelva a crear la configuración de forma manual.</span><span class="sxs-lookup"><span data-stu-id="fd64e-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="fd64e-110">Si el historial del salón de chat persiste (la persistencia del historial del salón de chat es una configuración opcional en una categoría que se aplica a todas las salas de la categoría; el valor predeterminado es persistir, pero se puede desactivar si se establece la opción **Habilitar historial de chat** en falso), el contenido se conserva cuando el salón de chat está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="fd64e-110">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="fd64e-111">Pero, dicho contenido no aparecerá en las búsquedas mientras el salón de chat permanezca deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="fd64e-111">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="fd64e-112">Si vuelve a habilitar el salón de chat, los usuarios podrán buscar mensajes publicados antes de que se deshabilitara el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="fd64e-112">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="fd64e-113">Para obtener detalles sobre cómo deshabilitar y habilitar salones de chat con la interfaz de línea de comandos de Windows PowerShell, consulte "administración de la sala" en [configurar el servidor de chat persistente mediante cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="fd64e-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="fd64e-114">Para deshabilitar un salón de chat, use un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="fd64e-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="fd64e-115">Para habilitar un salón de chat, establece la propiedad disabled en false:</span><span class="sxs-lookup"><span data-stu-id="fd64e-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="fd64e-116">Tenga en cuenta que los salones de chat no se pueden habilitar ni deshabilitar mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd64e-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="fd64e-117">Para obtener más información sobre cómo configurar salones de chat, consulte [configurar salas en Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="fd64e-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

