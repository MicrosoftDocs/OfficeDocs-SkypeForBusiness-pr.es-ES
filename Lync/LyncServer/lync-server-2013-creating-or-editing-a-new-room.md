---
title: 'Lync Server 2013: Crear o editar un salón de chat nuevo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd0fdbce300f417764e093fec3acb8705b2d17b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="69362-102">Crear o editar un salón de chat nuevo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69362-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69362-103">_**Última modificación del tema:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="69362-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="69362-104">La configuración de los salones de chat persistentes es común para los usuarios; un administrador de chat persistente, por lo general, no configura ni administra salones de chat.</span><span class="sxs-lookup"><span data-stu-id="69362-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="69362-105">Los cmdlets de Windows PowerShell para administrar salas solo están disponibles para los administradores de **CsPersistentChatAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="69362-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="69362-106">Los usuarios que son **creadores** de cualquier categoría pueden usar el cliente de Lync para crear y administrar salas.</span><span class="sxs-lookup"><span data-stu-id="69362-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="69362-107">Los usuarios que se han designado como administradores de un salón de chat específico también pueden realizar la administración continuada de la sala, como editar las propiedades de la sala o la pertenencia.</span><span class="sxs-lookup"><span data-stu-id="69362-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="69362-108">Los administradores de chats persistentes también pueden ser creadores, y no están sujetos a las restricciones impuestas a los creadores.</span><span class="sxs-lookup"><span data-stu-id="69362-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="69362-109">De manera opcional, si es un administrador de chat persistente, puede usar una interfaz de usuario para crear y administrar salones de chat en lugar de usar cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69362-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="69362-110">Para ello, habilite SIP para el servidor de chat persistente y, a continuación, use el cliente de Lync para crear y administrar los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="69362-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="69362-111">Si desea crear un flujo de trabajo de administración de salas personalizado para los usuarios, puede establecer la propiedad **RoomManagementUrl** en la configuración del servidor de chat persistente para redirigir a los usuarios a la solución personalizada desde el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="69362-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="69362-112">Para obtener detalles sobre la configuración de salones de chat con la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salas" en [configurar el servidor de chat persistente mediante cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="69362-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="69362-113">Para obtener más información sobre cómo configurar salones de chat, consulte [configurar salas en Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="69362-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69362-114">El servidor de chat persistente permite a los usuarios crear y administrar el salón de chat para un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="69362-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="69362-115">Sin embargo, los usuarios no pueden crear ni administrar salones de chat en otros sitios dentro de la misma topología.</span><span class="sxs-lookup"><span data-stu-id="69362-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="69362-116">Asegúrese de especificar los creadores y administradores del salón de chat de todos los sitios de su organización.</span><span class="sxs-lookup"><span data-stu-id="69362-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="69362-117">Los usuarios que estén alojados en un equipo con la aplicación de Lync Server superviviente no pueden crear nuevos salones de chat o ver la tarjeta de la sala de las habitaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="69362-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

