---
title: 'Lync Server 2013: Planeación de capacidad para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde4bcb499e38e729850f06bb08590bf537696e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="2216b-102">Planificación de capacidad para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2216b-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2216b-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="2216b-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="2216b-104">El servidor de chat persistente puede llevar a cabo una conversación en tiempo real con varios usuarios que puede persistir para una recuperación y búsqueda futura.</span><span class="sxs-lookup"><span data-stu-id="2216b-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="2216b-105">A diferencia de la mensajería instantánea (mi) grupal que se guarda en el buzón de un usuario si está configurado el historial de conversaciones, una sesión de servidor de chat persistente permanece abierta más tiempo y el contenido se guarda en un servidor, junto con los mensajes, archivos, direcciones URL y otros datos que forman parte de un conversación en curso.</span><span class="sxs-lookup"><span data-stu-id="2216b-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="2216b-106">El plan de capacidad es una parte importante de la preparación para implementar un servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2216b-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="2216b-107">Este tema proporciona detalles sobre las topologías de servidores de chat persistentes compatibles y las tablas de planeación de capacidad que puede usar para determinar la mejor configuración para su implementación.</span><span class="sxs-lookup"><span data-stu-id="2216b-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="2216b-108">También se describe cómo administrar mejor las implementaciones del servidor de chat persistentes que requieren mayor capacidad en horas punta.</span><span class="sxs-lookup"><span data-stu-id="2216b-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="2216b-109">Para descargar el servidor de chat persistente, consulte "servidor de chat persistente de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)Server 13" en.</span><span class="sxs-lookup"><span data-stu-id="2216b-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="2216b-110">Para obtener más información sobre cómo instalar el servidor de chat persistente, consulte [instalar el servidor de chat persistente en Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) y [configurar el servidor de chat persistente en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="2216b-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="2216b-111">Las herramientas de soporte técnico, como la herramienta de planeación de Lync Server, pueden ayudarle aún más para planear la capacidad.</span><span class="sxs-lookup"><span data-stu-id="2216b-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="2216b-112">Para obtener más información sobre la herramienta de planeación, consulte [comenzar el proceso de planeación de Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="2216b-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="2216b-113">Topologías compatibles con el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2216b-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="2216b-114">Puede implementar un servidor de chat persistente en grupos de un solo servidor o de varios servidores, y con topología de un único grupo o de varios grupos.</span><span class="sxs-lookup"><span data-stu-id="2216b-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="2216b-115">También se admite el servidor de chat persistente en el servidor Standard Edition para nuevas implementaciones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2216b-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="2216b-116">Sin embargo, el rendimiento y la escala se verán afectados, y dado que no hay una opción de alta disponibilidad para esta nueva implementación, esperamos que use esto principalmente para fines de pruebas de concepto, evaluación, etc.</span><span class="sxs-lookup"><span data-stu-id="2216b-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2216b-117">Para obtener más información sobre las dos topologías, vea <A href="lync-server-2013-planning-for-persistent-chat-server.md">planear el servidor de chat persistente en Lync server 2013</A> en la documentación de implementación y en <A href="lync-server-2013-deploying-persistent-chat-server.md">implementar el servidor de chat persistente en Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="2216b-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="2216b-118">Topología de servidor único</span><span class="sxs-lookup"><span data-stu-id="2216b-118">Single-Server Topology</span></span>

