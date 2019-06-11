---
title: 'Lync Server 2013: pautas de implementación para el servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400f8cceeb86d407297b3f564c01266a477ca0ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="beea3-102">Instrucciones de implementación para el servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="beea3-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beea3-103">_**Última modificación del tema:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="beea3-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="beea3-104">En este tema se describen las directrices de planeación para la implementación de Media Server.</span><span class="sxs-lookup"><span data-stu-id="beea3-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="beea3-105">Después de revisar estas instrucciones, le recomendamos que use la herramienta de planeación para crear y ver posibles topologías alternativas, que pueden servir como modelos para el aspecto de la topología final personalizada que decida implementar.</span><span class="sxs-lookup"><span data-stu-id="beea3-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="beea3-106">Servidor de mediación colocada o independiente?</span><span class="sxs-lookup"><span data-stu-id="beea3-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="beea3-107">De forma predeterminada, el servidor de mediación se encuentra en el servidor Standard Edition o en el servidor front-end de un grupo front-end en los sitios centrales.</span><span class="sxs-lookup"><span data-stu-id="beea3-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="beea3-108">La cantidad de llamadas por la red telefónica conmutada (RTC) que se pueden gestionar y la cantidad de equipos necesarios en el grupo dependerán de los siguientes factores:</span><span class="sxs-lookup"><span data-stu-id="beea3-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="beea3-109">El número de puertas de enlace o gateways controladas por el grupo de servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="beea3-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="beea3-110">Los períodos de gran tráfico de esas puertas de enlace</span><span class="sxs-lookup"><span data-stu-id="beea3-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="beea3-111">El porcentaje de llamadas que son llamadas cuyos medios omiten el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="beea3-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="beea3-112">Al planificar, asegúrate de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y las conferencias de A/V no configuradas para la omisión de medios, además del procesamiento necesario para gestionar las interacciones de señalización para la cantidad de llamadas que es necesario admitir en las horas de más actividad.</span><span class="sxs-lookup"><span data-stu-id="beea3-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="beea3-113">Si no hay suficiente CPU, debe implementar un grupo independiente de servidores de mediación; y las puertas de enlace RTC, IP-PBX y SBCs deberán dividirse en subconjuntos que se controlan mediante servidores de mediación en un mismo grupo y los servidores de mediación independientes en uno o más grupos de servidores independientes.</span><span class="sxs-lookup"><span data-stu-id="beea3-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="beea3-114">Si ha implementado puertas de enlace RTC, IP-PBX o controladores de borde de sesión (SBCs) que no son compatibles con las funciones correctas para interactuar con un grupo de servidores de mediación, entre los que se incluyen los siguientes, deberán asociarse con un conjunto independiente que contenga de un solo servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="beea3-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="beea3-115">Realizar el equilibrio de carga del sistema de nombres de dominio (DNS) de nivel de red en los servidores de mediación de un grupo (o bien enrutar el tráfico uniformemente a todos los servidores de mediación de un grupo)</span><span class="sxs-lookup"><span data-stu-id="beea3-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="beea3-116">Aceptar el tráfico de cualquier servidor de mediación de un grupo</span><span class="sxs-lookup"><span data-stu-id="beea3-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="beea3-117">Puede usar la herramienta de planeación de Microsoft Lync Server 2013, para evaluar si collocating el servidor de mediación con el grupo de servidores front-end puede controlar la carga.</span><span class="sxs-lookup"><span data-stu-id="beea3-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="beea3-118">Si su entorno no puede cumplir estos requisitos, debe implementar un grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="beea3-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="beea3-119">Consideraciones del sitio central y del sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="beea3-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="beea3-120">Los servidores de mediación del sitio central se pueden usar para enrutar llamadas para IP-PBX o puertas de enlace RTC en sitios de sucursales.</span><span class="sxs-lookup"><span data-stu-id="beea3-120">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="beea3-121">Sin embargo, si implementas los troncos SIP, debes implementar un servidor de mediación en el sitio en el que termina cada tronco.</span><span class="sxs-lookup"><span data-stu-id="beea3-121">If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="beea3-122">Tener un servidor de mediación en el sitio central las llamadas a una puerta de enlace IP o RTC en un sitio de sucursal no requieren el uso de la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="beea3-122">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass.</span></span> <span data-ttu-id="beea3-123">Sin embargo, si puede habilitar la omisión de medios, esta acción reducirá la latencia de la ruta multimedia y, por consiguiente, dará como resultado una mejor calidad de contenido multimedia porque la ruta multimedia ya no es necesaria para seguir la ruta de señalización.</span><span class="sxs-lookup"><span data-stu-id="beea3-123">However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path.</span></span> <span data-ttu-id="beea3-124">La omisión de medios también reducirá la carga de procesamiento del grupo.</span><span class="sxs-lookup"><span data-stu-id="beea3-124">Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="beea3-125">La omisión de medios no interactuará con todas las puertas de enlace RTC, las IP-PBX y los SBC.</span><span class="sxs-lookup"><span data-stu-id="beea3-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="beea3-126">Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con las IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="beea3-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="beea3-127">La omisión de elementos multimedia solo se admite con productos y versiones que se incluyen en el programa de interoperabilidad abierto de comunicaciones unificadas: Lync Server en <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span><span class="sxs-lookup"><span data-stu-id="beea3-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="beea3-128">Si se requiere resistencia al sitio de la sucursal, se debe implementar en el sitio de la sucursal un dispositivo de aplicación de media o una combinación de un servidor front-end, un servidor de mediación y una combinación.</span><span class="sxs-lookup"><span data-stu-id="beea3-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="beea3-129">(La hipótesis con la resistencia de los sitios de las sucursales es que la presencia y las conferencias no son resistentes en el sitio). Para obtener instrucciones sobre el planeamiento de sitios de sucursal para voz, vea [planear la resistencia de voz de un sitio de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="beea3-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="beea3-130">En el caso de interacciones con un IP-PBX, si el IP-PBX no es compatible con las interacciones de medios iniciales con varios cuadros de diálogo y interacciones de RFC 3960, puede recortar las primeras palabras del saludo para las llamadas entrantes desde el IP-PBX a los puntos de conexión de Lync.</span><span class="sxs-lookup"><span data-stu-id="beea3-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="beea3-131">Este comportamiento puede ser más grave si un servidor de mediación de un sitio central está enrutando las llamadas a un IP-PBX donde la ruta termina en un sitio de sucursal, porque se necesita más tiempo para que se complete la señalización.</span><span class="sxs-lookup"><span data-stu-id="beea3-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="beea3-132">Si experimenta este comportamiento, implementar un servidor de mediación en el sitio de la sucursal es la única forma de reducir el recorte de las primeras palabras.</span><span class="sxs-lookup"><span data-stu-id="beea3-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="beea3-133">Por último, si su sitio central tiene un sistema PBX con TDM, o si su IP-PBX no elimina la necesidad de una puerta de enlace RTC, debe implementar una puerta de enlace en la ruta de llamada y en el servidor PBX.</span><span class="sxs-lookup"><span data-stu-id="beea3-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="beea3-134">Para mejorar el rendimiento de medios del servidor de mediación independiente, es necesario habilitar el ajuste de escala en lado de recepción (RSS) en los adaptadores de red de estos servidores.</span><span class="sxs-lookup"><span data-stu-id="beea3-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="beea3-135">RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor.</span><span class="sxs-lookup"><span data-stu-id="beea3-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="beea3-136">Para obtener más información, vea "mejoras en la escala de recepción en Windows Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>" en.</span><span class="sxs-lookup"><span data-stu-id="beea3-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="beea3-137">Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="beea3-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

