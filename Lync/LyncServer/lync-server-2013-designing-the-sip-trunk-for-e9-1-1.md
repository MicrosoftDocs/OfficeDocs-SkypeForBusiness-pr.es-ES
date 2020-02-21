---
title: 'Lync Server 2013: diseño del tronco SIP para E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c4191ed20497b4136b4e836da112054bef5a446
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="765bc-102">Diseño del tronco SIP para E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="765bc-102">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="765bc-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="765bc-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="765bc-104">Lync Server usa troncos SIP para conectar una llamada de emergencia con el proveedor de servicios E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="765bc-104">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="765bc-105">Puede configurar un tronco SIP de servicio de emergencia para E9-1-1 en un sitio central, en varios sitios centrales o en cada sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="765bc-105">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="765bc-106">Sin embargo, si el vínculo WAN entre el sitio del autor de la llamada y el sitio que aloja el tronco SIP del servicio de emergencia no está disponible, una llamada realizada por un usuario en el sitio desconectado necesitará un registro de uso de teléfono especial en la directiva de voz de usuario que enrute la llamada al ECRC a través de la puerta de enlace de la red telefónica conmutada pública (RTC) local.</span><span class="sxs-lookup"><span data-stu-id="765bc-106">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="765bc-107">Lo mismo sucede si se aplica un control de admisión de llamadas a la llamada.</span><span class="sxs-lookup"><span data-stu-id="765bc-107">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="765bc-108">Hay dos formas de implementar un tronco SIP en un entorno de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="765bc-108">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="765bc-109">Use servidores de mediación multitarjeta que usen interfaces enrutadas públicamente dirigidas hacia el exterior para comunicarse con el proveedor de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="765bc-109">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="765bc-110">Use un controlador de borde de sesión (SBC) local para proporcionar un punto de demarcación segura entre los servidores de mediación y los servicios del proveedor de tronco del SIP.</span><span class="sxs-lookup"><span data-stu-id="765bc-110">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="765bc-111">Si elige el último método, asegúrese de que el modelo y la marca SBC que elija admite el paso de datos de ubicación PIDF-LO (Presence Information Data Format Location Object, en inglés) como parte de su SIP INVITE.</span><span class="sxs-lookup"><span data-stu-id="765bc-111">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="765bc-112">De lo contrario, las llamadas llegarán al proveedor de los servicios de emergencia sin información de su ubicación.</span><span class="sxs-lookup"><span data-stu-id="765bc-112">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="765bc-113">Para obtener más información sobre los SBC certificados, consulte "infraestructura calificada para <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>Microsoft Lync" en.</span><span class="sxs-lookup"><span data-stu-id="765bc-113">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="765bc-114">Los proveedores de servicios E9-1-1 proporcionan acceso a un par de SBC por redundancia.</span><span class="sxs-lookup"><span data-stu-id="765bc-114">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="765bc-115">Debe tomar varias decisiones con respecto a la topología del servidor de mediación y la configuración de enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="765bc-115">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="765bc-116">¿Va a tratar ambos SBC como equivalentes y usar el enrutamiento Round Robin para las llamadas entre ellos, o se designe un SBC como principal y el otro como secundario?</span><span class="sxs-lookup"><span data-stu-id="765bc-116">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="765bc-117">Para obtener más información sobre cómo implementar un tronco SIP en Lync Server, vea [¿Cómo puedo implementar el enlace troncal SIP en Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="765bc-117">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="765bc-118">Las siguientes preguntas le ayudarán a decidir cómo implementar troncos SIP para E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="765bc-118">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="765bc-119">**¿Tendrá que implementar el tronco SIP a través de una conexión alquilada dedicada o de una conexión a Internet compartida?**</span><span class="sxs-lookup"><span data-stu-id="765bc-119">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="765bc-p105">Es importante que las llamadas de emergencia conecten siempre. Una línea dedicada proporciona una conexión que no tendrá que reemplazarse por otro tráfico de la red y ofrece la posibilidad de implementar Calidad de servicio (QoS). Recuerde que si va a conectar con proveedores de servicios de emergencia en Internet público y debe garantizar la confidencialidad de las llamas de emergencia, es necesario el cifrado IPSec.</span><span class="sxs-lookup"><span data-stu-id="765bc-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="765bc-123">**¿Su implementación de E9-1-1 está diseñada para la tolerancia ante desastres?**</span><span class="sxs-lookup"><span data-stu-id="765bc-123">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="765bc-124">Como se trata de una solución de emergencia, la resistencia es importante.</span><span class="sxs-lookup"><span data-stu-id="765bc-124">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="765bc-125">Implementar los servidores de mediación principales y secundarios y los troncos SIP en las ubicaciones tolerantes a desastres.</span><span class="sxs-lookup"><span data-stu-id="765bc-125">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="765bc-126">Es una buena idea implementar el servidor de mediación principal más cercano a los usuarios que es compatible y enrutar las llamadas de conmutación por error a través del servidor de mediación secundario (ubicado en una ubicación geográfica distinta).</span><span class="sxs-lookup"><span data-stu-id="765bc-126">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="765bc-127">**¿Deberá implementar un tronco SIP independiente para cada sucursal?**</span><span class="sxs-lookup"><span data-stu-id="765bc-127">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="765bc-128">Lync Server ofrece varias estrategias para controlar la resistencia de voz en las sucursales, entre las que se incluyen: tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o insertar llamadas en la puerta de enlace local durante las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="765bc-128">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="765bc-129">Para obtener más información, consulte [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="765bc-129">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="765bc-130">**¿Está habilitado el servicio de control de admisión de llamadas (CAC)?**</span><span class="sxs-lookup"><span data-stu-id="765bc-130">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="765bc-131">Lync Server no administra las llamadas de emergencia de forma distinta a una llamada ordinaria.</span><span class="sxs-lookup"><span data-stu-id="765bc-131">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="765bc-132">Por este motivo, la administración de ancho de banda o el servicio de control de admisión de llamadas (CAC) puede afectar de forma negativa a una configuración de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="765bc-132">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="765bc-133">Las llamadas de emergencia se pueden bloquear o enrutar a la puerta de enlace RTC local si hay un CAC habilitado y se supera el límite configurado en un vínculo al que se están enrutando las llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="765bc-133">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="765bc-134">Como se ha indicado antes en este tema, dichas llamadas no tendrán datos de ubicación y se deben enrutar manualmente al ECRC.</span><span class="sxs-lookup"><span data-stu-id="765bc-134">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

