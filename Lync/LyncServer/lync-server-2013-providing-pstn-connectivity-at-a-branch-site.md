---
title: 'Lync Server 2013: suministro de conectividad RTC en un sitio de sucursal'
description: 'Lync Server 2013: suministro de conectividad RTC en un sitio de sucursal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Providing PSTN connectivity at a branch site
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398945(v=OCS.15)
ms:contentKeyID: 48185633
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63cbc03f78a27bda14c2906e31cc68bed5870878
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579706"
---
# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="f6238-103">Suministro de conectividad RTC en un sitio de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6238-103">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6238-104">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f6238-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f6238-105">Se recomienda usar la herramienta de planeación 2013 de Microsoft Lync Server para agregar sitios de sucursal a la topología y configurar la infraestructura de voz en sitios de sucursal.</span><span class="sxs-lookup"><span data-stu-id="f6238-105">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="f6238-106">Si no usa la herramienta de planeación, use los procedimientos descritos en los temas de esta sección, en primer lugar, para agregar los sitios de sucursal y, a continuación, para configurar la infraestructura de voz mediante la definición de la puerta de enlace de red telefónica conmutada (RTC) o mediante la configuración del tronco SIP (con o sin desvío de medios).</span><span class="sxs-lookup"><span data-stu-id="f6238-106">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="f6238-107">Otra opción consiste en conectar una central de conmutación (PBX) al sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="f6238-107">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6238-108">Si desea proporcionar resistencia de sitios de sucursal, debe implementar una aplicación de sucursal con funciones de supervivencia, un servidor de sucursal con funciones de supervivencia o un servidor Standard Edition en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="f6238-108">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="f6238-109">Para obtener más información, consulte <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a funciones de aplicación de sucursal con funciones de supervivencia o servidor con Lync server 2013</A> o <A href="lync-server-2013-deploying-lync-server.md">implementar Lync Server 2013</A>, según corresponda, en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="f6238-109">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f6238-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f6238-110">In This Section</span></span>

  - [<span data-ttu-id="f6238-111">Agregar sitios de sucursal a la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6238-111">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="f6238-112">Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6238-112">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="f6238-113">Configurar un tronco con la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6238-113">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="f6238-114">Configurar un tronco sin omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6238-114">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f6238-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f6238-115">See Also</span></span>


[<span data-ttu-id="f6238-116">Planeación de la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6238-116">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="f6238-117">Planeación de la conectividad con RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6238-117">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