<span data-ttu-id="2216b-119">La configuración mínima y la implementación más sencilla para el servidor de chat persistente es una topología única de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2216b-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="2216b-120">Esta implementación requiere un único servidor que ejecute el servidor de chat persistente (que, opcionalmente, ejecuta el servicio de cumplimiento, si el cumplimiento está habilitado), un servidor que hospede tanto la base de datos de SQL Server como la de la base de datos de SQL Server para almacenar el datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2216b-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2216b-121">No puede agregar servidores adicionales a un grupo de servidores de chat persistente que se inicie como una implementación de servidor único en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="2216b-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="2216b-122">Le recomendamos que use la topología del grupo de varios servidores, incluso si está usando un solo servidor.</span><span class="sxs-lookup"><span data-stu-id="2216b-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="2216b-123">De esta manera, podrás agregar más servidores más adelante, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="2216b-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="2216b-124">La siguiente ilustración muestra todos los componentes obligatorios y opcionales de una topología para un único servidor de usuario de chat persistente con cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="2216b-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="2216b-125">**Servidor único de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="2216b-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="2216b-126">![Topología de servidor único con servicio de cumplimiento](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topología de servidor único con servicio de cumplimiento")</span><span class="sxs-lookup"><span data-stu-id="2216b-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="2216b-127">Topología de varios servidores</span><span class="sxs-lookup"><span data-stu-id="2216b-127">Multiple-Server Topology</span></span>

<span data-ttu-id="2216b-128">Para proporcionar mayor capacidad y confiabilidad, puede implementar una topología de varios servidores, como se describe en [planear el servidor de chat persistente en Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="2216b-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="2216b-129">La topología de varios servidores puede incluir hasta cuatro equipos activos que ejecutan el servidor de chat persistente (la alta disponibilidad y las configuraciones de recuperación ante desastres permiten hasta ocho, pero solo cuatro pueden estar activos y los cuatro restantes en espera).</span><span class="sxs-lookup"><span data-stu-id="2216b-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="2216b-130">Cada servidor puede admitir hasta 20.000 usuarios simultáneos, para un total de 80.000 usuarios simultáneos conectados a un grupo de servidores de chat persistente con 4 servidores.</span><span class="sxs-lookup"><span data-stu-id="2216b-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="2216b-131">Una topología de varios servidores es la misma que la topología de servidor único, excepto en que varios servidores hospedan un servidor de chat persistente y pueden escalar más alto.</span><span class="sxs-lookup"><span data-stu-id="2216b-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="2216b-132">Varios equipos que ejecutan el servidor de chat persistente deben residir en el mismo dominio de servicios de dominio de Active Directory que Lync Server y el servicio de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2216b-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="2216b-133">La siguiente ilustración muestra todos los componentes de una topología de varios servidores con varios equipos que ejecutan un servidor de chat persistente, el servicio de cumplimiento opcional y una base de datos de cumplimiento independiente.</span><span class="sxs-lookup"><span data-stu-id="2216b-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="2216b-134">**Varios servidores de chat persistentes**</span><span class="sxs-lookup"><span data-stu-id="2216b-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="2216b-135">![Topología de varios servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topología de varios servidores")</span><span class="sxs-lookup"><span data-stu-id="2216b-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="2216b-136">En una implementación de servidor de chat persistente de cuatro servidores, en la que los usuarios de 80.000 pueden iniciar sesión y usar la conversación de forma permanente, la carga se distribuye uniformemente en 20.000 usuarios por servidor.</span><span class="sxs-lookup"><span data-stu-id="2216b-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="2216b-137">Si un servidor no está disponible, los usuarios que estén conectados a él perderán el acceso al servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2216b-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="2216b-138">Los usuarios desconectados se transferirán automáticamente a los servidores restantes hasta que se restaure el servidor que no se encuentra disponible.</span><span class="sxs-lookup"><span data-stu-id="2216b-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="2216b-139">En función de la cantidad de tráfico de chat persistente en la red, esta transferencia puede demorar unos minutos o más.</span><span class="sxs-lookup"><span data-stu-id="2216b-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="2216b-140">Como es posible que cada uno de los servidores restantes aloje hasta 30.000 usuarios, le recomendamos que restaure el servidor no disponible lo antes posible para evitar problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2216b-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="2216b-141">De lo contrario, puede hacer que otro servidor de chat persistente esté disponible con el generador de topologías o el cmdlet de Windows PowerShell **set-CsPersistentChatActiveServer**.</span><span class="sxs-lookup"><span data-stu-id="2216b-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="2216b-142">Planificación de capacidad del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2216b-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="2216b-143">Las siguientes tablas pueden ayudarle con la planificación de capacidad de un servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2216b-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="2216b-144">Modelan cómo afectan las capacidades de capacidad a cambiar la configuración del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2216b-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="2216b-145">Planificación de su capacidad máxima para el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2216b-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="2216b-146">Usa la siguiente tabla de muestra para determinar la cantidad de usuarios que podrás admitir.</span><span class="sxs-lookup"><span data-stu-id="2216b-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="2216b-147">Muestra de capacidad máxima del grupo de servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2216b-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2216b-148">Instancias activas del servicio de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2216b-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="2216b-149"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="2216b-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-150">Instancias del servicio de chat persistentes</span><span class="sxs-lookup"><span data-stu-id="2216b-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="2216b-151"><em>8 (4 debe estar inactivo; solo un máximo de 4 puede estar activo)</em></span><span class="sxs-lookup"><span data-stu-id="2216b-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-152">Usuarios activos conectados</span><span class="sxs-lookup"><span data-stu-id="2216b-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="2216b-153"><em>80,000</em></span><span class="sxs-lookup"><span data-stu-id="2216b-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-154">Cantidad total de usuarios aprovisionados</span><span class="sxs-lookup"><span data-stu-id="2216b-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="2216b-155">150,000</span><span class="sxs-lookup"><span data-stu-id="2216b-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-156">Cantidad de extremos</span><span class="sxs-lookup"><span data-stu-id="2216b-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="2216b-157">120,000</span><span class="sxs-lookup"><span data-stu-id="2216b-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2216b-158">En el ejemplo anterior, el plan es compatible con el número máximo de usuarios que permite el servidor de chat persistente: cuatro servidores/instancias del servicio de chat persistente (pueden tener cuatro servidores más pasivos con servidor de chat persistente para una alta disponibilidad y recuperación ante desastres) y 20.000 usuarios por servidor, para un total de 80.000 usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="2216b-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="2216b-159">Planificación de capacidad para administrar el acceso permanente al salón de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="2216b-160">La siguiente tabla de ejemplo puede ayudarle a planear la administración del acceso permanente al salón de chat en un grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2216b-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="2216b-161">Ejemplo de administración de acceso al salón de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-161">Managing Chat Room Access Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="2216b-162">Salones de chat pequeños</span><span class="sxs-lookup"><span data-stu-id="2216b-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="2216b-163">Salones de chat medianos</span><span class="sxs-lookup"><span data-stu-id="2216b-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="2216b-164">Salones de chat grandes</span><span class="sxs-lookup"><span data-stu-id="2216b-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="2216b-165">Total</span><span class="sxs-lookup"><span data-stu-id="2216b-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2216b-166">Tamaño de los salones de chat (cantidad de usuarios conectados)</span><span class="sxs-lookup"><span data-stu-id="2216b-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="2216b-167">30 por salón</span><span class="sxs-lookup"><span data-stu-id="2216b-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="2216b-168">150 por salón</span><span class="sxs-lookup"><span data-stu-id="2216b-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="2216b-169">16 000 por salón</span><span class="sxs-lookup"><span data-stu-id="2216b-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-170">Salones de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-171">32,000</span><span class="sxs-lookup"><span data-stu-id="2216b-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="2216b-172">1,067</span><span class="sxs-lookup"><span data-stu-id="2216b-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="2216b-173">base10</span><span class="sxs-lookup"><span data-stu-id="2216b-173">10</span></span></p></td>
<td><p><span data-ttu-id="2216b-174">33,077</span><span class="sxs-lookup"><span data-stu-id="2216b-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-175">% de salones que son auditorios</span><span class="sxs-lookup"><span data-stu-id="2216b-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="2216b-176">1 %</span><span class="sxs-lookup"><span data-stu-id="2216b-176">1%</span></span></p></td>
<td><p><span data-ttu-id="2216b-177">1 %</span><span class="sxs-lookup"><span data-stu-id="2216b-177">1%</span></span></p></td>
<td><p><span data-ttu-id="2216b-178">50%</span><span class="sxs-lookup"><span data-stu-id="2216b-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-179">% de salones que están abiertos</span><span class="sxs-lookup"><span data-stu-id="2216b-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="2216b-180">3%</span><span class="sxs-lookup"><span data-stu-id="2216b-180">3%</span></span></p></td>
<td><p><span data-ttu-id="2216b-181">3%</span><span class="sxs-lookup"><span data-stu-id="2216b-181">3%</span></span></p></td>
<td><p><span data-ttu-id="2216b-182">50%</span><span class="sxs-lookup"><span data-stu-id="2216b-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-183">Salones abiertos (ninguna pertenencia explícita)</span><span class="sxs-lookup"><span data-stu-id="2216b-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="2216b-184">960</span><span class="sxs-lookup"><span data-stu-id="2216b-184">960</span></span></p></td>
<td><p><span data-ttu-id="2216b-185">32</span><span class="sxs-lookup"><span data-stu-id="2216b-185">32</span></span></p></td>
<td><p><span data-ttu-id="2216b-186">5</span><span class="sxs-lookup"><span data-stu-id="2216b-186">5</span></span></p></td>
<td><p><span data-ttu-id="2216b-187">997</span><span class="sxs-lookup"><span data-stu-id="2216b-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-188">Salones no abiertos (salones regulares con pertenencia explícita)</span><span class="sxs-lookup"><span data-stu-id="2216b-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="2216b-189">31,040</span><span class="sxs-lookup"><span data-stu-id="2216b-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="2216b-190">1.035</span><span class="sxs-lookup"><span data-stu-id="2216b-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="2216b-191">5</span><span class="sxs-lookup"><span data-stu-id="2216b-191">5</span></span></p></td>
<td><p><span data-ttu-id="2216b-192">32,080</span><span class="sxs-lookup"><span data-stu-id="2216b-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-193">Salones de auditorio (entrada de moderadores adicionales)</span><span class="sxs-lookup"><span data-stu-id="2216b-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="2216b-194">,0</span><span class="sxs-lookup"><span data-stu-id="2216b-194">0</span></span></p></td>
<td><p><span data-ttu-id="2216b-195">32</span><span class="sxs-lookup"><span data-stu-id="2216b-195">32</span></span></p></td>
<td><p><span data-ttu-id="2216b-196">5</span><span class="sxs-lookup"><span data-stu-id="2216b-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-197">Salones administrados por pertenencia directa</span><span class="sxs-lookup"><span data-stu-id="2216b-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="2216b-198">50%</span><span class="sxs-lookup"><span data-stu-id="2216b-198">50%</span></span></p></td>
<td><p><span data-ttu-id="2216b-199">10%</span><span class="sxs-lookup"><span data-stu-id="2216b-199">10%</span></span></p></td>
<td><p><span data-ttu-id="2216b-200">0%</span><span class="sxs-lookup"><span data-stu-id="2216b-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-201">Salones administrados por grupos de usuarios</span><span class="sxs-lookup"><span data-stu-id="2216b-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="2216b-202">50%</span><span class="sxs-lookup"><span data-stu-id="2216b-202">50%</span></span></p></td>
<td><p><span data-ttu-id="2216b-203">90%</span><span class="sxs-lookup"><span data-stu-id="2216b-203">90%</span></span></p></td>
<td><p><span data-ttu-id="2216b-204">100%</span><span class="sxs-lookup"><span data-stu-id="2216b-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-205">Grupos de usuarios en la lista de pertenencia de cada salón de chat para los salones abiertos (no especificado explícitamente)</span><span class="sxs-lookup"><span data-stu-id="2216b-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="2216b-206">,0</span><span class="sxs-lookup"><span data-stu-id="2216b-206">0</span></span></p></td>
<td><p><span data-ttu-id="2216b-207">,0</span><span class="sxs-lookup"><span data-stu-id="2216b-207">0</span></span></p></td>
<td><p><span data-ttu-id="2216b-208">,0</span><span class="sxs-lookup"><span data-stu-id="2216b-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-209">Usuarios en la lista de pertenencia de cada salón de chat para los salones no abiertos</span><span class="sxs-lookup"><span data-stu-id="2216b-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-210">0,30</span><span class="sxs-lookup"><span data-stu-id="2216b-210">30</span></span></p></td>
<td><p><span data-ttu-id="2216b-211">150</span><span class="sxs-lookup"><span data-stu-id="2216b-211">150</span></span></p></td>
<td><p><span data-ttu-id="2216b-212">16,000</span><span class="sxs-lookup"><span data-stu-id="2216b-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-213">Grupos de usuarios en la lista de pertenencia de cada salón de chat para los salones no abiertos</span><span class="sxs-lookup"><span data-stu-id="2216b-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-214">3</span><span class="sxs-lookup"><span data-stu-id="2216b-214">3</span></span></p></td>
<td><p><span data-ttu-id="2216b-215">5</span><span class="sxs-lookup"><span data-stu-id="2216b-215">5</span></span></p></td>
<td><p><span data-ttu-id="2216b-216">base10</span><span class="sxs-lookup"><span data-stu-id="2216b-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-217">Usuarios y grupos de usuarios en la lista del administrador de cada salón de chat (para salones abiertos y no abiertos)</span><span class="sxs-lookup"><span data-stu-id="2216b-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="2216b-218">6</span><span class="sxs-lookup"><span data-stu-id="2216b-218">6</span></span></p></td>
<td><p><span data-ttu-id="2216b-219">6</span><span class="sxs-lookup"><span data-stu-id="2216b-219">6</span></span></p></td>
<td><p><span data-ttu-id="2216b-220">6</span><span class="sxs-lookup"><span data-stu-id="2216b-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-221">Usuarios y grupos de usuarios en la lista de moderadores de cada salón de chat de auditorio (para salones abiertos y no abiertos)</span><span class="sxs-lookup"><span data-stu-id="2216b-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="2216b-222">6</span><span class="sxs-lookup"><span data-stu-id="2216b-222">6</span></span></p></td>
<td><p><span data-ttu-id="2216b-223">6</span><span class="sxs-lookup"><span data-stu-id="2216b-223">6</span></span></p></td>
<td><p><span data-ttu-id="2216b-224">6</span><span class="sxs-lookup"><span data-stu-id="2216b-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-225">Entidades de pertenencia basadas en usuarios en todos los salones no abiertos</span><span class="sxs-lookup"><span data-stu-id="2216b-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-226">465,600</span><span class="sxs-lookup"><span data-stu-id="2216b-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="2216b-227">15,520</span><span class="sxs-lookup"><span data-stu-id="2216b-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-228">Entidades de pertenencia basadas en grupos de usuarios en todos los salones no abiertos</span><span class="sxs-lookup"><span data-stu-id="2216b-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-229">46,560</span><span class="sxs-lookup"><span data-stu-id="2216b-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="2216b-230">4656</span><span class="sxs-lookup"><span data-stu-id="2216b-230">4656</span></span></p></td>
<td><p><span data-ttu-id="2216b-231">50</span><span class="sxs-lookup"><span data-stu-id="2216b-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-232">Entidades basadas en usuarios y grupos de usuarios en todos los salones de chat de auditorio</span><span class="sxs-lookup"><span data-stu-id="2216b-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-233">,0</span><span class="sxs-lookup"><span data-stu-id="2216b-233">0</span></span></p></td>
<td><p><span data-ttu-id="2216b-234">192</span><span class="sxs-lookup"><span data-stu-id="2216b-234">192</span></span></p></td>
<td><p><span data-ttu-id="2216b-235">50</span><span class="sxs-lookup"><span data-stu-id="2216b-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-236">Entidades de administradores basadas en usuarios y grupos de usuarios en todas las listas de administrador de salones de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="2216b-237">192,000</span><span class="sxs-lookup"><span data-stu-id="2216b-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="2216b-238">6,400</span><span class="sxs-lookup"><span data-stu-id="2216b-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="2216b-239">60</span><span class="sxs-lookup"><span data-stu-id="2216b-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-240">Usuarios activos por salón de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="2216b-241"><em>0,30</em></span><span class="sxs-lookup"><span data-stu-id="2216b-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="2216b-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-243"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="2216b-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-244">Salones de chat por usuario</span><span class="sxs-lookup"><span data-stu-id="2216b-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="2216b-245"><em>2007</em></span><span class="sxs-lookup"><span data-stu-id="2216b-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="2216b-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="2216b-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-248"><em>apartado</em></span><span class="sxs-lookup"><span data-stu-id="2216b-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-249">Grupos de usuarios en la lista de pertenencia de cada salón de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="2216b-250"><em>base10</em></span><span class="sxs-lookup"><span data-stu-id="2216b-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-251"><em>base10</em></span><span class="sxs-lookup"><span data-stu-id="2216b-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-252"><em>4,5</em></span><span class="sxs-lookup"><span data-stu-id="2216b-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-253">Salones administrados por grupos de usuarios</span><span class="sxs-lookup"><span data-stu-id="2216b-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="2216b-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="2216b-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="2216b-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="2216b-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-257">Entidades de pertenencia basadas en grupos de usuarios en todos los salones de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-258">155,200</span><span class="sxs-lookup"><span data-stu-id="2216b-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="2216b-259">5173</span><span class="sxs-lookup"><span data-stu-id="2216b-259">5173</span></span></p></td>
<td><p><span data-ttu-id="2216b-260">68</span><span class="sxs-lookup"><span data-stu-id="2216b-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-261">Entidades de pertenencia basadas en usuarios en todos los salones de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-262">465,600</span><span class="sxs-lookup"><span data-stu-id="2216b-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="2216b-263">77,600</span><span class="sxs-lookup"><span data-stu-id="2216b-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="2216b-264">72,000</span><span class="sxs-lookup"><span data-stu-id="2216b-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-265">Usuarios y grupos de usuarios en las listas de administradores, moderadores y ámbitos de cada salón de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="2216b-266">6</span><span class="sxs-lookup"><span data-stu-id="2216b-266">6</span></span></p></td>
<td><p><span data-ttu-id="2216b-267">6</span><span class="sxs-lookup"><span data-stu-id="2216b-267">6</span></span></p></td>
<td><p><span data-ttu-id="2216b-268">6</span><span class="sxs-lookup"><span data-stu-id="2216b-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-269">Usuarios y grupos de usuarios en las listas de administradores, moderadores y ámbitos de todos los salones de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="2216b-270">192,000</span><span class="sxs-lookup"><span data-stu-id="2216b-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="2216b-271">6400</span><span class="sxs-lookup"><span data-stu-id="2216b-271">6400</span></span></p></td>
<td><p><span data-ttu-id="2216b-272">60</span><span class="sxs-lookup"><span data-stu-id="2216b-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-273">Entradas de control de acceso</span><span class="sxs-lookup"><span data-stu-id="2216b-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="2216b-274">704,160</span><span class="sxs-lookup"><span data-stu-id="2216b-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="2216b-275">26,768</span><span class="sxs-lookup"><span data-stu-id="2216b-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="2216b-276">160</span><span class="sxs-lookup"><span data-stu-id="2216b-276">160</span></span></p></td>
<td><p><span data-ttu-id="2216b-277">731,088</span><span class="sxs-lookup"><span data-stu-id="2216b-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-278">Máximo de entradas de control de acceso</span><span class="sxs-lookup"><span data-stu-id="2216b-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="2216b-279">2,000,000</span><span class="sxs-lookup"><span data-stu-id="2216b-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2216b-280">En el ejemplo anterior, al implementar los servidores de chat persistentes de acuerdo con las pautas recomendadas, pueden administrar hasta 80.000 usuarios activos en un grupo de cuatro servidores con la compatibilidad habilitada.</span><span class="sxs-lookup"><span data-stu-id="2216b-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="2216b-281">Esta muestra representa los salones de chat clasificados como pequeños (30 usuarios activos en un momento dado), medianos (150 usuarios activos) y grandes (16 000 usuarios activos).</span><span class="sxs-lookup"><span data-stu-id="2216b-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="2216b-282">El número de salones de chat con un tamaño determinado se calcula en función del número total de:</span><span class="sxs-lookup"><span data-stu-id="2216b-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="2216b-283">Usuarios activos en el sistema</span><span class="sxs-lookup"><span data-stu-id="2216b-283">Active users in the system</span></span>

  - <span data-ttu-id="2216b-284">Usuarios activos en los salones de chat del tamaño correspondiente</span><span class="sxs-lookup"><span data-stu-id="2216b-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="2216b-285">Salones de chat del tamaño correspondiente a los que se una un solo usuario</span><span class="sxs-lookup"><span data-stu-id="2216b-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="2216b-p111">Para cada salón de chat, la tabla de planificación de la capacidad anterior especifica la cantidad de entradas de control de acceso asociadas al salón de chat, incluidas las entradas asignadas directamente al salón de chat. Puedes controlar el acceso a salones de chat individuales al utilizar listas de control de acceso (ACL). También puedes controlar el acceso en cuanto a la categoría. En una ACL, una entrada de control de acceso individual puede corresponder a un grupo de usuarios (por ejemplo, un grupo de seguridad, una lista de distribución o a un solo usuario). Puedes definir las entradas de control de acceso de los administradores, los moderadores y los miembros de los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="2216b-p111">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room. You can control access to individual chat rooms by using access control lists (ACLs). You can also control access at the category level. In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user. You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2216b-p112">A la hora de planificar tu estrategia para administrar los salones de chat, ten en cuenta que la cantidad total de entradas de control de acceso permitida es 2 millones. Si las entradas de control de acceso que calcules superan los 2 millones, el rendimiento del servidor puede disminuir en gran medida. Para evitar este problema, siempre que sea posible, asegúrate de que las entradas de control de acceso sean grupos de usuarios, en lugar de usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="2216b-p112">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million. If the calculated access control entries exceed 2 million, server performance could degrade significantly. To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="2216b-294">Planificación de capacidad para administrar el acceso al salón de chat mediante una invitación</span><span class="sxs-lookup"><span data-stu-id="2216b-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="2216b-295">Puede usar la siguiente tabla de planeación de capacidad para comprender el número de invitaciones que el servidor de chat persistente crea y almacena en la base de datos de chat persistente cuando está configurada para enviar invitaciones.</span><span class="sxs-lookup"><span data-stu-id="2216b-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="2216b-296">Para administrar las invitaciones de la categoría, use la página **configuración de categoría de salón de chat** en el panel de control de Lync Server, o bien use el cmdlet de Windows PowerShell **set-csPersistentChatCategory**.</span><span class="sxs-lookup"><span data-stu-id="2216b-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="2216b-297">Puede administrar invitaciones en un salón de chat (en función de lo que permita la categoría) mediante la página de **Administración de salas** iniciada desde el cliente Lync, o mediante un cmdlet de Windows PowerShell, **set-csPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="2216b-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="2216b-298">Los datos de muestra de la siguiente tabla presuponen que, en la página **Configuración de salones de chat** para el 50 % de los salones de chat, la opción **Invitaciones** se ha configurado como **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2216b-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2216b-299">Si el valor calculado para la cantidad de invitaciones que el servidor genera supera 1 millón, el rendimiento del servidor puede disminuir en gran medida.</span><span class="sxs-lookup"><span data-stu-id="2216b-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="2216b-300">Para evitar este problema, asegúrese de minimizar la cantidad de salones de chat configurados para enviar invitaciones o restringir el número de usuarios que pueden unirse a salones de chat que se han configurado para enviar invitaciones.</span><span class="sxs-lookup"><span data-stu-id="2216b-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="2216b-301">Acceso a salón de chat por muestra de invitación</span><span class="sxs-lookup"><span data-stu-id="2216b-301">Chat Room Access by Invitation Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="2216b-302">Salones de chat pequeños</span><span class="sxs-lookup"><span data-stu-id="2216b-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="2216b-303">Salones de chat medianos</span><span class="sxs-lookup"><span data-stu-id="2216b-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="2216b-304">Salones de chat grandes</span><span class="sxs-lookup"><span data-stu-id="2216b-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="2216b-305">Total</span><span class="sxs-lookup"><span data-stu-id="2216b-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2216b-306">Usuarios que pueden tener acceso a salones de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="2216b-307">30 por salón</span><span class="sxs-lookup"><span data-stu-id="2216b-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="2216b-308">150 por salón</span><span class="sxs-lookup"><span data-stu-id="2216b-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="2216b-309">16 000 por salón</span><span class="sxs-lookup"><span data-stu-id="2216b-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-310">Porcentaje de salones que disponen de invitaciones</span><span class="sxs-lookup"><span data-stu-id="2216b-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="2216b-311">50%</span><span class="sxs-lookup"><span data-stu-id="2216b-311">50%</span></span></p></td>
<td><p><span data-ttu-id="2216b-312">50%</span><span class="sxs-lookup"><span data-stu-id="2216b-312">50%</span></span></p></td>
<td><p><span data-ttu-id="2216b-313">50%</span><span class="sxs-lookup"><span data-stu-id="2216b-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-314">Salones de chat configurados para enviar invitaciones</span><span class="sxs-lookup"><span data-stu-id="2216b-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="2216b-315"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="2216b-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="2216b-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-317"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="2216b-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-318">Usuarios que pueden acceder al salón de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="2216b-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="2216b-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="2216b-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="2216b-321"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="2216b-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-322">Invitaciones generadas por el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2216b-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="2216b-323">960,000</span><span class="sxs-lookup"><span data-stu-id="2216b-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="2216b-324">120,000</span><span class="sxs-lookup"><span data-stu-id="2216b-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="2216b-325">80,000</span><span class="sxs-lookup"><span data-stu-id="2216b-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="2216b-326">1,160,000</span><span class="sxs-lookup"><span data-stu-id="2216b-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-327">Cantidad máxima de invitaciones permitidas</span><span class="sxs-lookup"><span data-stu-id="2216b-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="2216b-328">2,000,000</span><span class="sxs-lookup"><span data-stu-id="2216b-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-329">Modelo 1: Inicio con la cantidad esperada de mensajes por salón por día</span><span class="sxs-lookup"><span data-stu-id="2216b-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-330">Tasa de chats por salón (por día)</span><span class="sxs-lookup"><span data-stu-id="2216b-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="2216b-331">50</span><span class="sxs-lookup"><span data-stu-id="2216b-331">50</span></span></p></td>
<td><p><span data-ttu-id="2216b-332">500</span><span class="sxs-lookup"><span data-stu-id="2216b-332">500</span></span></p></td>
<td><p><span data-ttu-id="2216b-333">100</span><span class="sxs-lookup"><span data-stu-id="2216b-333">100</span></span></p></td>
<td><p><span data-ttu-id="2216b-334">650</span><span class="sxs-lookup"><span data-stu-id="2216b-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-335">Tasa de chats (por segundo) en todos los salones</span><span class="sxs-lookup"><span data-stu-id="2216b-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-336">55.56</span><span class="sxs-lookup"><span data-stu-id="2216b-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="2216b-337">18.52</span><span class="sxs-lookup"><span data-stu-id="2216b-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="2216b-338">0.03</span><span class="sxs-lookup"><span data-stu-id="2216b-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="2216b-339">74</span><span class="sxs-lookup"><span data-stu-id="2216b-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-340">Modelo 2: Inicio con la cantidad de mensajes publicados por usuario por día</span><span class="sxs-lookup"><span data-stu-id="2216b-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-341">Tasa de chats por usuario por día</span><span class="sxs-lookup"><span data-stu-id="2216b-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="2216b-342">4,5</span><span class="sxs-lookup"><span data-stu-id="2216b-342">15</span></span></p></td>
<td><p><span data-ttu-id="2216b-343">5</span><span class="sxs-lookup"><span data-stu-id="2216b-343">5</span></span></p></td>
<td><p><span data-ttu-id="2216b-344">0.1</span><span class="sxs-lookup"><span data-stu-id="2216b-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="2216b-345">veinte</span><span class="sxs-lookup"><span data-stu-id="2216b-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-346">Tasa de chats por salón (por día)</span><span class="sxs-lookup"><span data-stu-id="2216b-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="2216b-347">38</span><span class="sxs-lookup"><span data-stu-id="2216b-347">38</span></span></p></td>
<td><p><span data-ttu-id="2216b-348">375</span><span class="sxs-lookup"><span data-stu-id="2216b-348">375</span></span></p></td>
<td><p><span data-ttu-id="2216b-349">800</span><span class="sxs-lookup"><span data-stu-id="2216b-349">800</span></span></p></td>
<td><p><span data-ttu-id="2216b-350">1,213</span><span class="sxs-lookup"><span data-stu-id="2216b-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-351">Tasa de chats (por segundo) en todos los salones</span><span class="sxs-lookup"><span data-stu-id="2216b-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-352">41.67</span><span class="sxs-lookup"><span data-stu-id="2216b-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="2216b-353">13.89</span><span class="sxs-lookup"><span data-stu-id="2216b-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="2216b-354">0.28</span><span class="sxs-lookup"><span data-stu-id="2216b-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="2216b-355">56</span><span class="sxs-lookup"><span data-stu-id="2216b-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="2216b-356">Modelo de usuario de rendimiento del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2216b-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="2216b-357">En la siguiente tabla se describe el modelo de usuario para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2216b-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="2216b-358">Constituye la base de los requisitos de planificación de la capacidad y representa una organización típica con 80 000 usuarios simultáneos, en cuatro servidores.</span><span class="sxs-lookup"><span data-stu-id="2216b-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="2216b-359">Modelo de usuario de rendimiento del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2216b-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2216b-360">Cantidad de usuarios activos conectados</span><span class="sxs-lookup"><span data-stu-id="2216b-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="2216b-361">80,000</span><span class="sxs-lookup"><span data-stu-id="2216b-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-362">Número de instancias de servicio del servidor de chat persistentes</span><span class="sxs-lookup"><span data-stu-id="2216b-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="2216b-363">4</span><span class="sxs-lookup"><span data-stu-id="2216b-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-364">Tamaño de salones de chat pequeños</span><span class="sxs-lookup"><span data-stu-id="2216b-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-365">30 usuarios</span><span class="sxs-lookup"><span data-stu-id="2216b-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-366">Tamaño de salones de chat medianos</span><span class="sxs-lookup"><span data-stu-id="2216b-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-367">150 usuarios</span><span class="sxs-lookup"><span data-stu-id="2216b-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-368">Tamaño de salones de chat grandes</span><span class="sxs-lookup"><span data-stu-id="2216b-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-369">16 000 usuarios</span><span class="sxs-lookup"><span data-stu-id="2216b-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-370">Cantidad total de salones de chat</span><span class="sxs-lookup"><span data-stu-id="2216b-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-371">33,077</span><span class="sxs-lookup"><span data-stu-id="2216b-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-372">Cantidad de salones de chat pequeños</span><span class="sxs-lookup"><span data-stu-id="2216b-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-373">32,000</span><span class="sxs-lookup"><span data-stu-id="2216b-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-374">Cantidad de salones de chat medianos</span><span class="sxs-lookup"><span data-stu-id="2216b-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-375">1,067</span><span class="sxs-lookup"><span data-stu-id="2216b-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-376">Cantidad de salones de chat grandes</span><span class="sxs-lookup"><span data-stu-id="2216b-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-377">base10</span><span class="sxs-lookup"><span data-stu-id="2216b-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-378">Cantidad total de salones de chat por usuario</span><span class="sxs-lookup"><span data-stu-id="2216b-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="2216b-379">apartado</span><span class="sxs-lookup"><span data-stu-id="2216b-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-380">Cantidad de salones de chat pequeños por usuario</span><span class="sxs-lookup"><span data-stu-id="2216b-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="2216b-381">2007</span><span class="sxs-lookup"><span data-stu-id="2216b-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-382">Cantidad de salones de chat medianos por usuario</span><span class="sxs-lookup"><span data-stu-id="2216b-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="2216b-383">1</span><span class="sxs-lookup"><span data-stu-id="2216b-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-384">Cantidad de salones de chat grandes por usuario</span><span class="sxs-lookup"><span data-stu-id="2216b-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="2216b-385">1</span><span class="sxs-lookup"><span data-stu-id="2216b-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-386">Cantidad de salones a los que se han unido por usuario</span><span class="sxs-lookup"><span data-stu-id="2216b-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="2216b-387">veinticuatro</span><span class="sxs-lookup"><span data-stu-id="2216b-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-388">Tasa máxima de uniones</span><span class="sxs-lookup"><span data-stu-id="2216b-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="2216b-389">10/segundo</span><span class="sxs-lookup"><span data-stu-id="2216b-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-390">Tasa de chats total</span><span class="sxs-lookup"><span data-stu-id="2216b-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="2216b-391">24/segundo</span><span class="sxs-lookup"><span data-stu-id="2216b-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-392">Tasa de chats en salones de chat pequeños</span><span class="sxs-lookup"><span data-stu-id="2216b-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-393">22.22/second</span><span class="sxs-lookup"><span data-stu-id="2216b-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-394">Tasa de chats en salones de chat medianos</span><span class="sxs-lookup"><span data-stu-id="2216b-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-395">1.67/second</span><span class="sxs-lookup"><span data-stu-id="2216b-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-396">Tasa de chats en salones de chat grandes</span><span class="sxs-lookup"><span data-stu-id="2216b-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="2216b-397">~0.15/second</span><span class="sxs-lookup"><span data-stu-id="2216b-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-398">Porcentaje de salones de chat configurados con invitaciones</span><span class="sxs-lookup"><span data-stu-id="2216b-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="2216b-399">50%</span><span class="sxs-lookup"><span data-stu-id="2216b-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-400">Porcentaje de pertenencia directa</span><span class="sxs-lookup"><span data-stu-id="2216b-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="2216b-401">50%</span><span class="sxs-lookup"><span data-stu-id="2216b-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-402">Porcentaje de pertenencia de grupo</span><span class="sxs-lookup"><span data-stu-id="2216b-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="2216b-403">50%</span><span class="sxs-lookup"><span data-stu-id="2216b-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-404">Número promedio de afiliaciones antecesoras en servicios de dominio de Active Directory</span><span class="sxs-lookup"><span data-stu-id="2216b-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="2216b-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="2216b-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-406">Cantidad de contactos suscritos por usuario</span><span class="sxs-lookup"><span data-stu-id="2216b-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="2216b-407">80</span><span class="sxs-lookup"><span data-stu-id="2216b-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-408">Cantidad promedio de extremos por usuario</span><span class="sxs-lookup"><span data-stu-id="2216b-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="2216b-409">1.5</span><span class="sxs-lookup"><span data-stu-id="2216b-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-410">Cantidad promedio de salones de chat visibles por extremo</span><span class="sxs-lookup"><span data-stu-id="2216b-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="2216b-411">1.5</span><span class="sxs-lookup"><span data-stu-id="2216b-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-412">Cantidad promedio de salones de chat visibles por usuario</span><span class="sxs-lookup"><span data-stu-id="2216b-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="2216b-413">2,25 (50% para 1 salón y 50% para 2 salones); hasta 6 salones abiertos, uno por monitor</span><span class="sxs-lookup"><span data-stu-id="2216b-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-414">Cantidad de participantes sondeados por intervalo</span><span class="sxs-lookup"><span data-stu-id="2216b-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="2216b-415">25 por salón de chat visible</span><span class="sxs-lookup"><span data-stu-id="2216b-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-416">Longitud del intervalo de sondeo</span><span class="sxs-lookup"><span data-stu-id="2216b-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="2216b-417">5 minutos</span><span class="sxs-lookup"><span data-stu-id="2216b-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-418">Cantidad de participantes sondeados por segundo</span><span class="sxs-lookup"><span data-stu-id="2216b-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="2216b-419">15,000</span><span class="sxs-lookup"><span data-stu-id="2216b-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2216b-420">Cantidad de cambios de presencia por hora y usuario</span><span class="sxs-lookup"><span data-stu-id="2216b-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="2216b-421">6</span><span class="sxs-lookup"><span data-stu-id="2216b-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2216b-422">Cantidad de cambios de presencia por segundo</span><span class="sxs-lookup"><span data-stu-id="2216b-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="2216b-423">133.33</span><span class="sxs-lookup"><span data-stu-id="2216b-423">133.33</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

