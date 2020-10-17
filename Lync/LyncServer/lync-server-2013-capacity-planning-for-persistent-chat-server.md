---
title: 'Lync Server 2013: Planeación de capacidad para el servidor de chat persistente'
description: 'Lync Server 2013: Planeación de la capacidad para el servidor de chat persistente.'
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
ms.openlocfilehash: f78f9f3666fb272b808ef36da2d3010f451d0079
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544496"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="d3492-103">Planeación de la capacidad para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3492-103">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3492-104">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d3492-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d3492-105">El servidor de chat persistente puede realizar chat en tiempo real para varios usuarios que puede persistir para una recuperación y búsqueda en el futuro.</span><span class="sxs-lookup"><span data-stu-id="d3492-105">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="d3492-106">A diferencia de la mensajería instantánea (mi) de grupo que se guarda en el buzón de un usuario si está configurado el historial de la conversación, una sesión del servidor de chat persistente permanece abierta más tiempo y el contenido se guarda en un servidor, junto con los mensajes, archivos, direcciones URL y otros datos que forman parte de una conversación en curso.</span><span class="sxs-lookup"><span data-stu-id="d3492-106">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="d3492-107">La planeación de la capacidad es una parte importante de la preparación para implementar el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d3492-107">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="d3492-108">En este tema se proporcionan detalles sobre las topologías de servidor de chat persistente admitidas y las tablas de planeación de capacidad que puede usar para determinar la mejor configuración para su implementación.</span><span class="sxs-lookup"><span data-stu-id="d3492-108">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="d3492-109">También se describe cómo administrar mejor las implementaciones del servidor de chat persistente que requieren mayor capacidad en horas punta.</span><span class="sxs-lookup"><span data-stu-id="d3492-109">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="d3492-110">Para descargar el servidor de chat persistente, consulte "servidor de chat persistente de Microsoft Lync Server 13" en [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) .</span><span class="sxs-lookup"><span data-stu-id="d3492-110">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="d3492-111">Para obtener información detallada sobre la instalación del servidor de chat persistente, vea [Installing persistent chat Server in Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) y [Configuring persistent chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d3492-111">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="d3492-112">Las herramientas de soporte, como la herramienta de planeación de Lync Server, pueden ayudarle con la planeación de capacidad.</span><span class="sxs-lookup"><span data-stu-id="d3492-112">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="d3492-113">Para obtener más información sobre la herramienta de planeación, consulte [comenzar el proceso de planeación de Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="d3492-113">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="d3492-114">Topologías compatibles con el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d3492-114">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="d3492-115">Puede implementar un servidor de chat persistente en grupos de un solo servidor o de varios servidores, y con una topología de un único grupo o de varios grupos.</span><span class="sxs-lookup"><span data-stu-id="d3492-115">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="d3492-116">Ahora también se admite el servidor de chat persistente en un servidor Standard Edition para implementaciones nuevas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3492-116">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="d3492-117">Sin embargo, el rendimiento y la escala se verán afectados, y dado que no hay una opción de alta disponibilidad para esta nueva implementación, esperamos que lo use principalmente con fines de prueba de concepto, evaluación, etc.</span><span class="sxs-lookup"><span data-stu-id="d3492-117">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d3492-118">Para obtener más información sobre ambas topologías, consulte <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for persistent chat Server in Lync server 2013</A> en este conjunto de documentación y <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying persistent chat Server in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d3492-118">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="d3492-119">Topología de un solo servidor</span><span class="sxs-lookup"><span data-stu-id="d3492-119">Single-Server Topology</span></span>

<span data-ttu-id="d3492-120">La configuración mínima y la implementación más sencilla para el servidor de chat persistente son una única topología de servidor front-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d3492-120">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="d3492-121">Esta implementación requiere un único servidor que ejecute el servidor de chat persistente (que, opcionalmente, ejecuta el servicio de cumplimiento, si el cumplimiento está habilitado), un servidor que hospede tanto la base de datos de SQL Server, como si se requiere el cumplimiento normativo, la base de datos de SQL Server donde se almacenarán los datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d3492-121">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3492-122">No puede agregar servidores adicionales a un grupo de servidores de chat persistente que se inicie como una implementación de un solo servidor en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="d3492-122">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="d3492-123">Se recomienda usar la topología de grupo de varios servidores, incluso si está usando un solo servidor.</span><span class="sxs-lookup"><span data-stu-id="d3492-123">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="d3492-124">De este modo, podrá agregar más servidores más adelante, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="d3492-124">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="d3492-125">En la siguiente figura se muestran todos los componentes necesarios y opcionales de una topología para un servidor front-end de servidor de chat persistente único con el cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="d3492-125">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="d3492-126">**Servidor de chat persistente único**</span><span class="sxs-lookup"><span data-stu-id="d3492-126">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="d3492-127">![Topología de un solo servidor con servicio de cumplimiento](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topología de un solo servidor con servicio de cumplimiento")</span><span class="sxs-lookup"><span data-stu-id="d3492-127">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="d3492-128">Topología de varios servidores</span><span class="sxs-lookup"><span data-stu-id="d3492-128">Multiple-Server Topology</span></span>

