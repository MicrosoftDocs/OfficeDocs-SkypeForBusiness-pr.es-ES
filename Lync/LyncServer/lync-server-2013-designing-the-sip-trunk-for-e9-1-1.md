---
title: 'Lync Server 2013: diseño del tronco del SIP para E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bee3985efd3510b62bfe43b3aa5742f63679093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="0ce93-102">Diseño del tronco del SIP para E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ce93-102">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ce93-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="0ce93-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="0ce93-104">Lync Server usa los troncos SIP para conectar una llamada de emergencia con el proveedor de servicios E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="0ce93-104">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="0ce93-105">Puedes configurar troncos SIP del servicio de emergencia para E9-1-1 en un sitio central, en varios sitios centrales o en cada sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="0ce93-105">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="0ce93-106">Pero, si el vínculo WAN entre el sitio del autor de la llamada y el sitio que aloja el tronco SIP del servicio de emergencia no está disponible, una llamada realizada por un usuario en el sitio desconectado necesitará un registro de uso de teléfono especial en la directiva de voz del usuario que redirigirá la llamada al ECRC a través de la puerta de enlace de la red telefónica conmutada (RTC) local.</span><span class="sxs-lookup"><span data-stu-id="0ce93-106">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="0ce93-107">Lo mismo sucede si se aplican los límites de las llamadas simultáneas del servicio de control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0ce93-107">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ce93-108">Hay dos formas de implementar un tronco de SIP en un entorno de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="0ce93-108">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="0ce93-109">Use servidores de mediación multitarjeta que usen sus interfaces de enrutamiento público con el exterior para comunicarse con el proveedor de troncal de SIP.</span><span class="sxs-lookup"><span data-stu-id="0ce93-109">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="0ce93-110">Use un controlador de borde de sesión (SBC) local para proporcionar un punto de delimitación seguro entre los servidores de mediación y los servicios del proveedor de troncal del SIP.</span><span class="sxs-lookup"><span data-stu-id="0ce93-110">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="0ce93-111">Si eliges el último método, asegúrate de que el modelo y la marca del SBC que elijas estén certificado y admitan el paso de datos de ubicación del objeto de localización del formato de datos de información de presencia (PIDF-LO) como parte de su SIP INVITE.</span><span class="sxs-lookup"><span data-stu-id="0ce93-111">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="0ce93-112">De lo contrario, las llamadas llegarán al proveedor de los servicios de emergencia sin información de su ubicación.</span><span class="sxs-lookup"><span data-stu-id="0ce93-112">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="0ce93-113">Para obtener más información sobre SBCs certificado, consulte "Infrastructure Qualified for Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>" en.</span><span class="sxs-lookup"><span data-stu-id="0ce93-113">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="0ce93-114">Los proveedores de servicios E9-1-1 proporcionan acceso a un par de SBCs por redundancia.</span><span class="sxs-lookup"><span data-stu-id="0ce93-114">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="0ce93-115">Debe tomar varias decisiones en relación con la topología de servidor de mediación y la configuración de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0ce93-115">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="0ce93-116">¿Tratará tanto SBCs como pares iguales y usará el enrutamiento de operación por turnos para las llamadas entre ellos, o se designará un SBC como principal y el otro como secundario?</span><span class="sxs-lookup"><span data-stu-id="0ce93-116">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="0ce93-117">Para obtener detalles sobre la implementación de un tronco SIP en Lync Server, consulte [¿Cómo puedo implementar la Troncalización SIP en Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="0ce93-117">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="0ce93-118">Las siguientes preguntas te ayudarán a decidir cómo implementar los troncos SIP para E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="0ce93-118">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="0ce93-119">**¿Tendría que implementar el tronco SIP a través de una conexión alquilada dedicada o de una conexión a Internet compartida?**</span><span class="sxs-lookup"><span data-stu-id="0ce93-119">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="0ce93-p105">Es importante que las llamadas de emergencia conecten siempre. Una línea dedicada proporciona una conexión que no tendrá que cambiarse por otro tráfico de la red y ofrece la posibilidad de implementar Calidad de servicio (QoS). Recuerda que si vas a conectar con proveedores de servicios de emergencia en la red de Internet pública y necesitas garantizar la confidencialidad de las llamadas de emergencia, es necesario el cifrado IPSec.</span><span class="sxs-lookup"><span data-stu-id="0ce93-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="0ce93-123">**¿Su implementación de E9-1-1 está diseñada para la tolerancia ante desastres?**</span><span class="sxs-lookup"><span data-stu-id="0ce93-123">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="0ce93-124">Como se trata de una solución de emergencia, la resistencia es importante.</span><span class="sxs-lookup"><span data-stu-id="0ce93-124">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="0ce93-125">Implementar los servidores de mediación y los troncos SIP principales y secundarios en ubicaciones con tolerancia ante desastres.</span><span class="sxs-lookup"><span data-stu-id="0ce93-125">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="0ce93-126">Es buena idea implementar el servidor de mediación principal más cercano a los usuarios que es compatible y enrutar las llamadas de conmutación por error a través del servidor de mediación secundaria (que se encuentra en una ubicación geográfica diferente).</span><span class="sxs-lookup"><span data-stu-id="0ce93-126">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="0ce93-127">**¿Tendría que implementar un tronco SIP independiente para cada sucursal?**</span><span class="sxs-lookup"><span data-stu-id="0ce93-127">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="0ce93-128">Lync Server proporciona varias estrategias para controlar la resistencia de voz en sucursales, entre las que se incluyen: tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o presionar las llamadas a la puerta de enlace local durante las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="0ce93-128">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="0ce93-129">Para obtener más información, consulte [Troncalización SIP de sitio de sucursal en Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="0ce93-129">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="0ce93-130">**¿Está habilitado el servicio de control de admisión de llamadas (CAC)?**</span><span class="sxs-lookup"><span data-stu-id="0ce93-130">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="0ce93-131">Lync Server no maneja las llamadas de emergencia de ninguna otra forma.</span><span class="sxs-lookup"><span data-stu-id="0ce93-131">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="0ce93-132">Por este motivo, la administración de ancho de banda o el servicio de control de admisión de llamadas (CAC) pueden afectar de forma negativa a una configuración de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="0ce93-132">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="0ce93-133">Las llamadas de emergencia se pueden bloquear o redirigir a la puerta de enlace RTC local si hay un CAC habilitado y se supera el límite configurado en un vínculo al que se están redirigiendo las llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="0ce93-133">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="0ce93-134">Como se ha indicado antes en este tema, dichas llamadas no tendrán datos de ubicación y se necesitan redirigir manualmente al ECRC.</span><span class="sxs-lookup"><span data-stu-id="0ce93-134">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

