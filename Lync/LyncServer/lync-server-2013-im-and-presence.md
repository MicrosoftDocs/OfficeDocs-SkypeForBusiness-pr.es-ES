---
title: Mensajería instantánea y presencia de Lync Server 2013
description: Lync Server 2013 la mensajería instantánea y la presencia.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0d04f0ee6decc03db1a6b5aa44cfedd7515c2d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573286"
---
# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="067a7-103">Mensajería instantánea y presencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="067a7-103">IM and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="067a7-104">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="067a7-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="067a7-105">La mensajería instantánea (mi) y la presencia se instalan automáticamente en cualquier implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="067a7-105">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="067a7-106">La información de *Presencia* permite que los usuarios puedan dirigirse a sus colegas en el momento oportuno y usando el canal de comunicación adecuado y, así, lograr un entorno de trabajo más productivo.</span><span class="sxs-lookup"><span data-stu-id="067a7-106">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="067a7-107">La presencia de los usuarios es una colección de información que incluye la disponibilidad, el deseo de comunicarse, otras notas (como la ubicación y el estado) y el modo de establecer contacto con el usuario.</span><span class="sxs-lookup"><span data-stu-id="067a7-107">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="067a7-108">La presencia se ha mejorado en Lync Server con imágenes, información de ubicación y un amplio conjunto de Estados de presencia que incluye el trabajo "no laborable", "no molestar" y "volver atrás", además de los Estados básicos, como "disponible", "ocupado" y "en una conferencia".</span><span class="sxs-lookup"><span data-stu-id="067a7-108">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="067a7-109">Los administradores también pueden definir estados de presencia personalizados o específicos de una organización.</span><span class="sxs-lookup"><span data-stu-id="067a7-109">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="067a7-p102">Las opciones de administración de contactos y de acceso de usuarios permiten a los usuarios controlar la información que pueden ver los demás. Los usuarios pueden establecer varios niveles de contactos, que podrán ver diferentes niveles de información de presencia.</span><span class="sxs-lookup"><span data-stu-id="067a7-p102">Contact management and user access options enable users to control what information others can see. Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="067a7-p103">Con solo mirar la lista de contactos, los usuarios podrán encontrar de inmediato todo lo que necesiten. Unos iconos sencillos de colores indican el estado de presencia de otros usuarios, y además aparecen la foto y la ubicación.</span><span class="sxs-lookup"><span data-stu-id="067a7-p103">By simply looking at a Contacts list, users can find everything they need to know at a glance. Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="067a7-114">Con la integración entre Lync Server y otros productos como Outlook y SharePoint, siempre que aparezca el nombre de un contacto, como en un mensaje de correo electrónico o en un sitio web de grupo, también se muestra el estado y la información de contacto.</span><span class="sxs-lookup"><span data-stu-id="067a7-114">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="067a7-115">Además, si implementa Exchange 2013, Lync Server y Exchange 2013 pueden compartir un almacén de contactos unificado, al que pueden tener acceso los clientes de ambos productos.</span><span class="sxs-lookup"><span data-stu-id="067a7-115">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="067a7-116">Con la mensajería instantánea en Lync Server, los usuarios pueden crear mensajes rápidamente entre sí con información oportuna.</span><span class="sxs-lookup"><span data-stu-id="067a7-116">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="067a7-117">Si lo prefiere, los usuarios también pueden comunicarse con usuarios de redes de mensajería instantánea pública, como MSN/Windows Live, Yahoo \! y AOL.</span><span class="sxs-lookup"><span data-stu-id="067a7-117">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="067a7-118">Tenga en cuenta que es posible que se requiera una licencia independiente para la conectividad de mensajería instantánea pública con Windows Live, AOL y Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="067a7-118">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="067a7-119">Lync Server también incluye compatibilidad con el protocolo extensible de mensajería y presencia (XMPP), por lo que los usuarios pueden intercambiar mensajes INSTANTÁNEos e información de presencia con usuarios de servicios XMPP, como Google Talk.</span><span class="sxs-lookup"><span data-stu-id="067a7-119">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="067a7-120">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="067a7-120">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="067a7-121">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="067a7-121">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="067a7-122">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="067a7-122">Messenger until the service shut down date.</span></span> <span data-ttu-id="067a7-123">Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="067a7-123">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="067a7-124">se ha anunciado.</span><span class="sxs-lookup"><span data-stu-id="067a7-124">has been announced.</span></span> <span data-ttu-id="067a7-125">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="067a7-125">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="067a7-126">La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="067a7-126">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="067a7-127">Service.</span><span class="sxs-lookup"><span data-stu-id="067a7-127">Messenger.</span></span> <span data-ttu-id="067a7-128">La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</span><span class="sxs-lookup"><span data-stu-id="067a7-128">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="067a7-129">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="067a7-129">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="067a7-130">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="067a7-130">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="067a7-131">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</span><span class="sxs-lookup"><span data-stu-id="067a7-131">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="067a7-132">El historial de la conversación permite que los usuarios mantengan un registro de las conversaciones de mensajería instantánea antiguas, y que puedan recuperar información que hayan enviado mediante mensajería instantánea hace meses.</span><span class="sxs-lookup"><span data-stu-id="067a7-132">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="067a7-133">La característica chat persistente permite a los usuarios participar en conversaciones basadas en temas con varios participantes que persisten a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="067a7-133">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="067a7-134">Los mensajes enviados a los salones de chat (foros de discusión) pueden ser persistentes (esto es, disponibles en el tiempo) para que las personas en diferentes ubicaciones y departamentos puedan participar, incluso cuando no están todos en línea al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="067a7-134">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="067a7-135">Si su organización debe seguir normativas de cumplimiento, puede implementar una característica de archivado de mensajes para almacenar el contenido de los mensajes instantáneos de todos los usuarios de su organización, o solo de algunos usuarios que se especifiquen.</span><span class="sxs-lookup"><span data-stu-id="067a7-135">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="067a7-136">Si también implementa Exchange 2013, el archivo de mensajería instantánea puede integrarse con la característica de retención de In-Place de Exchange, para proporcionar una única experiencia de administración para el cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="067a7-136">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

