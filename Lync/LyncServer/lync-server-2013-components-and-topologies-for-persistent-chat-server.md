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
ms.openlocfilehash: 862635d091a216df61058c0f0ff00eaa9d32a0c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="566ea-102">Componentes y topologías para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="566ea-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="566ea-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="566ea-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="566ea-104">El servidor de chat persistente admite configuraciones de servidor único y configuraciones de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="566ea-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="566ea-105">El servidor de chat persistente también puede ejecutarse en un servidor de Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="566ea-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="566ea-106">Estas configuraciones se componen de los siguientes componentes y topologías de servidores de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="566ea-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="566ea-107">Componentes del servidor de chat persistentes</span><span class="sxs-lookup"><span data-stu-id="566ea-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="566ea-108">La instalación de la versión más reciente del servidor de chat persistente requiere los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="566ea-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="566ea-109">Uno o más equipos que ejecutan el servidor de chat persistente y proporcionan los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="566ea-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="566ea-110">Servicio de chat persistente</span><span class="sxs-lookup"><span data-stu-id="566ea-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="566ea-111">Servicio de cumplimiento, que se activa si el cumplimiento está habilitado</span><span class="sxs-lookup"><span data-stu-id="566ea-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="566ea-112">En Lync Server 2013, los servicios Web de chat persistente para carga y descarga de archivos se colocan ahora&nbsp;con el servidor front-end de lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="566ea-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="566ea-113">Los servicios Web de chat persistentes para la administración de salones de chat también se&nbsp;colocan con el servidor front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="566ea-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="566ea-114">Servidores (es decir, hay más de un servidor si se usa el reflejo) que hospedan la base de datos back-end de SQL Server para hospedar la base de datos de contenido de chat persistente en la que se almacenan el contenido, las salas y las categorías del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="566ea-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="566ea-115">La base de datos back-end almacena los datos del historial de chats, incluida información sobre categorías y salones de chat persistentes que se crean.</span><span class="sxs-lookup"><span data-stu-id="566ea-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="566ea-116">Si se ha habilitado la compatibilidad, se pueden almacenar servidores (más de un servidor, si se usan reflejo) que hospedan la base de datos back-end de SQL Server para hospedar la base de datos de cumplimiento de chats persistentes, en la que se almacenan los eventos de cumplimiento y el contenido de chat para fines de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="566ea-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="566ea-117">Para administrar el servidor de chat persistente desde un equipo independiente (como una consola administrativa), use el panel de control de Lync Server en el equipo.</span><span class="sxs-lookup"><span data-stu-id="566ea-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="566ea-118">Este equipo debe implementarse en un dominio de servicios de dominio de Active Directory, con al menos un servidor de catálogo global en la raíz del bosque.</span><span class="sxs-lookup"><span data-stu-id="566ea-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="566ea-119">Para obtener más información sobre los requisitos de hardware y software para el servidor de chat persistente, consulte [los requisitos técnicos para el servidor de chat persistente en Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [hardware compatible para Lync Server 2013](lync-server-2013-supported-hardware.md), así como compatibilidad de la [infraestructura y el software de servidor en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="566ea-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="566ea-120">Collocation compatibles</span><span class="sxs-lookup"><span data-stu-id="566ea-120">Supported Collocation</span></span>

<span data-ttu-id="566ea-121">Lync Server 2013 admite una gran variedad de escenarios collocation, lo que le ofrece la flexibilidad de ahorrar costos de hardware ejecutando varios componentes en un servidor (si tiene una pequeña organización) o para ejecutar componentes individuales en diferentes servidores (si tiene una organización más grande que necesita escalabilidad y rendimiento).</span><span class="sxs-lookup"><span data-stu-id="566ea-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="566ea-122">Los factores de escalabilidad se deben considerar sin duda antes de decidir si se Collocate los componentes.</span><span class="sxs-lookup"><span data-stu-id="566ea-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="566ea-123">El servicio de cumplimiento de chat persistente, si el cumplimiento está habilitado, se encuentra en el servidor front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="566ea-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="566ea-124">Se puede implementar el servidor de chat persistente en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="566ea-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="566ea-125">El servidor back-end de servidor de chat persistente y la base de datos de cumplimiento de chat persistente se pueden colocar en el servidor Standard Edition en el servidor de back-end local de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="566ea-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="566ea-126">Para obtener más información sobre los componentes que se pueden colocar aquí, consulte [compatibilidad de servidor collocation en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="566ea-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="566ea-127">Para Lync Server 2013 Enterprise Edition, los servidores de chat persistentes no se pueden colocar en el servidor Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="566ea-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="566ea-128">La base de datos de SQL Server para el servidor de chat persistente puede colocarse con la base de datos del servidor back-end de un grupo de servidores front end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="566ea-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="566ea-129">La base de datos de SQL Server para el cumplimiento persistente de la conversación también puede incluirse con la base de datos servidor back-end de un grupo de servidores Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="566ea-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="566ea-130">El servidor que hospeda la base de datos de chat persistente puede hospedar otras bases de datos.</span><span class="sxs-lookup"><span data-stu-id="566ea-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="566ea-131">Sin embargo, cuando considere collocating la base de datos de chat persistente con otras bases de datos, tenga en cuenta que si está almacenando los mensajes de más de unos pocos usuarios, el espacio en disco necesario para la base de datos de chat persistente puede crecer muy grande.</span><span class="sxs-lookup"><span data-stu-id="566ea-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="566ea-132">Por esta razón, no recomendamos collocating la base de datos de chat persistente con la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="566ea-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="566ea-133">Si Collocate la base de datos de chat persistente con la base de datos back-end, puede usar una única instancia de SQL Server para cualquiera de las bases de datos o todas ellas, o bien puede usar una instancia independiente de SQL Server para cada base de datos, con la siguiente limitación:</span><span class="sxs-lookup"><span data-stu-id="566ea-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="566ea-134">Cada instancia de SQL Server puede contener una única base de datos back-end y una única base de datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="566ea-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="566ea-135">Para más información sobre collocation de todos los roles de servidor y bases de datos, consulte compatibilidad con [servidores de collocation en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación de soporte.</span><span class="sxs-lookup"><span data-stu-id="566ea-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="566ea-136">Topologías de servidores de chat persistentes</span><span class="sxs-lookup"><span data-stu-id="566ea-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="566ea-137">El servidor de chat persistente admite las siguientes topologías:</span><span class="sxs-lookup"><span data-stu-id="566ea-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="566ea-138">Servidor de servidor front-end de servidor de mensajería instantánea de servidor de Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="566ea-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="566ea-139">Servidor front-end de servidor de la mensajería instantánea de Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="566ea-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="566ea-140">Servidor de Lync Server 2013 Standard Edition con SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="566ea-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="566ea-141">Servidor de Lync Server 2013 Standard Edition y servidor de chat persistente en un servidor independiente que usa un servidor Standard Edition como servidor del próximo salto.</span><span class="sxs-lookup"><span data-stu-id="566ea-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="566ea-142">Puede Agregar un servidor de chat persistente a la implementación de Lync Server 2013 mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="566ea-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="566ea-143">Puede Agregar un servidor único o un grupo de servidores de chat persistente de servidor múltiple a su topología.</span><span class="sxs-lookup"><span data-stu-id="566ea-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="566ea-144">Después de crear un grupo de servidores de chat persistente con un único servidor mediante el generador de topologías, no puede agregar servidores adicionales al grupo.</span><span class="sxs-lookup"><span data-stu-id="566ea-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="566ea-145">Topología de servidor único</span><span class="sxs-lookup"><span data-stu-id="566ea-145">Single-Server Topology</span></span>

<span data-ttu-id="566ea-146">La configuración mínima y la implementación más sencilla para el servidor de chat persistente es una topología única de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="566ea-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="566ea-147">Esta implementación requiere un único servidor que ejecute el servidor de chat persistente (que, opcionalmente, ejecuta el servicio de cumplimiento, si el cumplimiento está habilitado), un servidor que hospede tanto la base de datos de SQL Server como la de la base de datos de SQL Server para almacenar el datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="566ea-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="566ea-148">No puede agregar servidores adicionales a un grupo de servidores de chat persistente que se inicie como una implementación de servidor único en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="566ea-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="566ea-149">Le recomendamos que use la topología del grupo de varios servidores, incluso si está usando un solo servidor, para que pueda agregar más servidores más adelante, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="566ea-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="566ea-150">La siguiente ilustración muestra todos los componentes obligatorios y opcionales de una topología para un único servidor de usuario de chat persistente con cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="566ea-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="566ea-151">**Servidor único de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="566ea-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="566ea-152">![Topología de servidor único con servicio de cumplimiento](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topología de servidor único con servicio de cumplimiento")</span><span class="sxs-lookup"><span data-stu-id="566ea-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="566ea-153">Topología de varios servidores</span><span class="sxs-lookup"><span data-stu-id="566ea-153">Multiple-Server Topology</span></span>

<span data-ttu-id="566ea-154">Para proporcionar mayor capacidad y confiabilidad, puede implementar una topología de varios servidores, como se describe en [planear el servidor de chat persistente en Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="566ea-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="566ea-155">La topología de varios servidores puede incluir hasta cuatro equipos activos que ejecutan el servidor de chat persistente (la alta disponibilidad y las configuraciones de recuperación ante desastres permiten hasta ocho, pero solo cuatro pueden estar activos y los cuatro restantes en espera).</span><span class="sxs-lookup"><span data-stu-id="566ea-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="566ea-156">Cada servidor puede admitir hasta 20.000 usuarios simultáneos, para un total de 80.000 usuarios simultáneos conectados a un grupo de servidores de chat persistente con 4 servidores.</span><span class="sxs-lookup"><span data-stu-id="566ea-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="566ea-157">Una topología de varios servidores es la misma que la topología de servidor único, excepto en que varios servidores hospedan un servidor de chat persistente y pueden escalar más alto.</span><span class="sxs-lookup"><span data-stu-id="566ea-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="566ea-158">Varios equipos que ejecutan el servidor de chat persistente deben residir en el mismo dominio de servicios de dominio de Active Directory que Lync Server y el servicio de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="566ea-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="566ea-159">La siguiente ilustración muestra todos los componentes de una topología de varios servidores con varios equipos que ejecutan un servidor de chat persistente, el servicio de cumplimiento opcional y una base de datos de cumplimiento independiente.</span><span class="sxs-lookup"><span data-stu-id="566ea-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="566ea-160">**Varios servidores de chat persistentes**</span><span class="sxs-lookup"><span data-stu-id="566ea-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="566ea-161">![Topología de varios servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topología de varios servidores")</span><span class="sxs-lookup"><span data-stu-id="566ea-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="566ea-162">Las topologías de varios servidores permiten agrupar las funciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="566ea-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="566ea-163">En un grupo de servidores, los servicios de chat persistentes se comunican y comparten datos.</span><span class="sxs-lookup"><span data-stu-id="566ea-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="566ea-164">Por ejemplo, el historial de conversaciones publicado originalmente en un servicio de chat persistente está disponible desde cualquier servicio de chat persistente en el sistema.</span><span class="sxs-lookup"><span data-stu-id="566ea-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="566ea-165">Cualquier servicio de chat persistente puede acceder a un archivo que se carga a través de un servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="566ea-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="566ea-166">Los usuarios se pueden conectar a diferentes servidores de aplicaciones para el servidor de mensajería instantánea y pueden estar conversando y comunicándose entre sí.</span><span class="sxs-lookup"><span data-stu-id="566ea-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="566ea-167">El puerto predeterminado de TCP 8011 conecta un servidor a un grupo de servidores y lo usa el servicio de chat persistente para comunicarse entre sí o con fines administrativos.</span><span class="sxs-lookup"><span data-stu-id="566ea-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

