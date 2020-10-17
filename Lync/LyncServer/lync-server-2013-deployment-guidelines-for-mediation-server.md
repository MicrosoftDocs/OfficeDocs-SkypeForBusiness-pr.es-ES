---
title: 'Lync Server 2013: directrices de implementación para el servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4e627dfdc161093d07243e6598807f3ad91cab1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522717"
---
# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="b1de7-102">Instrucciones de implementación para el servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1de7-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1de7-103">_**Última modificación del tema:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="b1de7-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="b1de7-104">En este tema se describen las directrices de planeación para la implementación del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="b1de7-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="b1de7-105">Después de revisar estas instrucciones, le recomendamos que use la herramienta de planeación para crear y ver posibles topologías alternativas, que pueden servir como modelos para determinar el aspecto de la topología adaptada final que decida implementar.</span><span class="sxs-lookup"><span data-stu-id="b1de7-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="b1de7-106">Servidor de mediación combinado o independiente</span><span class="sxs-lookup"><span data-stu-id="b1de7-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="b1de7-107">El servidor de mediación se combina de forma predeterminada en el servidor Standard Edition o en el servidor front-end de un grupo de servidores front-end en los sitios centrales.</span><span class="sxs-lookup"><span data-stu-id="b1de7-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="b1de7-108">El número de llamadas de red telefónica conmutada (RTC) que se pueden administrar y el número de máquinas necesarias en el grupo dependerá de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1de7-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="b1de7-109">El número de puertas de enlace del mismo nivel que controla el grupo de servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="b1de7-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="b1de7-110">Los períodos de tráfico de gran volumen a través de estas puertas de enlace</span><span class="sxs-lookup"><span data-stu-id="b1de7-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="b1de7-111">El porcentaje de llamadas que son llamadas cuyos medios omiten el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="b1de7-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="b1de7-112">Al planear, asegúrese de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y las conferencias de A/V que no están configuradas para el desvío de medios, así como el procesamiento necesario para controlar las interacciones de señalización para el número de llamadas de horas no disponibles que deben admitirse.</span><span class="sxs-lookup"><span data-stu-id="b1de7-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="b1de7-113">Si no hay suficiente CPU, debe implementar un grupo independiente de servidores de mediación; Además, las puertas de enlace RTC, las IP-PBX y los SBC deberán dividirse en subconjuntos controlados por los servidores de mediación combinados en un grupo y los servidores de mediación independientes en uno o más grupos de servidores independientes.</span><span class="sxs-lookup"><span data-stu-id="b1de7-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="b1de7-114">Si ha implementado puertas de enlace RTC, IP-PBX o controladores de borde de sesión (SBC) que no admiten las capacidades correctas para interactuar con un grupo de servidores de mediación, como los siguientes, se deberán asociar a un grupo independiente que consista en un único servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="b1de7-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="b1de7-115">Realizar el equilibrio de carga del sistema de nombres de dominio (DNS) de la capa de red en los servidores de mediación de un grupo (o enrutar el tráfico uniformemente a todos los servidores de mediación de un grupo)</span><span class="sxs-lookup"><span data-stu-id="b1de7-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="b1de7-116">Aceptar tráfico de cualquier servidor de mediación de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="b1de7-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="b1de7-117">Puede usar la herramienta de planeación 2013 de Microsoft Lync Server para evaluar si combinar el servidor de mediación con el grupo de servidores front-end puede controlar la carga.</span><span class="sxs-lookup"><span data-stu-id="b1de7-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="b1de7-118">Si el entorno no cumple estos requisitos, deberá implementar un grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="b1de7-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="b1de7-119">Consideraciones del sitio central y las sucursales</span><span class="sxs-lookup"><span data-stu-id="b1de7-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="b1de7-p105">Los servidores de mediación del sitio central se pueden usar para enrutar llamadas a puertas de enlace RTC o IP-PBX en las sucursales. Sin embargo, si implementa troncos SIP, deberá implementar un servidor de mediación en el sitio donde termina cada tronco. Para que un servidor de mediación del sitio central enrute las llamadas a una puerta de enlace RTC o IP-PBX en una sucursal, no es necesario usar desvío de medios. Sin embargo, si puede habilitar el desvío de medios y lo hace, se reducirá la latencia de la ruta de acceso a los medios y, por ello, mejorará la calidad de los medios, porque la ruta de acceso a los medios ya no estará obligada a seguir la ruta de acceso de señalización. El desvío de medios disminuirá también la carga de procesamiento del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="b1de7-p105">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites. If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates. Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass. However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path. Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b1de7-125">El desvío de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC.</span><span class="sxs-lookup"><span data-stu-id="b1de7-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="b1de7-126">Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con la IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="b1de7-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="b1de7-127">La omisión de medios solo se admite con productos y versiones que se enumeran en el programa de interoperabilidad abierto de comunicaciones unificadas – Lync Server en <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A> .</span><span class="sxs-lookup"><span data-stu-id="b1de7-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="b1de7-128">Si se necesita resistencia en la sucursal, se debe implementar una aplicación de sucursal con funciones de supervivencia o una combinación de servidor front-end, servidor de mediación y puerta de enlace en la sucursal.</span><span class="sxs-lookup"><span data-stu-id="b1de7-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="b1de7-129">(La hipótesis con resistencia de sitios de sucursal es que la presencia y la Conferencia no son resistentes en el sitio). Para obtener instrucciones sobre la planeación de sitios de sucursal para voz, vea [Planning for Branch-site Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="b1de7-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="b1de7-130">En el caso de las interacciones con un IP-PBX, si la IP-PBX no es compatible correctamente con interacciones de medios iniciales con varios cuadros de diálogo de RFC 3960 y con interacciones de RFC, puede haber un recorte de las primeras palabras del saludo para las llamadas entrantes desde los puntos de conexión de IP-PBX a Lync.</span><span class="sxs-lookup"><span data-stu-id="b1de7-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="b1de7-131">Este suceso puede agravarse si un servidor de mediación del sitio central enruta llamadas a un IP-PBX en el que la ruta termina en una sucursal, porque se necesita más tiempo para que la señalización finalice.</span><span class="sxs-lookup"><span data-stu-id="b1de7-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="b1de7-132">Si experimenta este comportamiento, la única forma de reducir el recorte de las primeras palabras es implementar un servidor de mediación en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="b1de7-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="b1de7-133">Por último, si el sitio central tiene un PBX TDM, o si el IP-PBX no evita la necesidad de una puerta de enlace RTC, deberá implementar una puerta de enlace en la ruta de la llamada para conectar el servidor de mediación y el PBX.</span><span class="sxs-lookup"><span data-stu-id="b1de7-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b1de7-134">Para mejorar el rendimiento de medios de un servidor de mediación independiente, debe habilitar el ajuste de escala en el lado de recepción (RSS) en los adaptadores de red de estos servidores.</span><span class="sxs-lookup"><span data-stu-id="b1de7-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="b1de7-135">El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor.</span><span class="sxs-lookup"><span data-stu-id="b1de7-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="b1de7-136">Para obtener más información, vea "mejoras en el ajuste de escala en lado de recepción en Windows Server" en <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A> .</span><span class="sxs-lookup"><span data-stu-id="b1de7-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="b1de7-137">Para obtener más información sobre cómo habilitar RSS, consulte la documentación de su adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="b1de7-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

