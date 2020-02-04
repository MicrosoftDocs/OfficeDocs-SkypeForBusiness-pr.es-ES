---
title: 'Lync Server 2013: Roles de servidor'
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
ms.openlocfilehash: b22115bf137c388fd6cd15103ac882056affa4f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="1aebf-102">Roles de servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aebf-102">Server roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1aebf-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="1aebf-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="1aebf-104">Cada servidor que ejecuta Lync Server ejecuta uno o varios *roles de servidor*.</span><span class="sxs-lookup"><span data-stu-id="1aebf-104">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="1aebf-105">Un rol de servidor es un conjunto definido de funcionalidades de Lync Server proporcionadas por ese servidor.</span><span class="sxs-lookup"><span data-stu-id="1aebf-105">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="1aebf-106">No es necesario implementar todos los roles de servidor disponibles en la red.</span><span class="sxs-lookup"><span data-stu-id="1aebf-106">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="1aebf-107">Instale solo los que incluyan la funcionalidad que desee.</span><span class="sxs-lookup"><span data-stu-id="1aebf-107">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="1aebf-108">Incluso si no está familiarizado con los roles de servidor de Lync Server, la herramienta de planeación puede guiar la mejor solución para los servidores que necesita implementar, en función de las características que desee.</span><span class="sxs-lookup"><span data-stu-id="1aebf-108">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="1aebf-109">Esta sección proporciona una breve introducción a los roles de servidor y las características generales que proporcionan:</span><span class="sxs-lookup"><span data-stu-id="1aebf-109">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="1aebf-110">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="1aebf-110">Standard Edition Server</span></span>

  - <span data-ttu-id="1aebf-111">Servidor front-end y servidor back-end</span><span class="sxs-lookup"><span data-stu-id="1aebf-111">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="1aebf-112">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="1aebf-112">Edge Server</span></span>

  - <span data-ttu-id="1aebf-113">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="1aebf-113">Mediation Server</span></span>

  - <span data-ttu-id="1aebf-114">Director</span><span class="sxs-lookup"><span data-stu-id="1aebf-114">Director</span></span>

  - <span data-ttu-id="1aebf-115">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="1aebf-115">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="1aebf-116">Almacén de chat persistente (servidor de back-end de chat persistente)</span><span class="sxs-lookup"><span data-stu-id="1aebf-116">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="1aebf-117">Almacén de cumplimiento de chat persistente (servidor back end de cumplimiento de chat persistente)</span><span class="sxs-lookup"><span data-stu-id="1aebf-117">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="1aebf-118">Para la mayoría de roles del servidor, puede implementar *grupos* de varios servidores que ejecuten el mismo rol del servidor para, así, obtener una mayor escalabilidad y alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1aebf-118">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="1aebf-119">Todos los servidores de un grupo de servidores necesitan ejecutar uno o varios roles del servidor idénticos.</span><span class="sxs-lookup"><span data-stu-id="1aebf-119">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="1aebf-120">Para la mayoría de los tipos de grupos de servidores de Lync, debe implementar un equilibrador de carga para distribuir el tráfico entre los distintos servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="1aebf-120">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="1aebf-121">Lync Server admite el equilibrio de carga del sistema de nombres de dominio (DNS) y los equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="1aebf-121">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="1aebf-122">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="1aebf-122">Standard Edition Server</span></span>

<span data-ttu-id="1aebf-123">El servidor Standard Edition está diseñado para pequeñas organizaciones y para proyectos piloto de organizaciones grandes.</span><span class="sxs-lookup"><span data-stu-id="1aebf-123">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="1aebf-124">Permite que muchas de las características de Lync Server, incluidas las bases de datos necesarias, se ejecuten en un solo servidor.</span><span class="sxs-lookup"><span data-stu-id="1aebf-124">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="1aebf-125">Esto le permite tener la funcionalidad de Lync Server a un costo menor, pero no proporciona una verdadera solución de alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1aebf-125">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="1aebf-126">El servidor Standard Edition le permite usar la mensajería instantánea (mi), presencia, Conferencia y telefonía IP empresarial, todo en un mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="1aebf-126">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="1aebf-127">Para obtener una solución de alta disponibilidad, use Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="1aebf-127">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="1aebf-128">Servidor front-end y servidor back-end</span><span class="sxs-lookup"><span data-stu-id="1aebf-128">Front End Server and Back End Server</span></span>

