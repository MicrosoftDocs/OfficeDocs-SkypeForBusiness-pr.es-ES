---
title: 'Lync Server 2013: Proporcionar conectividad RTC en un sitio de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Providing PSTN connectivity at a branch site
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398945(v=OCS.15)
ms:contentKeyID: 48185633
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7ba3c77c789d10e80319542cd163186eef2d4c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="546a3-102">Proporcionar conectividad RTC en un sitio de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="546a3-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="546a3-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="546a3-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="546a3-104">Le recomendamos que use la herramienta de planeación 2013 de Microsoft Lync Server para agregar sitios de sucursales a su topología y para configurar la infraestructura de voz en sitios de sucursales.</span><span class="sxs-lookup"><span data-stu-id="546a3-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="546a3-105">Si no usa la herramienta de planeación, siga los procedimientos que se describen en los temas de esta sección (primero, para agregar los sitios de la sucursal) y, a continuación, para configurar su infraestructura de voz definiendo la puerta de enlace de red telefónica conmutada (RTC) o la configuración del SIP tronco (con o sin omisión de medios).</span><span class="sxs-lookup"><span data-stu-id="546a3-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="546a3-106">Conectar una central de conmutación (PBX) al sitio de la sucursal es otra opción.</span><span class="sxs-lookup"><span data-stu-id="546a3-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="546a3-107">Si desea proporcionar resistencia al sitio de la sucursal, debe implementar un equipo de sucursales con la capacidad de supervivencia, un servidor de sucursal con la capacidad de supervivencia o un servidor Standard Edition en el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="546a3-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="546a3-108">Para obtener más información, consulte <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">implementación de un dispositivo de sucursal o servidor con Lync server 2013</A> o <A href="lync-server-2013-deploying-lync-server.md">implementación de Lync Server 2013</A>, según corresponda, en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="546a3-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="546a3-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="546a3-109">In This Section</span></span>

  - [<span data-ttu-id="546a3-110">Agregar sitios de sucursal a la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="546a3-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="546a3-111">Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="546a3-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="546a3-112">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="546a3-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="546a3-113">Configurar un tronco sin omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="546a3-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="546a3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="546a3-114">See Also</span></span>


[<span data-ttu-id="546a3-115">Planificar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="546a3-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="546a3-116">Planificación de la conectividad RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="546a3-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

