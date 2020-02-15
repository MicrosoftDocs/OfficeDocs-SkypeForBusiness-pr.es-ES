---
title: 'Lync Server 2013: compatibilidad con varios tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2f8e9bea40532486d75e76887e35b496df8631
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="41483-102">Compatibilidad con varios tronco en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41483-102">Multiple trunk support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41483-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="41483-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="41483-104">La funcionalidad de Lync Server 2013 admite varias asociaciones entre puertas de enlace y servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="41483-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="41483-105">Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red telefónica conmutada (RTC), un controlador de borde de sesión (SBC) o un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="41483-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="41483-106">Use el generador de topologías para asociar puertas de enlace con servidores de mediación (es decir, troncos).</span><span class="sxs-lookup"><span data-stu-id="41483-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="41483-107">Para asignar o quitar un tronco en Lync Server 2013, primero debe definir un tronco en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="41483-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="41483-108">Un tronco se compone de la siguiente Asociación: nombre de dominio completo (FQDN) del servidor de mediación, el puerto de escucha del servidor de mediación, el FQDN de la puerta de enlace y el puerto de escucha de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="41483-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="41483-109">Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="41483-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="41483-110">Esto proporciona resistencia adicional a la infraestructura de Enterprise Voice, lo que es especialmente útil en escenarios de interoperabilidad de central de conmutación (PBX).</span><span class="sxs-lookup"><span data-stu-id="41483-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="41483-111">Cuando se define un tronco, debe estar asociado con una ruta.</span><span class="sxs-lookup"><span data-stu-id="41483-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="41483-112">Para asociar un tronco a una ruta, defina un nombre sencillo para el tronco en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="41483-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="41483-113">Este nombre sencillo se usa como nombre del tronco en el panel de control de Lync Server, donde los troncos pueden asociarse con rutas.</span><span class="sxs-lookup"><span data-stu-id="41483-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="41483-114">El nombre de tronco simple se usa como nombre de puerta de enlace desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41483-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="41483-115">El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="41483-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="41483-116">En el generador de topologías, haga clic con el botón secundario en el servidor de mediación asociado y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="41483-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="41483-117">Especifique la puerta de enlace predeterminada para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="41483-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="41483-118">En el siguiente diagrama se ilustran los distintos troncos definidos para cada servidor de mediación y puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="41483-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="41483-119">**Enrutamiento de troncos M-N**</span><span class="sxs-lookup"><span data-stu-id="41483-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="41483-120">![Varias asignaciones de tronco.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Varias asignaciones de tronco.")</span><span class="sxs-lookup"><span data-stu-id="41483-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