<span data-ttu-id="d3492-129">Para proporcionar mayor capacidad y confiabilidad, puede implementar una topología de varios servidores, como se describe en [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="d3492-129">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="d3492-130">La topología de varios servidores puede incluir hasta cuatro equipos activos que ejecutan el servidor de chat persistente (la alta disponibilidad y las configuraciones de recuperación ante desastres permiten hasta ocho, pero solo cuatro pueden estar activos y los cuatro restantes en espera).</span><span class="sxs-lookup"><span data-stu-id="d3492-130">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="d3492-131">Cada servidor puede admitir hasta 20.000 usuarios simultáneos, para un total de 80.000 usuarios simultáneos conectados a un grupo de servidores de chat persistente con 4 servidores.</span><span class="sxs-lookup"><span data-stu-id="d3492-131">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="d3492-132">Una topología de varios servidores es la misma que la topología de un único servidor, excepto en que varios servidores hospedan un servidor de chat persistente y pueden escalar más.</span><span class="sxs-lookup"><span data-stu-id="d3492-132">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="d3492-133">Los distintos equipos que ejecutan el servidor de chat persistente deben residir en el mismo dominio de servicios de dominio de Active Directory que Lync Server y el servicio de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d3492-133">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="d3492-134">En la siguiente figura se muestran todos los componentes de una topología de varios servidores con varios equipos que ejecutan el servidor de chat persistente, el servicio opcional de cumplimiento y una base de datos de cumplimiento independiente.</span><span class="sxs-lookup"><span data-stu-id="d3492-134">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="d3492-135">**Varios servidores de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="d3492-135">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="d3492-136">![Topología de varios servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topología de varios servidores")</span><span class="sxs-lookup"><span data-stu-id="d3492-136">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="d3492-137">En una implementación de servidor de chat persistente de cuatro servidores, en la que los usuarios de 80.000 pueden iniciar sesión y usar chat persistente de forma simultánea, la carga se distribuye uniformemente en 20.000 usuarios por servidor.</span><span class="sxs-lookup"><span data-stu-id="d3492-137">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="d3492-138">Si un servidor deja de estar disponible, los usuarios que están conectados a ese servidor perderán el acceso al servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d3492-138">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="d3492-139">Los usuarios desconectados se transferirán automáticamente a los servidores restantes hasta que se restaure el servidor no disponible.</span><span class="sxs-lookup"><span data-stu-id="d3492-139">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="d3492-140">En función de la cantidad de tráfico de chat persistente en la red, esta transferencia puede tardar unos minutos o más.</span><span class="sxs-lookup"><span data-stu-id="d3492-140">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="d3492-141">Como es posible que cada uno de los servidores restantes aloje hasta 30.000 usuarios, se recomienda restaurar el servidor no disponible tan pronto como sea posible para evitar problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d3492-141">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="d3492-142">De lo contrario, puede hacer que otro servidor de chat persistente esté disponible mediante el generador de topologías o el cmdlet de Windows PowerShell **set-CsPersistentChatActiveServer**.</span><span class="sxs-lookup"><span data-stu-id="d3492-142">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="d3492-143">Planeación de capacidad del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d3492-143">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="d3492-144">Las tablas siguientes pueden ayudarle con la planeación de capacidad para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d3492-144">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="d3492-145">Modelan cómo afectan las capacidades de capacidad al cambio de la configuración del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d3492-145">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="d3492-146">Planeación de la capacidad máxima para el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d3492-146">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="d3492-147">Use la siguiente tabla de ejemplo para determinar el número de usuarios a los que podrá dar soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="d3492-147">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="d3492-148">Muestra de capacidad máxima del grupo de servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d3492-148">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3492-149">Instancias activas del servicio de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d3492-149">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="d3492-150"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="d3492-150"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-151">Instancias del servicio de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d3492-151">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="d3492-152"><em>8 (4 debe estar inactivo; solo un máximo de 4 pueden estar activos)</em></span><span class="sxs-lookup"><span data-stu-id="d3492-152"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-153">Usuarios activos conectados</span><span class="sxs-lookup"><span data-stu-id="d3492-153">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="d3492-154"><em>80,000</em></span><span class="sxs-lookup"><span data-stu-id="d3492-154"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-155">Total de usuarios aprovisionados</span><span class="sxs-lookup"><span data-stu-id="d3492-155">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="d3492-156">150.000</span><span class="sxs-lookup"><span data-stu-id="d3492-156">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-157">Número de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="d3492-157">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="d3492-158">120.000</span><span class="sxs-lookup"><span data-stu-id="d3492-158">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d3492-159">En el ejemplo anterior, el plan es admitir el número máximo de usuarios que permite el servidor de chat persistente: cuatro servidores o instancias del servicio de chat persistente (pueden tener cuatro servidores más pasivos que ejecutan el servidor de chat persistente para alta disponibilidad y recuperación ante desastres) y 20.000 usuarios por servidor, para un total de 80.000 usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="d3492-159">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="d3492-160">Planeación de la capacidad para administrar el acceso a salones de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d3492-160">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="d3492-161">La siguiente tabla de ejemplo puede ayudarle a planificar la administración del acceso a salones de chat persistente en un grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d3492-161">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="d3492-162">Ejemplo de administración de acceso a salones de chat</span><span class="sxs-lookup"><span data-stu-id="d3492-162">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="d3492-163">Salones de chat pequeños</span><span class="sxs-lookup"><span data-stu-id="d3492-163">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="d3492-164">Salones de chat medianos</span><span class="sxs-lookup"><span data-stu-id="d3492-164">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="d3492-165">Salones de chat grandes</span><span class="sxs-lookup"><span data-stu-id="d3492-165">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="d3492-166">Total</span><span class="sxs-lookup"><span data-stu-id="d3492-166">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3492-167">Tamaño de los salones de chat (número de usuarios conectados)</span><span class="sxs-lookup"><span data-stu-id="d3492-167">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="d3492-168">30 por salón</span><span class="sxs-lookup"><span data-stu-id="d3492-168">30 per room</span></span></p></td>
<td><p><span data-ttu-id="d3492-169">150 por salón</span><span class="sxs-lookup"><span data-stu-id="d3492-169">150 per room</span></span></p></td>
<td><p><span data-ttu-id="d3492-170">16.000 por salón</span><span class="sxs-lookup"><span data-stu-id="d3492-170">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-171">Salas de chat</span><span class="sxs-lookup"><span data-stu-id="d3492-171">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-172">32.000</span><span class="sxs-lookup"><span data-stu-id="d3492-172">32,000</span></span></p></td>
<td><p><span data-ttu-id="d3492-173">1.067</span><span class="sxs-lookup"><span data-stu-id="d3492-173">1,067</span></span></p></td>
<td><p><span data-ttu-id="d3492-174">10  </span><span class="sxs-lookup"><span data-stu-id="d3492-174">10</span></span></p></td>
<td><p><span data-ttu-id="d3492-175">33.077</span><span class="sxs-lookup"><span data-stu-id="d3492-175">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-176">% de salones que son de tipo auditorio</span><span class="sxs-lookup"><span data-stu-id="d3492-176">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="d3492-177">1%</span><span class="sxs-lookup"><span data-stu-id="d3492-177">1%</span></span></p></td>
<td><p><span data-ttu-id="d3492-178">1%</span><span class="sxs-lookup"><span data-stu-id="d3492-178">1%</span></span></p></td>
<td><p><span data-ttu-id="d3492-179">50%</span><span class="sxs-lookup"><span data-stu-id="d3492-179">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-180">% de salones que están abiertos</span><span class="sxs-lookup"><span data-stu-id="d3492-180">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="d3492-181">3%</span><span class="sxs-lookup"><span data-stu-id="d3492-181">3%</span></span></p></td>
<td><p><span data-ttu-id="d3492-182">3%</span><span class="sxs-lookup"><span data-stu-id="d3492-182">3%</span></span></p></td>
<td><p><span data-ttu-id="d3492-183">50%</span><span class="sxs-lookup"><span data-stu-id="d3492-183">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-184">Salas abiertas (no hay pertenencia explícita)</span><span class="sxs-lookup"><span data-stu-id="d3492-184">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="d3492-185">960</span><span class="sxs-lookup"><span data-stu-id="d3492-185">960</span></span></p></td>
<td><p><span data-ttu-id="d3492-186">32</span><span class="sxs-lookup"><span data-stu-id="d3492-186">32</span></span></p></td>
<td><p><span data-ttu-id="d3492-187">5 </span><span class="sxs-lookup"><span data-stu-id="d3492-187">5</span></span></p></td>
<td><p><span data-ttu-id="d3492-188">997</span><span class="sxs-lookup"><span data-stu-id="d3492-188">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-189">Salones no abiertos (salas normales con pertenencia explícita)</span><span class="sxs-lookup"><span data-stu-id="d3492-189">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="d3492-190">31.040</span><span class="sxs-lookup"><span data-stu-id="d3492-190">31,040</span></span></p></td>
<td><p><span data-ttu-id="d3492-191">1,035</span><span class="sxs-lookup"><span data-stu-id="d3492-191">1.035</span></span></p></td>
<td><p><span data-ttu-id="d3492-192">5 </span><span class="sxs-lookup"><span data-stu-id="d3492-192">5</span></span></p></td>
<td><p><span data-ttu-id="d3492-193">32.080</span><span class="sxs-lookup"><span data-stu-id="d3492-193">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-194">Salones de auditorio (entrada de moderadores adicionales)</span><span class="sxs-lookup"><span data-stu-id="d3492-194">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="d3492-195">comprendi</span><span class="sxs-lookup"><span data-stu-id="d3492-195">0</span></span></p></td>
<td><p><span data-ttu-id="d3492-196">32</span><span class="sxs-lookup"><span data-stu-id="d3492-196">32</span></span></p></td>
<td><p><span data-ttu-id="d3492-197">5 </span><span class="sxs-lookup"><span data-stu-id="d3492-197">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-198">Salones administrados por pertenencia directa</span><span class="sxs-lookup"><span data-stu-id="d3492-198">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="d3492-199">50%</span><span class="sxs-lookup"><span data-stu-id="d3492-199">50%</span></span></p></td>
<td><p><span data-ttu-id="d3492-200">10%</span><span class="sxs-lookup"><span data-stu-id="d3492-200">10%</span></span></p></td>
<td><p><span data-ttu-id="d3492-201">0 %</span><span class="sxs-lookup"><span data-stu-id="d3492-201">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-202">Salones administrados por grupos de usuarios</span><span class="sxs-lookup"><span data-stu-id="d3492-202">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="d3492-203">50%</span><span class="sxs-lookup"><span data-stu-id="d3492-203">50%</span></span></p></td>
<td><p><span data-ttu-id="d3492-204">90 %</span><span class="sxs-lookup"><span data-stu-id="d3492-204">90%</span></span></p></td>
<td><p><span data-ttu-id="d3492-205">100 %</span><span class="sxs-lookup"><span data-stu-id="d3492-205">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-206">Grupos de usuarios en la lista de pertenencia de cada salón de chat para salas abiertas (no se especifica explícitamente)</span><span class="sxs-lookup"><span data-stu-id="d3492-206">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="d3492-207">comprendi</span><span class="sxs-lookup"><span data-stu-id="d3492-207">0</span></span></p></td>
<td><p><span data-ttu-id="d3492-208">comprendi</span><span class="sxs-lookup"><span data-stu-id="d3492-208">0</span></span></p></td>
<td><p><span data-ttu-id="d3492-209">comprendi</span><span class="sxs-lookup"><span data-stu-id="d3492-209">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-210">Usuarios en la lista de pertenencia de cada salón de chat para salas no abiertas</span><span class="sxs-lookup"><span data-stu-id="d3492-210">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-211">semestre</span><span class="sxs-lookup"><span data-stu-id="d3492-211">30</span></span></p></td>
<td><p><span data-ttu-id="d3492-212">150</span><span class="sxs-lookup"><span data-stu-id="d3492-212">150</span></span></p></td>
<td><p><span data-ttu-id="d3492-213">16.000</span><span class="sxs-lookup"><span data-stu-id="d3492-213">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-214">Grupos de usuarios en la lista de pertenencia de cada salón de chat para salas no abiertas</span><span class="sxs-lookup"><span data-stu-id="d3492-214">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-215">3</span><span class="sxs-lookup"><span data-stu-id="d3492-215">3</span></span></p></td>
<td><p><span data-ttu-id="d3492-216">5 </span><span class="sxs-lookup"><span data-stu-id="d3492-216">5</span></span></p></td>
<td><p><span data-ttu-id="d3492-217">10  </span><span class="sxs-lookup"><span data-stu-id="d3492-217">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-218">Usuarios y grupos de usuarios en la lista de administradores de cada salón de chat (para salones abiertos y no abiertos)</span><span class="sxs-lookup"><span data-stu-id="d3492-218">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="d3492-219">6 </span><span class="sxs-lookup"><span data-stu-id="d3492-219">6</span></span></p></td>
<td><p><span data-ttu-id="d3492-220">6 </span><span class="sxs-lookup"><span data-stu-id="d3492-220">6</span></span></p></td>
<td><p><span data-ttu-id="d3492-221">6 </span><span class="sxs-lookup"><span data-stu-id="d3492-221">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-222">Usuarios y grupos de usuarios en la lista de moderadores de cada salón de chat de auditorio (para salones abiertos y no abiertos)</span><span class="sxs-lookup"><span data-stu-id="d3492-222">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="d3492-223">6 </span><span class="sxs-lookup"><span data-stu-id="d3492-223">6</span></span></p></td>
<td><p><span data-ttu-id="d3492-224">6 </span><span class="sxs-lookup"><span data-stu-id="d3492-224">6</span></span></p></td>
<td><p><span data-ttu-id="d3492-225">6 </span><span class="sxs-lookup"><span data-stu-id="d3492-225">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-226">Entidades de pertenencia basadas en usuarios en todos los salones no abiertos</span><span class="sxs-lookup"><span data-stu-id="d3492-226">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-227">465.600</span><span class="sxs-lookup"><span data-stu-id="d3492-227">465,600</span></span></p></td>
<td><p><span data-ttu-id="d3492-228">15.520</span><span class="sxs-lookup"><span data-stu-id="d3492-228">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-229">Entidades de pertenencia basadas en grupos de usuarios en todos los salones no abiertos</span><span class="sxs-lookup"><span data-stu-id="d3492-229">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-230">46.560</span><span class="sxs-lookup"><span data-stu-id="d3492-230">46,560</span></span></p></td>
<td><p><span data-ttu-id="d3492-231">4656</span><span class="sxs-lookup"><span data-stu-id="d3492-231">4656</span></span></p></td>
<td><p><span data-ttu-id="d3492-232">50</span><span class="sxs-lookup"><span data-stu-id="d3492-232">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-233">Entidades basadas en usuarios y grupos de usuarios en todos los salones de chat de Auditorio</span><span class="sxs-lookup"><span data-stu-id="d3492-233">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-234">comprendi</span><span class="sxs-lookup"><span data-stu-id="d3492-234">0</span></span></p></td>
<td><p><span data-ttu-id="d3492-235">192</span><span class="sxs-lookup"><span data-stu-id="d3492-235">192</span></span></p></td>
<td><p><span data-ttu-id="d3492-236">50</span><span class="sxs-lookup"><span data-stu-id="d3492-236">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-237">Entidades de administración basadas en usuarios y grupos de usuarios en todas las listas del administrador de salones de chat</span><span class="sxs-lookup"><span data-stu-id="d3492-237">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="d3492-238">192.000</span><span class="sxs-lookup"><span data-stu-id="d3492-238">192,000</span></span></p></td>
<td><p><span data-ttu-id="d3492-239">6.400</span><span class="sxs-lookup"><span data-stu-id="d3492-239">6,400</span></span></p></td>
<td><p><span data-ttu-id="d3492-240">60</span><span class="sxs-lookup"><span data-stu-id="d3492-240">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-241">Usuarios activos por salón de chat</span><span class="sxs-lookup"><span data-stu-id="d3492-241">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="d3492-242"><em>semestre</em></span><span class="sxs-lookup"><span data-stu-id="d3492-242"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-243"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="d3492-243"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-244"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="d3492-244"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-245">Salones de chat por usuario</span><span class="sxs-lookup"><span data-stu-id="d3492-245">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="d3492-246"><em>12</em></span><span class="sxs-lookup"><span data-stu-id="d3492-246"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="d3492-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-248"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="d3492-248"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-249"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="d3492-249"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-250">Grupos de usuarios en la lista de pertenencia de cada salón de chat</span><span class="sxs-lookup"><span data-stu-id="d3492-250">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="d3492-251"><em>metros</em></span><span class="sxs-lookup"><span data-stu-id="d3492-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-252"><em>metros</em></span><span class="sxs-lookup"><span data-stu-id="d3492-252"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-253"><em>15</em></span><span class="sxs-lookup"><span data-stu-id="d3492-253"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-254">Salones administrados por grupos de usuarios</span><span class="sxs-lookup"><span data-stu-id="d3492-254">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="d3492-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="d3492-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="d3492-256"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-257"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="d3492-257"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-258">Entidades de pertenencia basadas en grupos de usuarios en todos los salones de chat</span><span class="sxs-lookup"><span data-stu-id="d3492-258">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-259">155.200</span><span class="sxs-lookup"><span data-stu-id="d3492-259">155,200</span></span></p></td>
<td><p><span data-ttu-id="d3492-260">5173</span><span class="sxs-lookup"><span data-stu-id="d3492-260">5173</span></span></p></td>
<td><p><span data-ttu-id="d3492-261">68</span><span class="sxs-lookup"><span data-stu-id="d3492-261">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-262">Entidades de pertenencia basadas en usuarios en todos los salones de chat</span><span class="sxs-lookup"><span data-stu-id="d3492-262">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-263">465.600</span><span class="sxs-lookup"><span data-stu-id="d3492-263">465,600</span></span></p></td>
<td><p><span data-ttu-id="d3492-264">77.600</span><span class="sxs-lookup"><span data-stu-id="d3492-264">77,600</span></span></p></td>
<td><p><span data-ttu-id="d3492-265">72.000</span><span class="sxs-lookup"><span data-stu-id="d3492-265">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-266">Usuarios y grupos de usuarios en las listas de administradores, moderadores y ámbitos de cada salón de chat</span><span class="sxs-lookup"><span data-stu-id="d3492-266">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="d3492-267">6 </span><span class="sxs-lookup"><span data-stu-id="d3492-267">6</span></span></p></td>
<td><p><span data-ttu-id="d3492-268">6 </span><span class="sxs-lookup"><span data-stu-id="d3492-268">6</span></span></p></td>
<td><p><span data-ttu-id="d3492-269">6 </span><span class="sxs-lookup"><span data-stu-id="d3492-269">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-270">Usuarios y grupos de usuarios en las listas de administradores, moderadores y ámbitos de todos los salones de chat</span><span class="sxs-lookup"><span data-stu-id="d3492-270">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="d3492-271">192.000</span><span class="sxs-lookup"><span data-stu-id="d3492-271">192,000</span></span></p></td>
<td><p><span data-ttu-id="d3492-272">6400</span><span class="sxs-lookup"><span data-stu-id="d3492-272">6400</span></span></p></td>
<td><p><span data-ttu-id="d3492-273">60</span><span class="sxs-lookup"><span data-stu-id="d3492-273">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-274">Entradas de control de acceso</span><span class="sxs-lookup"><span data-stu-id="d3492-274">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="d3492-275">704.160</span><span class="sxs-lookup"><span data-stu-id="d3492-275">704,160</span></span></p></td>
<td><p><span data-ttu-id="d3492-276">26.768</span><span class="sxs-lookup"><span data-stu-id="d3492-276">26,768</span></span></p></td>
<td><p><span data-ttu-id="d3492-277">160</span><span class="sxs-lookup"><span data-stu-id="d3492-277">160</span></span></p></td>
<td><p><span data-ttu-id="d3492-278">731.088</span><span class="sxs-lookup"><span data-stu-id="d3492-278">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-279">Máximo de entradas de control de acceso</span><span class="sxs-lookup"><span data-stu-id="d3492-279">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="d3492-280">2 millones</span><span class="sxs-lookup"><span data-stu-id="d3492-280">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d3492-281">En el ejemplo anterior, al implementar los servidores de chat persistente de acuerdo con las instrucciones recomendadas, pueden administrar hasta 80.000 usuarios activos en un grupo de cuatro servidores con cumplimiento habilitado.</span><span class="sxs-lookup"><span data-stu-id="d3492-281">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="d3492-282">En este ejemplo se muestran los salones de chat clasificados como pequeños (30 usuarios activos en un momento dado), medio (usuarios activos de 150) y grandes (16.000 usuarios activos).</span><span class="sxs-lookup"><span data-stu-id="d3492-282">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="d3492-283">El número de salones de chat de un determinado tamaño se calcula en función del número total de:</span><span class="sxs-lookup"><span data-stu-id="d3492-283">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="d3492-284">Usuarios activos en el sistema</span><span class="sxs-lookup"><span data-stu-id="d3492-284">Active users in the system</span></span>

  - <span data-ttu-id="d3492-285">Usuarios activos en salones de chat de tamaño determinado</span><span class="sxs-lookup"><span data-stu-id="d3492-285">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="d3492-286">Salones de chat del tamaño especificado que un solo usuario combina</span><span class="sxs-lookup"><span data-stu-id="d3492-286">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="d3492-287">Para cada salón de chat, la tabla de planeación de capacidad anterior especifica el número de entradas de control de acceso que están asociadas con el salón de chat, incluidas las entradas que se asignan directamente al salón de chat.</span><span class="sxs-lookup"><span data-stu-id="d3492-287">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="d3492-288">Puede controlar el acceso a los salones de chat individuales mediante listas de control de acceso (ACL).</span><span class="sxs-lookup"><span data-stu-id="d3492-288">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="d3492-289">También puede controlar el acceso a nivel de categoría.</span><span class="sxs-lookup"><span data-stu-id="d3492-289">You can also control access at the category level.</span></span> <span data-ttu-id="d3492-290">En una ACL, una entrada de control de acceso individual puede ser un grupo de usuarios (por ejemplo, un grupo de seguridad, una lista de distribución o un único usuario).</span><span class="sxs-lookup"><span data-stu-id="d3492-290">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="d3492-291">Puede definir entradas de control de acceso para administradores de salones de chat, moderadores y miembros.</span><span class="sxs-lookup"><span data-stu-id="d3492-291">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3492-292">Al planear la estrategia de administración de salones de chat, tenga en cuenta que el número total de entradas de control de acceso permitidas es de 2 millones.</span><span class="sxs-lookup"><span data-stu-id="d3492-292">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="d3492-293">Si las entradas de control de acceso calculado superan los 2 millones, el rendimiento del servidor podría degradarse de forma significativa.</span><span class="sxs-lookup"><span data-stu-id="d3492-293">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="d3492-294">Para evitar este problema, siempre que sea posible, asegúrese de que las entradas de control de acceso son grupos de usuarios en lugar de usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="d3492-294">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="d3492-295">Planeación de la capacidad para administrar el acceso al salón de chat por invitación</span><span class="sxs-lookup"><span data-stu-id="d3492-295">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="d3492-296">Puede usar la siguiente tabla de planeación de capacidad para conocer el número de invitaciones que el servidor de chat persistente crea y almacena en la base de datos de chat persistente cuando está configurada para enviar invitaciones.</span><span class="sxs-lookup"><span data-stu-id="d3492-296">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="d3492-297">Para administrar invitaciones en la categoría, use la página **configuración de categoría de salón de chat** en el panel de control de Lync Server o use el cmdlet **set-CsPersistentChatCategory**de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3492-297">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="d3492-298">Puede administrar invitaciones en un salón de chat (en línea con lo que permite la categoría) mediante la página de **Administración de salas** iniciada desde el cliente de Lync o mediante un cmdlet de Windows PowerShell, **set-csPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="d3492-298">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="d3492-299">Los datos de ejemplo de la siguiente tabla asumen que, en la página de **configuración del salón de chat** para el 50 por ciento de todos los salones de chat, la opción **invitaciones** está establecida en **sí**.</span><span class="sxs-lookup"><span data-stu-id="d3492-299">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3492-300">Si el valor calculado para el número de invitaciones generadas por el servidor supera 1 millón, el rendimiento del servidor podría degradarse de forma significativa.</span><span class="sxs-lookup"><span data-stu-id="d3492-300">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="d3492-301">Para evitar este problema, asegúrese de minimizar el número de salones de chat configurados para enviar invitaciones o restringir el número de usuarios que pueden unirse a salones de chat configurados para enviar invitaciones.</span><span class="sxs-lookup"><span data-stu-id="d3492-301">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="d3492-302">Ejemplo de acceso a salones de chat por invitación</span><span class="sxs-lookup"><span data-stu-id="d3492-302">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="d3492-303">Salones de chat pequeños</span><span class="sxs-lookup"><span data-stu-id="d3492-303">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="d3492-304">Salones de chat medianos</span><span class="sxs-lookup"><span data-stu-id="d3492-304">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="d3492-305">Salones de chat grandes</span><span class="sxs-lookup"><span data-stu-id="d3492-305">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="d3492-306">Total</span><span class="sxs-lookup"><span data-stu-id="d3492-306">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3492-307">Usuarios que pueden acceder al salón de chat</span><span class="sxs-lookup"><span data-stu-id="d3492-307">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="d3492-308">30 por salón</span><span class="sxs-lookup"><span data-stu-id="d3492-308">30 per room</span></span></p></td>
