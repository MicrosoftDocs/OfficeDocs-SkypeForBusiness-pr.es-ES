---
title: 'Lync Server 2013: Nuevas características para acceso de usuario externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8c27df6befdba620407b3b1fd4fe537b8da831d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="0edfa-102">Nuevas características para acceso de usuario externo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0edfa-102">New features for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0edfa-103">_**Última modificación del tema:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="0edfa-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="0edfa-104">Lync Server 2013 presenta nuevas características que amplían las características y los métodos de comunicación para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0edfa-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="0edfa-105">Además, Lync Server 2013 introduce cambios en los servicios existentes para mejorar la integración y la ampliación de los servicios que están disponibles para su organización.</span><span class="sxs-lookup"><span data-stu-id="0edfa-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="0edfa-106">A continuación se resume un resumen de los cambios que pueden afectar a la planificación y la implementación de los servicios del servidor perimetral 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0edfa-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="0edfa-107">**La compatibilidad con IPv6 con las direcciones**   de Lync Server 2013 admite el direccionamiento IPv6 para todos los servicios de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="0edfa-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="0edfa-108">Si ha proporcionado direcciones IPv6 para las interfaces mediante la configuración de Windows Server, puede usar direcciones IPv6 en la configuración de su servidor perimetral a través de la configuración de dirección IP en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="0edfa-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0edfa-109">El uso de direcciones IPv6 en Lync Server 2013 depende de la compatibilidad de IPv6 en los enrutadores y los firewalls implementados por su organización, así como la compatibilidad con el proveedor de servicios de Internet.</span><span class="sxs-lookup"><span data-stu-id="0edfa-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="0edfa-110">**El protocolo de presencia y mensajería extensible (XMPP)**   Lync Server 2013 introduce un proxy XMPP totalmente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP implementada en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="0edfa-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="0edfa-111">Puede implementar la Federación XMPP como un componente opcional.</span><span class="sxs-lookup"><span data-stu-id="0edfa-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="0edfa-112">Agregar y configurar el proxy XMPP y la puerta de enlace XMPP permiten a los usuarios de Microsoft Lync 2013 agregar contactos de socios basados en XMPP para mensajería instantánea (mi) y presencia.</span><span class="sxs-lookup"><span data-stu-id="0edfa-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0edfa-113">Actualmente, los servicios XMPP de Lync Server 2013 solo proporcionan mensajería instantánea y presencia entre los clientes de Lync y los contactos basados en XMPP.</span><span class="sxs-lookup"><span data-stu-id="0edfa-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="0edfa-114">**Servicios de movilidad para clientes**   móviles introducidos en una actualización de cliente para Lync Server 2010, los servicios de movilidad de Lync Server 2013 permiten clientes móviles de Microsoft Lync en teléfonos móviles y tabletas con dispositivos móviles compatibles de Apple iOS, Android, Windows Phone o Nokia para realizar estas actividades, como enviar y recibir mensajes instantáneos, ver contactos y ver presencia.</span><span class="sxs-lookup"><span data-stu-id="0edfa-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="0edfa-115">Además, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, llamar a través del trabajo, acceso a un número único, correo de voz y notificación de llamada perdida.</span><span class="sxs-lookup"><span data-stu-id="0edfa-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0edfa-116">Los servicios de movilidad usan el proxy inverso y los servicios publicados que se implementan en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="0edfa-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="0edfa-117">No es necesario realizar cambios en los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="0edfa-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="0edfa-118">**Los directores son un rol**   opcional la función del servidor Director en la topología de Lync Server 2013 no ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="0edfa-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="0edfa-119">Aún, hospeda servicios Web, autentica previamente las solicitudes de usuarios entrantes y dirige a los usuarios externos a su grupo de servidores principales.</span><span class="sxs-lookup"><span data-stu-id="0edfa-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="0edfa-120">Cambiar el director de un rol recomendado a un rol opcional no disminuye el valor del Director, pero enfatiza la reducción del número de servidores y otros requisitos de hardware (por ejemplo, los equilibradores de carga de hardware del Director) sin poner en peligro las características y la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="0edfa-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="0edfa-121">Como los servidores front-end pueden hacer el mismo trabajo que el director sin impacto alguno en los servicios proporcionados, también puede implementar directores si así lo desea.</span><span class="sxs-lookup"><span data-stu-id="0edfa-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="0edfa-122">Puede excluir sin riesgos al director con la confianza de que los servidores front-end proporcionarán los mismos servicios en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0edfa-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0edfa-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0edfa-123">See Also</span></span>


[<span data-ttu-id="0edfa-124">Planificación y configuración de IPv6 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0edfa-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="0edfa-125">Planear acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0edfa-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="0edfa-126">Planeamiento de la Federación de protocolo de presencia y mensajería extensible (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0edfa-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

