---
title: Topología de referencia de Lync Server 2013 para pequeñas organizaciones
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
ms.openlocfilehash: 7e0171d9678d5d890cf4ecb81f6de25f9b558b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="37f10-102">Topología de referencia para Lync Server 2013 en pequeñas organizaciones</span><span class="sxs-lookup"><span data-stu-id="37f10-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37f10-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="37f10-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="37f10-104">La topología de referencia para organizaciones pequeñas muestra cómo puede implementar una solución robusta y de alta disponibilidad implementando solo tres servidores que ejecuten Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37f10-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="37f10-105">**Topología de referencia para pequeñas organizaciones**</span><span class="sxs-lookup"><span data-stu-id="37f10-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="37f10-106">![Diagrama de la topología de referencia con tres servidores implementados](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Diagrama de la topología de referencia con tres servidores implementados")</span><span class="sxs-lookup"><span data-stu-id="37f10-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="37f10-107">**Par de servidores Standard Edition implementados**     esta organización tiene 4.000 usuarios en su sitio central.</span><span class="sxs-lookup"><span data-stu-id="37f10-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="37f10-108">La organización ha implementado dos servidores Standard Edition y los ha emparejado para habilitar la alta disponibilidad y la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="37f10-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="37f10-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span><span class="sxs-lookup"><span data-stu-id="37f10-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="37f10-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span><span class="sxs-lookup"><span data-stu-id="37f10-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="37f10-111">Para obtener más información sobre las características de alta disponibilidad y recuperación ante desastres de Lync Server 2013, consulte [planear la alta disponibilidad y la recuperación ante desastres en Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="37f10-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="37f10-112">**Se recomienda la implementación del servidor perimetral.**    Aunque no es necesario implementar un servidor perimetral para la mensajería instantánea interna, la presencia y las conferencias, le recomendamos incluso para implementaciones pequeñas.</span><span class="sxs-lookup"><span data-stu-id="37f10-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="37f10-113">Puede maximizar la inversión de Lync Server implementando un servidor perimetral para proporcionar servicio a los usuarios que se encuentran fuera de los firewalls de la organización.</span><span class="sxs-lookup"><span data-stu-id="37f10-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="37f10-114">Entre las ventajas se incluye las siguientes:</span><span class="sxs-lookup"><span data-stu-id="37f10-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="37f10-115">Los usuarios de su organización pueden usar la funcionalidad de Lync Server, si están trabajando desde casa o están de viaje.</span><span class="sxs-lookup"><span data-stu-id="37f10-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="37f10-116">Los usuarios pueden invitar a usuarios externos para participar en reuniones.</span><span class="sxs-lookup"><span data-stu-id="37f10-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="37f10-117">Si tiene una organización de socios, proveedores o clientes que también usa Lync Server, puede formar una *relación federada* con esa organización.</span><span class="sxs-lookup"><span data-stu-id="37f10-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="37f10-118">La implementación de Lync Server reconocería los usuarios de esa organización federada, lo que lleva a una mejor colaboración.</span><span class="sxs-lookup"><span data-stu-id="37f10-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="37f10-119">Los usuarios pueden intercambiar mensajes instantáneos con usuarios de servicios de mensajería instantánea pública, entre los que se incluyen cualquiera de los siguientes: Windows\!Live, AOL, Yahoo y Google Talk.</span><span class="sxs-lookup"><span data-stu-id="37f10-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="37f10-120">Es posible que se necesite una licencia por separado para la conectividad de mensajería instantánea pública con estos servicios.</span><span class="sxs-lookup"><span data-stu-id="37f10-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="37f10-121">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="37f10-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="37f10-122">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="37f10-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="37f10-123">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="37f10-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="37f10-124">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="37f10-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="37f10-125">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="37f10-125">has been announced.</span></span> <span data-ttu-id="37f10-126">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="37f10-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="37f10-127">El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="37f10-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="37f10-128">Mensajería.</span><span class="sxs-lookup"><span data-stu-id="37f10-128">Messenger.</span></span> <span data-ttu-id="37f10-129">La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</span><span class="sxs-lookup"><span data-stu-id="37f10-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="37f10-130">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="37f10-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="37f10-131">La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="37f10-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="37f10-132">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="37f10-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="37f10-133">**Supervivencia del sitio de la sucursal.**    Esta organización está ejecutando un programa piloto de la característica de telefonía IP empresarial de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37f10-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="37f10-134">Algunos usuarios usan Lync Server como su única solución de voz.</span><span class="sxs-lookup"><span data-stu-id="37f10-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="37f10-135">Algunos de estos usuarios de la prueba piloto de voz se encuentran en el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="37f10-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="37f10-136">El sitio de la sucursal no tiene un vínculo de red de área extensa (WAN) confiable al sitio central para que se implemente en él un dispositivo de sucursal con la supervivencia.</span><span class="sxs-lookup"><span data-stu-id="37f10-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="37f10-137">Gracias a esta implementación, si el vínculo WAN deja de funcionar, los usuarios del sitio de sucursal podrán seguir realizando y recibiendo llamadas (llamadas dentro de la organización y llamadas RTC), disponer de la función del correo de voz y comunicarse por medio de la mensajería instantánea (MI) entre dos participantes.</span><span class="sxs-lookup"><span data-stu-id="37f10-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="37f10-138">Los usuarios también pueden autenticarse cuando el vínculo WAN no está disponible.</span><span class="sxs-lookup"><span data-stu-id="37f10-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="37f10-139">**Implementación de mensajería unificada de Exchange.**</span><span class="sxs-lookup"><span data-stu-id="37f10-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="37f10-140">Esta topología de referencia incluye un servidor de mensajería unificada (UM) de Exchange, que ejecuta Microsoft Exchange Server, no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37f10-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="37f10-141">Para obtener más información sobre la mensajería unificada de Exchange, consulte [planificación de la integración de mensajería unificada de Exchange en Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y la [integración de mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="37f10-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="37f10-142">**Servidor de Office Web Apps.**</span><span class="sxs-lookup"><span data-stu-id="37f10-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="37f10-143">Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web.</span><span class="sxs-lookup"><span data-stu-id="37f10-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="37f10-144">Office Web Apps Server permite que las diapositivas de PowerPoint se presenten en conferencias web.</span><span class="sxs-lookup"><span data-stu-id="37f10-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="37f10-145">Para obtener más información, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="37f10-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

