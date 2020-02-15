---
title: Lync Server 2013 roles de servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 093161cec5a13ac12840776dec731773782966c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="64650-102">Roles de servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64650-102">Server roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64650-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="64650-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="64650-104">Cada servidor que ejecuta Lync Server ejecuta uno o más *roles de servidor*.</span><span class="sxs-lookup"><span data-stu-id="64650-104">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="64650-105">Un rol de servidor es un conjunto definido de funcionalidades de Lync Server que proporciona el servidor.</span><span class="sxs-lookup"><span data-stu-id="64650-105">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="64650-106">No es necesario que implemente todos los roles del servidor disponibles en su red.</span><span class="sxs-lookup"><span data-stu-id="64650-106">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="64650-107">Instale solo los que incluyan la funcionalidad que desee.</span><span class="sxs-lookup"><span data-stu-id="64650-107">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="64650-108">Incluso si no está familiarizado con los roles de servidor de Lync Server, la herramienta de planeación puede guiarle a la mejor solución para los servidores que necesita implementar, en función de las características que desee.</span><span class="sxs-lookup"><span data-stu-id="64650-108">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="64650-109">En esta sección se proporciona un breve resumen de los roles del servidor y de las características generales que ofrecen:</span><span class="sxs-lookup"><span data-stu-id="64650-109">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="64650-110">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="64650-110">Standard Edition Server</span></span>

  - <span data-ttu-id="64650-111">Servidor front-end y servidor back-end</span><span class="sxs-lookup"><span data-stu-id="64650-111">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="64650-112">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="64650-112">Edge Server</span></span>

  - <span data-ttu-id="64650-113">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="64650-113">Mediation Server</span></span>

  - <span data-ttu-id="64650-114">Dirección</span><span class="sxs-lookup"><span data-stu-id="64650-114">Director</span></span>

  - <span data-ttu-id="64650-115">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="64650-115">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="64650-116">Almacén de chat persistente (servidor back-end de chat persistente)</span><span class="sxs-lookup"><span data-stu-id="64650-116">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="64650-117">Almacén de cumplimiento de chat persistente (servidor back-end de cumplimiento de chat persistente)</span><span class="sxs-lookup"><span data-stu-id="64650-117">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="64650-118">Para la mayoría de roles del servidor, puede implementar *grupos* de varios servidores que ejecuten el mismo rol del servidor con el fin de obtener una mayor escalabilidad y alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="64650-118">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="64650-119">Todos los servidores de un grupo de servidores deben ejecutar uno o varios roles del servidor idénticos.</span><span class="sxs-lookup"><span data-stu-id="64650-119">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="64650-120">Para la mayoría de los tipos de grupos de servidores de Lync Server, debe implementar un equilibrador de carga para distribuir el tráfico entre los distintos servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="64650-120">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="64650-121">Lync Server admite tanto el equilibrio de carga del sistema de nombres de dominio (DNS) como los equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="64650-121">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="64650-122">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="64650-122">Standard Edition Server</span></span>

<span data-ttu-id="64650-123">El servidor Standard Edition está diseñado para organizaciones pequeñas y para proyectos piloto de organizaciones de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="64650-123">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="64650-124">Permite que muchas de las características de Lync Server, incluidas las bases de datos necesarias, se ejecuten en un único servidor.</span><span class="sxs-lookup"><span data-stu-id="64650-124">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="64650-125">Esto le permite disponer de funcionalidad de Lync Server para un menor costo, pero no proporciona una solución de alta disponibilidad real.</span><span class="sxs-lookup"><span data-stu-id="64650-125">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="64650-126">El servidor Standard Edition permite usar la mensajería instantánea (mi), la presencia, la Conferencia y la telefonía IP empresarial, todo ello en un servidor.</span><span class="sxs-lookup"><span data-stu-id="64650-126">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="64650-127">Para una solución de alta disponibilidad, use Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="64650-127">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="64650-128">Servidor front-end y servidor back-end</span><span class="sxs-lookup"><span data-stu-id="64650-128">Front End Server and Back End Server</span></span>

