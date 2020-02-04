---
title: 'Lync Server 2013: Topologías compatibles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f200cde348d1fbdc931daa25abef28aec804a1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="939fb-102">Topologías compatibles en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="939fb-102">Supported topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="939fb-103">_**Última modificación del tema:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="939fb-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="939fb-104">Lync Server 2013 admite la implementación de sitios locales en una organización y la integración de implementaciones locales con implementaciones de Lync Online, que se conoce como una implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="939fb-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="939fb-105">En una implementación híbrida, algunos usuarios están alojados en locales y algunos usuarios están alojados en línea.</span><span class="sxs-lookup"><span data-stu-id="939fb-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="939fb-106">En el caso de implementaciones locales, Lync Server 2013 admite la implementación de uno o varios sitios que se pueden escalar para cumplir con los requisitos de ubicación y disponibilidad elevados.</span><span class="sxs-lookup"><span data-stu-id="939fb-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="939fb-107">Puede estructurar estos sitios y sus componentes para cumplir con los requisitos de acceso y resistencia de su organización.</span><span class="sxs-lookup"><span data-stu-id="939fb-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="939fb-108">Una implementación local de Lync Server 2013 consta de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="939fb-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="939fb-109">Su implementación debe incluir al menos un sitio central (también conocido como un centro de datos).</span><span class="sxs-lookup"><span data-stu-id="939fb-109">Your deployment must include at least one central site (also known as a data center).</span></span> <span data-ttu-id="939fb-110">Cada sitio central debe contener al menos un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="939fb-110">Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server.</span></span> <span data-ttu-id="939fb-111">Se componen de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="939fb-111">These consist of the following:</span></span>
    
      - <span data-ttu-id="939fb-112">El grupo de servidores front-end Enterprise Edition, que consta de uno o varios servidores front-end (por lo general, al menos dos servidores front-end para escalabilidad) y un servidor back-end independiente.</span><span class="sxs-lookup"><span data-stu-id="939fb-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="939fb-113">Un grupo de servidores front-end puede contener un máximo de doce servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="939fb-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="939fb-114">El equilibrio de carga es necesario para varios servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="939fb-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="939fb-115">Para el tráfico SIP, recomendamos el equilibrio de carga de DNS, pero también se admite el equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="939fb-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="939fb-116">Si usa el equilibrio de carga de DNS para el tráfico SIP, aún necesita un equilibrador de carga de hardware para el tráfico HTTP.</span><span class="sxs-lookup"><span data-stu-id="939fb-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="939fb-117">Recomendamos el reflejo de SQL Server para una alta disponibilidad de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="939fb-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="939fb-118">La base de datos back-end requiere una instancia independiente, pero puede Collocate la base de datos de archivado, la supervisión de la base de datos, la base de datos de chat persistente y la base de datos de cumplimiento persistente de la conversación.</span><span class="sxs-lookup"><span data-stu-id="939fb-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="939fb-119">Lync Server 2013 admite el uso de un clúster compartido para los archivos compartidos en la implementación.</span><span class="sxs-lookup"><span data-stu-id="939fb-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="939fb-120">Para obtener más información sobre los requisitos de almacenamiento de base de datos, consulte [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="939fb-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="939fb-121">Para obtener más información sobre los requisitos de almacenamiento de archivos, consulte [compatibilidad de almacenamiento de archivos en Lync Server 2013](lync-server-2013-file-storage-support.md).</span><span class="sxs-lookup"><span data-stu-id="939fb-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="939fb-122">Si Collocate bases de datos de Lync Server, se recomienda encarecidamente evaluar todos los factores que pueden afectar a la disponibilidad y el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="939fb-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="939fb-123">Para comprobar las capacidades de conmutación por error, se recomienda probar todos los escenarios de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="939fb-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="939fb-124">Servidor Standard Edition, que incluye una base de datos de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="939fb-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="939fb-125">Su implementación también puede tener uno o más sitios de sucursales asociados con un sitio central.</span><span class="sxs-lookup"><span data-stu-id="939fb-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="939fb-126">En esta sección se describen los sitios y componentes de una implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="939fb-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="939fb-127">Para obtener más información sobre el sitio de Lync Server 2013, la topología y la planeación de componentes, consulte fundamentos de la [topología que debe conocer antes de planear Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) y las [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md) en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="939fb-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="939fb-128">Para obtener más información sobre la integración de componentes de versiones anteriores, consulte [rutas de migración compatibles y escenarios de coexistencia en Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="939fb-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="939fb-129">Los grupos de servidores estirados no son compatibles con los roles de servidor de front-end, Edge, mediación y director.</span><span class="sxs-lookup"><span data-stu-id="939fb-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="939fb-130">Topologías y componentes de sitio central (local)</span><span class="sxs-lookup"><span data-stu-id="939fb-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="939fb-131">Aunque una topología de sitio central debe incluir un grupo de servidores front-end o un servidor Standard Edition, cada sitio central también puede contener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="939fb-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="939fb-132">Varias agrupaciones front end, que pueden estar en el mismo dominio o en dominios diferentes.</span><span class="sxs-lookup"><span data-stu-id="939fb-132">Multiple Front End pools, which can be in the same domain or different domains.</span></span> <span data-ttu-id="939fb-133">Sin embargo, todos los servidores front-end de un grupo de servidores front-end y el servidor back-end de ese grupo deben estar en el mismo dominio.</span><span class="sxs-lookup"><span data-stu-id="939fb-133">However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="939fb-134">Varios servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="939fb-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="939fb-135">Office Web Apps Server, que se usa con aplicaciones Web de Office en Lync Server 2013, para controlar el uso compartido y el procesamiento de presentaciones de Microsoft PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="939fb-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="939fb-136">Servidor perimetral o grupo Edge en la red perimetral, si desea que su implementación admita socios federados, conectividad de mensajería instantánea pública, una puerta de enlace de protocolo de presencia y mensajería extensible (XMPP), acceso de usuarios remotos, participación de usuarios anónimos en reuniones, o mensajería unificada de Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="939fb-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="939fb-137">No puede Collocate ningún otro rol de servidor con un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="939fb-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="939fb-138">Recomendamos el equilibrio de carga de DNS, cuando corresponda, pero también se admite el equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="939fb-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="939fb-139">La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="939fb-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="939fb-140">No puede usar equilibrio de carga de DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.</span><span class="sxs-lookup"><span data-stu-id="939fb-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="939fb-141">Para obtener más información sobre los requisitos de equilibrio de carga y la compatibilidad, consulte [planear el acceso de usuarios externos en Lync server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación e [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="939fb-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="939fb-142">Servidor o grupo de mediación, si desea proporcionar soporte técnico de telefonía IP empresarial o conferencias de acceso telefónico local en un grupo de servidores front-end en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="939fb-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="939fb-143">Según el modo en que implemente la asistencia de voz empresarial, puede Collocate el servidor de mediación en un grupo de servidores front-end (el valor predeterminado) o implementar un servidor o grupo de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="939fb-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="939fb-144">Puede usar DNS, hardware o el equilibrio de carga de la aplicación (cuando corresponda) para distribuir el tráfico de un grupo de puerta de enlace del grupo de servidores de mediación, como una puerta de enlace RTC, IP-PBX o un control de borde de sesión (SBC) de SIP. Para obtener más información sobre cómo planear la topología de servidor de mediación adecuada, consulte [directrices de implementación para servidor de mediación en Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="939fb-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="939fb-145">Servidor de chat persistente, si desea que los usuarios puedan participar a lo largo del tiempo en conversaciones basadas en temas y en varias partes.</span><span class="sxs-lookup"><span data-stu-id="939fb-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="939fb-146">Para proporcionar más capacidad y una mayor confiabilidad, su topología puede incluir varios equipos que ejecuten el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="939fb-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="939fb-147">No puede Collocate servidor de chat persistente con otros roles de servidor en un grupo de servidores Enterprise.</span><span class="sxs-lookup"><span data-stu-id="939fb-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="939fb-148">Sin embargo, puede Collocate el servidor de chat persistente en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="939fb-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="939fb-149">El chat persistente requiere una base de datos y, si implementa un cumplimiento persistente de las conversaciones, una base de datos de cumplimiento persistente de la conversación, pero las bases de datos se pueden colocar con la base de datos de archivado, la base de datos de supervisión o el servidor back-end de una edición Enterprise Grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="939fb-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="939fb-150">Para obtener más información sobre cómo planear la topología adecuada del servidor de chat persistente, consulte [planificación de servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="939fb-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="939fb-151">Supervisión: Si desea admitir la recopilación de datos de la calidad de la experiencia de audio/vídeo (QoE) y la grabación de detalles de llamadas (CDR) de las conferencias de telefonía IP empresarial y A/V de su implementación.</span><span class="sxs-lookup"><span data-stu-id="939fb-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="939fb-152">De manera opcional, puede instalar Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager), que usa la supervisión de datos de CDR y QoE para generar alertas casi en tiempo real que muestran el estado de la confiabilidad de las llamadas y la calidad de los medios.</span><span class="sxs-lookup"><span data-stu-id="939fb-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="939fb-153">La supervisión, cuando se implementa, se encuentra en servidores de aplicaciones para el usuario o en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="939fb-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="939fb-154">La supervisión requiere una base de datos, pero la base de datos puede colocarse con la base de datos de archivado, la base de datos de chat persistente, la base de datos de cumplimiento persistente de chat o en el servidor back-end de un grupo de servidores front end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="939fb-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="939fb-155">Archivar, si desea archivar las comunicaciones y el contenido de la reunión de mensajería instantánea (por razones de cumplimiento normativo) en su implementación.</span><span class="sxs-lookup"><span data-stu-id="939fb-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="939fb-156">El archivado, cuando se implementa, se encuentra en servidores front-end o en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="939fb-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="939fb-157">El almacenamiento de archivado requiere la implementación de una base de datos de archivado o la integración con el almacenamiento de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="939fb-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="939fb-158">Si usa ambos, lo que se conoce como *modo mixto*, el almacenamiento de Exchange 2013 se usa para almacenar datos de archivo para los usuarios que se encuentran en el 2013 de Exchange y la base de datos de archivado se usa para archivar los datos de todos los demás usuarios de la implementación.</span><span class="sxs-lookup"><span data-stu-id="939fb-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="939fb-159">Si necesita una base de datos de archivado, la base de datos puede colocarse en la base de datos de supervisión, en la base de datos de chat persistente, en una base de datos de cumplimiento persistente o en el servidor back-end de un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="939fb-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="939fb-160">Para obtener detalles sobre el planeamiento de la topología de archivado adecuada, consulte [planear el archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="939fb-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="939fb-161">Grupo de directores o directores, si desea facilitar la resistencia y el redireccionamiento de las solicitudes de usuario de Lync Server 2013 al grupo de hogar del usuario, que puede ser un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="939fb-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="939fb-162">Le recomendamos que implemente un director o un grupo de directores en cada sitio central que admita el acceso de usuarios externos y en cada sitio central en el que implemente uno o más grupos front-end.</span><span class="sxs-lookup"><span data-stu-id="939fb-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="939fb-163">Cada grupo de directores puede contener un máximo de diez directores.</span><span class="sxs-lookup"><span data-stu-id="939fb-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="939fb-164">No se puede incluir un director con ningún otro rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="939fb-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="939fb-165">Para obtener más información sobre cómo planear la topología de Director adecuada, consulte [escenarios del Director de Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="939fb-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="939fb-166">Proxy inverso, que no es un componente de 2013 de Lync Server, pero es necesario si desea permitir el uso compartido de contenido web para usuarios federados o para admitir el tráfico de movilidad.</span><span class="sxs-lookup"><span data-stu-id="939fb-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="939fb-167">No se puede Collocate un servidor proxy inverso con ningún rol de servidor de Lync Server 2013, pero puede implementar compatibilidad con proxy invertida para una implementación de Lync Server 2013 si configura la compatibilidad en un servidor proxy inverso existente de su organización que se usa para otros aplicación.</span><span class="sxs-lookup"><span data-stu-id="939fb-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="939fb-168">Para obtener detalles sobre los servidores proxy inversos, vea [configuración de servidores proxy inversos para Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="939fb-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="939fb-169">En Lync Server 2013, las conferencias, la supervisión y el archivado de A/V se ejecutan en servidores de aplicaciones para el usuario y ya no tienen roles de servidor diferentes.</span><span class="sxs-lookup"><span data-stu-id="939fb-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="939fb-170">Todas las agrupaciones de front-end y los servidores Standard Edition que se implementan en un sitio central comparten cualquiera de las siguientes opciones de implementación para el sitio central:</span><span class="sxs-lookup"><span data-stu-id="939fb-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="939fb-171">Grupo de directores o directores</span><span class="sxs-lookup"><span data-stu-id="939fb-171">Director or Director pool</span></span>

  - <span data-ttu-id="939fb-172">Servidor o grupo de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="939fb-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="939fb-173">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="939fb-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="939fb-174">Servidor perimetral o grupo Edge</span><span class="sxs-lookup"><span data-stu-id="939fb-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="939fb-175">Servidor o grupo de servidores de chat persistentes</span><span class="sxs-lookup"><span data-stu-id="939fb-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="939fb-176">Supervisión</span><span class="sxs-lookup"><span data-stu-id="939fb-176">Monitoring</span></span>

  - <span data-ttu-id="939fb-177">Archivado</span><span class="sxs-lookup"><span data-stu-id="939fb-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="939fb-178">Es posible implementar un servidor de mensajería unificada de Exchange con la implementación de Lync Server 2013 si desea admitir la integración de la mensajería unificada de Exchange 2013, pero no es un componente del sitio de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="939fb-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="939fb-179">Varios sitios centrales también pueden compartir cualquiera de las siguientes opciones que se implementan en un sitio central:</span><span class="sxs-lookup"><span data-stu-id="939fb-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="939fb-180">Servidor o grupo de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="939fb-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="939fb-181">Servidor perimetral o grupo Edge</span><span class="sxs-lookup"><span data-stu-id="939fb-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="939fb-182">Servidor o grupo de servidores de chat persistentes</span><span class="sxs-lookup"><span data-stu-id="939fb-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="939fb-183">Archivado</span><span class="sxs-lookup"><span data-stu-id="939fb-183">Archiving</span></span>

  - <span data-ttu-id="939fb-184">Supervisión</span><span class="sxs-lookup"><span data-stu-id="939fb-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="939fb-185">Es posible implementar un servidor de mensajería unificada de Exchange con la implementación de Lync Server 2013 y compartirlo con varios sitios centrales, pero no es un componente del sitio de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="939fb-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="939fb-186">Para obtener más información sobre los roles y la funcionalidad del servidor de Lync Server 2013, vea [roles de servidor en Lync server 2013](lync-server-2013-server-roles.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="939fb-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="939fb-187">Para obtener un resumen de la compatibilidad de servidor de Lync Server 2013 Server collocation, consulte compatibilidad con [servidores de collocation de Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="939fb-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="939fb-188">Además de los roles de servidor y la funcionalidad que se han explicado anteriormente en esta sección, Lync Server 2013 tiene componentes y opciones adicionales, que pueden incluir algunos o todos los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="939fb-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="939fb-189">Firewalls</span><span class="sxs-lookup"><span data-stu-id="939fb-189">Firewalls</span></span>

  - <span data-ttu-id="939fb-190">Puertas de enlace RTC (si se implementa la telefonía IP empresarial)</span><span class="sxs-lookup"><span data-stu-id="939fb-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="939fb-191">Servidor de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="939fb-191">Exchange UM Server</span></span>

  - <span data-ttu-id="939fb-192">Equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="939fb-192">DNS load balancing</span></span>

  - <span data-ttu-id="939fb-193">Equilibradores de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="939fb-193">Hardware load balancers</span></span>

  - <span data-ttu-id="939fb-194">Bases de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="939fb-194">SQL Server databases</span></span>

  - <span data-ttu-id="939fb-195">Recursos compartidos de archivos</span><span class="sxs-lookup"><span data-stu-id="939fb-195">File shares</span></span>

<span data-ttu-id="939fb-196">Para obtener detalles sobre todas las características, componentes y opciones de Lync Server 2013, consulte la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="939fb-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="939fb-197">Topologías y componentes de sitio de sucursal (local)</span><span class="sxs-lookup"><span data-stu-id="939fb-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="939fb-198">Un sitio de sucursal está asociado con un sitio central, y cada uno de los dispositivos de sucursal con la supervivencia de un sitio de sucursal está asociado con un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition en el sitio central asociado.</span><span class="sxs-lookup"><span data-stu-id="939fb-198">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site.</span></span> <span data-ttu-id="939fb-199">Los sitios de sucursales dependen del sitio central para la mayor parte de su funcionalidad, de modo que los componentes de un sitio de sucursal contienen solo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="939fb-199">Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="939fb-200">Un equipo de sucursales con la que se combina una puerta de enlace de red telefónica conmutada (RTC) con alguna funcionalidad de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="939fb-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="939fb-201">Se puede dar un servidor de mediación con la instancia del registrador de la aplicación de rama superviviente y puede implementar un servidor de mediación o un grupo de servidores de mediación independientes.</span><span class="sxs-lookup"><span data-stu-id="939fb-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="939fb-202">Un servidor de sucursal con la supervivencia, que es un servidor de Windows Server con el registrador de Lync Server 2013 y el software de servidor de mediación instalado.</span><span class="sxs-lookup"><span data-stu-id="939fb-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="939fb-203">Una puerta de enlace independiente de RTC (que no forma parte del equipo de sucursal con supervivencia) y un servidor de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="939fb-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="939fb-204">Los requisitos para servidores de sucursal revivientes son los mismos que los de cualquier rol de servidor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="939fb-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

