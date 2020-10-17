---
title: 'Lync Server 2013: puertos y protocolos para servidores internos'
description: 'Lync Server 2013: puertos y protocolos para servidores internos.'
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
ms.openlocfilehash: d7d8f12c78c5dec5caacaeb1156f4d228b7cd591
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566366"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="38de3-103">Puertos y protocolos para servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38de3-103">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38de3-104">_**Última modificación del tema:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="38de3-104">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="38de3-105">En esta sección se resumen los puertos y protocolos que usan los servidores, los equilibradores de carga y los clientes en una implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38de3-105">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="38de3-106">Los clientes de Lync y Communicator cuando participan en una comunicación de una a una, a menudo se denominan de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="38de3-106">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="38de3-107">Técnicamente, los dos clientes se comunican en una conversación de una a una, con la unidad de control multipunto (IMMCU) de mensajería instantánea en la parte central.</span><span class="sxs-lookup"><span data-stu-id="38de3-107">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="38de3-108">IMMCU es un componente del servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="38de3-108">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="38de3-109">La colocación de IMMCU en el flujo de trabajo de comunicación necesario permite el registro detallado de llamadas y otras características que permite el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="38de3-109">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="38de3-110">La comunicación es desde un puerto de origen dinámico en el cliente al puerto del servidor front-end TLS/TCP/5061 (asumiendo el uso de la seguridad de la capa de transporte recomendada).</span><span class="sxs-lookup"><span data-stu-id="38de3-110">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="38de3-111">Por diseño, la comunicación punto a punto (así como la mensajería instantánea de varios participantes) solo es posible cuando Lync Server y el IMMCU está activo y disponible.</span><span class="sxs-lookup"><span data-stu-id="38de3-111">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="38de3-112">Detalles de puerto y protocolo</span><span class="sxs-lookup"><span data-stu-id="38de3-112">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="38de3-113">Firewall de Windows debe estar en ejecución antes de iniciar los servicios de Lync Server en un servidor, ya que esto se debe a que Lync Server abre los puertos necesarios en el firewall.</span><span class="sxs-lookup"><span data-stu-id="38de3-113">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="38de3-114">Para obtener más información sobre la configuración del firewall para los componentes perimetrales, consulte [determine external a/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38de3-114">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="38de3-115">En la tabla siguiente se enumeran los puertos que debe abrir en cada rol del servidor interno.</span><span class="sxs-lookup"><span data-stu-id="38de3-115">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="38de3-116">Puertos de servidor obligatorios (por rol del servidor)</span><span class="sxs-lookup"><span data-stu-id="38de3-116">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="38de3-117">Rol de servidor</span><span class="sxs-lookup"><span data-stu-id="38de3-117">Server role</span></span></th>
<th><span data-ttu-id="38de3-118">Nombre del servicio</span><span class="sxs-lookup"><span data-stu-id="38de3-118">Service name</span></span></th>
<th><span data-ttu-id="38de3-119">Puerto</span><span class="sxs-lookup"><span data-stu-id="38de3-119">Port</span></span></th>
<th><span data-ttu-id="38de3-120">Protocolo</span><span class="sxs-lookup"><span data-stu-id="38de3-120">Protocol</span></span></th>
<th><span data-ttu-id="38de3-121">Notas</span><span class="sxs-lookup"><span data-stu-id="38de3-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38de3-122">Todos los servidores</span><span class="sxs-lookup"><span data-stu-id="38de3-122">All Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-123">Explorador SQL</span><span class="sxs-lookup"><span data-stu-id="38de3-123">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="38de3-124">1434</span><span class="sxs-lookup"><span data-stu-id="38de3-124">1434</span></span></p></td>
<td><p><span data-ttu-id="38de3-125">UDP</span><span class="sxs-lookup"><span data-stu-id="38de3-125">UDP</span></span></p></td>
<td><p><span data-ttu-id="38de3-126">Explorador SQL para la copia replicada local de la base de datos del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="38de3-126">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-127">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-127">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-128">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-128">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="38de3-129">5060</span><span class="sxs-lookup"><span data-stu-id="38de3-129">5060</span></span></p></td>
<td><p><span data-ttu-id="38de3-130">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-130">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-131">Opcionalmente lo usan los servidores Standard Edition y front-end para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="38de3-131">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-132">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-132">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-133">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-133">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="38de3-134">5061</span><span class="sxs-lookup"><span data-stu-id="38de3-134">5061</span></span></p></td>
<td><p><span data-ttu-id="38de3-135">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-135">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-p102">Lo usan los servidores Standard Edition y los grupos de servidores front-end para todas la comunicaciones SIP internas entre los servidores (MTLS), para las comunicaciones SIP entre el cliente y del servidor (TLS) y para las comunicaciones entre los servidores front-end y los servidores de mediación (MTLS). También se usa para las comunicaciones con el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="38de3-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-138">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-138">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-139">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-139">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="38de3-140">444</span><span class="sxs-lookup"><span data-stu-id="38de3-140">444</span></span></p></td>
<td><p><span data-ttu-id="38de3-141">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38de3-141">HTTPS</span></span></p>
<p><span data-ttu-id="38de3-142">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-142">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-143">Se usa para la comunicación HTTPS entre el foco (el componente de Lync Server que administra el estado de conferencia) y los servidores individuales.</span><span class="sxs-lookup"><span data-stu-id="38de3-143">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="38de3-144">Este puerto también se usa para la comunicación TCP entre las aplicaciones de sucursal con funciones de supervivencia y los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="38de3-144">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-145">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-145">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-146">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-146">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="38de3-147">135</span><span class="sxs-lookup"><span data-stu-id="38de3-147">135</span></span></p></td>
<td><p><span data-ttu-id="38de3-148">DCOM y llamada a procedimiento remoto (RPC)</span><span class="sxs-lookup"><span data-stu-id="38de3-148">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="38de3-149">Se usa para operaciones basadas en DCOM como la migración de los usuarios, la sincronización del replicador de usuarios y la sincronización de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="38de3-149">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-150">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-150">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-151">Servicio de conferencia de mensajería instantánea de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-151">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="38de3-152">5062</span><span class="sxs-lookup"><span data-stu-id="38de3-152">5062</span></span></p></td>
<td><p><span data-ttu-id="38de3-153">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-153">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-154">Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="38de3-154">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-155">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-155">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-156">Servicio de conferencia Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-156">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="38de3-157">8057</span><span class="sxs-lookup"><span data-stu-id="38de3-157">8057</span></span></p></td>
<td><p><span data-ttu-id="38de3-158">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-158">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-159">Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.</span><span class="sxs-lookup"><span data-stu-id="38de3-159">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-160">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-160">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-161">Servicio de compatibilidad con conferencias web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-161">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="38de3-162">8058</span><span class="sxs-lookup"><span data-stu-id="38de3-162">8058</span></span></p></td>
<td><p><span data-ttu-id="38de3-163">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-163">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-164">Se usa para escuchar las conexiones del modelo de objetos compartidos persistentes (PSOM) desde el cliente de Live Meeting y las versiones anteriores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38de3-164">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-165">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-165">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-166">Servicio de conferencia de audio y vídeo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-166">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="38de3-167">5063</span><span class="sxs-lookup"><span data-stu-id="38de3-167">5063</span></span></p></td>
<td><p><span data-ttu-id="38de3-168">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-168">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-169">Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="38de3-169">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-170">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-170">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-171">Servicio de conferencia de audio y vídeo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-171">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="38de3-172">57501-65535</span><span class="sxs-lookup"><span data-stu-id="38de3-172">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="38de3-173">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="38de3-173">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="38de3-174">Intervalo de puerto de medios usado para conferencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="38de3-174">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-175">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-176">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-176">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="38de3-177">80</span><span class="sxs-lookup"><span data-stu-id="38de3-177">80</span></span></p></td>
<td><p><span data-ttu-id="38de3-178">HTTP</span><span class="sxs-lookup"><span data-stu-id="38de3-178">HTTP</span></span></p></td>
<td><p><span data-ttu-id="38de3-179">Se usa para la comunicación entre los servidores front-end y los FQDN (direcciones URL usadas por los componentes web IIS) cuando no se usa HTTPS.</span><span class="sxs-lookup"><span data-stu-id="38de3-179">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-180">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-180">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-181">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-181">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="38de3-182">443</span><span class="sxs-lookup"><span data-stu-id="38de3-182">443</span></span></p></td>
<td><p><span data-ttu-id="38de3-183">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38de3-183">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="38de3-184">Se usa para la comunicación entre los servidores front-end y los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS).</span><span class="sxs-lookup"><span data-stu-id="38de3-184">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-185">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-185">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-186">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-186">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="38de3-187">8080</span><span class="sxs-lookup"><span data-stu-id="38de3-187">8080</span></span></p></td>
<td><p><span data-ttu-id="38de3-188">TCP y HTTP</span><span class="sxs-lookup"><span data-stu-id="38de3-188">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="38de3-189">Lo usan los componentes Web para el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="38de3-189">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-190">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-190">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-191">Componente del servidor Web</span><span class="sxs-lookup"><span data-stu-id="38de3-191">Web server component</span></span></p></td>
<td><p><span data-ttu-id="38de3-192">4443</span><span class="sxs-lookup"><span data-stu-id="38de3-192">4443</span></span></p></td>
<td><p><span data-ttu-id="38de3-193">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38de3-193">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="38de3-194">HTTPS (desde proxy inverso) y comunicaciones entre grupos de servidores front-end de HTTPS para el inicio de sesión con detección automática.</span><span class="sxs-lookup"><span data-stu-id="38de3-194">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-195">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-195">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-196">Componente del servidor Web</span><span class="sxs-lookup"><span data-stu-id="38de3-196">Web server component</span></span></p></td>
<td><p><span data-ttu-id="38de3-197">8060</span><span class="sxs-lookup"><span data-stu-id="38de3-197">8060</span></span></p></td>
<td><p><span data-ttu-id="38de3-198">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-198">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-199">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-199">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-200">Componente del servidor Web</span><span class="sxs-lookup"><span data-stu-id="38de3-200">Web server component</span></span></p></td>
<td><p><span data-ttu-id="38de3-201">8061</span><span class="sxs-lookup"><span data-stu-id="38de3-201">8061</span></span></p></td>
<td><p><span data-ttu-id="38de3-202">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-202">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-203">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-203">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-204">Componente de servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="38de3-204">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="38de3-205">5086</span><span class="sxs-lookup"><span data-stu-id="38de3-205">5086</span></span></p></td>
<td><p><span data-ttu-id="38de3-206">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-206">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-207">Puerto SIP usado por los procesos internos de Mobility Services</span><span class="sxs-lookup"><span data-stu-id="38de3-207">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-208">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-208">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-209">Componente de servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="38de3-209">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="38de3-210">5087</span><span class="sxs-lookup"><span data-stu-id="38de3-210">5087</span></span></p></td>
<td><p><span data-ttu-id="38de3-211">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-211">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-212">Puerto SIP usado por los procesos internos de Mobility Services</span><span class="sxs-lookup"><span data-stu-id="38de3-212">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-213">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-213">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-214">Componente de servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="38de3-214">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="38de3-215">443</span><span class="sxs-lookup"><span data-stu-id="38de3-215">443</span></span></p></td>
<td><p><span data-ttu-id="38de3-216">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38de3-216">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-217">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-217">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-218">Servicio de operador de conferencia de Lync Server (Conferencia de acceso telefónico local)</span><span class="sxs-lookup"><span data-stu-id="38de3-218">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="38de3-219">5064</span><span class="sxs-lookup"><span data-stu-id="38de3-219">5064</span></span></p></td>
<td><p><span data-ttu-id="38de3-220">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-220">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-221">Se usa para las solicitudes SIP entrantes de las conferencias telefónicas.</span><span class="sxs-lookup"><span data-stu-id="38de3-221">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-222">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-222">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-223">Servicio de operador de conferencia de Lync Server (Conferencia de acceso telefónico local)</span><span class="sxs-lookup"><span data-stu-id="38de3-223">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="38de3-224">5072</span><span class="sxs-lookup"><span data-stu-id="38de3-224">5072</span></span></p></td>
<td><p><span data-ttu-id="38de3-225">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-225">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-226">Se usa para las solicitudes SIP entrantes para el operador (llamadas de conferencia de acceso telefónico local).</span><span class="sxs-lookup"><span data-stu-id="38de3-226">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-227">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="38de3-227">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="38de3-228">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-228">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="38de3-229">5070</span><span class="sxs-lookup"><span data-stu-id="38de3-229">5070</span></span></p></td>
<td><p><span data-ttu-id="38de3-230">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-230">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-231">Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="38de3-231">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-232">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="38de3-232">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="38de3-233">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-233">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="38de3-234">5067</span><span class="sxs-lookup"><span data-stu-id="38de3-234">5067</span></span></p></td>
<td><p><span data-ttu-id="38de3-235">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-235">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-236">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="38de3-236">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-237">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="38de3-237">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="38de3-238">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-238">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="38de3-239">5068</span><span class="sxs-lookup"><span data-stu-id="38de3-239">5068</span></span></p></td>
<td><p><span data-ttu-id="38de3-240">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-240">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-241">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="38de3-241">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-242">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="38de3-242">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="38de3-243">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-243">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="38de3-244">5081</span><span class="sxs-lookup"><span data-stu-id="38de3-244">5081</span></span></p></td>
<td><p><span data-ttu-id="38de3-245">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-245">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-246">Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="38de3-246">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-247">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="38de3-247">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="38de3-248">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-248">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="38de3-249">5082</span><span class="sxs-lookup"><span data-stu-id="38de3-249">5082</span></span></p></td>
<td><p><span data-ttu-id="38de3-250">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-250">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-251">Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="38de3-251">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-252">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-252">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-253">Servicio de uso compartido de aplicaciones de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-253">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="38de3-254">5065</span><span class="sxs-lookup"><span data-stu-id="38de3-254">5065</span></span></p></td>
<td><p><span data-ttu-id="38de3-255">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-255">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-256">Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="38de3-256">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-257">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-257">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-258">Servicio de uso compartido de aplicaciones de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-258">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="38de3-259">49152-65535</span><span class="sxs-lookup"><span data-stu-id="38de3-259">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="38de3-260">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-260">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-261">Intervalo de puerto de medios usado para compartir aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="38de3-261">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-262">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-262">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-263">Servicio de anuncio de conferencia de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-263">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="38de3-264">5073</span><span class="sxs-lookup"><span data-stu-id="38de3-264">5073</span></span></p></td>
<td><p><span data-ttu-id="38de3-265">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-265">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-266">Se usa para las solicitudes SIP entrantes para el servicio de anuncio de conferencia de Lync Server (es decir, para las conferencias de acceso telefónico local).</span><span class="sxs-lookup"><span data-stu-id="38de3-266">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-267">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-267">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-268">Servicio de estacionamiento de llamadas de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-268">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="38de3-269">5075</span><span class="sxs-lookup"><span data-stu-id="38de3-269">5075</span></span></p></td>
<td><p><span data-ttu-id="38de3-270">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-270">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-271">Se usa para las solicitudes SIP entrantes de la aplicación Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="38de3-271">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-272">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-272">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-273">Servicio de prueba de audio de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-273">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="38de3-274">5076</span><span class="sxs-lookup"><span data-stu-id="38de3-274">5076</span></span></p></td>
<td><p><span data-ttu-id="38de3-275">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-275">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-276">Se usa para las solicitudes SIP entrantes del servicio de prueba de audio.</span><span class="sxs-lookup"><span data-stu-id="38de3-276">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-277">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-277">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-278">No aplicable</span><span class="sxs-lookup"><span data-stu-id="38de3-278">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="38de3-279">5066</span><span class="sxs-lookup"><span data-stu-id="38de3-279">5066</span></span></p></td>
<td><p><span data-ttu-id="38de3-280">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-280">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-281">Se usa para la puerta de enlace 9-1-1 mejorado (E9-1-1) saliente</span><span class="sxs-lookup"><span data-stu-id="38de3-281">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-282">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-282">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-283">Servicio de grupo de respuesta de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-283">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="38de3-284">5071</span><span class="sxs-lookup"><span data-stu-id="38de3-284">5071</span></span></p></td>
<td><p><span data-ttu-id="38de3-285">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-285">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-286">Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="38de3-286">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-287">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-287">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-288">Servicio de grupo de respuesta de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-288">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="38de3-289">8404</span><span class="sxs-lookup"><span data-stu-id="38de3-289">8404</span></span></p></td>
<td><p><span data-ttu-id="38de3-290">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-290">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-291">Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="38de3-291">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-292">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-292">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-293">Servicio de directiva de ancho de banda de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-293">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="38de3-294">5080</span><span class="sxs-lookup"><span data-stu-id="38de3-294">5080</span></span></p></td>
<td><p><span data-ttu-id="38de3-295">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-295">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-296">Lo usa el servicio de directiva de ancho de banda del tráfico TURN perimetral A/V para el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="38de3-296">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-297">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-297">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-298">Servicio de directiva de ancho de banda de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-298">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="38de3-299">448</span><span class="sxs-lookup"><span data-stu-id="38de3-299">448</span></span></p></td>
<td><p><span data-ttu-id="38de3-300">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-300">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-301">Se usa para el control de admisión de llamadas por el servicio de directiva de ancho de banda de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38de3-301">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-302">Servidores front-end donde reside el almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="38de3-302">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="38de3-303">Agente de replicador maestro de Microsoft Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-303">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="38de3-304">445</span><span class="sxs-lookup"><span data-stu-id="38de3-304">445</span></span></p></td>
<td><p><span data-ttu-id="38de3-305">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-305">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-306">Se usa para insertar los datos de configuración desde el almacén de administración central en los servidores que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38de3-306">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-307">Todos los servidores</span><span class="sxs-lookup"><span data-stu-id="38de3-307">All Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-308">Explorador SQL</span><span class="sxs-lookup"><span data-stu-id="38de3-308">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="38de3-309">1434</span><span class="sxs-lookup"><span data-stu-id="38de3-309">1434</span></span></p></td>
<td><p><span data-ttu-id="38de3-310">UDP</span><span class="sxs-lookup"><span data-stu-id="38de3-310">UDP</span></span></p></td>
<td><p><span data-ttu-id="38de3-311">Explorador SQL para la copia replicada local de los datos del almacén de administración central en la instancia local de SQL Server</span><span class="sxs-lookup"><span data-stu-id="38de3-311">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-312">Todos los usuarios internos</span><span class="sxs-lookup"><span data-stu-id="38de3-312">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-313">Varios</span><span class="sxs-lookup"><span data-stu-id="38de3-313">Various</span></span></p></td>
<td><p><span data-ttu-id="38de3-314">49152-57500</span><span class="sxs-lookup"><span data-stu-id="38de3-314">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="38de3-315">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="38de3-315">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="38de3-316">El intervalo de puerto de medios se usa para audioconferencias en todos los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="38de3-316">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="38de3-317">Usada por todos los servidores que terminan audio: servidores front-end (para el servicio de operador de conferencia de Lync Server, el servicio de anuncio de conferencia de Lync Server y el servicio de conferencia de audio y vídeo de Lync Server) y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="38de3-317">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-318">Servidores de Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="38de3-318">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38de3-319">443</span><span class="sxs-lookup"><span data-stu-id="38de3-319">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38de3-320">Se usa en Lync Server 2013 para conectarse a Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="38de3-320">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-321">Reparto</span><span class="sxs-lookup"><span data-stu-id="38de3-321">Directors</span></span></p></td>
<td><p><span data-ttu-id="38de3-322">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-322">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="38de3-323">5060</span><span class="sxs-lookup"><span data-stu-id="38de3-323">5060</span></span></p></td>
<td><p><span data-ttu-id="38de3-324">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-324">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-325">Se usa opcionalmente para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="38de3-325">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-326">Reparto</span><span class="sxs-lookup"><span data-stu-id="38de3-326">Directors</span></span></p></td>
<td><p><span data-ttu-id="38de3-327">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-327">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="38de3-328">444</span><span class="sxs-lookup"><span data-stu-id="38de3-328">444</span></span></p></td>
<td><p><span data-ttu-id="38de3-329">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38de3-329">HTTPS</span></span></p>
<p><span data-ttu-id="38de3-330">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-330">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-331">Comunicación entre servidores front-end y director.</span><span class="sxs-lookup"><span data-stu-id="38de3-331">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="38de3-332">Además, la publicación de certificados de cliente (para los servidores front-end) o la validación si ya se ha publicado el certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="38de3-332">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-333">Reparto</span><span class="sxs-lookup"><span data-stu-id="38de3-333">Directors</span></span></p></td>
<td><p><span data-ttu-id="38de3-334">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-334">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="38de3-335">80</span><span class="sxs-lookup"><span data-stu-id="38de3-335">80</span></span></p></td>
<td><p><span data-ttu-id="38de3-336">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-336">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-p105">Se usa para la comunicación inicial desde los directores a los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS). En condiciones normales, cambiará a tráfico HTTPS usando el puerto 443 y el tipo de protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="38de3-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-339">Reparto</span><span class="sxs-lookup"><span data-stu-id="38de3-339">Directors</span></span></p></td>
<td><p><span data-ttu-id="38de3-340">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-340">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="38de3-341">443</span><span class="sxs-lookup"><span data-stu-id="38de3-341">443</span></span></p></td>
<td><p><span data-ttu-id="38de3-342">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38de3-342">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="38de3-343">Se usa para la comunicación desde los directores a los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS).</span><span class="sxs-lookup"><span data-stu-id="38de3-343">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-344">Reparto</span><span class="sxs-lookup"><span data-stu-id="38de3-344">Directors</span></span></p></td>
<td><p><span data-ttu-id="38de3-345">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-345">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="38de3-346">5061</span><span class="sxs-lookup"><span data-stu-id="38de3-346">5061</span></span></p></td>
<td><p><span data-ttu-id="38de3-347">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-347">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-348">Se usa para comunicaciones internas entre servidores y para conexiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="38de3-348">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-349">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="38de3-349">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-350">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-350">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="38de3-351">5070</span><span class="sxs-lookup"><span data-stu-id="38de3-351">5070</span></span></p></td>
<td><p><span data-ttu-id="38de3-352">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-352">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-353">Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="38de3-353">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-354">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="38de3-354">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-355">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-355">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="38de3-356">5067</span><span class="sxs-lookup"><span data-stu-id="38de3-356">5067</span></span></p></td>
<td><p><span data-ttu-id="38de3-357">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-357">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-358">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="38de3-358">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-359">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="38de3-359">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-360">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-360">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="38de3-361">5068</span><span class="sxs-lookup"><span data-stu-id="38de3-361">5068</span></span></p></td>
<td><p><span data-ttu-id="38de3-362">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-362">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-363">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="38de3-363">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-364">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="38de3-364">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="38de3-365">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38de3-365">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="38de3-366">5070</span><span class="sxs-lookup"><span data-stu-id="38de3-366">5070</span></span></p></td>
<td><p><span data-ttu-id="38de3-367">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-367">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-368">Se usa para solicitudes SIP desde los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="38de3-368">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-369">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="38de3-369">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="38de3-370">SIP de chat persistente</span><span class="sxs-lookup"><span data-stu-id="38de3-370">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="38de3-371">5041</span><span class="sxs-lookup"><span data-stu-id="38de3-371">5041</span></span></p></td>
<td><p><span data-ttu-id="38de3-372">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-372">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-373">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="38de3-373">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="38de3-374">Chat persistente Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="38de3-374">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="38de3-375">881</span><span class="sxs-lookup"><span data-stu-id="38de3-375">881</span></span></p></td>
<td><p><span data-ttu-id="38de3-376">TCP (TLS) y TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-376">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-377">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="38de3-377">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="38de3-378">Servicio de transferencia de archivos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="38de3-378">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="38de3-379">443</span><span class="sxs-lookup"><span data-stu-id="38de3-379">443</span></span></p></td>
<td><p><span data-ttu-id="38de3-380">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-380">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="38de3-381">Algunos escenarios de control remoto de llamadas requieren una conexión entre el servidor front-end o el director y la PBX.</span><span class="sxs-lookup"><span data-stu-id="38de3-381">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="38de3-382">Aunque Lync Server ya no usa el puerto TCP 5060, durante la implementación de control remoto de llamadas, se crea una configuración de servidor de confianza, que asocia el FQDN del servidor de línea RCC con el puerto TCP que el director o el servidor front-end usará para conectarse al sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="38de3-382">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="38de3-383">Para obtener más información, consulte el cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38de3-383">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="38de3-384">Para los grupos de servidores que solo usan equilibrio de carga de hardware (no equilibrio de carga de DNS), en la siguiente tabla se muestran los puertos que necesitan para abrir los equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="38de3-384">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="38de3-385">Puertos del equilibrador de carga de hardware si solo usa equilibrio de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="38de3-385">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38de3-386">Equilibrador de carga</span><span class="sxs-lookup"><span data-stu-id="38de3-386">Load Balancer</span></span></th>
<th><span data-ttu-id="38de3-387">Puerto</span><span class="sxs-lookup"><span data-stu-id="38de3-387">Port</span></span></th>
<th><span data-ttu-id="38de3-388">Protocolo</span><span class="sxs-lookup"><span data-stu-id="38de3-388">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38de3-389">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-389">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-390">5061</span><span class="sxs-lookup"><span data-stu-id="38de3-390">5061</span></span></p></td>
<td><p><span data-ttu-id="38de3-391">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-391">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-392">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-392">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-393">444</span><span class="sxs-lookup"><span data-stu-id="38de3-393">444</span></span></p></td>
<td><p><span data-ttu-id="38de3-394">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38de3-394">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-395">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-395">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-396">135</span><span class="sxs-lookup"><span data-stu-id="38de3-396">135</span></span></p></td>
<td><p><span data-ttu-id="38de3-397">DCOM y llamada a procedimiento remoto (RPC)</span><span class="sxs-lookup"><span data-stu-id="38de3-397">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-398">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-398">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-399">80</span><span class="sxs-lookup"><span data-stu-id="38de3-399">80</span></span></p></td>
<td><p><span data-ttu-id="38de3-400">HTTP</span><span class="sxs-lookup"><span data-stu-id="38de3-400">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-401">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-401">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-402">8080</span><span class="sxs-lookup"><span data-stu-id="38de3-402">8080</span></span></p></td>
<td><p><span data-ttu-id="38de3-403">TCP - Recuperación cliente y dispositivo del certificado raíz del servidor de front-end – clientes y dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="38de3-403">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-404">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-404">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-405">443</span><span class="sxs-lookup"><span data-stu-id="38de3-405">443</span></span></p></td>
<td><p><span data-ttu-id="38de3-406">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38de3-406">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-407">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-407">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-408">4443</span><span class="sxs-lookup"><span data-stu-id="38de3-408">4443</span></span></p></td>
<td><p><span data-ttu-id="38de3-409">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="38de3-409">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-410">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-410">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-411">5072</span><span class="sxs-lookup"><span data-stu-id="38de3-411">5072</span></span></p></td>
<td><p><span data-ttu-id="38de3-412">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-412">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-413">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-413">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-414">5073</span><span class="sxs-lookup"><span data-stu-id="38de3-414">5073</span></span></p></td>
<td><p><span data-ttu-id="38de3-415">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-415">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-416">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-416">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-417">5075</span><span class="sxs-lookup"><span data-stu-id="38de3-417">5075</span></span></p></td>
<td><p><span data-ttu-id="38de3-418">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-418">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-419">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-419">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-420">5076</span><span class="sxs-lookup"><span data-stu-id="38de3-420">5076</span></span></p></td>
<td><p><span data-ttu-id="38de3-421">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-421">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-422">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-422">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-423">5071</span><span class="sxs-lookup"><span data-stu-id="38de3-423">5071</span></span></p></td>
<td><p><span data-ttu-id="38de3-424">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-424">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-425">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-425">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-426">5080</span><span class="sxs-lookup"><span data-stu-id="38de3-426">5080</span></span></p></td>
<td><p><span data-ttu-id="38de3-427">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-427">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-428">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-428">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-429">448</span><span class="sxs-lookup"><span data-stu-id="38de3-429">448</span></span></p></td>
<td><p><span data-ttu-id="38de3-430">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-430">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-431">Equilibrador de carga del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="38de3-431">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-432">5070</span><span class="sxs-lookup"><span data-stu-id="38de3-432">5070</span></span></p></td>
<td><p><span data-ttu-id="38de3-433">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-433">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-434">Equilibrador de carga del servidor front-end (si el grupo también ejecuta el servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="38de3-434">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="38de3-435">5070</span><span class="sxs-lookup"><span data-stu-id="38de3-435">5070</span></span></p></td>
<td><p><span data-ttu-id="38de3-436">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-436">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-437">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="38de3-437">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-438">443</span><span class="sxs-lookup"><span data-stu-id="38de3-438">443</span></span></p></td>
<td><p><span data-ttu-id="38de3-439">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38de3-439">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-440">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="38de3-440">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-441">444</span><span class="sxs-lookup"><span data-stu-id="38de3-441">444</span></span></p></td>
<td><p><span data-ttu-id="38de3-442">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38de3-442">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-443">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="38de3-443">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-444">5061</span><span class="sxs-lookup"><span data-stu-id="38de3-444">5061</span></span></p></td>
<td><p><span data-ttu-id="38de3-445">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-445">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-446">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="38de3-446">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-447">4443</span><span class="sxs-lookup"><span data-stu-id="38de3-447">4443</span></span></p></td>
<td><p><span data-ttu-id="38de3-448">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="38de3-448">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38de3-p107">Los grupos de servidores front-end y de directores que usan equilibrio de carga de DNS también deben tener implementado un equilibrador de carga de hardware. En la siguiente tabla se muestran los puertos que se deben abrir en estos equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="38de3-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="38de3-451">Puertos del equilibrador de carga de hardware si usa equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="38de3-451">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38de3-452">Equilibrador de carga</span><span class="sxs-lookup"><span data-stu-id="38de3-452">Load Balancer</span></span></th>
<th><span data-ttu-id="38de3-453">Puerto</span><span class="sxs-lookup"><span data-stu-id="38de3-453">Port</span></span></th>
<th><span data-ttu-id="38de3-454">Protocolo</span><span class="sxs-lookup"><span data-stu-id="38de3-454">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38de3-455">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-455">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-456">80</span><span class="sxs-lookup"><span data-stu-id="38de3-456">80</span></span></p></td>
<td><p><span data-ttu-id="38de3-457">HTTP</span><span class="sxs-lookup"><span data-stu-id="38de3-457">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-458">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-458">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-459">443</span><span class="sxs-lookup"><span data-stu-id="38de3-459">443</span></span></p></td>
<td><p><span data-ttu-id="38de3-460">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38de3-460">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-461">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-461">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-462">8080</span><span class="sxs-lookup"><span data-stu-id="38de3-462">8080</span></span></p></td>
<td><p><span data-ttu-id="38de3-463">TCP - Recuperación cliente y dispositivo del certificado raíz del servidor de front-end – clientes y dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="38de3-463">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-464">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="38de3-464">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-465">4443</span><span class="sxs-lookup"><span data-stu-id="38de3-465">4443</span></span></p></td>
<td><p><span data-ttu-id="38de3-466">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="38de3-466">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-467">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="38de3-467">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-468">443</span><span class="sxs-lookup"><span data-stu-id="38de3-468">443</span></span></p></td>
<td><p><span data-ttu-id="38de3-469">HTTPS</span><span class="sxs-lookup"><span data-stu-id="38de3-469">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-470">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="38de3-470">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="38de3-471">4443</span><span class="sxs-lookup"><span data-stu-id="38de3-471">4443</span></span></p></td>
<td><p><span data-ttu-id="38de3-472">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="38de3-472">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="38de3-473">Puertos de cliente requeridos</span><span class="sxs-lookup"><span data-stu-id="38de3-473">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38de3-474">Componente</span><span class="sxs-lookup"><span data-stu-id="38de3-474">Component</span></span></th>
<th><span data-ttu-id="38de3-475">Puerto</span><span class="sxs-lookup"><span data-stu-id="38de3-475">Port</span></span></th>
<th><span data-ttu-id="38de3-476">Protocolo</span><span class="sxs-lookup"><span data-stu-id="38de3-476">Protocol</span></span></th>
<th><span data-ttu-id="38de3-477">Notas</span><span class="sxs-lookup"><span data-stu-id="38de3-477">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38de3-478">Clientes</span><span class="sxs-lookup"><span data-stu-id="38de3-478">Clients</span></span></p></td>
<td><p><span data-ttu-id="38de3-479">67/68</span><span class="sxs-lookup"><span data-stu-id="38de3-479">67/68</span></span></p></td>
<td><p><span data-ttu-id="38de3-480">DCHP</span><span class="sxs-lookup"><span data-stu-id="38de3-480">DHCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-481">Lo usa Lync Server para buscar el FQDN del registrador (es decir, si se produce un error en el SRV de DNS y no se configura la configuración manual).</span><span class="sxs-lookup"><span data-stu-id="38de3-481">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-482">Clientes</span><span class="sxs-lookup"><span data-stu-id="38de3-482">Clients</span></span></p></td>
<td><p><span data-ttu-id="38de3-483">443</span><span class="sxs-lookup"><span data-stu-id="38de3-483">443</span></span></p></td>
<td><p><span data-ttu-id="38de3-484">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-484">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-485">Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="38de3-485">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-486">Clientes</span><span class="sxs-lookup"><span data-stu-id="38de3-486">Clients</span></span></p></td>
<td><p><span data-ttu-id="38de3-487">443</span><span class="sxs-lookup"><span data-stu-id="38de3-487">443</span></span></p></td>
<td><p><span data-ttu-id="38de3-488">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-488">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-489">Se usa para el acceso de usuarios externos a las sesiones de conferencia web.</span><span class="sxs-lookup"><span data-stu-id="38de3-489">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-490">Clientes</span><span class="sxs-lookup"><span data-stu-id="38de3-490">Clients</span></span></p></td>
<td><p><span data-ttu-id="38de3-491">443</span><span class="sxs-lookup"><span data-stu-id="38de3-491">443</span></span></p></td>
<td><p><span data-ttu-id="38de3-492">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="38de3-492">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="38de3-493">Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP)</span><span class="sxs-lookup"><span data-stu-id="38de3-493">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-494">Clientes</span><span class="sxs-lookup"><span data-stu-id="38de3-494">Clients</span></span></p></td>
<td><p><span data-ttu-id="38de3-495">3478</span><span class="sxs-lookup"><span data-stu-id="38de3-495">3478</span></span></p></td>
<td><p><span data-ttu-id="38de3-496">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="38de3-496">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="38de3-497">Se usa para el acceso de usuarios externos a las sesiones y los medios de a/V (UDP)</span><span class="sxs-lookup"><span data-stu-id="38de3-497">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-498">Clientes</span><span class="sxs-lookup"><span data-stu-id="38de3-498">Clients</span></span></p></td>
<td><p><span data-ttu-id="38de3-499">5061</span><span class="sxs-lookup"><span data-stu-id="38de3-499">5061</span></span></p></td>
<td><p><span data-ttu-id="38de3-500">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38de3-500">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="38de3-501">Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="38de3-501">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-502">Clientes</span><span class="sxs-lookup"><span data-stu-id="38de3-502">Clients</span></span></p></td>
<td><p><span data-ttu-id="38de3-503">6891-6901</span><span class="sxs-lookup"><span data-stu-id="38de3-503">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="38de3-504">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-504">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-505">Se usa para la transferencia de archivos entre clientes de Lync y clientes anteriores (clientes de Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 y Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="38de3-505">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-506">Clientes</span><span class="sxs-lookup"><span data-stu-id="38de3-506">Clients</span></span></p></td>
<td><p><span data-ttu-id="38de3-507">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="38de3-507">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="38de3-508">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="38de3-508">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="38de3-509">Intervalo de puertos de audio (se requieren 20 puertos como mínimo)</span><span class="sxs-lookup"><span data-stu-id="38de3-509">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-510">Clientes</span><span class="sxs-lookup"><span data-stu-id="38de3-510">Clients</span></span></p></td>
<td><p><span data-ttu-id="38de3-511">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="38de3-511">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="38de3-512">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="38de3-512">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="38de3-513">Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo)</span><span class="sxs-lookup"><span data-stu-id="38de3-513">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-514">Clientes</span><span class="sxs-lookup"><span data-stu-id="38de3-514">Clients</span></span></p></td>
<td><p><span data-ttu-id="38de3-515">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="38de3-515">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="38de3-516">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-516">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-517">Transferencias de archivos de punto a punto (para la transferencia de archivos de conferencia, los clientes usan PSOM).</span><span class="sxs-lookup"><span data-stu-id="38de3-517">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38de3-518">Clientes</span><span class="sxs-lookup"><span data-stu-id="38de3-518">Clients</span></span></p></td>
<td><p><span data-ttu-id="38de3-519">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="38de3-519">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="38de3-520">TCP</span><span class="sxs-lookup"><span data-stu-id="38de3-520">TCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-521">Uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="38de3-521">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38de3-522">Teléfono de área común Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="38de3-522">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="38de3-523">Teléfono de escritorio Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="38de3-523">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="38de3-524">HP 4110 IP Phone (teléfono de área común)</span><span class="sxs-lookup"><span data-stu-id="38de3-524">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="38de3-525">HP 4120 IP Phone (teléfono de escritorio)</span><span class="sxs-lookup"><span data-stu-id="38de3-525">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="38de3-526">Teléfono de área común Polycom CX500 IP</span><span class="sxs-lookup"><span data-stu-id="38de3-526">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="38de3-527">Teléfono de escritorio Polycom CX600 IP</span><span class="sxs-lookup"><span data-stu-id="38de3-527">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="38de3-528">Teléfono de escritorio Polycom CX700 IP</span><span class="sxs-lookup"><span data-stu-id="38de3-528">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="38de3-529">Teléfono de conferencia Polycom CX3000 IP</span><span class="sxs-lookup"><span data-stu-id="38de3-529">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="38de3-530">67/68</span><span class="sxs-lookup"><span data-stu-id="38de3-530">67/68</span></span></p></td>
<td><p><span data-ttu-id="38de3-531">DCHP</span><span class="sxs-lookup"><span data-stu-id="38de3-531">DHCP</span></span></p></td>
<td><p><span data-ttu-id="38de3-532">Usada por los dispositivos enumerados para buscar el certificado de Lync Server, el FQDN de aprovisionamiento y el FQDN del registrador.</span><span class="sxs-lookup"><span data-stu-id="38de3-532">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38de3-533">**\*** Para configurar los puertos específicos para estos tipos de medios, use el cmdlet CsConferencingConfiguration (los parámetros clientmediaportrangeenabled, ClientMediaPort y ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="38de3-533">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="38de3-534">Los clientes de set programs for Lync crean automáticamente las excepciones de firewall del sistema operativo necesarias en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="38de3-534">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="38de3-535">Los puertos que se utilizan para el acceso de usuarios externos son necesarios en cualquier escenario en el que el cliente deba atravesar el firewall de la organización (por ejemplo, las comunicaciones o reuniones externas alojadas por otras organizaciones).</span><span class="sxs-lookup"><span data-stu-id="38de3-535">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

