---
title: Lync Server 2013 topología de referencia para pequeñas organizaciones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9947fe1657551b901b6b68cc3efbbf811b261b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="ea940-102">Topología de referencia para Lync Server 2013 en pequeñas organizaciones</span><span class="sxs-lookup"><span data-stu-id="ea940-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea940-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="ea940-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="ea940-104">La topología de referencia para organizaciones pequeñas muestra cómo puede implementar una solución robusta y de alta disponibilidad mediante la implementación de solo tres servidores que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea940-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="ea940-105">**Topología de referencia para pequeñas organizaciones**</span><span class="sxs-lookup"><span data-stu-id="ea940-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="ea940-106">![Topología de referencia implementar tres diagramas de servidores](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Topología de referencia implementar tres diagramas de servidores")</span><span class="sxs-lookup"><span data-stu-id="ea940-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="ea940-107">**Par de servidores Standard Edition implementados**     esta organización tiene 4.000 usuarios en su sitio central.</span><span class="sxs-lookup"><span data-stu-id="ea940-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="ea940-108">La organización ha implementado dos servidores Standard Edition y los ha combinado para habilitar la alta disponibilidad y la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="ea940-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="ea940-109">Cada servidor aloja 2.000 usuarios, pero la información acerca de todos los usuarios se sincroniza entre los dos servidores.</span><span class="sxs-lookup"><span data-stu-id="ea940-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="ea940-110">Si se produce un error, un administrador puede conmutar por error a los usuarios para que los atienda el otro servidor, con el mínimo de interrupciones para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ea940-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="ea940-111">Para obtener más información sobre las características de alta disponibilidad y recuperación ante desastres en Lync Server 2013, consulte [planeación de alta disponibilidad y recuperación ante desastres en Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ea940-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="ea940-112">**Se recomienda la implementación de servidores perimetrales.**    Aunque no se requiere la implementación de un servidor perimetral para la mensajería instantánea interna, la presencia y la Conferencia, le recomendamos incluso en el caso de implementaciones pequeñas.</span><span class="sxs-lookup"><span data-stu-id="ea940-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="ea940-113">Puede maximizar la inversión de Lync Server implementando un servidor perimetral para proporcionar servicio a los usuarios que están actualmente fuera de los firewalls de la organización.</span><span class="sxs-lookup"><span data-stu-id="ea940-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="ea940-114">Entre las ventajas se incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ea940-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="ea940-115">Los propios usuarios de su organización pueden usar la funcionalidad de Lync Server, si trabajan desde casa o están de viaje.</span><span class="sxs-lookup"><span data-stu-id="ea940-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="ea940-116">Sus usuarios pueden invitar a usuarios externos para participar en reuniones.</span><span class="sxs-lookup"><span data-stu-id="ea940-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="ea940-117">Si tiene una organización de asociados, proveedores o clientes que también usa Lync Server, puede crear una *relación federada* con esa organización.</span><span class="sxs-lookup"><span data-stu-id="ea940-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="ea940-118">La implementación de Lync Server entonces reconocerá a los usuarios de esa organización federada, lo que le proporcionará una mejor colaboración.</span><span class="sxs-lookup"><span data-stu-id="ea940-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="ea940-119">Los usuarios pueden intercambiar mensajes instantáneos con usuarios de servicios de mensajería instantánea pública, entre los que se incluyen los siguientes: Windows Live,\!AOL, Yahoo y Google Talk.</span><span class="sxs-lookup"><span data-stu-id="ea940-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="ea940-120">Es posible que se requiera una licencia independiente para la conectividad de mensajería instantánea pública con estos servicios.</span><span class="sxs-lookup"><span data-stu-id="ea940-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="ea940-121">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="ea940-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="ea940-122">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ea940-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="ea940-123">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="ea940-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="ea940-124">Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ea940-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="ea940-125">se ha anunciado.</span><span class="sxs-lookup"><span data-stu-id="ea940-125">has been announced.</span></span> <span data-ttu-id="ea940-126">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ea940-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="ea940-127">La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ea940-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="ea940-128">Service.</span><span class="sxs-lookup"><span data-stu-id="ea940-128">Messenger.</span></span> <span data-ttu-id="ea940-129">La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</span><span class="sxs-lookup"><span data-stu-id="ea940-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="ea940-130">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="ea940-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="ea940-131">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="ea940-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="ea940-132">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</span><span class="sxs-lookup"><span data-stu-id="ea940-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="ea940-133">**Supervivencia del sitio de sucursal.**    Esta organización está ejecutando un programa piloto de la característica Enterprise Voice de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea940-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="ea940-134">Algunos usuarios usan Lync Server como su única solución de voz.</span><span class="sxs-lookup"><span data-stu-id="ea940-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="ea940-135">Algunos de estos usuarios de la prueba piloto de voz se encuentran en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="ea940-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="ea940-136">El sitio de sucursal no tiene un vínculo de red de área extensa (WAN) confiable al sitio central, por lo que se implementa una aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="ea940-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="ea940-137">Con esta implementación, si el vínculo WAN deja de funcionar, los usuarios del sitio de sucursal pueden seguir realizando y recibiendo llamadas (ambas llamadas dentro de la organización y las llamadas RTC), tienen funcionalidad de correo de voz y se comunican con la mensajería instantánea de dos participantes (mi).</span><span class="sxs-lookup"><span data-stu-id="ea940-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="ea940-138">Los usuarios también pueden autenticarse cuando el vínculo WAN tampoco está disponible.</span><span class="sxs-lookup"><span data-stu-id="ea940-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="ea940-139">**Implementación de mensajería unificada de Exchange.**</span><span class="sxs-lookup"><span data-stu-id="ea940-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="ea940-140">Esta topología de referencia incluye un servidor de mensajería unificada (UM) de Exchange, que ejecuta Microsoft Exchange Server, no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea940-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="ea940-141">Para obtener más información acerca de la mensajería unificada de Exchange, consulte [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y [Hosted Exchange Unified Messaging Integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="ea940-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="ea940-142">**Office Web Apps Server.**</span><span class="sxs-lookup"><span data-stu-id="ea940-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="ea940-143">Se recomienda implementar un Office Web Apps Server o granja de servidores de Office Web Apps Server en cada organización que use conferencias web.</span><span class="sxs-lookup"><span data-stu-id="ea940-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="ea940-144">Office Web Apps Server hace posible que las diapositivas de PowerPoint se presenten en las conferencias web.</span><span class="sxs-lookup"><span data-stu-id="ea940-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="ea940-145">Para obtener más información, consulte Configuración de la [integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="ea940-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

