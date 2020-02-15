---
title: 'Lync Server 2013: información general sobre el enlace troncal SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbf29b02af831f82050e9a032a35f0fa57c1eb1e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="6d063-102">Información general sobre el enlace troncal SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d063-102">Overview of SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d063-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6d063-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6d063-p101">La implementación de un enlace troncal SIP puede suponer un enorme avance a la hora de simplificar las telecomunicaciones de la organización y adaptarse a las mejoras más recientes de las comunicaciones en tiempo real. Una de las principales ventajas del enlace troncal SIP consiste en que es posible consolidar las conexiones de la organización a la red telefónica conmutada (RTC) en un único sitio central, cosa que con la versión anterior no era posible, ya que se usaban troncos de multiplexación por división de tiempo (TDM), lo que normalmente requería un tronco por cada sucursal.</span><span class="sxs-lookup"><span data-stu-id="6d063-p101">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications. One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="6d063-106">Enlace troncal SIP en Lync Server</span><span class="sxs-lookup"><span data-stu-id="6d063-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="6d063-107">Las capacidades de enlace troncal de SIP para Lync Server 2013 permiten lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6d063-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="6d063-108">Un usuario de la empresa dentro o fuera del firewall corporativo pueda realizar una llamada local o de larga distancia especificada por un número conforme a E.164 con terminación en la RTC como un servicio del proveedor de servicios correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6d063-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="6d063-109">Cualquier suscriptor de RTC puede ponerse en contacto con un usuario de la empresa dentro o fuera del firewall corporativo marcando un número de llamada directa a la extensión (DID) asociado a ese usuario de la empresa.</span><span class="sxs-lookup"><span data-stu-id="6d063-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="6d063-110">Ahorro económico</span><span class="sxs-lookup"><span data-stu-id="6d063-110">Cost Savings</span></span>

<span data-ttu-id="6d063-111">El ahorro económico inherente al enlace troncal SIP puede ser considerable:</span><span class="sxs-lookup"><span data-stu-id="6d063-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="6d063-112">El costo de las llamadas de larga distancia suele ser mucho menor con un tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="6d063-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="6d063-113">Es posible reducir tanto los costos de facilidad de uso como la complejidad de la implementación.</span><span class="sxs-lookup"><span data-stu-id="6d063-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="6d063-p102">Las tasas de interfaz de acceso básica (BRI) y de interfaz de acceso principal (PRI) se pueden evitar si se conecta un tronco SIP directamente al ITSP, a un costo visiblemente menor. En los troncos TDM, los proveedores del servicio establecían el cargo de las llamadas por minuto. El costo del enlace troncal SIP se puede basar en el uso de ancho de banda, que puede adquirirse en incrementos más pequeños y, por tanto, más económicos (el costo real depende del modelo de servicio del ITSP que se elija).</span><span class="sxs-lookup"><span data-stu-id="6d063-p102">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost. In TDM trunking, service providers charge for calls by the minute. The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments. (The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="6d063-118">Enlace troncal SIP frente a puerta de enlace RTC o PBX IP</span><span class="sxs-lookup"><span data-stu-id="6d063-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="6d063-p103">Como los troncos SIP se conectan directamente al proveedor del servicio, se puede prescindir de las puertas de enlace RTC y, en consecuencia, del costo de administración y complejidad que estas conllevan. El uso de un tronco SIP se traduce en un ahorro económico muy significativo gracias a que se requiere menos mantenimiento y administración.</span><span class="sxs-lookup"><span data-stu-id="6d063-p103">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity. Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="6d063-121">Servicios de VoIP ampliados</span><span class="sxs-lookup"><span data-stu-id="6d063-121">Expanded VoIP Services</span></span>

<span data-ttu-id="6d063-122">Con frecuencia, las características de voz constituyen la principal motivación para implementar un enlace troncal SIP, si bien la compatibilidad de voz es solo el primer paso.</span><span class="sxs-lookup"><span data-stu-id="6d063-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="6d063-123">Con el enlace troncal SIP, puede ampliar las capacidades de VoIP y habilitar Lync Server 2013 para proporcionar un conjunto de servicios más completo.</span><span class="sxs-lookup"><span data-stu-id="6d063-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="6d063-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6d063-124">For example:</span></span>

  - <span data-ttu-id="6d063-125">La detección de presencia mejorada para dispositivos que no ejecutan Lync Server 2013 puede proporcionar mejor integración con teléfonos móviles, lo que le permite ver cuándo un usuario se encuentra en una llamada de teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="6d063-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="6d063-126">El servicio de llamadas de emergencia E9-1-1 permite que los responsables que atienden las llamadas al 911 sepan dónde se encuentra la persona que realiza la llamada a través de su número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="6d063-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d063-127">Contacte con su ITSP para obtener una lista de los servicios que este admite y que se pueden habilitar en la organización.</span><span class="sxs-lookup"><span data-stu-id="6d063-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

