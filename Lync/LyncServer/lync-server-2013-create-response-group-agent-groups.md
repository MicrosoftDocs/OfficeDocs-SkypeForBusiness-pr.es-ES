---
title: 'Lync Server 2013: Crear grupos de agentes de grupos de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e2a8a41b67818cf1f2aec9ec8daaa46eeff783a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="50eb2-102">Crear grupos de agentes de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50eb2-102">Create Response Group agent groups Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50eb2-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="50eb2-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="50eb2-104">Cuando se crea un grupo de agentes, se seleccionan los agentes que se asignan al grupo y se especifica la configuración de grupo adicional, como el método de enrutamiento y si un agente puede iniciar y cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="50eb2-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="50eb2-105">Un agente que debe iniciar y cerrar sesión en el grupo, lo cual difiere de la sesión o de la salida de Lync Server, se denomina *agente formal*.</span><span class="sxs-lookup"><span data-stu-id="50eb2-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="50eb2-106">Los agentes formales deben iniciar sesión en el grupo para poder recibir llamadas enrutadas al grupo.</span><span class="sxs-lookup"><span data-stu-id="50eb2-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="50eb2-107">Esto puede resultar útil para los agentes que atienden llamadas del grupo a media jornada.</span><span class="sxs-lookup"><span data-stu-id="50eb2-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="50eb2-108">Agentes formales inicie y cierre sesión en sus grupos haciendo clic en un elemento de menú de Lync 2013 para abrir el explorador de Internet de Windows Internet Explorer y mostrar una consola de página web.</span><span class="sxs-lookup"><span data-stu-id="50eb2-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="50eb2-109">Un agente que no inicia ni cierra sesión en el grupo recibe el nombre de  *agente informal*.</span><span class="sxs-lookup"><span data-stu-id="50eb2-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="50eb2-110">Los agentes informales inician sesión automáticamente en el grupo cuando inician sesión en Lync Server y no pueden cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="50eb2-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50eb2-111">Solo los usuarios locales pueden ser agentes.</span><span class="sxs-lookup"><span data-stu-id="50eb2-111">Only on-premises users can be agents.</span></span> <span data-ttu-id="50eb2-112">Si un agente se mueve de local a conectado, las llamadas a grupos de respuesta no se dirigirán a ese agente.</span><span class="sxs-lookup"><span data-stu-id="50eb2-112">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="50eb2-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="50eb2-113">In This Section</span></span>

[<span data-ttu-id="50eb2-114">Crear o modificar un grupo de agentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50eb2-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

