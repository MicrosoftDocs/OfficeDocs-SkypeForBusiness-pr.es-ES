---
title: 'Lync Server 2013: nuevas características del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6203e6a7ee99f4b080fa93976a2a937e62fe9d3c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="a19e5-102">Nuevas características del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a19e5-102">New Persistent Chat Server features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a19e5-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="a19e5-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="a19e5-104">Lync Server 2013, el servidor de chat persistente permite participar en conversaciones basadas en temas con varios participantes que persisten a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="a19e5-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="a19e5-105">El servidor de chat persistente puede ayudar a su organización a hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a19e5-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="a19e5-106">Mejorar la comunicación entre equipos geográficamente dispersos y multifuncionales</span><span class="sxs-lookup"><span data-stu-id="a19e5-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="a19e5-107">Ampliar el uso de la información y la participación</span><span class="sxs-lookup"><span data-stu-id="a19e5-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="a19e5-108">Mejorar la comunicación con la organización extendida</span><span class="sxs-lookup"><span data-stu-id="a19e5-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="a19e5-109">Reducir la sobrecarga de la información</span><span class="sxs-lookup"><span data-stu-id="a19e5-109">Reduce information overload</span></span>

  - <span data-ttu-id="a19e5-110">Mejorar el uso de la información</span><span class="sxs-lookup"><span data-stu-id="a19e5-110">Improve information awareness</span></span>

  - <span data-ttu-id="a19e5-111">Aumentar la divulgación de información y conocimientos importantes</span><span class="sxs-lookup"><span data-stu-id="a19e5-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="a19e5-112">Lync Server 2013, el servidor de chat persistente no está disponible en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="a19e5-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="a19e5-113">En este momento, solo está disponible para clientes locales de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a19e5-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="a19e5-114">En Lync 2013, la funcionalidad de chat persistente se integra en el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a19e5-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="a19e5-115">Como resultado, los usuarios tienen acceso a la mensajería instantánea, presencia, audio, vídeo, conferencias y chat persistente en el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a19e5-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="a19e5-116">Para obtener más información sobre el cliente de Lync 2013, consulte <https://go.microsoft.com/fwlink/p/?linkid=270877> .</span><span class="sxs-lookup"><span data-stu-id="a19e5-116">For more information about the Lync 2013 client, see <https://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="a19e5-117">En este tema se describen los cambios de características entre la nueva versión de Lync Server 2013, el servidor de chat persistente y la versión anterior (Microsoft Lync Server 2010, Group chat), entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="a19e5-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="a19e5-118">Proporcionar una experiencia administrativa en el panel de control de Lync Server y eliminar la herramienta de administración de chat en grupo</span><span class="sxs-lookup"><span data-stu-id="a19e5-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="a19e5-119">Integre la configuración del servidor de chat persistente en el generador de topologías mediante la eliminación de la herramienta de configuración de chat en grupo</span><span class="sxs-lookup"><span data-stu-id="a19e5-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="a19e5-120">Facilitar la migración y la actualización de versiones anteriores del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a19e5-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="a19e5-121">Proporcionar soluciones de alta disponibilidad y recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="a19e5-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="a19e5-122">Para obtener más información acerca de la versión más reciente del servidor de chat persistente, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a19e5-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="a19e5-123">La ayuda de chat persistente <https://go.microsoft.com/fwlink/p/?linkid=270945> , en la que se proporciona una lista detallada de características de chat persistente, cómo funcionan y cómo usarlas mientras se ejecuta el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a19e5-123">The Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="a19e5-124">La [planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación referente a la planeación, [Deploying persistent chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) en la documentación sobre implementación, [migración de Lync Server 2010, chat grupal o grupo de Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) en la documentación de la migración y [Administración de Lync Server 2013, persistent](managing-lync-server-2013-persistent-chat-server.md) chat Server en la documentación de operaciones, todo lo que proporciona instrucciones para configurar el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a19e5-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="a19e5-125">El archivo. msi de documentación del servidor de chat persistente (archivo de Windows Installer) permite a los usuarios acceder a documentación sin conexión completa sobre el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a19e5-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="a19e5-126">Cambios en la topología de clave para el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a19e5-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="a19e5-127">Entre los siguientes cambios de alto nivel para el servidor de chat persistente se incluyen:</span><span class="sxs-lookup"><span data-stu-id="a19e5-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="a19e5-128">El servidor de chat persistente ahora es un rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="a19e5-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="a19e5-129">En Microsoft Lync Server 2010, el servidor de chat en grupo era una aplicación de confianza de terceros para Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a19e5-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="a19e5-130">Chat persistente puede agregarse a la topología de Lync Server 2013 mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="a19e5-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="a19e5-131">En Lync Server 2013, la funcionalidad del servidor de chat persistente se implementa con tres nuevos roles de servidor:</span><span class="sxs-lookup"><span data-stu-id="a19e5-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="a19e5-132">**PersistentChatService:** Este es el rol front-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a19e5-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="a19e5-133">En las implementaciones de Standard Edition, el rol de servicio del servidor de chat persistente se combina en el servidor Standard Edition implementado por el arranque, como cualquier otra función de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a19e5-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="a19e5-134">En las implementaciones de Enterprise Edition, la función del servicio de chat persistente se implementa en equipos independientes por arranque, como cualquier otra función de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a19e5-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="a19e5-135">**PersistentChatStore:** Servidor back-end que corresponde a la base de datos de contenido de chat persistente, donde se almacena todo el contenido de chat.</span><span class="sxs-lookup"><span data-stu-id="a19e5-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="a19e5-136">**PersistentChatComplianceStore:** Rol de servidor back-end que corresponde a la base de datos de cumplimiento de chat persistente, donde se almacenan todos los eventos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a19e5-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="a19e5-137">Estos roles de servidor de chat persistente son opcionales, y solo los clientes que desean una funcionalidad completa del servidor de chat persistente pueden instalarlos.</span><span class="sxs-lookup"><span data-stu-id="a19e5-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="a19e5-138">El rol **PersistentChatComplianceStore** solo es necesario si elige implementar el cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a19e5-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="a19e5-139">El rol **PersistentChatService** ejecuta dos servicios:</span><span class="sxs-lookup"><span data-stu-id="a19e5-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="a19e5-140">Servicio de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a19e5-140">Persistent Chat service</span></span>

  - <span data-ttu-id="a19e5-141">Servicio de cumplimiento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a19e5-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="a19e5-142">El hecho de que estos servicios se ejecuten en cada servidor de chat persistente proporciona alta disponibilidad para estos servicios en un grupo de servidores de chat persistente multiservidor.</span><span class="sxs-lookup"><span data-stu-id="a19e5-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="a19e5-143">Además, para admitir la carga y descarga de archivos en salones de chat persistente, el servidor de chat persistente incluye un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="a19e5-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="a19e5-144">Anteriormente, este servicio se incluyó en el servidor de chat persistente, en el servidor front-end y en Internet Information Services (IIS) necesario para instalarse como un requisito previo.</span><span class="sxs-lookup"><span data-stu-id="a19e5-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="a19e5-145">En el servidor de chat persistente de Lync Server 2013, el servicio Web de carga/descarga de archivos se combina con el servidor front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a19e5-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="a19e5-146">Como efecto secundario, Internet Information Services (IIS) ya no es un requisito previo para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a19e5-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="a19e5-147">El servicio Web de carga/descarga de archivos se identifica como **PersistentChat** en el administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="a19e5-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a19e5-148">El rol <STRONG>PersistentChatService</STRONG> se puede ejecutar en el mismo servidor que un &nbsp; servidor front-end de Lync Server 2013 solo si el servidor front-end es un &nbsp; servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a19e5-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="a19e5-149">El rol <STRONG>PersistentChatService</STRONG> no se puede ejecutar de forma independiente de un &nbsp; servidor Front-end 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a19e5-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="a19e5-150">Solo se puede instalar en el contexto de una implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a19e5-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="a19e5-151">En el servidor de chat persistente, se ha eliminado el servicio de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a19e5-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="a19e5-152">En Lync Server 2010, chat en grupo, el servicio de búsqueda se ejecutó en cada servidor front-end del servidor de chat de grupo y realizó el enrutamiento a uno de los servidores de canal.</span><span class="sxs-lookup"><span data-stu-id="a19e5-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="a19e5-153">Lync Server 2013 se basa en el enrutamiento mediante objetos de contacto, donde cada grupo de servidores de chat persistente se representa mediante un objeto de contacto que los servidores front-end de Lync Server usan para identificar y enrutar las solicitudes a un grupo de servidores de chat persistente adecuado y a uno de los equipos que ejecutan el servidor de chat persistente en el grupo.</span><span class="sxs-lookup"><span data-stu-id="a19e5-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="a19e5-154">En Lync Server 2013, hay modificaciones del servicio de cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="a19e5-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="a19e5-155">En Lync Server 2010, el servicio de cumplimiento se ejecutó de forma independiente (no combinada) y solo en un único servidor.</span><span class="sxs-lookup"><span data-stu-id="a19e5-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="a19e5-156">El servicio de cumplimiento ahora se ejecuta en todos los servidores front-end del servidor de chat persistente, junto con el servicio de chat persistente y, por lo tanto, proporciona alta disponibilidad en un grupo de servidores de chat persistente multiservidor.</span><span class="sxs-lookup"><span data-stu-id="a19e5-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="a19e5-157">Se puede configurar un adaptador de cumplimiento único para extraer datos de la base de datos de cumplimiento y en uno de los otros sistemas (archivo XML, archivos hospedados por Exchange, etc.).</span><span class="sxs-lookup"><span data-stu-id="a19e5-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="a19e5-158">El servidor de chat persistente incluye un adaptador XML.</span><span class="sxs-lookup"><span data-stu-id="a19e5-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="a19e5-159">La cola de Message Queue Server (también conocido como MSMQ) que comparte el servicio de chat persistente y el servicio de cumplimiento en cada servidor front-end del servidor de chat persistente es ahora una cola privada compartida solo por los dos servicios.</span><span class="sxs-lookup"><span data-stu-id="a19e5-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="a19e5-160">Todos los servicios de cumplimiento escriben en la misma base de datos back-end de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a19e5-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="a19e5-161">También se han leído de esa base de datos, con el fin de enviar los datos a su instancia del adaptador.</span><span class="sxs-lookup"><span data-stu-id="a19e5-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="a19e5-162">El servidor back-end de cumplimiento se representa como un nuevo rol de servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="a19e5-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a19e5-163">Como en versiones anteriores, todos los datos de cumplimiento se procesan una sola vez.</span><span class="sxs-lookup"><span data-stu-id="a19e5-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="a19e5-164">Los datos se pueden procesar mediante cualquiera de las instancias de adaptador invocadas por el servicio de cumplimiento que se ejecuta en los diversos equipos del servidor de chat persistente de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a19e5-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="a19e5-165">En el servidor de chat persistente, una de las instancias de adaptador podría procesar los datos.</span><span class="sxs-lookup"><span data-stu-id="a19e5-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19e5-166">Para obtener información sobre la instalación de Message Queue Server, consulte <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">instalar sistemas operativos y requisitos previos de software en servidores para Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="a19e5-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="a19e5-167">En Lync Server 2013, hay mejoras en la alta disponibilidad y la recuperación ante desastres:</span><span class="sxs-lookup"><span data-stu-id="a19e5-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="a19e5-168">Mejoras de alta disponibilidad: el reflejo de SQL Server se usa para proporcionar alta disponibilidad para la base de datos de contenido del servidor de chat persistente y la base de datos de cumplimiento de chat persistente dentro de un centro de datos (en el sitio).</span><span class="sxs-lookup"><span data-stu-id="a19e5-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="a19e5-169">Mejoras en la recuperación ante desastres: el servidor de chat persistente admite una arquitectura de grupo extendida que permite estirar un único grupo de servidores de chat persistente en dos sitios (es decir, un único grupo lógico en la topología, con los servidores del grupo ubicados físicamente en dos sitios).</span><span class="sxs-lookup"><span data-stu-id="a19e5-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="a19e5-170">El trasvase de registros de SQL Server se usa para la recuperación ante desastres entre sitios.</span><span class="sxs-lookup"><span data-stu-id="a19e5-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="a19e5-171">Para obtener más información acerca de la alta disponibilidad y la recuperación ante desastres, consulte [Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="a19e5-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="a19e5-172">Cambios clave de administración y administración para el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a19e5-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="a19e5-173">Lync Server 2013 le ha facilitado la administración y la administración del servidor de chat persistente proporcionando:</span><span class="sxs-lookup"><span data-stu-id="a19e5-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="a19e5-174">Administración y administración unificadas.</span><span class="sxs-lookup"><span data-stu-id="a19e5-174">Unified administration and management.</span></span> <span data-ttu-id="a19e5-175">Lync Server 2013 facilita la administración y la administración del servidor de chat persistente mediante el uso de herramientas que ya están familiarizadas con los administradores de Lync.</span><span class="sxs-lookup"><span data-stu-id="a19e5-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="a19e5-176">El servidor de chat persistente incluye una experiencia de interfaz de usuario administrativa integrada con el panel de control de Lync Server, que soluciona problemas de rendimiento con versiones anteriores de la interfaz de usuario del servidor de chat en grupo.</span><span class="sxs-lookup"><span data-stu-id="a19e5-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="a19e5-177">Además, el servidor de chat persistente incluye una colección de cmdlets de Windows PowerShell para administrar y administrar categorías de servidor de chat persistente, salones de servidores de chat persistente (incluidos la eliminación de salones y el purgado de contenido obsoleto) y complementos.</span><span class="sxs-lookup"><span data-stu-id="a19e5-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="a19e5-178">Modelo de administración simplificado.</span><span class="sxs-lookup"><span data-stu-id="a19e5-178">Simplified administration model.</span></span> <span data-ttu-id="a19e5-179">Lync Server 2013 ha cambiado y simplificado el modelo de servidor de chat persistente al enfrentar los siguientes requisitos clave del cliente:</span><span class="sxs-lookup"><span data-stu-id="a19e5-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="a19e5-180">Quite las jerarquías complejas anidadas de ámbitos y categorías.</span><span class="sxs-lookup"><span data-stu-id="a19e5-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="a19e5-181">Soporte para definir listas de denegación y listas permitidas (ámbitos) para los clientes actuales de MindAlign que tienen previsto migrar a un servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a19e5-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="a19e5-182">¿Qué diferencias hay entre las funciones de usuario de versiones anteriores del servidor de chat en grupo?</span><span class="sxs-lookup"><span data-stu-id="a19e5-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="a19e5-183">Lync Server 2010, Group chat tenía un rol de administrador de usuarios, un rol de administrador de salón de chat y un rol de administrador de Lync Server que podía administrar complementos. el servidor de chat persistente simplemente proporciona un rol de administrador de chat persistente (similar a otros roles de control de acceso basado en roles (RBAC) de Lync Server).</span><span class="sxs-lookup"><span data-stu-id="a19e5-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="a19e5-184">Cualquier persona que sea miembro de este rol RBAC puede administrar salones de chat, complementos y categorías (y, por lo tanto, obtener el acceso de los usuarios a estas categorías) y la configuración del grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a19e5-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="a19e5-185">¿Qué diferencias hay entre las categorías de salones de chat de versiones anteriores del servidor de chat de grupo?</span><span class="sxs-lookup"><span data-stu-id="a19e5-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="a19e5-186">Las categorías de salones de chat ya no se pueden anidar y la categoría raíz ya no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="a19e5-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="a19e5-187">Miembros permitidos/DeniedMembers comprende lo que un ámbito solía estar en las versiones de servidor de chat de grupo heredado (excepto que no admite la especificación de una lista denegada).</span><span class="sxs-lookup"><span data-stu-id="a19e5-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="a19e5-188">Los ámbitos ya no se pueden invalidar porque no hay categorías anidadas.</span><span class="sxs-lookup"><span data-stu-id="a19e5-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="a19e5-189">Un administrador de chat persistente en Lync Server 2013 puede crear y administrar categorías de salones de chat.</span><span class="sxs-lookup"><span data-stu-id="a19e5-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="a19e5-190">Como parte de la creación y la administración de categorías de salones de chat, un administrador de chat persistente puede configurar entidades de identidad (grupos/usuarios de Active Directory) que tienen acceso a miembros o creadores de salones de chat de una categoría determinada.</span><span class="sxs-lookup"><span data-stu-id="a19e5-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="a19e5-191">Un administrador de chat persistente también puede Agregar DeniedMembers a una categoría y se convierten en exclusiones explícitas de la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="a19e5-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="a19e5-192">Los DeniedMembers anulan a los que se encuentran en AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="a19e5-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="a19e5-193">¿Qué diferencias hay entre las propiedades de los salones de chat de versiones anteriores del servidor de chat en grupo?</span><span class="sxs-lookup"><span data-stu-id="a19e5-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="a19e5-194">Existe un nuevo concepto de salones de chat abiertos en Lync Server 2013, el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a19e5-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="a19e5-195">Todos los miembros permitidos pueden unirse al salón de chat, sin pertenencia exclusiva.</span><span class="sxs-lookup"><span data-stu-id="a19e5-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="a19e5-196">Se han eliminado las siguientes propiedades de salón de chat incluidas en versiones anteriores del servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="a19e5-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="a19e5-197">Tema: ahora solo hay una descripción en una sala.</span><span class="sxs-lookup"><span data-stu-id="a19e5-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="a19e5-198">Crear nueva lista de miembros: en el servidor de chat persistente, todos los salones de chat comienzan con una pertenencia vacía (y pueden maximizar hasta una pertenencia igual a los miembros permitidos).</span><span class="sxs-lookup"><span data-stu-id="a19e5-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="a19e5-199">Carga de archivos: se usa como configuración por salón de chat para controlar si se permite la carga y descarga de archivos.</span><span class="sxs-lookup"><span data-stu-id="a19e5-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="a19e5-200">Ahora solo se establece el nivel de categoría y se aplica a todas las salas de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="a19e5-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="a19e5-201">Historial de chat: se usa para controlar la configuración de un salón de chat si se habilitó el historial de chats, pero ahora solo se establece en el nivel de categoría y se aplica a todos los salones de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="a19e5-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="a19e5-202">Invitados: una sala siempre hereda la configuración de invitaciones para la categoría; o puede desactivarse en la sala.</span><span class="sxs-lookup"><span data-stu-id="a19e5-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="a19e5-203">Una sala no puede activar invitaciones si la categoría se estableció previamente como invitaciones.</span><span class="sxs-lookup"><span data-stu-id="a19e5-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="a19e5-204">¿Qué diferencias hay entre las directivas de versiones anteriores del servidor de chat en grupo?</span><span class="sxs-lookup"><span data-stu-id="a19e5-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="a19e5-205">El servidor de chat persistente tiene una nueva Directiva de Lync habilitada con chat persistente, por usuario/grupo/sitio/configuración global.</span><span class="sxs-lookup"><span data-stu-id="a19e5-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="a19e5-206">En el cliente de Lync 2013, el entorno de chat persistente solo está disponible para los usuarios que están habilitados por la Directiva para chat persistente (ya sea directamente o a través de la configuración de grupo de servidores/sitio/global).</span><span class="sxs-lookup"><span data-stu-id="a19e5-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="a19e5-207">Las versiones anteriores del servidor de chat en grupo no tenían ninguna directiva integrada en las directivas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a19e5-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="a19e5-208">En el caso de los usuarios y por categoría y por habitación, al usar la característica **Can upload files** per user, puede convertir al usuario en Administrador, administrador de un salón de chat o configurar la capacidad del usuario para cargar archivos.</span><span class="sxs-lookup"><span data-stu-id="a19e5-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="a19e5-209">La característica de **carga de archivos** del servidor de chat persistente es solo por categoría.</span><span class="sxs-lookup"><span data-stu-id="a19e5-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="a19e5-210">Registro</span><span class="sxs-lookup"><span data-stu-id="a19e5-210">Logging</span></span>

<span data-ttu-id="a19e5-211">El registro del servidor de chat persistente y System Center Operations Manager se integra en el registro de seguimiento de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a19e5-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a19e5-212">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a19e5-212">See Also</span></span>


[<span data-ttu-id="a19e5-213">Planeación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a19e5-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
