---
title: 'Lync Server 2013: administración de grupos de agentes de grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6cbea3b1a0d6638206a022ce5aded610dd60f23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="ecc88-102">Administrar grupos de agentes de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecc88-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecc88-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ecc88-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ecc88-104">Un grupo de agentes consta de un grupo de personas que están designadas para responder llamadas a un grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ecc88-104">An agent group consists of a group of people who are designated to answer calls to a response group.</span></span> <span data-ttu-id="ecc88-105">Al crear un grupo de agentes, seleccione los agentes que están asignados al grupo y especifique la configuración adicional del grupo, como el método de enrutamiento y si un agente puede iniciar y cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="ecc88-105">When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ecc88-106">Los usuarios deben estar habilitados para telefonía IP empresarial antes de que pueda agregarlos a grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="ecc88-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="ecc88-107">Para obtener más información sobre cómo habilitar un usuario para telefonía IP empresarial, consulte <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Habilitar usuarios para telefonía IP empresarial en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ecc88-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ecc88-108">Solo los usuarios locales pueden ser agentes.</span><span class="sxs-lookup"><span data-stu-id="ecc88-108">Only on-premises users can be agents.</span></span> <span data-ttu-id="ecc88-109">Si un agente se mueve de local a conectado, las llamadas a grupos de respuesta no se dirigirán a ese agente.</span><span class="sxs-lookup"><span data-stu-id="ecc88-109">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="ecc88-110">Un agente que debe iniciar y cerrar sesión en el grupo, lo cual difiere de la sesión o de la salida de Lync Server, se denomina *agente formal*.</span><span class="sxs-lookup"><span data-stu-id="ecc88-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="ecc88-111">Los agentes formales deben iniciar sesión en el grupo antes de que puedan recibir llamadas dirigidas al grupo.</span><span class="sxs-lookup"><span data-stu-id="ecc88-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="ecc88-112">Esto puede resultar útil para los agentes que atienden llamadas del grupo a media jornada.</span><span class="sxs-lookup"><span data-stu-id="ecc88-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="ecc88-113">Agentes formales inicie y cierre sesión en sus grupos haciendo clic en un elemento de menú de Lync 2013 para abrir el explorador de Internet de Windows Internet Explorer y mostrar una consola de página web.</span><span class="sxs-lookup"><span data-stu-id="ecc88-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="ecc88-114">Un agente que no inicia ni cierra sesión en el grupo recibe el nombre de  *agente informal*.</span><span class="sxs-lookup"><span data-stu-id="ecc88-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="ecc88-115">Los agentes informales inician sesión automáticamente en el grupo cuando inician sesión en Lync Server y no pueden cerrar sesión en el grupo.</span><span class="sxs-lookup"><span data-stu-id="ecc88-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ecc88-p106">Cuando asigne usuarios como agentes de grupo de respuesta, indíqueles que, si tienen habilitado el modo de privacidad, deberán buscar contactos de "Observador de presencia de RGS" y agregarlos a su lista de contactos. Los agentes que tengan el modo de privacidad habilitado, pero que no tengan "Observador de presencia RGS" en su lista de contactos no podrán recibir llamadas en el grupo de respuesta. Los agentes que no tengan habilitado el modo de privacidad, no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="ecc88-p106">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ecc88-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ecc88-119">In This Section</span></span>

  - [<span data-ttu-id="ecc88-120">Crear o modificar un grupo de agentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecc88-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="ecc88-121">Eliminar un grupo de agentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecc88-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

