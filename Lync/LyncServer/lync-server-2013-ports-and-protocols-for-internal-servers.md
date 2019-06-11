---
title: 'Lync Server 2013: puertos y protocolos para servidores internos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026843216e433ebea120384209ed90f38be3437b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="37234-102">Puertos y protocolos para servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37234-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37234-103">_**Última modificación del tema:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="37234-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="37234-104">En esta sección se resumen los puertos y protocolos usados por servidores, equilibradores de carga y clientes en una implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37234-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="37234-105">Los clientes de Lync y Communicator, cuando participan en una sola comunicación, se suelen denominar de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="37234-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="37234-106">Técnicamente, los dos clientes se comunican en una conversación de una en una, con la unidad de control multipunto de mensajería instantánea (IMMCU) en el medio.</span><span class="sxs-lookup"><span data-stu-id="37234-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="37234-107">El IMMCU es un componente de servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="37234-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="37234-108">La colocación de IMMCU en el flujo de trabajo de comunicaciones requerido permite la grabación de detalles de llamadas y otras características que permite el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="37234-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="37234-109">La comunicación es de un puerto de origen dinámico en el cliente al puerto del servidor front-end TLS/TCP/5061 (asumiendo el uso de la seguridad de la capa de transporte recomendada).</span><span class="sxs-lookup"><span data-stu-id="37234-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="37234-110">Por diseño, la comunicación de punto a punto (así como la de mensajería instantánea de varios participantes) solo es posible cuando Lync Server y IMMCU está activo y disponible.</span><span class="sxs-lookup"><span data-stu-id="37234-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="37234-111">Detalles de protocolo y puerto</span><span class="sxs-lookup"><span data-stu-id="37234-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37234-112">El Firewall de Windows debe estar ejecutándose antes de iniciar los servicios de Lync Server en un servidor, porque es cuando Lync Server abre los puertos necesarios en el firewall.</span><span class="sxs-lookup"><span data-stu-id="37234-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="37234-113">Para obtener más información sobre la configuración del firewall para los componentes de Edge, consulte [determinar el firewall externo a/V y los requisitos de puerto para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37234-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="37234-114">En la tabla siguiente se enumeran los puertos que debe abrir en cada rol del servidor interno.</span><span class="sxs-lookup"><span data-stu-id="37234-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="37234-115">Puertos de servidor obligatorios (por rol de servidor)</span><span class="sxs-lookup"><span data-stu-id="37234-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="37234-116">Rol de servidor</span><span class="sxs-lookup"><span data-stu-id="37234-116">Server role</span></span></th>
<th><span data-ttu-id="37234-117">Nombre de servicio</span><span class="sxs-lookup"><span data-stu-id="37234-117">Service name</span></span></th>
<th><span data-ttu-id="37234-118">Puerto</span><span class="sxs-lookup"><span data-stu-id="37234-118">Port</span></span></th>
<th><span data-ttu-id="37234-119">Protocolo</span><span class="sxs-lookup"><span data-stu-id="37234-119">Protocol</span></span></th>
<th><span data-ttu-id="37234-120">Notas</span><span class="sxs-lookup"><span data-stu-id="37234-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37234-121">Todos los servidores</span><span class="sxs-lookup"><span data-stu-id="37234-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-122">Explorador SQL</span><span class="sxs-lookup"><span data-stu-id="37234-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="37234-123">1434</span><span class="sxs-lookup"><span data-stu-id="37234-123">1434</span></span></p></td>
<td><p><span data-ttu-id="37234-124">UDP</span><span class="sxs-lookup"><span data-stu-id="37234-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="37234-125">Explorador SQL para la copia replicada local de la base de datos del almacén central de administración.</span><span class="sxs-lookup"><span data-stu-id="37234-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-126">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-127">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="37234-128">5060</span><span class="sxs-lookup"><span data-stu-id="37234-128">5060</span></span></p></td>
<td><p><span data-ttu-id="37234-129">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-130">Opcionalmente lo usan los servidores Standard Edition y front-end para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="37234-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-131">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-132">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="37234-133">5061</span><span class="sxs-lookup"><span data-stu-id="37234-133">5061</span></span></p></td>
<td><p><span data-ttu-id="37234-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="37234-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-135">Lo usan los servidores Standard Edition y los grupos de servidores front-end para todas las comunicaciones SIP internas entre los servidores (MTLS), para las comunicaciones SIP entre el cliente y el servidor (TLS) y para las comunicaciones SIP entre los servidores front-end y los servidores de mediación (MTLS).</span><span class="sxs-lookup"><span data-stu-id="37234-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="37234-136">También se usa para comunicaciones con el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="37234-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-137">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-138">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="37234-139">444</span><span class="sxs-lookup"><span data-stu-id="37234-139">444</span></span></p></td>
<td><p><span data-ttu-id="37234-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="37234-140">HTTPS</span></span></p>
<p><span data-ttu-id="37234-141">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-142">Se usa para la comunicación HTTPS entre el foco (el componente de Lync Server que administra el estado de la Conferencia) y los servidores individuales.</span><span class="sxs-lookup"><span data-stu-id="37234-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="37234-143">Este puerto también se usa para la comunicación TCP entre los equipos de las sucursales y los servidores de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="37234-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-144">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-145">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="37234-146">135</span><span class="sxs-lookup"><span data-stu-id="37234-146">135</span></span></p></td>
<td><p><span data-ttu-id="37234-147">DCOM y llamada a procedimiento remoto (RPC)</span><span class="sxs-lookup"><span data-stu-id="37234-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="37234-148">Se usa para operaciones basadas en DCOM, como la migración de los usuarios, la sincronización del replicador de usuarios y la sincronización de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="37234-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-149">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-150">Servicio de conferencia de mensajería instantánea de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="37234-151">5062</span><span class="sxs-lookup"><span data-stu-id="37234-151">5062</span></span></p></td>
<td><p><span data-ttu-id="37234-152">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-153">Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="37234-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-154">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-155">Servicio de conferencias web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="37234-156">8057</span><span class="sxs-lookup"><span data-stu-id="37234-156">8057</span></span></p></td>
<td><p><span data-ttu-id="37234-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="37234-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-158">Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.</span><span class="sxs-lookup"><span data-stu-id="37234-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-159">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-160">Servicio de compatibilidad con conferencias web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="37234-161">8058</span><span class="sxs-lookup"><span data-stu-id="37234-161">8058</span></span></p></td>
<td><p><span data-ttu-id="37234-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="37234-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-163">Se usa para escuchar conexiones persistentes del modelo de objetos compartidos (PSOM) desde el cliente de Live Meeting y las versiones anteriores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37234-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-164">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-165">Servicio de conferencia de audio y vídeo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="37234-166">5063</span><span class="sxs-lookup"><span data-stu-id="37234-166">5063</span></span></p></td>
<td><p><span data-ttu-id="37234-167">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-168">Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="37234-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-169">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-170">Servicio de conferencia de audio y vídeo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="37234-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="37234-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="37234-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="37234-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="37234-173">Intervalo de puertos de medios que se usa para conferencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="37234-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-174">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-175">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="37234-176">80</span><span class="sxs-lookup"><span data-stu-id="37234-176">80</span></span></p></td>
<td><p><span data-ttu-id="37234-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="37234-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="37234-178">Se usa para la comunicación entre los servidores front-end y los FQDN (direcciones URL que usan los componentes web de IIS) cuando no se usa HTTPS.</span><span class="sxs-lookup"><span data-stu-id="37234-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-179">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-180">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="37234-181">443</span><span class="sxs-lookup"><span data-stu-id="37234-181">443</span></span></p></td>
<td><p><span data-ttu-id="37234-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="37234-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="37234-183">Se usa para la comunicación entre los servidores front-end y los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS).</span><span class="sxs-lookup"><span data-stu-id="37234-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-184">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-185">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="37234-186">8080</span><span class="sxs-lookup"><span data-stu-id="37234-186">8080</span></span></p></td>
<td><p><span data-ttu-id="37234-187">TCP y HTTP</span><span class="sxs-lookup"><span data-stu-id="37234-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="37234-188">Lo usan los componentes web para acceso externo.</span><span class="sxs-lookup"><span data-stu-id="37234-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-189">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-190">Componente de servidor web</span><span class="sxs-lookup"><span data-stu-id="37234-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="37234-191">4443</span><span class="sxs-lookup"><span data-stu-id="37234-191">4443</span></span></p></td>
<td><p><span data-ttu-id="37234-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="37234-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="37234-193">Comunicaciones entre grupos de HTTPS (desde proxy inverso) y HTTPS front-end para el inicio de sesión con detección automática.</span><span class="sxs-lookup"><span data-stu-id="37234-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-194">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-195">Componente de servidor web</span><span class="sxs-lookup"><span data-stu-id="37234-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="37234-196">8060</span><span class="sxs-lookup"><span data-stu-id="37234-196">8060</span></span></p></td>
<td><p><span data-ttu-id="37234-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="37234-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-198">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-199">Componente de servidor web</span><span class="sxs-lookup"><span data-stu-id="37234-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="37234-200">8061</span><span class="sxs-lookup"><span data-stu-id="37234-200">8061</span></span></p></td>
<td><p><span data-ttu-id="37234-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="37234-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-202">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-203">Componente de servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="37234-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="37234-204">5086</span><span class="sxs-lookup"><span data-stu-id="37234-204">5086</span></span></p></td>
<td><p><span data-ttu-id="37234-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="37234-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-206">Puerto SIP que usan los procesos internos de los servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="37234-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-207">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-208">Componente de servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="37234-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="37234-209">5087</span><span class="sxs-lookup"><span data-stu-id="37234-209">5087</span></span></p></td>
<td><p><span data-ttu-id="37234-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="37234-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-211">Puerto SIP que usan los procesos internos de los servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="37234-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-212">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-213">Componente de servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="37234-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="37234-214">443</span><span class="sxs-lookup"><span data-stu-id="37234-214">443</span></span></p></td>
<td><p><span data-ttu-id="37234-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="37234-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-216">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-217">Servicio del operador de conferencias de Lync Server (Conferencia de acceso telefónico local)</span><span class="sxs-lookup"><span data-stu-id="37234-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="37234-218">5064</span><span class="sxs-lookup"><span data-stu-id="37234-218">5064</span></span></p></td>
<td><p><span data-ttu-id="37234-219">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-220">Se usa para las solicitudes SIP entrantes de las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="37234-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-221">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-222">Servicio del operador de conferencias de Lync Server (Conferencia de acceso telefónico local)</span><span class="sxs-lookup"><span data-stu-id="37234-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="37234-223">5072</span><span class="sxs-lookup"><span data-stu-id="37234-223">5072</span></span></p></td>
<td><p><span data-ttu-id="37234-224">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-225">Se usa para las solicitudes SIP entrantes para operadores (llamar en conferencia).</span><span class="sxs-lookup"><span data-stu-id="37234-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-226">Servidores front-end que también ejecutan un servidor de mediación combinado</span><span class="sxs-lookup"><span data-stu-id="37234-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="37234-227">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="37234-228">5070</span><span class="sxs-lookup"><span data-stu-id="37234-228">5070</span></span></p></td>
<td><p><span data-ttu-id="37234-229">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-230">Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="37234-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-231">Servidores front-end que también ejecutan un servidor de mediación combinado</span><span class="sxs-lookup"><span data-stu-id="37234-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="37234-232">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="37234-233">5067</span><span class="sxs-lookup"><span data-stu-id="37234-233">5067</span></span></p></td>
<td><p><span data-ttu-id="37234-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="37234-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-235">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="37234-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-236">Servidores front-end que también ejecutan un servidor de mediación combinado</span><span class="sxs-lookup"><span data-stu-id="37234-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="37234-237">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="37234-238">5068</span><span class="sxs-lookup"><span data-stu-id="37234-238">5068</span></span></p></td>
<td><p><span data-ttu-id="37234-239">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-240">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="37234-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-241">Servidores front-end que también ejecutan un servidor de mediación combinado</span><span class="sxs-lookup"><span data-stu-id="37234-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="37234-242">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="37234-243">5081</span><span class="sxs-lookup"><span data-stu-id="37234-243">5081</span></span></p></td>
<td><p><span data-ttu-id="37234-244">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-245">Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="37234-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-246">Servidores front-end que también ejecutan un servidor de mediación combinado</span><span class="sxs-lookup"><span data-stu-id="37234-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="37234-247">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="37234-248">5082</span><span class="sxs-lookup"><span data-stu-id="37234-248">5082</span></span></p></td>
<td><p><span data-ttu-id="37234-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="37234-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-250">Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="37234-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-251">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-252">Servicio de uso compartido de aplicaciones de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="37234-253">5065</span><span class="sxs-lookup"><span data-stu-id="37234-253">5065</span></span></p></td>
<td><p><span data-ttu-id="37234-254">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-255">Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="37234-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-256">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-257">Servicio de uso compartido de aplicaciones de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="37234-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="37234-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="37234-259">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-260">Intervalo de puertos de medios que se usa para compartir aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="37234-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-261">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-262">Servicio de anuncios de conferencias de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="37234-263">5073</span><span class="sxs-lookup"><span data-stu-id="37234-263">5073</span></span></p></td>
<td><p><span data-ttu-id="37234-264">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-265">Se usa para las solicitudes SIP entrantes para el servicio de anuncios de conferencias de Lync Server (es decir, para conferencias de acceso telefónico local).</span><span class="sxs-lookup"><span data-stu-id="37234-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-266">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-267">Servicio de estacionamiento de llamadas de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="37234-268">5075</span><span class="sxs-lookup"><span data-stu-id="37234-268">5075</span></span></p></td>
<td><p><span data-ttu-id="37234-269">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-270">Se usa para las solicitudes SIP entrantes de la aplicación Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="37234-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-271">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-272">Servicio de prueba de audio de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="37234-273">5076</span><span class="sxs-lookup"><span data-stu-id="37234-273">5076</span></span></p></td>
<td><p><span data-ttu-id="37234-274">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-275">Se usa para las solicitudes SIP entrantes del servicio de prueba de audio.</span><span class="sxs-lookup"><span data-stu-id="37234-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-276">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-277">No aplicable</span><span class="sxs-lookup"><span data-stu-id="37234-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="37234-278">5066</span><span class="sxs-lookup"><span data-stu-id="37234-278">5066</span></span></p></td>
<td><p><span data-ttu-id="37234-279">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-280">Se usa para la puerta de enlace 9-1-1 mejorado (E9-1-1) saliente.</span><span class="sxs-lookup"><span data-stu-id="37234-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-281">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-282">Servicio de grupo de respuesta de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="37234-283">5071</span><span class="sxs-lookup"><span data-stu-id="37234-283">5071</span></span></p></td>
<td><p><span data-ttu-id="37234-284">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-285">Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="37234-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-286">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-287">Servicio de grupo de respuesta de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="37234-288">8404</span><span class="sxs-lookup"><span data-stu-id="37234-288">8404</span></span></p></td>
<td><p><span data-ttu-id="37234-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="37234-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-290">Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="37234-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-291">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-292">Servicio de directiva de ancho de banda de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="37234-293">5080</span><span class="sxs-lookup"><span data-stu-id="37234-293">5080</span></span></p></td>
<td><p><span data-ttu-id="37234-294">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-295">Lo usa el servicio de directiva de ancho de banda del tráfico TURN perimetral A/V para el servicio de control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="37234-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-296">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="37234-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-297">Servicio de directiva de ancho de banda de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="37234-298">448</span><span class="sxs-lookup"><span data-stu-id="37234-298">448</span></span></p></td>
<td><p><span data-ttu-id="37234-299">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-300">Usado por el servicio de directivas de ancho de banda de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37234-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-301">Servidores front-end en los que reside el almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="37234-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="37234-302">Servicio agente de replicación maestra de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="37234-303">445</span><span class="sxs-lookup"><span data-stu-id="37234-303">445</span></span></p></td>
<td><p><span data-ttu-id="37234-304">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-305">Se usa para insertar los datos de configuración desde el almacén de administración central en servidores que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37234-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-306">Todos los servidores</span><span class="sxs-lookup"><span data-stu-id="37234-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-307">Explorador SQL</span><span class="sxs-lookup"><span data-stu-id="37234-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="37234-308">1434</span><span class="sxs-lookup"><span data-stu-id="37234-308">1434</span></span></p></td>
<td><p><span data-ttu-id="37234-309">UDP</span><span class="sxs-lookup"><span data-stu-id="37234-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="37234-310">Explorador SQL para la copia replicada local de los datos del almacén central de administración en la instancia local de SQL Server</span><span class="sxs-lookup"><span data-stu-id="37234-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-311">Todos los usuarios internos</span><span class="sxs-lookup"><span data-stu-id="37234-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="37234-312">Varios</span><span class="sxs-lookup"><span data-stu-id="37234-312">Various</span></span></p></td>
<td><p><span data-ttu-id="37234-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="37234-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="37234-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="37234-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="37234-315">El intervalo de puertos de medios se usa para audioconferencias en todos los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="37234-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="37234-316">Usado por todos los servidores que terminan audio: servidores front-end (para el servicio del operador de conferencias de Lync Server, servicio de anuncios de conferencias de Lync Server y el servicio de audioconferencias de audio y vídeo de Lync) y servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="37234-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-317">Servidores de Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="37234-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37234-318">443</span><span class="sxs-lookup"><span data-stu-id="37234-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37234-319">Usado por Lync Server 2013 para conectarse a Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="37234-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-320">Directores</span><span class="sxs-lookup"><span data-stu-id="37234-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="37234-321">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="37234-322">5060</span><span class="sxs-lookup"><span data-stu-id="37234-322">5060</span></span></p></td>
<td><p><span data-ttu-id="37234-323">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-324">Se usa opcionalmente para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="37234-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-325">Directores</span><span class="sxs-lookup"><span data-stu-id="37234-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="37234-326">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="37234-327">444</span><span class="sxs-lookup"><span data-stu-id="37234-327">444</span></span></p></td>
<td><p><span data-ttu-id="37234-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="37234-328">HTTPS</span></span></p>
<p><span data-ttu-id="37234-329">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-330">Comunicación entre servidores front-end y Director.</span><span class="sxs-lookup"><span data-stu-id="37234-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="37234-331">Además, la publicación de certificados de cliente (a servidores de aplicaciones para el usuario) o la validación si el certificado de cliente ya se ha publicado.</span><span class="sxs-lookup"><span data-stu-id="37234-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-332">Directores</span><span class="sxs-lookup"><span data-stu-id="37234-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="37234-333">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="37234-334">80</span><span class="sxs-lookup"><span data-stu-id="37234-334">80</span></span></p></td>
<td><p><span data-ttu-id="37234-335">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-p105">Se usa para la comunicación inicial desde los Directores a los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS). En condiciones normales, cambiará a tráfico HTTPS a través del puerto 443 y el tipo de protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="37234-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-338">Directores</span><span class="sxs-lookup"><span data-stu-id="37234-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="37234-339">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="37234-340">443</span><span class="sxs-lookup"><span data-stu-id="37234-340">443</span></span></p></td>
<td><p><span data-ttu-id="37234-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="37234-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="37234-342">Se usa para la comunicación desde los Directores a los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS).</span><span class="sxs-lookup"><span data-stu-id="37234-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-343">Directores</span><span class="sxs-lookup"><span data-stu-id="37234-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="37234-344">Servicio front-end de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="37234-345">5061</span><span class="sxs-lookup"><span data-stu-id="37234-345">5061</span></span></p></td>
<td><p><span data-ttu-id="37234-346">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-347">Se usa para comunicaciones internas entre servidores y para conexiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="37234-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-348">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="37234-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-349">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="37234-350">5070</span><span class="sxs-lookup"><span data-stu-id="37234-350">5070</span></span></p></td>
<td><p><span data-ttu-id="37234-351">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-352">Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="37234-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-353">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="37234-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-354">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="37234-355">5067</span><span class="sxs-lookup"><span data-stu-id="37234-355">5067</span></span></p></td>
<td><p><span data-ttu-id="37234-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="37234-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-357">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="37234-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-358">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="37234-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-359">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="37234-360">5068</span><span class="sxs-lookup"><span data-stu-id="37234-360">5068</span></span></p></td>
<td><p><span data-ttu-id="37234-361">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-362">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="37234-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-363">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="37234-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="37234-364">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37234-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="37234-365">5070</span><span class="sxs-lookup"><span data-stu-id="37234-365">5070</span></span></p></td>
<td><p><span data-ttu-id="37234-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="37234-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-367">Se usa para solicitudes SIP desde los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="37234-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-368">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="37234-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="37234-369">SIP de chat persistente</span><span class="sxs-lookup"><span data-stu-id="37234-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="37234-370">5041</span><span class="sxs-lookup"><span data-stu-id="37234-370">5041</span></span></p></td>
<td><p><span data-ttu-id="37234-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="37234-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-372">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="37234-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="37234-373">Windows Communication Foundation (WCF) de chat persistente</span><span class="sxs-lookup"><span data-stu-id="37234-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="37234-374">881</span><span class="sxs-lookup"><span data-stu-id="37234-374">881</span></span></p></td>
<td><p><span data-ttu-id="37234-375">TCP (TLS) y TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="37234-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-376">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="37234-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="37234-377">Servicio de transferencia de archivos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="37234-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="37234-378">443</span><span class="sxs-lookup"><span data-stu-id="37234-378">443</span></span></p></td>
<td><p><span data-ttu-id="37234-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="37234-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="37234-380">Algunos escenarios de control remoto de llamadas requieren una conexión entre el servidor front-end o el Director y la PBX.</span><span class="sxs-lookup"><span data-stu-id="37234-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="37234-381">Aunque Lync Server ya no usa el puerto TCP 5060, durante la implementación de control remoto de llamadas, se crea una configuración de servidor de confianza, que asocia el FQDN del servidor de línea RCC con el puerto TCP que usará el servidor o director de front-end para conectarse al sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="37234-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="37234-382">Para obtener más información, vea el cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37234-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="37234-383">Para los grupos que solo usan equilibrio de carga de hardware (no equilibrio de carga de DNS), en la siguiente tabla se muestran los puertos que necesitan para abrir los equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="37234-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="37234-384">Puertos del equilibrador de carga de hardware si solo usa equilibrio de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="37234-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37234-385">Equilibrador de carga</span><span class="sxs-lookup"><span data-stu-id="37234-385">Load Balancer</span></span></th>
<th><span data-ttu-id="37234-386">Puerto</span><span class="sxs-lookup"><span data-stu-id="37234-386">Port</span></span></th>
<th><span data-ttu-id="37234-387">Protocolo</span><span class="sxs-lookup"><span data-stu-id="37234-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37234-388">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-389">5061</span><span class="sxs-lookup"><span data-stu-id="37234-389">5061</span></span></p></td>
<td><p><span data-ttu-id="37234-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="37234-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-391">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-392">444</span><span class="sxs-lookup"><span data-stu-id="37234-392">444</span></span></p></td>
<td><p><span data-ttu-id="37234-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="37234-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-394">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-395">135</span><span class="sxs-lookup"><span data-stu-id="37234-395">135</span></span></p></td>
<td><p><span data-ttu-id="37234-396">DCOM y llamada a procedimiento remoto (RPC)</span><span class="sxs-lookup"><span data-stu-id="37234-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-397">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-398">80</span><span class="sxs-lookup"><span data-stu-id="37234-398">80</span></span></p></td>
<td><p><span data-ttu-id="37234-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="37234-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-400">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-401">8080</span><span class="sxs-lookup"><span data-stu-id="37234-401">8080</span></span></p></td>
<td><p><span data-ttu-id="37234-402">TCP, Recuperación cliente y dispositivo del certificado raíz del servidor de front-end, clientes y dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="37234-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-403">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-404">443</span><span class="sxs-lookup"><span data-stu-id="37234-404">443</span></span></p></td>
<td><p><span data-ttu-id="37234-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="37234-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-406">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-407">4443</span><span class="sxs-lookup"><span data-stu-id="37234-407">4443</span></span></p></td>
<td><p><span data-ttu-id="37234-408">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="37234-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-409">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-410">5072</span><span class="sxs-lookup"><span data-stu-id="37234-410">5072</span></span></p></td>
<td><p><span data-ttu-id="37234-411">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-412">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-413">5073</span><span class="sxs-lookup"><span data-stu-id="37234-413">5073</span></span></p></td>
<td><p><span data-ttu-id="37234-414">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-415">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-416">5075</span><span class="sxs-lookup"><span data-stu-id="37234-416">5075</span></span></p></td>
<td><p><span data-ttu-id="37234-417">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-418">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-419">5076</span><span class="sxs-lookup"><span data-stu-id="37234-419">5076</span></span></p></td>
<td><p><span data-ttu-id="37234-420">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-421">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-422">5071</span><span class="sxs-lookup"><span data-stu-id="37234-422">5071</span></span></p></td>
<td><p><span data-ttu-id="37234-423">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-424">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-425">5080</span><span class="sxs-lookup"><span data-stu-id="37234-425">5080</span></span></p></td>
<td><p><span data-ttu-id="37234-426">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-427">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-428">448</span><span class="sxs-lookup"><span data-stu-id="37234-428">448</span></span></p></td>
<td><p><span data-ttu-id="37234-429">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-430">Equilibrador de carga del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="37234-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-431">5070</span><span class="sxs-lookup"><span data-stu-id="37234-431">5070</span></span></p></td>
<td><p><span data-ttu-id="37234-432">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-433">Equilibrador de carga del servidor front-end (si el grupo también ejecuta el servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="37234-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="37234-434">5070</span><span class="sxs-lookup"><span data-stu-id="37234-434">5070</span></span></p></td>
<td><p><span data-ttu-id="37234-435">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-436">Equilibrador de carga del Director</span><span class="sxs-lookup"><span data-stu-id="37234-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-437">443</span><span class="sxs-lookup"><span data-stu-id="37234-437">443</span></span></p></td>
<td><p><span data-ttu-id="37234-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="37234-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-439">Equilibrador de carga del Director</span><span class="sxs-lookup"><span data-stu-id="37234-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-440">444</span><span class="sxs-lookup"><span data-stu-id="37234-440">444</span></span></p></td>
<td><p><span data-ttu-id="37234-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="37234-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-442">Equilibrador de carga del Director</span><span class="sxs-lookup"><span data-stu-id="37234-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-443">5061</span><span class="sxs-lookup"><span data-stu-id="37234-443">5061</span></span></p></td>
<td><p><span data-ttu-id="37234-444">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-445">Equilibrador de carga del Director</span><span class="sxs-lookup"><span data-stu-id="37234-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-446">4443</span><span class="sxs-lookup"><span data-stu-id="37234-446">4443</span></span></p></td>
<td><p><span data-ttu-id="37234-447">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="37234-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="37234-p107">Los grupos de servidores front-end y de Directores que usan equilibrio de carga de DNS también deben tener implementado un equilibrador de carga de hardware. En la siguiente tabla se muestran los puertos que se deben abrir en estos equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="37234-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="37234-450">Puertos del equilibrador de carga de hardware si usa equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="37234-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37234-451">Equilibrador de carga</span><span class="sxs-lookup"><span data-stu-id="37234-451">Load Balancer</span></span></th>
<th><span data-ttu-id="37234-452">Puerto</span><span class="sxs-lookup"><span data-stu-id="37234-452">Port</span></span></th>
<th><span data-ttu-id="37234-453">Protocolo</span><span class="sxs-lookup"><span data-stu-id="37234-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37234-454">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-455">80</span><span class="sxs-lookup"><span data-stu-id="37234-455">80</span></span></p></td>
<td><p><span data-ttu-id="37234-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="37234-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-457">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-458">443</span><span class="sxs-lookup"><span data-stu-id="37234-458">443</span></span></p></td>
<td><p><span data-ttu-id="37234-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="37234-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-460">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-461">8080</span><span class="sxs-lookup"><span data-stu-id="37234-461">8080</span></span></p></td>
<td><p><span data-ttu-id="37234-462">TCP, Recuperación cliente y dispositivo del certificado raíz del servidor de front-end, clientes y dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="37234-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-463">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="37234-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-464">4443</span><span class="sxs-lookup"><span data-stu-id="37234-464">4443</span></span></p></td>
<td><p><span data-ttu-id="37234-465">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="37234-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-466">Equilibrador de carga del Director</span><span class="sxs-lookup"><span data-stu-id="37234-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-467">443</span><span class="sxs-lookup"><span data-stu-id="37234-467">443</span></span></p></td>
<td><p><span data-ttu-id="37234-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="37234-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-469">Equilibrador de carga del Director</span><span class="sxs-lookup"><span data-stu-id="37234-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="37234-470">4443</span><span class="sxs-lookup"><span data-stu-id="37234-470">4443</span></span></p></td>
<td><p><span data-ttu-id="37234-471">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="37234-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="37234-472">Puertos de cliente necesarios</span><span class="sxs-lookup"><span data-stu-id="37234-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37234-473">Componente</span><span class="sxs-lookup"><span data-stu-id="37234-473">Component</span></span></th>
<th><span data-ttu-id="37234-474">Puerto</span><span class="sxs-lookup"><span data-stu-id="37234-474">Port</span></span></th>
<th><span data-ttu-id="37234-475">Protocolo</span><span class="sxs-lookup"><span data-stu-id="37234-475">Protocol</span></span></th>
<th><span data-ttu-id="37234-476">Notas</span><span class="sxs-lookup"><span data-stu-id="37234-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37234-477">Clientes</span><span class="sxs-lookup"><span data-stu-id="37234-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="37234-478">67/68</span><span class="sxs-lookup"><span data-stu-id="37234-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="37234-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="37234-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="37234-480">Utilizado por Lync Server para encontrar el nombre completo del registrador (es decir, si no se puede establecer la configuración manual de DNS SRV).</span><span class="sxs-lookup"><span data-stu-id="37234-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-481">Clientes</span><span class="sxs-lookup"><span data-stu-id="37234-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="37234-482">443</span><span class="sxs-lookup"><span data-stu-id="37234-482">443</span></span></p></td>
<td><p><span data-ttu-id="37234-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="37234-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-484">Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="37234-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-485">Clientes</span><span class="sxs-lookup"><span data-stu-id="37234-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="37234-486">443</span><span class="sxs-lookup"><span data-stu-id="37234-486">443</span></span></p></td>
<td><p><span data-ttu-id="37234-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="37234-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-488">Se usa para el acceso de usuarios externos a las sesiones de conferencia web.</span><span class="sxs-lookup"><span data-stu-id="37234-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-489">Clientes</span><span class="sxs-lookup"><span data-stu-id="37234-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="37234-490">443</span><span class="sxs-lookup"><span data-stu-id="37234-490">443</span></span></p></td>
<td><p><span data-ttu-id="37234-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="37234-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="37234-492">Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP).</span><span class="sxs-lookup"><span data-stu-id="37234-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-493">Clientes</span><span class="sxs-lookup"><span data-stu-id="37234-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="37234-494">3478</span><span class="sxs-lookup"><span data-stu-id="37234-494">3478</span></span></p></td>
<td><p><span data-ttu-id="37234-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="37234-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="37234-496">Se usa para el acceso de usuarios externos a los medios y las sesiones de A/V (UDP)</span><span class="sxs-lookup"><span data-stu-id="37234-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-497">Clientes</span><span class="sxs-lookup"><span data-stu-id="37234-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="37234-498">5061</span><span class="sxs-lookup"><span data-stu-id="37234-498">5061</span></span></p></td>
<td><p><span data-ttu-id="37234-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="37234-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="37234-500">Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="37234-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-501">Clientes</span><span class="sxs-lookup"><span data-stu-id="37234-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="37234-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="37234-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="37234-503">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-504">Se usa para la transferencia de archivos entre clientes de Lync y clientes anteriores (clientes de Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 y Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="37234-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-505">Clientes</span><span class="sxs-lookup"><span data-stu-id="37234-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="37234-506">1024-65535\*</span><span class="sxs-lookup"><span data-stu-id="37234-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="37234-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="37234-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="37234-508">Intervalo de puertos de audio (se requieren 20 puertos como mínimo).</span><span class="sxs-lookup"><span data-stu-id="37234-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-509">Clientes</span><span class="sxs-lookup"><span data-stu-id="37234-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="37234-510">1024-65535\*</span><span class="sxs-lookup"><span data-stu-id="37234-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="37234-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="37234-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="37234-512">Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo).</span><span class="sxs-lookup"><span data-stu-id="37234-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-513">Clientes</span><span class="sxs-lookup"><span data-stu-id="37234-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="37234-514">1024-65535\*</span><span class="sxs-lookup"><span data-stu-id="37234-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="37234-515">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-516">Transferencias de archivos de punto a punto (para la transferencia de archivos de conferencia, los clientes usan PSOM).</span><span class="sxs-lookup"><span data-stu-id="37234-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37234-517">Clientes</span><span class="sxs-lookup"><span data-stu-id="37234-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="37234-518">1024-65535\*</span><span class="sxs-lookup"><span data-stu-id="37234-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="37234-519">TCP</span><span class="sxs-lookup"><span data-stu-id="37234-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="37234-520">Uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="37234-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37234-521">Teléfono de área común Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="37234-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="37234-522">Teléfono de escritorio Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="37234-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="37234-523">Teléfono IP HP 4110 (teléfono de área común)</span><span class="sxs-lookup"><span data-stu-id="37234-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="37234-524">Teléfono IP HP 4120 (teléfono de escritorio)</span><span class="sxs-lookup"><span data-stu-id="37234-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="37234-525">Teléfono de área común Polycom CX500 IP</span><span class="sxs-lookup"><span data-stu-id="37234-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="37234-526">Teléfono de escritorio Polycom CX600 IP</span><span class="sxs-lookup"><span data-stu-id="37234-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="37234-527">Teléfono de escritorio Polycom CX700 IP</span><span class="sxs-lookup"><span data-stu-id="37234-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="37234-528">Teléfono de conferencia Polycom CX3000 IP</span><span class="sxs-lookup"><span data-stu-id="37234-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="37234-529">67/68</span><span class="sxs-lookup"><span data-stu-id="37234-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="37234-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="37234-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="37234-531">Usado por los dispositivos de la lista para buscar el certificado de Lync Server, el FQDN de aprovisionamiento y el registrador de FQDN.</span><span class="sxs-lookup"><span data-stu-id="37234-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="37234-532">**\*** Para configurar puertos específicos para estos tipos de medios, use el cmdlet CsConferencingConfiguration (ClientMediaPortRangeEnabled, ClientMediaPort y ClientMediaPortRange parámetros).</span><span class="sxs-lookup"><span data-stu-id="37234-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37234-533">El conjunto de programas para clientes de Lync crea automáticamente las excepciones de firewall del sistema operativo necesarias en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="37234-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="37234-534">Los puertos que se usan para el acceso de usuarios externos son necesarios en cualquier escenario en el que el cliente deba atravesar el firewall de la organización (por ejemplo, las comunicaciones o reuniones externas que se hospedan en otras organizaciones).</span><span class="sxs-lookup"><span data-stu-id="37234-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

