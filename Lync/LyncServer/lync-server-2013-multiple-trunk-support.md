---
title: 'Lync Server 2013: compatibilidad con múltiples troncales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156db04ceb26809c7043f30e9e01ea0071e0a31d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="21e5a-102">Compatibilidad con varios troncales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21e5a-102">Multiple trunk support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21e5a-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="21e5a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="21e5a-104">La funcionalidad de Lync Server 2013 admite varias asociaciones entre puertas de enlace y servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="21e5a-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="21e5a-105">Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red de telefonía pública conmutada (RTC), controlador de borde de sesión (SBC) o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="21e5a-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="21e5a-106">Use el generador de topología para asociar puertas de enlace con servidores de mediación (es decir, troncos).</span><span class="sxs-lookup"><span data-stu-id="21e5a-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="21e5a-107">Para asignar o quitar un tronco en Lync Server 2013, primero debe definir un tronco en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="21e5a-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="21e5a-108">Un tronco consiste en la siguiente Asociación: nombre de dominio completo (FQDN) de Media Server, el puerto de escucha del servidor de mediación, el FQDN de la puerta de enlace y el puerto de escucha de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="21e5a-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="21e5a-109">Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="21e5a-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="21e5a-110">Esto proporciona resistencia adicional a la infraestructura de telefonía IP empresarial, que es especialmente útil en escenarios de interoperabilidad de la intercambiación privada (PBX).</span><span class="sxs-lookup"><span data-stu-id="21e5a-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="21e5a-111">Cuando se define un tronco, debe estar asociado con una ruta.</span><span class="sxs-lookup"><span data-stu-id="21e5a-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="21e5a-112">Para asociar un tronco a una ruta, defina un nombre simple para el tronco en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="21e5a-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="21e5a-113">Este nombre simple se usa como el nombre del tronco en el panel de control de Lync Server, donde los troncos se pueden asociar a rutas.</span><span class="sxs-lookup"><span data-stu-id="21e5a-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="21e5a-114">El nombre de tronco simple se usa como nombre de la puerta de enlace desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21e5a-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="21e5a-115">El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="21e5a-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="21e5a-116">En el generador de topología, haga clic con el botón secundario en el servidor de mediación asociado y luego haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="21e5a-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="21e5a-117">Especificar la puerta de enlace predeterminada para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="21e5a-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="21e5a-118">En el siguiente diagrama se muestran los diversos troncos que se definen para cada servidor de mediación y puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="21e5a-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="21e5a-119">**Enrutamiento de troncal M-N**</span><span class="sxs-lookup"><span data-stu-id="21e5a-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="21e5a-120">![Varias asignaciones de tronco.] (images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Varias asignaciones de tronco.")</span><span class="sxs-lookup"><span data-stu-id="21e5a-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