<td><p><span data-ttu-id="d3492-309">150 por salón</span><span class="sxs-lookup"><span data-stu-id="d3492-309">150 per room</span></span></p></td>
<td><p><span data-ttu-id="d3492-310">16.000 por salón</span><span class="sxs-lookup"><span data-stu-id="d3492-310">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-311">Porcentaje de salones que tienen invitaciones</span><span class="sxs-lookup"><span data-stu-id="d3492-311">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="d3492-312">50%</span><span class="sxs-lookup"><span data-stu-id="d3492-312">50%</span></span></p></td>
<td><p><span data-ttu-id="d3492-313">50%</span><span class="sxs-lookup"><span data-stu-id="d3492-313">50%</span></span></p></td>
<td><p><span data-ttu-id="d3492-314">50%</span><span class="sxs-lookup"><span data-stu-id="d3492-314">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-315">Salones de chat configurados para enviar invitaciones</span><span class="sxs-lookup"><span data-stu-id="d3492-315">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="d3492-316"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="d3492-316"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-317"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="d3492-317"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-318"><em>2,5</em></span><span class="sxs-lookup"><span data-stu-id="d3492-318"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-319">Usuarios que pueden acceder al salón de chat</span><span class="sxs-lookup"><span data-stu-id="d3492-319">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="d3492-320"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="d3492-320"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-321"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="d3492-321"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="d3492-322"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="d3492-322"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-323">Invitaciones generadas por el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d3492-323">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="d3492-324">960.000</span><span class="sxs-lookup"><span data-stu-id="d3492-324">960,000</span></span></p></td>
<td><p><span data-ttu-id="d3492-325">120.000</span><span class="sxs-lookup"><span data-stu-id="d3492-325">120,000</span></span></p></td>
<td><p><span data-ttu-id="d3492-326">80,000</span><span class="sxs-lookup"><span data-stu-id="d3492-326">80,000</span></span></p></td>
<td><p><span data-ttu-id="d3492-327">1.160.000</span><span class="sxs-lookup"><span data-stu-id="d3492-327">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-328">Número máximo de invitaciones permitidas</span><span class="sxs-lookup"><span data-stu-id="d3492-328">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="d3492-329">2 millones</span><span class="sxs-lookup"><span data-stu-id="d3492-329">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-330">Modelo 1: comienzo con número previsto de mensajes por habitación por día</span><span class="sxs-lookup"><span data-stu-id="d3492-330">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-331">Tasa de chats por salón (por día)</span><span class="sxs-lookup"><span data-stu-id="d3492-331">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="d3492-332">50</span><span class="sxs-lookup"><span data-stu-id="d3492-332">50</span></span></p></td>
<td><p><span data-ttu-id="d3492-333">500</span><span class="sxs-lookup"><span data-stu-id="d3492-333">500</span></span></p></td>
<td><p><span data-ttu-id="d3492-334">100</span><span class="sxs-lookup"><span data-stu-id="d3492-334">100</span></span></p></td>
<td><p><span data-ttu-id="d3492-335">650</span><span class="sxs-lookup"><span data-stu-id="d3492-335">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-336">Tasa de chat (por segundo) en todas las salas</span><span class="sxs-lookup"><span data-stu-id="d3492-336">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-337">55,56</span><span class="sxs-lookup"><span data-stu-id="d3492-337">55.56</span></span></p></td>
<td><p><span data-ttu-id="d3492-338">18,52</span><span class="sxs-lookup"><span data-stu-id="d3492-338">18.52</span></span></p></td>
<td><p><span data-ttu-id="d3492-339">0,03</span><span class="sxs-lookup"><span data-stu-id="d3492-339">0.03</span></span></p></td>
<td><p><span data-ttu-id="d3492-340">74</span><span class="sxs-lookup"><span data-stu-id="d3492-340">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-341">Modelo 2: Inicio con el número de mensajes publicados por usuario y día</span><span class="sxs-lookup"><span data-stu-id="d3492-341">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-342">Tasa de chat por usuario y día</span><span class="sxs-lookup"><span data-stu-id="d3492-342">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="d3492-343">15 </span><span class="sxs-lookup"><span data-stu-id="d3492-343">15</span></span></p></td>
<td><p><span data-ttu-id="d3492-344">5 </span><span class="sxs-lookup"><span data-stu-id="d3492-344">5</span></span></p></td>
<td><p><span data-ttu-id="d3492-345">0,1</span><span class="sxs-lookup"><span data-stu-id="d3492-345">0.1</span></span></p></td>
<td><p><span data-ttu-id="d3492-346">20</span><span class="sxs-lookup"><span data-stu-id="d3492-346">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-347">Tasa de chats por salón (por día)</span><span class="sxs-lookup"><span data-stu-id="d3492-347">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="d3492-348">38</span><span class="sxs-lookup"><span data-stu-id="d3492-348">38</span></span></p></td>
<td><p><span data-ttu-id="d3492-349">375</span><span class="sxs-lookup"><span data-stu-id="d3492-349">375</span></span></p></td>
<td><p><span data-ttu-id="d3492-350">800</span><span class="sxs-lookup"><span data-stu-id="d3492-350">800</span></span></p></td>
<td><p><span data-ttu-id="d3492-351">1.213</span><span class="sxs-lookup"><span data-stu-id="d3492-351">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-352">Tasa de chat (por segundo) en todas las salas</span><span class="sxs-lookup"><span data-stu-id="d3492-352">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-353">41,67</span><span class="sxs-lookup"><span data-stu-id="d3492-353">41.67</span></span></p></td>
<td><p><span data-ttu-id="d3492-354">13,89</span><span class="sxs-lookup"><span data-stu-id="d3492-354">13.89</span></span></p></td>
<td><p><span data-ttu-id="d3492-355">0,28</span><span class="sxs-lookup"><span data-stu-id="d3492-355">0.28</span></span></p></td>
<td><p><span data-ttu-id="d3492-356">56</span><span class="sxs-lookup"><span data-stu-id="d3492-356">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="d3492-357">Modelo de usuario de rendimiento del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d3492-357">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="d3492-358">En la tabla siguiente se describe el modelo de usuario para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d3492-358">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="d3492-359">Proporciona la base para los requisitos de planeación de la capacidad y representa una organización típica con 80.000 usuarios simultáneos en cuatro servidores.</span><span class="sxs-lookup"><span data-stu-id="d3492-359">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="d3492-360">Modelo de usuario de rendimiento del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d3492-360">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3492-361">Número de usuarios activos conectados</span><span class="sxs-lookup"><span data-stu-id="d3492-361">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="d3492-362">80,000</span><span class="sxs-lookup"><span data-stu-id="d3492-362">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-363">Número de instancias de servicio del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d3492-363">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="d3492-364">4 </span><span class="sxs-lookup"><span data-stu-id="d3492-364">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-365">Tamaño de salones de chat pequeños</span><span class="sxs-lookup"><span data-stu-id="d3492-365">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-366">30 usuarios</span><span class="sxs-lookup"><span data-stu-id="d3492-366">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-367">Tamaño de salones de chat medianos</span><span class="sxs-lookup"><span data-stu-id="d3492-367">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-368">150 usuarios</span><span class="sxs-lookup"><span data-stu-id="d3492-368">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-369">Tamaño de salones de chat grandes</span><span class="sxs-lookup"><span data-stu-id="d3492-369">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-370">16.000 usuarios</span><span class="sxs-lookup"><span data-stu-id="d3492-370">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-371">Cantidad total de salones de chat</span><span class="sxs-lookup"><span data-stu-id="d3492-371">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-372">33.077</span><span class="sxs-lookup"><span data-stu-id="d3492-372">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-373">Número de salones de chat pequeños</span><span class="sxs-lookup"><span data-stu-id="d3492-373">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-374">32.000</span><span class="sxs-lookup"><span data-stu-id="d3492-374">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-375">Número de salones de chat medianos</span><span class="sxs-lookup"><span data-stu-id="d3492-375">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-376">1.067</span><span class="sxs-lookup"><span data-stu-id="d3492-376">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-377">Número de salones de chat grandes</span><span class="sxs-lookup"><span data-stu-id="d3492-377">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-378">10  </span><span class="sxs-lookup"><span data-stu-id="d3492-378">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-379">Cantidad total de salones de chat por usuario</span><span class="sxs-lookup"><span data-stu-id="d3492-379">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="d3492-380">16 </span><span class="sxs-lookup"><span data-stu-id="d3492-380">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-381">Número de salones de chat pequeños por usuario</span><span class="sxs-lookup"><span data-stu-id="d3492-381">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="d3492-382">12 </span><span class="sxs-lookup"><span data-stu-id="d3492-382">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-383">Número de salones de chat medianos por usuario</span><span class="sxs-lookup"><span data-stu-id="d3492-383">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="d3492-384">segundo</span><span class="sxs-lookup"><span data-stu-id="d3492-384">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-385">Número de salones de chat grandes por usuario</span><span class="sxs-lookup"><span data-stu-id="d3492-385">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="d3492-386">segundo</span><span class="sxs-lookup"><span data-stu-id="d3492-386">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-387">Número de salones Unidos por usuario</span><span class="sxs-lookup"><span data-stu-id="d3492-387">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="d3492-388">apartado</span><span class="sxs-lookup"><span data-stu-id="d3492-388">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-389">Tasa máxima de combinaciones</span><span class="sxs-lookup"><span data-stu-id="d3492-389">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="d3492-390">10/segundo</span><span class="sxs-lookup"><span data-stu-id="d3492-390">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-391">Tasa de chats total</span><span class="sxs-lookup"><span data-stu-id="d3492-391">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="d3492-392">24/segundo</span><span class="sxs-lookup"><span data-stu-id="d3492-392">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-393">Tasa de chats para salones de chat pequeños</span><span class="sxs-lookup"><span data-stu-id="d3492-393">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-394">22.22/segundo</span><span class="sxs-lookup"><span data-stu-id="d3492-394">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-395">Tasa de chats para salones de chat medianos</span><span class="sxs-lookup"><span data-stu-id="d3492-395">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-396">1.67/segundo</span><span class="sxs-lookup"><span data-stu-id="d3492-396">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-397">Tasa de chats para salones de chat grandes</span><span class="sxs-lookup"><span data-stu-id="d3492-397">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d3492-398">~ 0,15/segundo</span><span class="sxs-lookup"><span data-stu-id="d3492-398">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-399">Porcentaje de salones de chat configurados para invitaciones</span><span class="sxs-lookup"><span data-stu-id="d3492-399">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="d3492-400">50%</span><span class="sxs-lookup"><span data-stu-id="d3492-400">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-401">Porcentaje de pertenencia directa</span><span class="sxs-lookup"><span data-stu-id="d3492-401">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="d3492-402">50%</span><span class="sxs-lookup"><span data-stu-id="d3492-402">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-403">Porcentaje de pertenencias a grupos</span><span class="sxs-lookup"><span data-stu-id="d3492-403">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="d3492-404">50%</span><span class="sxs-lookup"><span data-stu-id="d3492-404">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-405">Número medio de afiliaciones antecesoras en servicios de dominio de Active Directory</span><span class="sxs-lookup"><span data-stu-id="d3492-405">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="d3492-406">100-200</span><span class="sxs-lookup"><span data-stu-id="d3492-406">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-407">Número de contactos suscritos por usuario</span><span class="sxs-lookup"><span data-stu-id="d3492-407">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="d3492-408">80</span><span class="sxs-lookup"><span data-stu-id="d3492-408">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-409">Número medio de puntos de conexión por usuario</span><span class="sxs-lookup"><span data-stu-id="d3492-409">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="d3492-410">1,5</span><span class="sxs-lookup"><span data-stu-id="d3492-410">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-411">Número medio de salones de chat visibles por extremo</span><span class="sxs-lookup"><span data-stu-id="d3492-411">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="d3492-412">1,5</span><span class="sxs-lookup"><span data-stu-id="d3492-412">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-413">Número medio de salones de chat visibles por usuario</span><span class="sxs-lookup"><span data-stu-id="d3492-413">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="d3492-414">2,25 (50% para 1 habitación y 50% para 2 habitaciones); Hasta 6 salas abiertas, una por monitor</span><span class="sxs-lookup"><span data-stu-id="d3492-414">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-415">Número de participantes sondeados por intervalo</span><span class="sxs-lookup"><span data-stu-id="d3492-415">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="d3492-416">25 por salón de chat visible</span><span class="sxs-lookup"><span data-stu-id="d3492-416">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-417">Longitud del intervalo de sondeo</span><span class="sxs-lookup"><span data-stu-id="d3492-417">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="d3492-418">5 minutos</span><span class="sxs-lookup"><span data-stu-id="d3492-418">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-419">Número de participantes sondeados por segundo</span><span class="sxs-lookup"><span data-stu-id="d3492-419">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="d3492-420">15.000</span><span class="sxs-lookup"><span data-stu-id="d3492-420">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3492-421">Número de cambios de presencia por hora por usuario</span><span class="sxs-lookup"><span data-stu-id="d3492-421">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="d3492-422">6 </span><span class="sxs-lookup"><span data-stu-id="d3492-422">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3492-423">Número de cambios de presencia por segundo</span><span class="sxs-lookup"><span data-stu-id="d3492-423">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="d3492-424">133,33</span><span class="sxs-lookup"><span data-stu-id="d3492-424">133.33</span></span></p></td>
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

