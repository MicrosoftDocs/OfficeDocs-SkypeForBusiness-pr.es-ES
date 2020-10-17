---
title: Topologías admitidas de Lync Server 2013
description: Lync Server 2013 topologías compatibles.
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
ms.openlocfilehash: 39c19577fbda7e377e145abfd473d2cf8e6d4a1a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558026"
---
# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="7a1c4-103">Topologías admitidas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a1c4-103">Supported topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a1c4-104">_**Última modificación del tema:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="7a1c4-104">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="7a1c4-105">Lync Server 2013 admite la implementación de sitios locales en una organización y la integración de implementaciones locales con las implementaciones de Lync Online, lo que se conoce como implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-105">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="7a1c4-106">En una implementación híbrida, algunos usuarios se hospedan en la instalación local y algunos usuarios se hospedan en línea.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-106">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="7a1c4-107">En el caso de las implementaciones locales, Lync Server 2013 admite la implementación de uno o varios sitios que se pueden escalar para satisfacer los requisitos de ubicación y disponibilidad elevados.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-107">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="7a1c4-108">Puede estructurar estos sitios y sus componentes para cumplir los requisitos de acceso y resistencia de su organización.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-108">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="7a1c4-109">Una implementación local de Lync Server 2013 consta de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-109">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="7a1c4-p103">La implementación debe incluir como mínimo un sitio central (también conocido como centro de datos). Cada sitio central debe tener como mínimo un grupo front-end Enterprise Edition o un servidor Standard Edition. Estos consisten en:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-p103">Your deployment must include at least one central site (also known as a data center). Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server. These consist of the following:</span></span>
    
      - <span data-ttu-id="7a1c4-113">Un grupo de servidores front-end de Enterprise Edition, que está formado por uno o varios servidores front-end (normalmente, al menos dos servidores front-end por razones de escalabilidad) y un servidor back-end independiente.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-113">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="7a1c4-114">Un grupo de servidores front-end puede contener un máximo de doce servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-114">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="7a1c4-115">Se necesita un equilibrio de carga para varios servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-115">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="7a1c4-116">Para tráfico SIP, se recomienda un equilibrio de carga de DNS, aunque también se admite un equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-116">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="7a1c4-117">Si usa un equilibrio de carga de DNS para el tráfico SIP, seguirá necesitando un equilibrador de carga de hardware para el tráfico HTTP.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-117">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="7a1c4-118">Se recomienda crear un reflejo de SQL Server para obtener una alta disponibilidad de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-118">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="7a1c4-119">La base de datos de back-end requiere una instancia independiente, aunque puede colocar en ella la base de datos de archivado, la base de datos de reflejo, la base de datos de chat persistente y la base de datos de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-119">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="7a1c4-120">Lync Server 2013 admite el uso de un clúster compartido para los recursos compartidos de archivos en la implementación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-120">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="7a1c4-121">Para obtener más información sobre los requisitos de almacenamiento de bases de datos, consulte [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="7a1c4-121">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="7a1c4-122">Para obtener más información sobre los requisitos de almacenamiento de archivos, consulte [compatibilidad de almacenamiento de archivos en Lync Server 2013](lync-server-2013-file-storage-support.md).</span><span class="sxs-lookup"><span data-stu-id="7a1c4-122">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7a1c4-123">Si combinar las bases de datos de Lync Server, se recomienda encarecidamente evaluar todos los factores que pueden afectar a la disponibilidad y al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-123">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="7a1c4-124">Para comprobar las capacidades de conmutación por error, se recomienda probar todos los escenarios de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-124">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a1c4-125">Un servidor Standard Edition, que incluye una base de datos colocada de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-125">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="7a1c4-126">La implementación también puede tener uno o varios sitios de sucursales asociados al sitio central.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-126">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="7a1c4-127">En esta sección se describen los sitios y los componentes de una implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-127">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="7a1c4-128">Para obtener más información sobre el sitio de Lync Server 2013, la topología y la planeación de componentes, consulte [Topology Basics debe conocer antes de planear Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) y las [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-128">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="7a1c4-129">Para obtener más información sobre la integración de los componentes de versiones anteriores, vea [rutas de migración compatibles y escenarios de coexistencia en Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="7a1c4-129">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a1c4-130">Los grupos de servidores extendidos no son compatibles con los roles de servidor de front-end, perimetral, mediación y director.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-130">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="7a1c4-131">Topología y componentes de un sitio central</span><span class="sxs-lookup"><span data-stu-id="7a1c4-131">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="7a1c4-132">Aunque una topología de sitio central debe incluir un grupo front-end o servidor Standard Edition, cada sitio central puede contener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-132">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="7a1c4-p107">Varios grupos front-end, que pueden estar en el mismo dominio o en dominios diferentes. Sin embargo, todos los servidores front-end de un grupo front-end y el servidor back-end de dicho grupo deben encontrarse en el mismo dominio.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-p107">Multiple Front End pools, which can be in the same domain or different domains. However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="7a1c4-135">Varios servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-135">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="7a1c4-136">Office Web Apps Server, que se usa con aplicaciones Web de Office en Lync Server 2013 para controlar el uso compartido y la representación de presentaciones de Microsoft PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-136">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="7a1c4-137">Servidor perimetral o grupo de servidores perimetrales en la red perimetral, si desea que la implementación admita socios federados, conectividad de mensajería instantánea pública, una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP), acceso de usuarios remotos, participación de usuarios anónimos en reuniones o mensajería unificada (MU) de Exchange.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-137">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="7a1c4-138">No se puede colocar ningún otro rol de servidor en un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-138">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="7a1c4-139">Se recomienda un equilibrio de carga de DNS, siempre que sea apropiado, aunque también se admite un equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-139">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="7a1c4-140">La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-140">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="7a1c4-141">No puede usar el equilibrio de carga de DNS en una interfaz perimetral y el equilibrio de carga de hardware en la otra interfaz perimetral.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-141">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="7a1c4-142">Para obtener más información sobre los requisitos y la compatibilidad de equilibrio de carga, consulte [Planning for external User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación y [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-142">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="7a1c4-143">Servidor o grupo de servidores de mediación, si desea admitir Enterprise Voice o conferencias de acceso telefónico local en un grupo de servidores front-end en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-143">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="7a1c4-144">En función de cómo implemente la asistencia de telefonía IP empresarial, puede combinar el servidor de mediación en un grupo de servidores front-end (opción predeterminada) o implementar un servidor o grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-144">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="7a1c4-145">Puede usar el equilibrio de carga de DNS, hardware o aplicación (cuando corresponda) para distribuir el tráfico de la puerta de enlace del grupo de servidores de mediación, incluidos una puerta de enlace RTC, una IP-PBX o un control de borde de sesión (SBC) del tronco SIP. Para obtener más información sobre cómo planear la topología del servidor de mediación adecuada, consulte [directrices de implementación para servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-145">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="7a1c4-146">Servidor de chat persistente, si desea que los usuarios puedan participar en conversaciones basadas en temas con varios participantes que persisten a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-146">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="7a1c4-147">Para proporcionar más capacidad y aumentar la confiabilidad, la topología puede incluir varios equipos que ejecuten el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-147">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="7a1c4-148">No puede combinar servidor de chat persistente con otros roles de servidor en un grupo de servidores Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-148">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="7a1c4-149">Sin embargo, puede combinar servidor de chat persistente en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-149">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="7a1c4-150">El chat persistente requiere una base de datos y, si implementa el cumplimiento de chat persistente, también necesitará una base de datos de cumplimiento de chat persistente; sin embargo, las bases de datos pueden colocarse con la base de datos de archivado, la base de datos de supervisión o en el servidor back-en de un grupo de servidores front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-150">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="7a1c4-151">Para obtener más información sobre cómo planear la topología adecuada del servidor de chat persistente, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-151">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="7a1c4-152">Servidor de supervisión, si desea permitir en su implementación la recopilación de datos de la calidad de la experiencia (QoE) de audio y vídeo y el registro de detalles de las llamadas (CDR) para Enterprise Voice y conferencias A/V.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-152">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="7a1c4-153">Opcionalmente, puede instalar Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager), que usa datos de supervisión de CDR y QoE para generar alertas cercanas al tiempo real que muestren el estado de la confiabilidad de las llamadas y la calidad de los medios.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-153">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="7a1c4-154">El servidor de supervisión, cuando se implementa, se coloca en los servidores front-end o en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-154">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="7a1c4-155">El servidor de supervisión requiere una base de datos, pero la base de datos se puede colocar en la base de datos de archivado, la base de datos de chat persistente, la base de datos de cumplimiento de chat persistente o en el servidor back-end de un grupo de servidores front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-155">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="7a1c4-156">Servidor de archivado, si desea archivar el contenido de las comunicaciones y las reuniones de mensajería instantánea (por razones de cumplimiento de normas) en su implementación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-156">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="7a1c4-157">El servidor de archivado, cuando se implementa se coloca en servidores front-end o en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-157">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="7a1c4-158">El almacenamiento de archivado requiere la implementación de una base de datos de archivado o la integración con el almacenamiento de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-158">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="7a1c4-159">Si usa ambos, lo que se conoce como *modo mixto*, el almacenamiento de Exchange 2013 se usa para almacenar datos de archivo para los usuarios que están hospedados en Exchange 2013 y la base de datos de archivado se usa para archivar datos para todos los demás usuarios de la implementación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-159">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="7a1c4-160">Si requiere una base de datos de archivo, esta base de datos se puede colocar en la base de datos de supervisión, en la base de datos de chat persistente, en la base de datos de cumplimiento de chat persistente o en el servidor back-end de un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-160">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="7a1c4-161">Para obtener más información sobre cómo planear la topología de archivado adecuada, consulte [Planning for archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-161">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="7a1c4-162">Un director o un grupo de directores, si desea facilitar la resistencia y el redireccionamiento de las solicitudes de usuario de Lync Server 2013 al grupo principal del usuario, que puede ser un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-162">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="7a1c4-163">Recomendamos implementar un director o grupo de directores en cada sitio central que permita el acceso de usuarios externos y en cada sitio central en el que implemente uno o varios grupos front-end.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-163">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="7a1c4-164">Cada grupo de directores puede tener un máximo de diez directores.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-164">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="7a1c4-165">Un director no se puede instalar con ningún otro rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-165">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="7a1c4-166">Para obtener más información sobre cómo planear la topología de Director adecuada, consulte [escenarios para el Director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-166">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="7a1c4-167">Proxy inverso, que no es un componente 2013 de Lync Server, pero es necesario si desea admitir el uso compartido de contenido web para usuarios federados o para admitir el tráfico de movilidad.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-167">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="7a1c4-168">No se puede combinar un servidor proxy inverso con ningún rol de servidor de Lync Server 2013, pero se puede implementar la compatibilidad con un proxy inverso para una implementación de Lync Server 2013 mediante la configuración de la compatibilidad en un servidor proxy inverso existente en la organización que se usa para otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-168">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="7a1c4-169">Para obtener más información sobre los servidores proxy inversos, consulte [configuración de servidores proxy inversos para Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-169">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a1c4-170">En Lync Server 2013, la Conferencia, la supervisión y el archivado de A/V se ejecutan en servidores front-end y ya no son roles de servidor independientes.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-170">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="7a1c4-171">Todos los grupos front-end y servidores Standard Edition que implemente en un sitio central comparten cualquiera de los siguientes servidores que implemente para el sitio central:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-171">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="7a1c4-172">Director o grupo de directores</span><span class="sxs-lookup"><span data-stu-id="7a1c4-172">Director or Director pool</span></span>

  - <span data-ttu-id="7a1c4-173">Servidor de mediación independiente o grupo</span><span class="sxs-lookup"><span data-stu-id="7a1c4-173">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="7a1c4-174">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="7a1c4-174">Office Web Apps Server</span></span>

  - <span data-ttu-id="7a1c4-175">Servidor perimetral o grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="7a1c4-175">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="7a1c4-176">Grupo o servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="7a1c4-176">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="7a1c4-177">Supervisión</span><span class="sxs-lookup"><span data-stu-id="7a1c4-177">Monitoring</span></span>

  - <span data-ttu-id="7a1c4-178">Archivado</span><span class="sxs-lookup"><span data-stu-id="7a1c4-178">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a1c4-179">Se puede implementar un servidor de mensajería unificada de Exchange con la implementación de Lync Server 2013 si desea admitir la integración de la mensajería unificada de Exchange 2013, pero no es un componente del sitio de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-179">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="7a1c4-180">Varios sitios centrales también pueden compartir cualquiera de los siguientes servidores que implemente en un sitio central:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-180">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="7a1c4-181">Servidor de mediación independiente o grupo</span><span class="sxs-lookup"><span data-stu-id="7a1c4-181">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="7a1c4-182">Servidor perimetral o grupo perimetral</span><span class="sxs-lookup"><span data-stu-id="7a1c4-182">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="7a1c4-183">Grupo o servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="7a1c4-183">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="7a1c4-184">Archivado</span><span class="sxs-lookup"><span data-stu-id="7a1c4-184">Archiving</span></span>

  - <span data-ttu-id="7a1c4-185">Supervisión</span><span class="sxs-lookup"><span data-stu-id="7a1c4-185">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a1c4-186">Un servidor de mensajería unificada de Exchange puede implementarse con la implementación de Lync Server 2013 y compartirse con varios sitios centrales, pero no es un componente del sitio de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-186">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="7a1c4-187">Para obtener más información sobre las funciones y funciones del servidor de Lync Server 2013, consulte [roles de servidor en Lync server 2013](lync-server-2013-server-roles.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-187">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="7a1c4-188">Para obtener un resumen de la compatibilidad del servidor de Lync Server 2013 Server combinación, consulte Supported [Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="7a1c4-188">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="7a1c4-189">Además de las funciones y funciones de servidor descritas anteriormente en esta sección, Lync Server 2013 tiene componentes y opciones adicionales, que pueden incluir algunas o todas las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-189">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="7a1c4-190">Firewalls</span><span class="sxs-lookup"><span data-stu-id="7a1c4-190">Firewalls</span></span>

  - <span data-ttu-id="7a1c4-191">Puertas de enlace RTC (si implementa Enterprise Voice)</span><span class="sxs-lookup"><span data-stu-id="7a1c4-191">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="7a1c4-192">Servidor de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="7a1c4-192">Exchange UM Server</span></span>

  - <span data-ttu-id="7a1c4-193">Equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="7a1c4-193">DNS load balancing</span></span>

  - <span data-ttu-id="7a1c4-194">Equilibradores de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="7a1c4-194">Hardware load balancers</span></span>

  - <span data-ttu-id="7a1c4-195">Bases de datos SQL Server</span><span class="sxs-lookup"><span data-stu-id="7a1c4-195">SQL Server databases</span></span>

  - <span data-ttu-id="7a1c4-196">Recursos compartidos de archivos</span><span class="sxs-lookup"><span data-stu-id="7a1c4-196">File shares</span></span>

<span data-ttu-id="7a1c4-197">Para obtener más información sobre las características, los componentes y las opciones de Lync Server 2013, consulte la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-197">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="7a1c4-198">Topología y componentes de sitios de sucursales</span><span class="sxs-lookup"><span data-stu-id="7a1c4-198">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="7a1c4-p115">Un sitio de sucursal está asociado a un sitio central, y todas las aplicaciones de sucursal con funciones de supervivencia de un sitio de sucursal están asociadas con un grupo de front-end Enterprise Edition o con un servidor Standard Edition del sitio central asociado. Los sitios de sucursales dependen del sitio central para la mayoría de sus funciones, por lo que entre los componentes de un sitio de sucursal solo pueden estar los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7a1c4-p115">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site. Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="7a1c4-201">Una aplicación de sucursal con funciones de supervivencia que combina una puerta de enlace de red telefónica conmutada (RTC) con alguna funcionalidad de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-201">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="7a1c4-202">Un servidor de mediación se puede combinar con la instancia del registrador en la aplicación de sucursal con funciones de supervivencia y se puede implementar un servidor de mediación independiente o un grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-202">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="7a1c4-203">Un servidor de sucursal con funciones de supervivencia, que es un servidor que ejecuta Windows Server con el registrador de Lync Server 2013 registrador y el software del servidor de mediación instalado.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-203">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="7a1c4-204">Una puerta de enlace RTC independiente (no forma parte de la aplicación de sucursal con funciones de supervivencia) y un servidor de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-204">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="7a1c4-205">Los requisitos de los servidores de sucursal con funciones de supervivencia son los mismos que los de cualquier rol de servidor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a1c4-205">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