<span data-ttu-id="64650-129">En Lync Server Enterprise Edition, el servidor front-end es el rol de servidor principal y ejecuta muchas funciones básicas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64650-129">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="64650-130">El servidor front-end, junto con los servidores back-end, son los únicos roles de servidor necesarios para estar en cualquier implementación de Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="64650-130">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="64650-p106">Un *grupo de servidores front-end* es un conjunto de servidores front-end configurados de forma idéntica que trabajan juntos para proporcionar servicios a un grupo común de usuarios. Un grupo de varios servidores ejecutando el mismo rol proporciona escalabilidad y funciones de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="64650-p106">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users. A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="64650-133">El servidor front-end incluye:</span><span class="sxs-lookup"><span data-stu-id="64650-133">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="64650-134">Registro y autenticación de usuarios</span><span class="sxs-lookup"><span data-stu-id="64650-134">User authentication and registration</span></span>

  - <span data-ttu-id="64650-135">Información de presencia e intercambio de tarjetas de contacto</span><span class="sxs-lookup"><span data-stu-id="64650-135">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="64650-136">Servicios de libreta de direcciones y ampliación de la lista de distribución</span><span class="sxs-lookup"><span data-stu-id="64650-136">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="64650-137">Funcionalidad de MI, incluidas las conferencias de MI de varios participantes</span><span class="sxs-lookup"><span data-stu-id="64650-137">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="64650-138">Conferencia web, conferencia de acceso telefónico local por y conferencia A/V (si se ha implementado)</span><span class="sxs-lookup"><span data-stu-id="64650-138">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="64650-139">Hospedaje de aplicaciones, para ambas aplicaciones incluidas en Lync Server (por ejemplo, operador de conferencia y aplicación de grupo de respuesta) y aplicaciones de terceros</span><span class="sxs-lookup"><span data-stu-id="64650-139">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="64650-140">Opcionalmente, la supervisión, para recopilar información de uso en forma de registros de detalles de las llamadas (CDR) y registros de errores de las llamadas (CER).</span><span class="sxs-lookup"><span data-stu-id="64650-140">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="64650-141">Esta información proporciona métricas sobre la calidad de los medios (audio y vídeo) que atraviesan la red tanto para llamadas de telefonía IP empresariales como para conferencias de A/V.</span><span class="sxs-lookup"><span data-stu-id="64650-141">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="64650-142">Componentes web para las tareas basadas en web compatibles, como el Programador web y Join Launcher.</span><span class="sxs-lookup"><span data-stu-id="64650-142">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="64650-143">Opcionalmente, el archivado, para archivar comunicaciones de MI y contenido de reuniones con fines de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="64650-143">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="64650-144">Para obtener más información, consulte [planeación del archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="64650-144">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="64650-145">En Lync Server 2010 y versiones anteriores, la supervisión y el archivado eran roles de servidor independientes, no combinados en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="64650-145">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="64650-146">Opcionalmente, si el chat persistente está habilitado, servicios web de chat persistente para la administración de salones de chat y para la carga y descarga de archivos.</span><span class="sxs-lookup"><span data-stu-id="64650-146">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="64650-p109">Los grupos de servidores front-end también son el lugar principal de almacenamiento para los datos de conferencia y de usuario. La información sobre cada usuario se replica entre tres servidores front-end del grupo, y se hace una copia de seguridad de la misma en los servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="64650-p109">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="64650-149">Además, un grupo de servidores front-end de la implementación también ejecuta el *servidor de administración central*, que administra e implementa datos de configuración básica en todos los servidores que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64650-149">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="64650-150">El servidor de administración central también proporciona funcionalidad de transferencia de archivos y Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64650-150">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="64650-151">Los servidores back-end son servidores de base de datos que ejecutan Microsoft SQL Server y que proporcionan los servicios de bases de datos para el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="64650-151">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="64650-152">Los servidores back-end actúan como almacenes de copias de seguridad de los datos de conferencia y de usuario del grupo, y constituyen los lugares principales de almacenamiento para otras bases de datos, como la de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="64650-152">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="64650-153">Puede tener un solo servidor back-end, pero se recomienda una solución que use la creación de reflejos de SQL Server para la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="64650-153">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="64650-154">Los servidores back-end no ejecutan ningún software de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64650-154">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="64650-155">No se recomiendan las bases de datos de combinar Lync Server con otras bases de datos.</span><span class="sxs-lookup"><span data-stu-id="64650-155">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="64650-156">Si lo hace, puede que se vea afectada la disponibilidad y el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="64650-156">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="64650-157">La información almacenada en las bases de datos del servidor back-end incluye información de presencia, listas de contactos de los usuarios, datos de conferencia (incluidos los datos persistentes sobre el estado de todas las conferencias actuales) y datos de programación de conferencias.</span><span class="sxs-lookup"><span data-stu-id="64650-157">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="64650-158">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="64650-158">Edge Server</span></span>

<span data-ttu-id="64650-159">Servidor perimetral permite a los usuarios comunicarse y colaborar con usuarios fuera de los firewalls de la organización.</span><span class="sxs-lookup"><span data-stu-id="64650-159">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="64650-160">Estos usuarios externos pueden incluir los propios usuarios de la organización que actualmente trabajan fuera del sitio, usuarios de organizaciones de socios federados y usuarios externos que han invitado a unirse a conferencias hospedadas en su implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64650-160">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="64650-161">El servidor perimetral también habilita la conectividad con los servicios de conectividad de mensajería instantánea pública, incluidos\!Windows Live, AOL, Yahoo y Google Talk.</span><span class="sxs-lookup"><span data-stu-id="64650-161">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="64650-162">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="64650-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="64650-163">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="64650-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="64650-164">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="64650-164">Messenger until the service shut down date.</span></span> <span data-ttu-id="64650-165">Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="64650-165">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="64650-166">se ha anunciado.</span><span class="sxs-lookup"><span data-stu-id="64650-166">has been announced.</span></span> <span data-ttu-id="64650-167">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="64650-167">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="64650-168">La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="64650-168">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="64650-169">Service.</span><span class="sxs-lookup"><span data-stu-id="64650-169">Messenger.</span></span> <span data-ttu-id="64650-170">La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</span><span class="sxs-lookup"><span data-stu-id="64650-170">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="64650-171">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="64650-171">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="64650-172">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="64650-172">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="64650-173">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</span><span class="sxs-lookup"><span data-stu-id="64650-173">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="64650-174">La implementación del servidor perimetral también habilita los servicios de movilidad, que admiten la funcionalidad de Lync en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="64650-174">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="64650-175">Los usuarios pueden utilizar dispositivos móviles compatibles Apple iOS, Android, Windows Phone o Nokia para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver el estado de presencia.</span><span class="sxs-lookup"><span data-stu-id="64650-175">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="64650-176">Asimismo, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, Vía trabajo, conexión con un solo número, correo de voz y llamadas perdidas.</span><span class="sxs-lookup"><span data-stu-id="64650-176">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="64650-177">La característica de movilidad también admite las *notificaciones de inserción* en los dispositivos móviles que no son compatibles con las aplicaciones que se ejecutan en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="64650-177">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="64650-178">Las notificaciones de inserción son notificaciones que se envían a dispositivos móviles sobre un evento que se produce mientras una aplicación móvil está inactiva.</span><span class="sxs-lookup"><span data-stu-id="64650-178">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="64650-179">Los servidores perimetrales también incluyen un proxy totalmente integrado del Protocolo extensible de mensajería y presencia (XMPP), con una puerta de enlace XMPP incluida en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="64650-179">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="64650-180">Puede configurar estos componentes XMPP para permitir que los usuarios de Lync Server 2013 puedan agregar contactos de socios basados en XMPP (como Google Talk) para la mensajería instantánea y la presencia.</span><span class="sxs-lookup"><span data-stu-id="64650-180">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="64650-181">Para obtener más información, consulte [Planning for external User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="64650-181">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="64650-182">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="64650-182">Mediation Server</span></span>

<span data-ttu-id="64650-183">El servidor de mediación es un componente necesario para implementar la telefonía IP empresarial y la Conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="64650-183">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="64650-184">El servidor de mediación traduce la señalización y, en algunas configuraciones, los medios entre la infraestructura interna de Lync Server y una puerta de enlace de red telefónica conmutada (RTC), IP-PBX o un tronco de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="64650-184">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="64650-185">El servidor de mediación se puede ejecutar combinado en el mismo servidor que el servidor front-end o solo en un grupo del servidor de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="64650-185">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="64650-186">Para obtener más información, consulte [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="64650-186">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="64650-187">Dirección</span><span class="sxs-lookup"><span data-stu-id="64650-187">Director</span></span>

<span data-ttu-id="64650-188">Los directores pueden autenticar solicitudes de usuario de Lync Server, pero no alojan cuentas de usuario ni proporcionan servicios de presencia o conferencia.</span><span class="sxs-lookup"><span data-stu-id="64650-188">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="64650-189">Los directores son de mucha utilidad para mejorar la seguridad en las implementaciones que habilitan el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="64650-189">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="64650-190">El director puede autenticar las solicitudes antes de enviarlas a los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="64650-190">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="64650-191">En caso de un ataque por denegación de servicio, el ataque termina en el director y no alcanza los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="64650-191">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="64650-192">Para obtener más información, consulte [escenarios del Director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="64650-192">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="64650-193">Roles de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="64650-193">Persistent Chat Server Roles</span></span>

<span data-ttu-id="64650-p121">El chat persistente permite a los usuarios participar en conversaciones con varios participantes sobre un tema en particular que persisten a lo largo del tiempo. El servidor front-end de chat persistente ejecuta el servicio de chat persistente. El servidor back-end de chat persistente almacena los datos del historial de chat y la información sobre categorías y salones de chat. El servidor back-end opcional de cumplimiento de chat persistente puede almacenar el contenido del chat y los eventos de cumplimiento con fines de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="64650-p121">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="64650-198">Los servidores que ejecutan Lync Server Standard Edition también pueden ejecutar chat persistente colocado en el mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="64650-198">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="64650-199">No puede combinar el servidor front-end de chat persistente con el servidor front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="64650-199">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="64650-200">Para obtener más información, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="64650-200">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="64650-201">Vea también</span><span class="sxs-lookup"><span data-stu-id="64650-201">See Also</span></span>


[<span data-ttu-id="64650-202">Componente de servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64650-202">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="64650-203">Planeación del archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64650-203">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="64650-204">Planeación del acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64650-204">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="64650-205">Escenarios para el Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64650-205">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="64650-206">Planeación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64650-206">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