<span data-ttu-id="1aebf-129">En Lync Server Enterprise Edition, el servidor front-end es el rol de servidor principal y ejecuta muchas funciones básicas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1aebf-129">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="1aebf-130">El servidor front-end, junto con los servidores back-end, son los únicos roles de servidor que deben estar en cualquier implementación de Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="1aebf-130">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="1aebf-131">Un *Grupo front-end* es un conjunto de servidores front-end, configurado de manera idéntica, que funcionan conjuntamente para proporcionar servicios a un grupo común de usuarios.</span><span class="sxs-lookup"><span data-stu-id="1aebf-131">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="1aebf-132">Un grupo de varios servidores ejecutando el mismo rol proporciona escalabilidad y funciones de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="1aebf-132">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="1aebf-133">El servidor front-end incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1aebf-133">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="1aebf-134">Autenticación y registro de usuarios</span><span class="sxs-lookup"><span data-stu-id="1aebf-134">User authentication and registration</span></span>

  - <span data-ttu-id="1aebf-135">Información de presencia y de la tarjeta de contacto</span><span class="sxs-lookup"><span data-stu-id="1aebf-135">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="1aebf-136">Servicios de libreta de direcciones y expansión de la lista de distribución</span><span class="sxs-lookup"><span data-stu-id="1aebf-136">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="1aebf-137">Funciones de mensajería instantánea, incluidas las conferencias de mensajería instantánea entre varias partes</span><span class="sxs-lookup"><span data-stu-id="1aebf-137">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="1aebf-138">Conferencia Web, Conferencia de acceso telefónico local RTC y conferencia A/V (si se ha implementado)</span><span class="sxs-lookup"><span data-stu-id="1aebf-138">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="1aebf-139">Hospedaje de aplicaciones, para las dos aplicaciones incluidas con Lync Server (por ejemplo, el operador de conferencias y la aplicación de grupo de respuesta) y aplicaciones de terceros</span><span class="sxs-lookup"><span data-stu-id="1aebf-139">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="1aebf-140">Opcionalmente, la supervisión, para recopilar información de uso en forma de registros detallados de llamadas (CDR) y registros de errores de llamadas (CER).</span><span class="sxs-lookup"><span data-stu-id="1aebf-140">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="1aebf-141">Esta información proporciona métricas sobre la calidad de los medios (audio y vídeo) que atraviesan tu red tanto las llamadas de voz empresariales como las conferencias A/V.</span><span class="sxs-lookup"><span data-stu-id="1aebf-141">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="1aebf-142">Componentes web para las tareas basadas en web compatibles, como el Programador web y el Iniciador de participación en reuniones.</span><span class="sxs-lookup"><span data-stu-id="1aebf-142">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="1aebf-143">Opcionalmente, el archivado, para archivar comunicaciones de MI y contenido de reuniones con fines de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="1aebf-143">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="1aebf-144">Para obtener más información, vea [planificación de archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="1aebf-144">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="1aebf-145">En Lync Server 2010 y versiones anteriores, la supervisión y el archivado eran roles de servidor diferentes, no colocados en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1aebf-145">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="1aebf-146">Opcionalmente, si el chat persistente está habilitado, servicios web de chat persistente para la administración de salones de chat y para la carga y descarga de archivos.</span><span class="sxs-lookup"><span data-stu-id="1aebf-146">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="1aebf-p109">Los grupos de servidores front-end también son el lugar principal de almacenamiento de los datos de conferencia y de usuario. La información sobre cada usuario se replica entre tres servidores front-end del grupo, y se hace una copia de seguridad de esta información en los servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="1aebf-p109">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="1aebf-149">Además, un grupo de servidores front-end de la implementación también ejecuta el *servidor de administración central*, que administra e implementa los datos de configuración básica de todos los servidores que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1aebf-149">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="1aebf-150">El servidor de administración central también proporciona capacidades de Shell de administración y transferencia de archivos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1aebf-150">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="1aebf-151">Los servidores back-end son servidores de base de datos que ejecutan Microsoft SQL Server y que proporcionan los servicios de base de datos para el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="1aebf-151">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="1aebf-152">Los servidores back-end actúan como almacenes de copias de seguridad de los datos de conferencia y de usuario del grupo y, asimismo, constituyen los lugares principales de almacenamiento para otras bases de datos, como la de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="1aebf-152">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="1aebf-153">Puede tener un único servidor de servicios de fondo, pero se recomienda usar el reflejo de SQL Server para la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="1aebf-153">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="1aebf-154">Los servidores back-end no ejecutan software de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1aebf-154">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1aebf-155">No recomendamos collocating bases de datos de Lync Server con otras bases de datos.</span><span class="sxs-lookup"><span data-stu-id="1aebf-155">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="1aebf-156">Si lo hace, la disponibilidad y el rendimiento pueden verse afectados.</span><span class="sxs-lookup"><span data-stu-id="1aebf-156">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="1aebf-157">La información almacenada en las bases de datos del servidor back-end incluye información de presencia, listas de contactos de los usuarios, datos de conferencia (incluidos los datos persistentes sobre el estado de todas las conferencias actuales) y datos de programación de conferencias.</span><span class="sxs-lookup"><span data-stu-id="1aebf-157">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="1aebf-158">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="1aebf-158">Edge Server</span></span>

<span data-ttu-id="1aebf-159">El servidor perimetral permite a los usuarios comunicarse y colaborar con usuarios ajenos a los firewalls de la organización.</span><span class="sxs-lookup"><span data-stu-id="1aebf-159">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="1aebf-160">Estos usuarios externos pueden incluir los usuarios de la organización que actualmente están trabajando fuera del sitio, los usuarios de organizaciones de socios federados y los usuarios externos que han recibido una invitación para unirse a conferencias hospedadas en su implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1aebf-160">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="1aebf-161">El servidor perimetral también permite la conectividad con servicios de conectividad de mensajería instantánea pública, como Windows\!Live, AOL, Yahoo y Google Talk.</span><span class="sxs-lookup"><span data-stu-id="1aebf-161">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="1aebf-162">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="1aebf-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="1aebf-163">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1aebf-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="1aebf-164">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="1aebf-164">Messenger until the service shut down date.</span></span> <span data-ttu-id="1aebf-165">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1aebf-165">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="1aebf-166">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="1aebf-166">has been announced.</span></span> <span data-ttu-id="1aebf-167">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1aebf-167">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="1aebf-168">El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1aebf-168">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="1aebf-169">Mensajería.</span><span class="sxs-lookup"><span data-stu-id="1aebf-169">Messenger.</span></span> <span data-ttu-id="1aebf-170">La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</span><span class="sxs-lookup"><span data-stu-id="1aebf-170">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="1aebf-171">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="1aebf-171">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="1aebf-172">La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="1aebf-172">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="1aebf-173">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="1aebf-173">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="1aebf-174">La implementación de servidor perimetral también permite servicios de movilidad, que admiten la funcionalidad de Lync en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="1aebf-174">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="1aebf-175">Los usuarios pueden usar dispositivos móviles Apple iOS, Android, Windows Phone o Nokia compatibles para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver el estado de presencia.</span><span class="sxs-lookup"><span data-stu-id="1aebf-175">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="1aebf-176">Además, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, llamar a través del trabajo, acceso a un número único, correo de voz y llamadas perdidas.</span><span class="sxs-lookup"><span data-stu-id="1aebf-176">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="1aebf-177">La característica de movilidad también admite las *notificaciones de inserción* en los dispositivos móviles que no son compatibles con las aplicaciones que se ejecutan en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1aebf-177">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="1aebf-178">Las notificaciones de inserción son notificaciones que se envían a dispositivos móviles sobre un evento que se produce mientras una aplicación móvil está inactiva.</span><span class="sxs-lookup"><span data-stu-id="1aebf-178">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="1aebf-179">Los servidores perimetrales también incluyen un proxy totalmente integrado de Extensible Messaging and Presence Protocol (XMPP), con una puerta de enlace XMPP incluida en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="1aebf-179">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="1aebf-180">Puede configurar estos componentes XMPP para permitir a los usuarios de Lync Server 2013 agregar contactos de socios basados en XMPP (como Google Talk) para la mensajería instantánea y la presencia.</span><span class="sxs-lookup"><span data-stu-id="1aebf-180">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="1aebf-181">Para obtener más información, vea [planificación para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="1aebf-181">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="1aebf-182">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="1aebf-182">Mediation Server</span></span>

<span data-ttu-id="1aebf-183">Servidor de mediación es un componente necesario para implementar la telefonía IP empresarial y las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="1aebf-183">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="1aebf-184">Servidor de mediación traduce la señalización y, en algunas configuraciones, medios entre la infraestructura interna de Lync Server y una puerta de enlace de red telefónica conmutada (RTC), IP-PBX o un tronco de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="1aebf-184">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="1aebf-185">Puede ejecutar el servidor de mediación en el mismo servidor que el servidor front-end o separarlo en un grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="1aebf-185">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="1aebf-186">Para obtener más información, vea [componente de servidor de mediación en Lync server 2013](lync-server-2013-mediation-server-component.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="1aebf-186">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="1aebf-187">Director</span><span class="sxs-lookup"><span data-stu-id="1aebf-187">Director</span></span>

<span data-ttu-id="1aebf-188">Los directores pueden autenticar solicitudes de usuario de Lync Server, pero no alojan cuentas de usuario ni proporcionan servicios de presencia o de conferencia.</span><span class="sxs-lookup"><span data-stu-id="1aebf-188">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="1aebf-189">Los directores son de mucha utilidad para mejorar la seguridad en las implementaciones donde el acceso de usuarios externos está permitido.</span><span class="sxs-lookup"><span data-stu-id="1aebf-189">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="1aebf-190">El director puede autenticar las solicitudes antes de enviarlas a los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="1aebf-190">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="1aebf-191">En caso de un ataque por denegación de servicio, el ataque termina en el director y no llega los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="1aebf-191">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="1aebf-192">Para obtener más información, consulte [escenarios del Director de Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="1aebf-192">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="1aebf-193">Roles de servidor de chat persistentes</span><span class="sxs-lookup"><span data-stu-id="1aebf-193">Persistent Chat Server Roles</span></span>

<span data-ttu-id="1aebf-p121">El chat persistente permite a los usuarios participar en conversaciones entre varias entidades sobre un tema en particular que persisten a lo largo del tiempo. El servidor front-end de chat persistente ejecuta el servicio de chat persistente, mientras que el servidor back-end de chat persistente almacena los datos del historial de chat y la información sobre categorías y salones de chat. El servidor back-end opcional de cumplimiento de chat persistente puede almacenar el contenido del chat y los eventos de cumplimiento con fines de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="1aebf-p121">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="1aebf-198">Los servidores que ejecutan Lync Server Standard Edition también pueden ejecutar una conversación persistente colocada en el mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="1aebf-198">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="1aebf-199">No puede Collocate el servidor front-end de chat persistente con el servidor front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="1aebf-199">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="1aebf-200">Para obtener más información, consulte [planear el servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="1aebf-200">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1aebf-201">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aebf-201">See Also</span></span>


[<span data-ttu-id="1aebf-202">Componente de servidor de mediación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aebf-202">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="1aebf-203">Planificar el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aebf-203">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="1aebf-204">Planear acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aebf-204">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="1aebf-205">Escenarios para el director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aebf-205">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="1aebf-206">Planeación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aebf-206">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

