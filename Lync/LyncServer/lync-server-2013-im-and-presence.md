---
title: 'Lync Server 2013: Mensajería instantánea (MI) y presencia'
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
ms.openlocfilehash: 57f57d4fae488a7d4946a0adb1f8350d02114a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="c841f-102">Mensajería instantánea (MI) y presencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c841f-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c841f-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c841f-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="c841f-104">La mensajería instantánea y la presencia se instalan automáticamente en cualquier implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c841f-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="c841f-105">La información de *presencia* permite a los usuarios enfocar colegas en el momento adecuado con la forma de comunicación adecuada para conducir a un entorno de trabajo más productivo.</span><span class="sxs-lookup"><span data-stu-id="c841f-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="c841f-106">La presencia de un usuario es una recopilación de información que incluye disponibilidad, disposición para comunicarse, notas adicionales (como la ubicación y el estado) y cómo se puede contactar con el usuario.</span><span class="sxs-lookup"><span data-stu-id="c841f-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="c841f-107">La presencia se ha mejorado en Lync Server con imágenes, información de ubicación y un amplio conjunto de Estados de presencia que incluye "no disponible", "no molestar" y "volver atrás", además de los Estados básicos como "disponible", "ocupado" y "en una conferencia".</span><span class="sxs-lookup"><span data-stu-id="c841f-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="c841f-108">Los administradores también pueden definir Estados de presencia personalizados y específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="c841f-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="c841f-109">Las opciones de administración de contactos y de acceso de usuarios permiten a los usuarios controlar qué información pueden ver los demás.</span><span class="sxs-lookup"><span data-stu-id="c841f-109">Contact management and user access options enable users to control what information others can see.</span></span> <span data-ttu-id="c841f-110">Los usuarios pueden establecer diferentes niveles de contactos, cada uno de los cuales puede ver diferentes niveles de información de presencia.</span><span class="sxs-lookup"><span data-stu-id="c841f-110">Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="c841f-111">Al mirar simplemente una lista de contactos, los usuarios pueden encontrar todo lo que necesitan saber de un vistazo.</span><span class="sxs-lookup"><span data-stu-id="c841f-111">By simply looking at a Contacts list, users can find everything they need to know at a glance.</span></span> <span data-ttu-id="c841f-112">Los iconos de colores simples indican que el estado de presencia de otros usuarios, además de la imagen y la ubicación.</span><span class="sxs-lookup"><span data-stu-id="c841f-112">Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="c841f-113">Con la integración entre Lync Server y otros productos, como Outlook y SharePoint, cuando aparezca el nombre de un contacto, como en un mensaje de correo electrónico o en un sitio web de equipo, también se mostrará el estado y la información de contacto.</span><span class="sxs-lookup"><span data-stu-id="c841f-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="c841f-114">Además, si implementa Exchange 2013, Lync Server y Exchange 2013 pueden compartir un almacén de contactos unificado, al que los clientes de cualquiera de los productos pueden obtener acceso.</span><span class="sxs-lookup"><span data-stu-id="c841f-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="c841f-115">Con la mensajería instantánea de Lync Server, los usuarios pueden enviar mensajes rápidamente entre sí con información puntual.</span><span class="sxs-lookup"><span data-stu-id="c841f-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="c841f-116">Si lo prefiere, los usuarios también pueden comunicarse con usuarios de redes de mensajería instantánea pública, como MSN/Windows Live\!, Yahoo y AOL.</span><span class="sxs-lookup"><span data-stu-id="c841f-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="c841f-117">Tenga en cuenta que es posible que se necesite una licencia independiente para la conectividad de mensajería instantánea pública con Windows Live, AOL y Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="c841f-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="c841f-118">Lync Server también incluye compatibilidad con el protocolo de presencia y mensajería extensible (XMPP), de modo que los usuarios puedan intercambiar mensajes INSTANTÁNEos e información de presencia con usuarios de servicios XMPP, como Google Talk.</span><span class="sxs-lookup"><span data-stu-id="c841f-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="c841f-119">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="c841f-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="c841f-120">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c841f-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="c841f-121">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="c841f-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="c841f-122">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c841f-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c841f-123">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="c841f-123">has been announced.</span></span> <span data-ttu-id="c841f-124">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c841f-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="c841f-125">El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c841f-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="c841f-126">Mensajería.</span><span class="sxs-lookup"><span data-stu-id="c841f-126">Messenger.</span></span> <span data-ttu-id="c841f-127">La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</span><span class="sxs-lookup"><span data-stu-id="c841f-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="c841f-128">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="c841f-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="c841f-129">La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="c841f-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="c841f-130">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="c841f-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="c841f-131">El historial de conversaciones permite a los usuarios realizar un seguimiento de las conversaciones de mensajes instantáneos anteriores y recuperar información que puede haber sido transmitida por mensajes instantáneos hace meses.</span><span class="sxs-lookup"><span data-stu-id="c841f-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="c841f-132">La característica de chat persistente permite a los usuarios participar en conversaciones de varias partes y basadas en temas que persisten a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="c841f-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="c841f-133">Los mensajes publicados en los salones de chat (foros de discusión) pueden ser persistentes (es decir, disponibles a lo largo del tiempo), de modo que puedan participar las personas de diferentes ubicaciones y departamentos, incluso cuando no estén conectados al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c841f-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="c841f-134">Si su organización debe seguir las normas de cumplimiento, puede implementar una característica de archivado de mensajes para archivar el contenido de los mensajes instantáneos de todos los usuarios de su organización o solo para algunos usuarios que especifique.</span><span class="sxs-lookup"><span data-stu-id="c841f-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="c841f-135">Si también implementa Exchange 2013, el archivo de mensajería instantánea se puede integrar con la característica de conservación local de Exchange, para proporcionar una experiencia de administración única para su cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c841f-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

