---
title: 'Lync Server 2013: componentes y topologías para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586a24f4cfacd2ed28947102a7d5a129159a26bd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502507"
---
# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="af935-102">Componentes y topologías para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af935-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af935-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="af935-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="af935-104">El servidor de chat persistente admite configuraciones de un solo servidor y de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="af935-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="af935-105">El servidor de chat persistente también puede ejecutarse en un servidor de Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="af935-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="af935-106">Estas configuraciones constan de los siguientes componentes y topologías del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="af935-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="af935-107">Componentes del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="af935-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="af935-108">La instalación de la versión más reciente del servidor de chat persistente requiere los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="af935-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="af935-109">Uno o más equipos que ejecuten el servidor de chat persistente y proporcionen los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="af935-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="af935-110">Servicio de chat persistente</span><span class="sxs-lookup"><span data-stu-id="af935-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="af935-111">Servicio de cumplimiento, que se activa si el cumplimiento está habilitado</span><span class="sxs-lookup"><span data-stu-id="af935-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="af935-112">En Lync Server 2013, los servicios Web de chat persistente para la carga y descarga de archivos se encuentra ahora en el &nbsp; servidor front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af935-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="af935-113">Los servicios Web de chat persistente para la administración de salones de chat también se combinan con el &nbsp; servidor front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af935-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="af935-114">Servidores (es decir, más de un servidor si se usa la creación de reflejo) que hospeden la base de datos back-end de SQL Server para hospedar la base de datos de contenido de chat persistente en la que se almacenan el contenido, las salas y las categorías de los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="af935-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="af935-115">La base de datos back-end almacena los datos del historial de chat, incluida la información sobre categorías y salones de chat persistente que se crean.</span><span class="sxs-lookup"><span data-stu-id="af935-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="af935-116">Si se habilitó el cumplimiento normativo, se crearán un servidor (es) (más de un servidor si se usa la creación de reflejo) que hospeden la base de datos back-end de SQL Server para hospedar la base de datos de cumplimiento de chat persistente, en la que se almacenan los eventos de cumplimiento y el contenido de chat para fines de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="af935-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="af935-117">Para administrar el servidor de chat persistente desde un equipo independiente (como una consola administrativa), use el panel de control de Lync Server en el equipo.</span><span class="sxs-lookup"><span data-stu-id="af935-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="af935-118">A continuación, este equipo debe implementarse en un dominio de servicios de dominio de Active Directory, con al menos un servidor de catálogo global en la raíz del bosque.</span><span class="sxs-lookup"><span data-stu-id="af935-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="af935-119">Para obtener más información acerca de los requisitos de hardware y software para el servidor de chat persistente, consulte [Technical Requirements for persistent chat Server in Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server Software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="af935-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="af935-120">Escenarios de instalación compatibles</span><span class="sxs-lookup"><span data-stu-id="af935-120">Supported Collocation</span></span>

<span data-ttu-id="af935-121">Lync Server 2013 admite una amplia variedad de escenarios de combinación, lo que proporciona la flexibilidad necesaria para ahorrar costos de hardware mediante la ejecución de varios componentes en un servidor (si tiene una organización pequeña) o para ejecutar componentes individuales en diferentes servidores (si tiene una organización más grande que necesita escalabilidad y rendimiento).</span><span class="sxs-lookup"><span data-stu-id="af935-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="af935-122">Los factores de escalabilidad se deben tener en cuenta antes de decidir si los componentes se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="af935-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="af935-123">El servicio de cumplimiento de chat persistente, si el cumplimiento está habilitado, se combina con el servidor front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af935-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="af935-124">El servidor de chat persistente se puede implementar en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="af935-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="af935-125">El servidor back-end del servidor de chat persistente y la base de datos de cumplimiento de chat persistente se pueden combinar en el servidor Standard Edition en el servidor back-end local de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="af935-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="af935-126">Para obtener más información sobre los componentes que se pueden combinar allí, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="af935-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="af935-127">Para Lync Server 2013 Enterprise Edition, los servidores de chat persistente no se pueden combinar en el servidor Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="af935-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="af935-128">La base de datos de SQL Server para el servidor de chat persistente se puede combinar con la base de datos del servidor back-end de un grupo de servidores front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="af935-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="af935-129">La base de datos de SQL Server para el cumplimiento de chat persistente también se puede combinar con la base de datos del servidor back-end de un grupo de servidores Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="af935-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="af935-130">El servidor que hospeda la base de datos de chat persistente puede hospedar otras bases de datos.</span><span class="sxs-lookup"><span data-stu-id="af935-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="af935-131">Sin embargo, cuando considere la posibilidad de combinar la base de datos de chat persistente con otras bases de datos, tenga en cuenta que si está almacenando los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de chat persistente puede aumentar considerablemente.</span><span class="sxs-lookup"><span data-stu-id="af935-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="af935-132">Por este motivo, no se recomienda combinar la base de datos de chat persistente con la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="af935-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="af935-133">Si combinar la base de datos de chat persistente con la base de datos back-end, puede usar una única instancia de SQL Server para cualquiera o todas las bases de datos, o puede usar una instancia independiente de SQL Server para cada base de datos, con la siguiente limitación:</span><span class="sxs-lookup"><span data-stu-id="af935-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="af935-134">Cada instancia de SQL Server puede contener una sola base de datos back-end y una sola base de datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="af935-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="af935-135">Para obtener más información sobre la combinación de todos los roles de servidor y las bases de datos, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="af935-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="af935-136">Topologías de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="af935-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="af935-137">El servidor de chat persistente admite las siguientes topologías:</span><span class="sxs-lookup"><span data-stu-id="af935-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="af935-138">Servidor front-end de servidor de chat persistente de servidor único de Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="af935-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="af935-139">Servidor front-end de servidor de chat persistente de varios servidores de Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="af935-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="af935-140">Lync Server 2013 servidor Standard Edition con SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="af935-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="af935-141">Servidor de Lync Server 2013 Standard Edition y servidor de chat persistente en un servidor independiente que usa un servidor Standard Edition como servidor del próximo salto.</span><span class="sxs-lookup"><span data-stu-id="af935-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="af935-142">Puede Agregar un servidor de chat persistente a la implementación de Lync Server 2013 mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="af935-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="af935-143">Puede Agregar un servidor único o un grupo de servidores de chat persistente de varios servidores a la topología.</span><span class="sxs-lookup"><span data-stu-id="af935-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="af935-144">Después de crear un grupo de servidores de chat persistente con un único servidor mediante el generador de topologías, no puede agregar más servidores al grupo.</span><span class="sxs-lookup"><span data-stu-id="af935-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="af935-145">Topología de un solo servidor</span><span class="sxs-lookup"><span data-stu-id="af935-145">Single-Server Topology</span></span>

