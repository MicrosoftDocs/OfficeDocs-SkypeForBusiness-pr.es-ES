---
title: 'Lync Server 2013: crear o editar un salón nuevo'
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
ms.openlocfilehash: 564db7b9d1bfaab00e51628377f330da05af17e8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="122da-102">Crear o editar un salón nuevo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="122da-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="122da-103">_**Última modificación del tema:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="122da-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="122da-104">La configuración de salones de chat persistente suele ser controlada por los usuarios; un administrador de chat persistente no suele configurar ni administrar salones de chat.</span><span class="sxs-lookup"><span data-stu-id="122da-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="122da-105">Los cmdlets de Windows PowerShell para administrar salas solo están disponibles para los administradores de **CsPersistentChatAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="122da-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="122da-106">Los usuarios que son **creadores** en una categoría concreta pueden usar el cliente Lync para crear y administrar salones.</span><span class="sxs-lookup"><span data-stu-id="122da-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="122da-107">Los usuarios designados como responsables de un salón de chat específico también pueden realizar tareas de administración continuas en el salón, por ejemplo, modificar las propiedades o los miembros del salón.</span><span class="sxs-lookup"><span data-stu-id="122da-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="122da-108">Los administradores de chat persistente también pueden ser creadores y no están sujetos a las restricciones impuestas en los creadores.</span><span class="sxs-lookup"><span data-stu-id="122da-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="122da-109">Opcionalmente, si es un administrador de chat persistente, puede usar una interfaz de usuario para crear y administrar salones de chat en lugar de usar los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="122da-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="122da-110">Para ello, habilite SIP para el servidor de chat persistente y, a continuación, use el cliente Lync para crear y administrar salones de chat.</span><span class="sxs-lookup"><span data-stu-id="122da-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="122da-111">Si desea crear un flujo de trabajo de administración de salones personalizado para sus usuarios, puede establecer la propiedad **RoomManagementUrl** en la configuración del servidor de chat persistente para redirigir a los usuarios a la solución personalizada desde el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="122da-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="122da-112">Para obtener más información sobre cómo configurar salones de chat mediante la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salones" en [Configuring persistent chat Server by Using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="122da-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="122da-113">Para obtener más información sobre cómo configurar salones de chat, vea [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="122da-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="122da-114">El servidor de chat persistente permite a los usuarios crear y administrar salones de chat para un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="122da-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="122da-115">Sin embargo, los usuarios no pueden crear ni administrar salones de chat en otros sitios dentro de la misma topología.</span><span class="sxs-lookup"><span data-stu-id="122da-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="122da-116">Asegúrese de especificar los creadores y creadores de salones de chat para todos los sitios de la organización.</span><span class="sxs-lookup"><span data-stu-id="122da-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="122da-117">Los usuarios hospedados en una aplicación de sucursal con funciones de supervivencia de Lync Server no pueden crear salones de chat nuevos ni ver la tarjeta de la sala para las salas existentes.</span><span class="sxs-lookup"><span data-stu-id="122da-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

