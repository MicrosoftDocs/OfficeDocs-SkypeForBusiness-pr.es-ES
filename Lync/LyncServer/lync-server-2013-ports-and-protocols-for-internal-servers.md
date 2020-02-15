---
title: 'Lync Server 2013: puertos y protocolos para servidores internos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c748a79fe118c9b1d233a7a276bd8298a0e1c3e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="e8f28-102">Puertos y protocolos para servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8f28-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8f28-103">_**Última modificación del tema:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="e8f28-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="e8f28-104">En esta sección se resumen los puertos y protocolos que usan los servidores, los equilibradores de carga y los clientes en una implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8f28-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e8f28-105">Los clientes de Lync y Communicator cuando participan en una comunicación de una a una, a menudo se denominan de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="e8f28-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="e8f28-106">Técnicamente, los dos clientes se comunican en una conversación de una a una, con la unidad de control multipunto (IMMCU) de mensajería instantánea en la parte central.</span><span class="sxs-lookup"><span data-stu-id="e8f28-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="e8f28-107">IMMCU es un componente del servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e8f28-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="e8f28-108">La colocación de IMMCU en el flujo de trabajo de comunicación necesario permite el registro detallado de llamadas y otras características que permite el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e8f28-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="e8f28-109">La comunicación es desde un puerto de origen dinámico en el cliente al puerto del servidor front-end TLS/TCP/5061 (asumiendo el uso de la seguridad de la capa de transporte recomendada).</span><span class="sxs-lookup"><span data-stu-id="e8f28-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="e8f28-110">Por diseño, la comunicación punto a punto (así como la mensajería instantánea de varios participantes) solo es posible cuando Lync Server y el IMMCU está activo y disponible.</span><span class="sxs-lookup"><span data-stu-id="e8f28-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="e8f28-111">Detalles de puerto y protocolo</span><span class="sxs-lookup"><span data-stu-id="e8f28-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8f28-112">Firewall de Windows debe estar en ejecución antes de iniciar los servicios de Lync Server en un servidor, ya que esto se debe a que Lync Server abre los puertos necesarios en el firewall.</span><span class="sxs-lookup"><span data-stu-id="e8f28-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="e8f28-113">Para obtener más información sobre la configuración del firewall para los componentes perimetrales, consulte [determine external a/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8f28-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="e8f28-114">En la tabla siguiente se enumeran los puertos que debe abrir en cada rol del servidor interno.</span><span class="sxs-lookup"><span data-stu-id="e8f28-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="e8f28-115">Puertos de servidor obligatorios (por rol del servidor)</span><span class="sxs-lookup"><span data-stu-id="e8f28-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="e8f28-116">Rol de servidor</span><span class="sxs-lookup"><span data-stu-id="e8f28-116">Server role</span></span></th>
<th><span data-ttu-id="e8f28-117">Nombre del servicio</span><span class="sxs-lookup"><span data-stu-id="e8f28-117">Service name</span></span></th>
<th><span data-ttu-id="e8f28-118">Puerto</span><span class="sxs-lookup"><span data-stu-id="e8f28-118">Port</span></span></th>
<th><span data-ttu-id="e8f28-119">Protocolo</span><span class="sxs-lookup"><span data-stu-id="e8f28-119">Protocol</span></span></th>
<th><span data-ttu-id="e8f28-120">Notas</span><span class="sxs-lookup"><span data-stu-id="e8f28-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-121">Todos los servidores</span><span class="sxs-lookup"><span data-stu-id="e8f28-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-122">Explorador SQL</span><span class="sxs-lookup"><span data-stu-id="e8f28-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="e8f28-123">1434</span><span class="sxs-lookup"><span data-stu-id="e8f28-123">1434</span></span></p></td>
<td><p><span data-ttu-id="e8f28-124">UDP</span><span class="sxs-lookup"><span data-stu-id="e8f28-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-125">Explorador SQL para la copia replicada local de la base de datos del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="e8f28-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-126">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-127">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-128">5060</span><span class="sxs-lookup"><span data-stu-id="e8f28-128">5060</span></span></p></td>
<td><p><span data-ttu-id="e8f28-129">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-130">Opcionalmente lo usan los servidores Standard Edition y front-end para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e8f28-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-131">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-132">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-133">5061</span><span class="sxs-lookup"><span data-stu-id="e8f28-133">5061</span></span></p></td>
<td><p><span data-ttu-id="e8f28-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-p102">Lo usan los servidores Standard Edition y los grupos de servidores front-end para todas la comunicaciones SIP internas entre los servidores (MTLS), para las comunicaciones SIP entre el cliente y del servidor (TLS) y para las comunicaciones entre los servidores front-end y los servidores de mediación (MTLS). También se usa para las comunicaciones con el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="e8f28-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-137">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-138">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-139">444</span><span class="sxs-lookup"><span data-stu-id="e8f28-139">444</span></span></p></td>
<td><p><span data-ttu-id="e8f28-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8f28-140">HTTPS</span></span></p>
<p><span data-ttu-id="e8f28-141">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-142">Se usa para la comunicación HTTPS entre el foco (el componente de Lync Server que administra el estado de conferencia) y los servidores individuales.</span><span class="sxs-lookup"><span data-stu-id="e8f28-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="e8f28-143">Este puerto también se usa para la comunicación TCP entre las aplicaciones de sucursal con funciones de supervivencia y los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="e8f28-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-144">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-145">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-146">135</span><span class="sxs-lookup"><span data-stu-id="e8f28-146">135</span></span></p></td>
<td><p><span data-ttu-id="e8f28-147">DCOM y llamada a procedimiento remoto (RPC)</span><span class="sxs-lookup"><span data-stu-id="e8f28-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-148">Se usa para operaciones basadas en DCOM como la migración de los usuarios, la sincronización del replicador de usuarios y la sincronización de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e8f28-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-149">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-150">Servicio de conferencia de mensajería instantánea de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-151">5062</span><span class="sxs-lookup"><span data-stu-id="e8f28-151">5062</span></span></p></td>
<td><p><span data-ttu-id="e8f28-152">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-153">Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="e8f28-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-154">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-155">Servicio de conferencia Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-156">8057</span><span class="sxs-lookup"><span data-stu-id="e8f28-156">8057</span></span></p></td>
<td><p><span data-ttu-id="e8f28-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-158">Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.</span><span class="sxs-lookup"><span data-stu-id="e8f28-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-159">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-160">Servicio de compatibilidad con conferencias web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-161">8058</span><span class="sxs-lookup"><span data-stu-id="e8f28-161">8058</span></span></p></td>
<td><p><span data-ttu-id="e8f28-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-163">Se usa para escuchar las conexiones del modelo de objetos compartidos persistentes (PSOM) desde el cliente de Live Meeting y las versiones anteriores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8f28-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-164">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-165">Servicio de conferencia de audio y vídeo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-166">5063</span><span class="sxs-lookup"><span data-stu-id="e8f28-166">5063</span></span></p></td>
<td><p><span data-ttu-id="e8f28-167">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-168">Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="e8f28-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-169">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-170">Servicio de conferencia de audio y vídeo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="e8f28-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="e8f28-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="e8f28-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-173">Intervalo de puerto de medios usado para conferencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e8f28-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-174">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-175">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-176">80</span><span class="sxs-lookup"><span data-stu-id="e8f28-176">80</span></span></p></td>
<td><p><span data-ttu-id="e8f28-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="e8f28-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-178">Se usa para la comunicación entre los servidores front-end y los FQDN (direcciones URL usadas por los componentes web IIS) cuando no se usa HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e8f28-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-179">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-180">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-181">443</span><span class="sxs-lookup"><span data-stu-id="e8f28-181">443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8f28-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="e8f28-183">Se usa para la comunicación entre los servidores front-end y los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS).</span><span class="sxs-lookup"><span data-stu-id="e8f28-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-184">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-185">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-186">8080</span><span class="sxs-lookup"><span data-stu-id="e8f28-186">8080</span></span></p></td>
<td><p><span data-ttu-id="e8f28-187">TCP y HTTP</span><span class="sxs-lookup"><span data-stu-id="e8f28-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-188">Lo usan los componentes Web para el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="e8f28-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-189">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-190">Componente del servidor Web</span><span class="sxs-lookup"><span data-stu-id="e8f28-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="e8f28-191">4443</span><span class="sxs-lookup"><span data-stu-id="e8f28-191">4443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8f28-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="e8f28-193">HTTPS (desde proxy inverso) y comunicaciones entre grupos de servidores front-end de HTTPS para el inicio de sesión con detección automática.</span><span class="sxs-lookup"><span data-stu-id="e8f28-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-194">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-195">Componente del servidor Web</span><span class="sxs-lookup"><span data-stu-id="e8f28-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="e8f28-196">8060</span><span class="sxs-lookup"><span data-stu-id="e8f28-196">8060</span></span></p></td>
<td><p><span data-ttu-id="e8f28-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-198">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-199">Componente del servidor Web</span><span class="sxs-lookup"><span data-stu-id="e8f28-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="e8f28-200">8061</span><span class="sxs-lookup"><span data-stu-id="e8f28-200">8061</span></span></p></td>
<td><p><span data-ttu-id="e8f28-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-202">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-203">Componente de servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="e8f28-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="e8f28-204">5086</span><span class="sxs-lookup"><span data-stu-id="e8f28-204">5086</span></span></p></td>
<td><p><span data-ttu-id="e8f28-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-206">Puerto SIP usado por los procesos internos de Mobility Services</span><span class="sxs-lookup"><span data-stu-id="e8f28-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-207">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-208">Componente de servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="e8f28-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="e8f28-209">5087</span><span class="sxs-lookup"><span data-stu-id="e8f28-209">5087</span></span></p></td>
<td><p><span data-ttu-id="e8f28-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-211">Puerto SIP usado por los procesos internos de Mobility Services</span><span class="sxs-lookup"><span data-stu-id="e8f28-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-212">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-213">Componente de servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="e8f28-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="e8f28-214">443</span><span class="sxs-lookup"><span data-stu-id="e8f28-214">443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8f28-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-216">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-217">Servicio de operador de conferencia de Lync Server (Conferencia de acceso telefónico local)</span><span class="sxs-lookup"><span data-stu-id="e8f28-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-218">5064</span><span class="sxs-lookup"><span data-stu-id="e8f28-218">5064</span></span></p></td>
<td><p><span data-ttu-id="e8f28-219">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-220">Se usa para las solicitudes SIP entrantes de las conferencias telefónicas.</span><span class="sxs-lookup"><span data-stu-id="e8f28-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-221">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-222">Servicio de operador de conferencia de Lync Server (Conferencia de acceso telefónico local)</span><span class="sxs-lookup"><span data-stu-id="e8f28-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-223">5072</span><span class="sxs-lookup"><span data-stu-id="e8f28-223">5072</span></span></p></td>
<td><p><span data-ttu-id="e8f28-224">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-225">Se usa para las solicitudes SIP entrantes para el operador (llamadas de conferencia de acceso telefónico local).</span><span class="sxs-lookup"><span data-stu-id="e8f28-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-226">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="e8f28-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e8f28-227">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-228">5070</span><span class="sxs-lookup"><span data-stu-id="e8f28-228">5070</span></span></p></td>
<td><p><span data-ttu-id="e8f28-229">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-230">Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="e8f28-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-231">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="e8f28-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e8f28-232">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-233">5067</span><span class="sxs-lookup"><span data-stu-id="e8f28-233">5067</span></span></p></td>
<td><p><span data-ttu-id="e8f28-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-235">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="e8f28-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-236">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="e8f28-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e8f28-237">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-238">5068</span><span class="sxs-lookup"><span data-stu-id="e8f28-238">5068</span></span></p></td>
<td><p><span data-ttu-id="e8f28-239">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-240">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="e8f28-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-241">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="e8f28-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e8f28-242">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-243">5081</span><span class="sxs-lookup"><span data-stu-id="e8f28-243">5081</span></span></p></td>
<td><p><span data-ttu-id="e8f28-244">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-245">Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="e8f28-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-246">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="e8f28-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e8f28-247">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-248">5082</span><span class="sxs-lookup"><span data-stu-id="e8f28-248">5082</span></span></p></td>
<td><p><span data-ttu-id="e8f28-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-250">Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="e8f28-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-251">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-252">Servicio de uso compartido de aplicaciones de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-253">5065</span><span class="sxs-lookup"><span data-stu-id="e8f28-253">5065</span></span></p></td>
<td><p><span data-ttu-id="e8f28-254">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-255">Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e8f28-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-256">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-257">Servicio de uso compartido de aplicaciones de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="e8f28-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="e8f28-259">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-260">Intervalo de puerto de medios usado para compartir aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e8f28-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-261">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-262">Servicio de anuncio de conferencia de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-263">5073</span><span class="sxs-lookup"><span data-stu-id="e8f28-263">5073</span></span></p></td>
<td><p><span data-ttu-id="e8f28-264">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-265">Se usa para las solicitudes SIP entrantes para el servicio de anuncio de conferencia de Lync Server (es decir, para las conferencias de acceso telefónico local).</span><span class="sxs-lookup"><span data-stu-id="e8f28-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-266">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-267">Servicio de estacionamiento de llamadas de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-268">5075</span><span class="sxs-lookup"><span data-stu-id="e8f28-268">5075</span></span></p></td>
<td><p><span data-ttu-id="e8f28-269">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-270">Se usa para las solicitudes SIP entrantes de la aplicación Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e8f28-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-271">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-272">Servicio de prueba de audio de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-273">5076</span><span class="sxs-lookup"><span data-stu-id="e8f28-273">5076</span></span></p></td>
<td><p><span data-ttu-id="e8f28-274">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-275">Se usa para las solicitudes SIP entrantes del servicio de prueba de audio.</span><span class="sxs-lookup"><span data-stu-id="e8f28-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-276">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-277">No aplicable</span><span class="sxs-lookup"><span data-stu-id="e8f28-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="e8f28-278">5066</span><span class="sxs-lookup"><span data-stu-id="e8f28-278">5066</span></span></p></td>
<td><p><span data-ttu-id="e8f28-279">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-280">Se usa para la puerta de enlace 9-1-1 mejorado (E9-1-1) saliente</span><span class="sxs-lookup"><span data-stu-id="e8f28-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-281">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-282">Servicio de grupo de respuesta de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-283">5071</span><span class="sxs-lookup"><span data-stu-id="e8f28-283">5071</span></span></p></td>
<td><p><span data-ttu-id="e8f28-284">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-285">Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e8f28-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-286">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-287">Servicio de grupo de respuesta de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-288">8404</span><span class="sxs-lookup"><span data-stu-id="e8f28-288">8404</span></span></p></td>
<td><p><span data-ttu-id="e8f28-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-290">Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e8f28-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-291">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-292">Servicio de directiva de ancho de banda de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-293">5080</span><span class="sxs-lookup"><span data-stu-id="e8f28-293">5080</span></span></p></td>
<td><p><span data-ttu-id="e8f28-294">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-295">Lo usa el servicio de directiva de ancho de banda del tráfico TURN perimetral A/V para el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e8f28-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-296">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-297">Servicio de directiva de ancho de banda de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-298">448</span><span class="sxs-lookup"><span data-stu-id="e8f28-298">448</span></span></p></td>
<td><p><span data-ttu-id="e8f28-299">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-300">Se usa para el control de admisión de llamadas por el servicio de directiva de ancho de banda de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8f28-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-301">Servidores front-end donde reside el almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="e8f28-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="e8f28-302">Agente de replicador maestro de Microsoft Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-303">445</span><span class="sxs-lookup"><span data-stu-id="e8f28-303">445</span></span></p></td>
<td><p><span data-ttu-id="e8f28-304">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-305">Se usa para insertar los datos de configuración desde el almacén de administración central en los servidores que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8f28-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-306">Todos los servidores</span><span class="sxs-lookup"><span data-stu-id="e8f28-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-307">Explorador SQL</span><span class="sxs-lookup"><span data-stu-id="e8f28-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="e8f28-308">1434</span><span class="sxs-lookup"><span data-stu-id="e8f28-308">1434</span></span></p></td>
<td><p><span data-ttu-id="e8f28-309">UDP</span><span class="sxs-lookup"><span data-stu-id="e8f28-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-310">Explorador SQL para la copia replicada local de los datos del almacén de administración central en la instancia local de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-311">Todos los usuarios internos</span><span class="sxs-lookup"><span data-stu-id="e8f28-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-312">Varios</span><span class="sxs-lookup"><span data-stu-id="e8f28-312">Various</span></span></p></td>
<td><p><span data-ttu-id="e8f28-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="e8f28-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="e8f28-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="e8f28-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-315">El intervalo de puerto de medios se usa para audioconferencias en todos los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="e8f28-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="e8f28-316">Usada por todos los servidores que terminan audio: servidores front-end (para el servicio de operador de conferencia de Lync Server, el servicio de anuncio de conferencia de Lync Server y el servicio de conferencia de audio y vídeo de Lync Server) y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="e8f28-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-317">Servidores de Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="e8f28-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8f28-318">443</span><span class="sxs-lookup"><span data-stu-id="e8f28-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8f28-319">Se usa en Lync Server 2013 para conectarse a Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="e8f28-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-320">Reparto</span><span class="sxs-lookup"><span data-stu-id="e8f28-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="e8f28-321">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-322">5060</span><span class="sxs-lookup"><span data-stu-id="e8f28-322">5060</span></span></p></td>
<td><p><span data-ttu-id="e8f28-323">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-324">Se usa opcionalmente para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e8f28-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-325">Reparto</span><span class="sxs-lookup"><span data-stu-id="e8f28-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="e8f28-326">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-327">444</span><span class="sxs-lookup"><span data-stu-id="e8f28-327">444</span></span></p></td>
<td><p><span data-ttu-id="e8f28-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8f28-328">HTTPS</span></span></p>
<p><span data-ttu-id="e8f28-329">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-330">Comunicación entre servidores front-end y director.</span><span class="sxs-lookup"><span data-stu-id="e8f28-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="e8f28-331">Además, la publicación de certificados de cliente (para los servidores front-end) o la validación si ya se ha publicado el certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="e8f28-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-332">Reparto</span><span class="sxs-lookup"><span data-stu-id="e8f28-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="e8f28-333">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-334">80</span><span class="sxs-lookup"><span data-stu-id="e8f28-334">80</span></span></p></td>
<td><p><span data-ttu-id="e8f28-335">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-p105">Se usa para la comunicación inicial desde los directores a los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS). En condiciones normales, cambiará a tráfico HTTPS usando el puerto 443 y el tipo de protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="e8f28-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-338">Reparto</span><span class="sxs-lookup"><span data-stu-id="e8f28-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="e8f28-339">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-340">443</span><span class="sxs-lookup"><span data-stu-id="e8f28-340">443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8f28-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="e8f28-342">Se usa para la comunicación desde los directores a los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS).</span><span class="sxs-lookup"><span data-stu-id="e8f28-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-343">Reparto</span><span class="sxs-lookup"><span data-stu-id="e8f28-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="e8f28-344">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-345">5061</span><span class="sxs-lookup"><span data-stu-id="e8f28-345">5061</span></span></p></td>
<td><p><span data-ttu-id="e8f28-346">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-347">Se usa para comunicaciones internas entre servidores y para conexiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="e8f28-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-348">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="e8f28-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-349">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-350">5070</span><span class="sxs-lookup"><span data-stu-id="e8f28-350">5070</span></span></p></td>
<td><p><span data-ttu-id="e8f28-351">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-352">Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e8f28-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-353">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="e8f28-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-354">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-355">5067</span><span class="sxs-lookup"><span data-stu-id="e8f28-355">5067</span></span></p></td>
<td><p><span data-ttu-id="e8f28-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-357">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="e8f28-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-358">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="e8f28-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-359">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-360">5068</span><span class="sxs-lookup"><span data-stu-id="e8f28-360">5068</span></span></p></td>
<td><p><span data-ttu-id="e8f28-361">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-362">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="e8f28-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-363">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="e8f28-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="e8f28-364">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8f28-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-365">5070</span><span class="sxs-lookup"><span data-stu-id="e8f28-365">5070</span></span></p></td>
<td><p><span data-ttu-id="e8f28-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-367">Se usa para solicitudes SIP desde los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="e8f28-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-368">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e8f28-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="e8f28-369">SIP de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e8f28-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-370">5041</span><span class="sxs-lookup"><span data-stu-id="e8f28-370">5041</span></span></p></td>
<td><p><span data-ttu-id="e8f28-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-372">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e8f28-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="e8f28-373">Chat persistente Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="e8f28-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-374">881</span><span class="sxs-lookup"><span data-stu-id="e8f28-374">881</span></span></p></td>
<td><p><span data-ttu-id="e8f28-375">TCP (TLS) y TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-376">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e8f28-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="e8f28-377">Servicio de transferencia de archivos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e8f28-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="e8f28-378">443</span><span class="sxs-lookup"><span data-stu-id="e8f28-378">443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e8f28-380">Algunos escenarios de control remoto de llamadas requieren una conexión entre el servidor front-end o el director y la PBX.</span><span class="sxs-lookup"><span data-stu-id="e8f28-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="e8f28-381">Aunque Lync Server ya no usa el puerto TCP 5060, durante la implementación de control remoto de llamadas, se crea una configuración de servidor de confianza, que asocia el FQDN del servidor de línea RCC con el puerto TCP que el director o el servidor front-end usará para conectarse al sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="e8f28-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="e8f28-382">Para obtener más información, consulte el cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8f28-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="e8f28-383">Para los grupos de servidores que solo usan equilibrio de carga de hardware (no equilibrio de carga de DNS), en la siguiente tabla se muestran los puertos que necesitan para abrir los equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="e8f28-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="e8f28-384">Puertos del equilibrador de carga de hardware si solo usa equilibrio de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="e8f28-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8f28-385">Equilibrador de carga</span><span class="sxs-lookup"><span data-stu-id="e8f28-385">Load Balancer</span></span></th>
<th><span data-ttu-id="e8f28-386">Puerto</span><span class="sxs-lookup"><span data-stu-id="e8f28-386">Port</span></span></th>
<th><span data-ttu-id="e8f28-387">Protocolo</span><span class="sxs-lookup"><span data-stu-id="e8f28-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-388">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-389">5061</span><span class="sxs-lookup"><span data-stu-id="e8f28-389">5061</span></span></p></td>
<td><p><span data-ttu-id="e8f28-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-391">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-392">444</span><span class="sxs-lookup"><span data-stu-id="e8f28-392">444</span></span></p></td>
<td><p><span data-ttu-id="e8f28-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8f28-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-394">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-395">135</span><span class="sxs-lookup"><span data-stu-id="e8f28-395">135</span></span></p></td>
<td><p><span data-ttu-id="e8f28-396">DCOM y llamada a procedimiento remoto (RPC)</span><span class="sxs-lookup"><span data-stu-id="e8f28-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-397">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-398">80</span><span class="sxs-lookup"><span data-stu-id="e8f28-398">80</span></span></p></td>
<td><p><span data-ttu-id="e8f28-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="e8f28-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-400">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-401">8080</span><span class="sxs-lookup"><span data-stu-id="e8f28-401">8080</span></span></p></td>
<td><p><span data-ttu-id="e8f28-402">TCP - Recuperación cliente y dispositivo del certificado raíz del servidor de front-end – clientes y dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="e8f28-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-403">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-404">443</span><span class="sxs-lookup"><span data-stu-id="e8f28-404">443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8f28-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-406">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-407">4443</span><span class="sxs-lookup"><span data-stu-id="e8f28-407">4443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-408">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="e8f28-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-409">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-410">5072</span><span class="sxs-lookup"><span data-stu-id="e8f28-410">5072</span></span></p></td>
<td><p><span data-ttu-id="e8f28-411">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-412">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-413">5073</span><span class="sxs-lookup"><span data-stu-id="e8f28-413">5073</span></span></p></td>
<td><p><span data-ttu-id="e8f28-414">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-415">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-416">5075</span><span class="sxs-lookup"><span data-stu-id="e8f28-416">5075</span></span></p></td>
<td><p><span data-ttu-id="e8f28-417">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-418">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-419">5076</span><span class="sxs-lookup"><span data-stu-id="e8f28-419">5076</span></span></p></td>
<td><p><span data-ttu-id="e8f28-420">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-421">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-422">5071</span><span class="sxs-lookup"><span data-stu-id="e8f28-422">5071</span></span></p></td>
<td><p><span data-ttu-id="e8f28-423">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-424">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-425">5080</span><span class="sxs-lookup"><span data-stu-id="e8f28-425">5080</span></span></p></td>
<td><p><span data-ttu-id="e8f28-426">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-427">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-428">448</span><span class="sxs-lookup"><span data-stu-id="e8f28-428">448</span></span></p></td>
<td><p><span data-ttu-id="e8f28-429">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-430">Equilibrador de carga del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="e8f28-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-431">5070</span><span class="sxs-lookup"><span data-stu-id="e8f28-431">5070</span></span></p></td>
<td><p><span data-ttu-id="e8f28-432">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-433">Equilibrador de carga del servidor front-end (si el grupo también ejecuta el servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="e8f28-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-434">5070</span><span class="sxs-lookup"><span data-stu-id="e8f28-434">5070</span></span></p></td>
<td><p><span data-ttu-id="e8f28-435">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-436">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="e8f28-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-437">443</span><span class="sxs-lookup"><span data-stu-id="e8f28-437">443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8f28-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-439">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="e8f28-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-440">444</span><span class="sxs-lookup"><span data-stu-id="e8f28-440">444</span></span></p></td>
<td><p><span data-ttu-id="e8f28-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8f28-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-442">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="e8f28-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-443">5061</span><span class="sxs-lookup"><span data-stu-id="e8f28-443">5061</span></span></p></td>
<td><p><span data-ttu-id="e8f28-444">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-445">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="e8f28-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-446">4443</span><span class="sxs-lookup"><span data-stu-id="e8f28-446">4443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-447">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="e8f28-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e8f28-p107">Los grupos de servidores front-end y de directores que usan equilibrio de carga de DNS también deben tener implementado un equilibrador de carga de hardware. En la siguiente tabla se muestran los puertos que se deben abrir en estos equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="e8f28-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="e8f28-450">Puertos del equilibrador de carga de hardware si usa equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="e8f28-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8f28-451">Equilibrador de carga</span><span class="sxs-lookup"><span data-stu-id="e8f28-451">Load Balancer</span></span></th>
<th><span data-ttu-id="e8f28-452">Puerto</span><span class="sxs-lookup"><span data-stu-id="e8f28-452">Port</span></span></th>
<th><span data-ttu-id="e8f28-453">Protocolo</span><span class="sxs-lookup"><span data-stu-id="e8f28-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-454">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-455">80</span><span class="sxs-lookup"><span data-stu-id="e8f28-455">80</span></span></p></td>
<td><p><span data-ttu-id="e8f28-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="e8f28-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-457">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-458">443</span><span class="sxs-lookup"><span data-stu-id="e8f28-458">443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8f28-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-460">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-461">8080</span><span class="sxs-lookup"><span data-stu-id="e8f28-461">8080</span></span></p></td>
<td><p><span data-ttu-id="e8f28-462">TCP - Recuperación cliente y dispositivo del certificado raíz del servidor de front-end – clientes y dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="e8f28-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-463">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e8f28-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-464">4443</span><span class="sxs-lookup"><span data-stu-id="e8f28-464">4443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-465">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="e8f28-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-466">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="e8f28-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-467">443</span><span class="sxs-lookup"><span data-stu-id="e8f28-467">443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8f28-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-469">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="e8f28-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="e8f28-470">4443</span><span class="sxs-lookup"><span data-stu-id="e8f28-470">4443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-471">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="e8f28-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="e8f28-472">Puertos de cliente requeridos</span><span class="sxs-lookup"><span data-stu-id="e8f28-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8f28-473">Componente</span><span class="sxs-lookup"><span data-stu-id="e8f28-473">Component</span></span></th>
<th><span data-ttu-id="e8f28-474">Puerto</span><span class="sxs-lookup"><span data-stu-id="e8f28-474">Port</span></span></th>
<th><span data-ttu-id="e8f28-475">Protocolo</span><span class="sxs-lookup"><span data-stu-id="e8f28-475">Protocol</span></span></th>
<th><span data-ttu-id="e8f28-476">Notas</span><span class="sxs-lookup"><span data-stu-id="e8f28-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-477">Clientes</span><span class="sxs-lookup"><span data-stu-id="e8f28-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="e8f28-478">67/68</span><span class="sxs-lookup"><span data-stu-id="e8f28-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="e8f28-479">DCHP</span><span class="sxs-lookup"><span data-stu-id="e8f28-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-480">Lo usa Lync Server para buscar el FQDN del registrador (es decir, si se produce un error en el SRV de DNS y no se configura la configuración manual).</span><span class="sxs-lookup"><span data-stu-id="e8f28-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-481">Clientes</span><span class="sxs-lookup"><span data-stu-id="e8f28-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="e8f28-482">443</span><span class="sxs-lookup"><span data-stu-id="e8f28-482">443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-484">Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="e8f28-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-485">Clientes</span><span class="sxs-lookup"><span data-stu-id="e8f28-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="e8f28-486">443</span><span class="sxs-lookup"><span data-stu-id="e8f28-486">443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-488">Se usa para el acceso de usuarios externos a las sesiones de conferencia web.</span><span class="sxs-lookup"><span data-stu-id="e8f28-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-489">Clientes</span><span class="sxs-lookup"><span data-stu-id="e8f28-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="e8f28-490">443</span><span class="sxs-lookup"><span data-stu-id="e8f28-490">443</span></span></p></td>
<td><p><span data-ttu-id="e8f28-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="e8f28-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-492">Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP)</span><span class="sxs-lookup"><span data-stu-id="e8f28-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-493">Clientes</span><span class="sxs-lookup"><span data-stu-id="e8f28-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="e8f28-494">3478</span><span class="sxs-lookup"><span data-stu-id="e8f28-494">3478</span></span></p></td>
<td><p><span data-ttu-id="e8f28-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="e8f28-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-496">Se usa para el acceso de usuarios externos a las sesiones y los medios de a/V (UDP)</span><span class="sxs-lookup"><span data-stu-id="e8f28-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-497">Clientes</span><span class="sxs-lookup"><span data-stu-id="e8f28-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="e8f28-498">5061</span><span class="sxs-lookup"><span data-stu-id="e8f28-498">5061</span></span></p></td>
<td><p><span data-ttu-id="e8f28-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e8f28-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="e8f28-500">Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="e8f28-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-501">Clientes</span><span class="sxs-lookup"><span data-stu-id="e8f28-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="e8f28-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="e8f28-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="e8f28-503">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-504">Se usa para la transferencia de archivos entre clientes de Lync y clientes anteriores (clientes de Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 y Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="e8f28-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-505">Clientes</span><span class="sxs-lookup"><span data-stu-id="e8f28-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="e8f28-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="e8f28-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="e8f28-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="e8f28-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-508">Intervalo de puertos de audio (se requieren 20 puertos como mínimo)</span><span class="sxs-lookup"><span data-stu-id="e8f28-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-509">Clientes</span><span class="sxs-lookup"><span data-stu-id="e8f28-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="e8f28-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="e8f28-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="e8f28-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="e8f28-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-512">Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo)</span><span class="sxs-lookup"><span data-stu-id="e8f28-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-513">Clientes</span><span class="sxs-lookup"><span data-stu-id="e8f28-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="e8f28-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="e8f28-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="e8f28-515">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-516">Transferencias de archivos de punto a punto (para la transferencia de archivos de conferencia, los clientes usan PSOM).</span><span class="sxs-lookup"><span data-stu-id="e8f28-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f28-517">Clientes</span><span class="sxs-lookup"><span data-stu-id="e8f28-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="e8f28-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="e8f28-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="e8f28-519">TCP</span><span class="sxs-lookup"><span data-stu-id="e8f28-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-520">Uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e8f28-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f28-521">Teléfono de área común Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="e8f28-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="e8f28-522">Teléfono de escritorio Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="e8f28-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="e8f28-523">HP 4110 IP Phone (teléfono de área común)</span><span class="sxs-lookup"><span data-stu-id="e8f28-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="e8f28-524">HP 4120 IP Phone (teléfono de escritorio)</span><span class="sxs-lookup"><span data-stu-id="e8f28-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="e8f28-525">Teléfono de área común Polycom CX500 IP</span><span class="sxs-lookup"><span data-stu-id="e8f28-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="e8f28-526">Teléfono de escritorio Polycom CX600 IP</span><span class="sxs-lookup"><span data-stu-id="e8f28-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="e8f28-527">Teléfono de escritorio Polycom CX700 IP</span><span class="sxs-lookup"><span data-stu-id="e8f28-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="e8f28-528">Teléfono de conferencia Polycom CX3000 IP</span><span class="sxs-lookup"><span data-stu-id="e8f28-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="e8f28-529">67/68</span><span class="sxs-lookup"><span data-stu-id="e8f28-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="e8f28-530">DCHP</span><span class="sxs-lookup"><span data-stu-id="e8f28-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="e8f28-531">Usada por los dispositivos enumerados para buscar el certificado de Lync Server, el FQDN de aprovisionamiento y el FQDN del registrador.</span><span class="sxs-lookup"><span data-stu-id="e8f28-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e8f28-532">**\*** Para configurar los puertos específicos para estos tipos de medios, use el cmdlet CsConferencingConfiguration (los parámetros clientmediaportrangeenabled, ClientMediaPort y ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="e8f28-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8f28-533">Los clientes de set programs for Lync crean automáticamente las excepciones de firewall del sistema operativo necesarias en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="e8f28-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e8f28-534">Los puertos que se utilizan para el acceso de usuarios externos son necesarios en cualquier escenario en el que el cliente deba atravesar el firewall de la organización (por ejemplo, las comunicaciones o reuniones externas alojadas por otras organizaciones).</span><span class="sxs-lookup"><span data-stu-id="e8f28-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