<span data-ttu-id="af935-146">La configuración mínima y la implementación más sencilla para el servidor de chat persistente son una única topología de servidor front-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="af935-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="af935-147">Esta implementación requiere un único servidor que ejecute el servidor de chat persistente (que, opcionalmente, ejecuta el servicio de cumplimiento, si el cumplimiento está habilitado), un servidor que hospede tanto la base de datos de SQL Server, como si se requiere el cumplimiento normativo, la base de datos de SQL Server donde se almacenarán los datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="af935-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="af935-148">No puede agregar servidores adicionales a un grupo de servidores de chat persistente que se inicie como una implementación de un solo servidor en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="af935-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="af935-149">Recomendamos usar la topología de grupo de varios servidores (aun cuando vaya a usar un solo servidor) para que, de este modo, pueda agregar más servidores posteriormente si así lo necesita.</span><span class="sxs-lookup"><span data-stu-id="af935-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="af935-150">En la siguiente figura se muestran todos los componentes necesarios y opcionales de una topología para un servidor front-end de servidor de chat persistente único con el cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="af935-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="af935-151">**Servidor de chat persistente único**</span><span class="sxs-lookup"><span data-stu-id="af935-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="af935-152">![Topología de un solo servidor con servicio de cumplimiento](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topología de un solo servidor con servicio de cumplimiento")</span><span class="sxs-lookup"><span data-stu-id="af935-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="af935-153">Topología de varios servidores</span><span class="sxs-lookup"><span data-stu-id="af935-153">Multiple-Server Topology</span></span>

<span data-ttu-id="af935-154">Para proporcionar mayor capacidad y confiabilidad, puede implementar una topología de varios servidores, como se describe en [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="af935-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="af935-155">La topología de varios servidores puede incluir hasta cuatro equipos activos que ejecutan el servidor de chat persistente (la alta disponibilidad y las configuraciones de recuperación ante desastres permiten hasta ocho, pero solo cuatro pueden estar activos y los cuatro restantes en espera).</span><span class="sxs-lookup"><span data-stu-id="af935-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="af935-156">Cada servidor puede admitir hasta 20.000 usuarios simultáneos, para un total de 80.000 usuarios simultáneos conectados a un grupo de servidores de chat persistente con 4 servidores.</span><span class="sxs-lookup"><span data-stu-id="af935-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="af935-157">Una topología de varios servidores es la misma que la topología de un único servidor, excepto en que varios servidores hospedan un servidor de chat persistente y pueden escalar más.</span><span class="sxs-lookup"><span data-stu-id="af935-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="af935-158">Los distintos equipos que ejecutan el servidor de chat persistente deben residir en el mismo dominio de servicios de dominio de Active Directory que Lync Server y el servicio de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="af935-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="af935-159">En la siguiente figura se muestran todos los componentes de una topología de varios servidores con varios equipos que ejecutan el servidor de chat persistente, el servicio opcional de cumplimiento y una base de datos de cumplimiento independiente.</span><span class="sxs-lookup"><span data-stu-id="af935-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="af935-160">**Varios servidores de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="af935-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="af935-161">![Topología de varios servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topología de varios servidores")</span><span class="sxs-lookup"><span data-stu-id="af935-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="af935-162">Las topologías de varios servidores permiten agrupar las funciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="af935-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="af935-163">En un grupo de servidores, los servicios de chat persistente se comunican y comparten datos.</span><span class="sxs-lookup"><span data-stu-id="af935-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="af935-164">Por ejemplo, el historial de chat que se publicó originalmente en un servicio de chat persistente está disponible desde cualquier servicio de chat persistente en el sistema.</span><span class="sxs-lookup"><span data-stu-id="af935-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="af935-165">Cualquier servicio de chat persistente puede acceder a un archivo que se carga a través de un servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="af935-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="af935-166">Los usuarios pueden conectarse a diferentes servidores front-end del servidor de chat persistente y pueden estar chateando y comunicándose entre sí.</span><span class="sxs-lookup"><span data-stu-id="af935-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="af935-167">El puerto predeterminado TCP 8011 conecta un servidor a un grupo de servidores y lo usa el servicio de chat persistente para comunicarse entre ellos o con fines administrativos.</span><span class="sxs-lookup"><span data-stu-id="af935-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

