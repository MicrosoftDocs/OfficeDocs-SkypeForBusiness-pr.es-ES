---
title: 'Lync Server 2013: Información general sobre los enlaces troncales SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e2c79261923456575e208aa472daae4aaab5f55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="50960-102">Información general sobre los enlaces troncales SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50960-102">Overview of SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50960-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="50960-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="50960-p101">La implementación de un enlace troncal SIP puede suponer un enorme avance a la hora de simplificar las telecomunicaciones de la organización y adaptarse a las mejoras más recientes de las comunicaciones en tiempo real. Una de las principales ventajas del enlace troncal SIP consiste en que es posible consolidar las conexiones de la organización a la red telefónica conmutada (RTC) en un único sitio central, cosa que con la versión anterior no era posible, ya que se usaban troncos de multiplexación por división de tiempo (TDM), lo que normalmente necesitaba un tronco por cada sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="50960-p101">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications. One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="50960-106">Troncalización SIP en Lync Server</span><span class="sxs-lookup"><span data-stu-id="50960-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="50960-107">Las capacidades de Troncalización SIP de Lync Server 2013 permiten lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="50960-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="50960-108">Un usuario de la empresa, ya sea dentro o fuera del firewall de la empresa, puede hacer una llamada local o una llamada de larga distancia especificada por un número compatible con E. 164 que haya finalizado en la RTC como servicio del proveedor de servicios correspondiente.</span><span class="sxs-lookup"><span data-stu-id="50960-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="50960-109">Cualquier abonado de RTC puede ponerse en contacto con un usuario empresarial dentro o fuera del Firewall corporativo marcando un número de marcado interno directo que está asociado con ese usuario de la empresa.</span><span class="sxs-lookup"><span data-stu-id="50960-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="50960-110">Ahorro económico</span><span class="sxs-lookup"><span data-stu-id="50960-110">Cost Savings</span></span>

<span data-ttu-id="50960-111">El ahorro económico inherente al enlace troncal SIP puede ser considerable:</span><span class="sxs-lookup"><span data-stu-id="50960-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="50960-112">El coste de las llamadas de larga distancia suele ser mucho menor con un tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="50960-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="50960-113">Es posible reducir tanto los costes de manejabilidad como la complejidad de la implementación.</span><span class="sxs-lookup"><span data-stu-id="50960-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="50960-p102">Las tasas de interfaz de acceso básica (BRI) y de interfaz de acceso principal (PRI) se pueden evitar si se conecta un tronco SIP directamente al ITSP, a un coste visiblemente menor. En los enlaces troncales TDM, los proveedores de servicios establecen el cargo de las llamadas por minuto. El coste del enlace troncal SIP se puede basar en el uso de ancho de banda, que puede comprarse en incrementos más pequeños y, por tanto, más económicos (el coste real depende del modelo de servicio del ITSP que elijas).</span><span class="sxs-lookup"><span data-stu-id="50960-p102">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost. In TDM trunking, service providers charge for calls by the minute. The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments. (The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="50960-118">Enlace troncal SIP en comparación con el hospedaje de una puerta de enlace RTC o PBX IP</span><span class="sxs-lookup"><span data-stu-id="50960-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="50960-p103">Como los troncos SIP se conectan directamente al proveedor de servicios, se puede prescindir de las puertas de enlace RTC y, en consecuencia, del coste de administración y complejidad que estas conllevan. El uso de un tronco SIP se traduce en un ahorro económico muy significativo, ya que requiere menos mantenimiento y administración.</span><span class="sxs-lookup"><span data-stu-id="50960-p103">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity. Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="50960-121">Servicios de VoIP ampliados</span><span class="sxs-lookup"><span data-stu-id="50960-121">Expanded VoIP Services</span></span>

<span data-ttu-id="50960-122">Con frecuencia, las características de voz constituyen la principal motivación para implementar un enlace troncal SIP, si bien la compatibilidad de voz es solo el primer paso.</span><span class="sxs-lookup"><span data-stu-id="50960-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="50960-123">Con los troncales SIP, puede ampliar las capacidades de VoIP y habilitar Lync Server 2013 para ofrecer un conjunto de servicios más completo.</span><span class="sxs-lookup"><span data-stu-id="50960-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="50960-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="50960-124">For example:</span></span>

  - <span data-ttu-id="50960-125">La detección de presencia mejorada para dispositivos que no ejecutan Lync Server 2013 puede proporcionar mejor integración con teléfonos móviles, lo que le permite ver cuándo un usuario se encuentra en una llamada de teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="50960-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="50960-126">El servicio de llamadas de emergencia E9-1-1 permite que los responsables que atienden las llamadas al 911 sepan dónde se encuentra la persona que realiza la llamada a través de su número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="50960-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50960-127">Ponte en contacto con tu ITSP para obtener una lista de los servicios que este admite y que puedes habilitar en tu organización.</span><span class="sxs-lookup"><span data-stu-id="50960-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

