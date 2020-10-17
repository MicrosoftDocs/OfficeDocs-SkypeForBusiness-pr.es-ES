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
ms.openlocfilehash: 858ec90cf3811318cc29a902b56ac8ff31c46a22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513407"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="f2401-102">Puertos y protocolos para servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2401-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2401-103">_**Última modificación del tema:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="f2401-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="f2401-104">En esta sección se resumen los puertos y protocolos que usan los servidores, los equilibradores de carga y los clientes en una implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2401-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f2401-105">Los clientes de Lync y Communicator cuando participan en una comunicación de una a una, a menudo se denominan de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="f2401-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="f2401-106">Técnicamente, los dos clientes se comunican en una conversación de una a una, con la unidad de control multipunto (IMMCU) de mensajería instantánea en la parte central.</span><span class="sxs-lookup"><span data-stu-id="f2401-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="f2401-107">IMMCU es un componente del servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f2401-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="f2401-108">La colocación de IMMCU en el flujo de trabajo de comunicación necesario permite el registro detallado de llamadas y otras características que permite el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f2401-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="f2401-109">La comunicación es desde un puerto de origen dinámico en el cliente al puerto del servidor front-end TLS/TCP/5061 (asumiendo el uso de la seguridad de la capa de transporte recomendada).</span><span class="sxs-lookup"><span data-stu-id="f2401-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="f2401-110">Por diseño, la comunicación punto a punto (así como la mensajería instantánea de varios participantes) solo es posible cuando Lync Server y el IMMCU está activo y disponible.</span><span class="sxs-lookup"><span data-stu-id="f2401-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="f2401-111">Detalles de puerto y protocolo</span><span class="sxs-lookup"><span data-stu-id="f2401-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2401-112">Firewall de Windows debe estar en ejecución antes de iniciar los servicios de Lync Server en un servidor, ya que esto se debe a que Lync Server abre los puertos necesarios en el firewall.</span><span class="sxs-lookup"><span data-stu-id="f2401-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="f2401-113">Para obtener más información sobre la configuración del firewall para los componentes perimetrales, consulte [determine external a/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2401-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="f2401-114">En la tabla siguiente se enumeran los puertos que debe abrir en cada rol del servidor interno.</span><span class="sxs-lookup"><span data-stu-id="f2401-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="f2401-115">Puertos de servidor obligatorios (por rol del servidor)</span><span class="sxs-lookup"><span data-stu-id="f2401-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="f2401-116">Rol de servidor</span><span class="sxs-lookup"><span data-stu-id="f2401-116">Server role</span></span></th>
<th><span data-ttu-id="f2401-117">Nombre del servicio</span><span class="sxs-lookup"><span data-stu-id="f2401-117">Service name</span></span></th>
<th><span data-ttu-id="f2401-118">Puerto</span><span class="sxs-lookup"><span data-stu-id="f2401-118">Port</span></span></th>
<th><span data-ttu-id="f2401-119">Protocolo</span><span class="sxs-lookup"><span data-stu-id="f2401-119">Protocol</span></span></th>
<th><span data-ttu-id="f2401-120">Notas</span><span class="sxs-lookup"><span data-stu-id="f2401-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2401-121">Todos los servidores</span><span class="sxs-lookup"><span data-stu-id="f2401-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-122">Explorador SQL</span><span class="sxs-lookup"><span data-stu-id="f2401-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="f2401-123">1434</span><span class="sxs-lookup"><span data-stu-id="f2401-123">1434</span></span></p></td>
<td><p><span data-ttu-id="f2401-124">UDP</span><span class="sxs-lookup"><span data-stu-id="f2401-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="f2401-125">Explorador SQL para la copia replicada local de la base de datos del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="f2401-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-126">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-127">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f2401-128">5060</span><span class="sxs-lookup"><span data-stu-id="f2401-128">5060</span></span></p></td>
<td><p><span data-ttu-id="f2401-129">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-130">Opcionalmente lo usan los servidores Standard Edition y front-end para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2401-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-131">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-132">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f2401-133">5061</span><span class="sxs-lookup"><span data-stu-id="f2401-133">5061</span></span></p></td>
<td><p><span data-ttu-id="f2401-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-p102">Lo usan los servidores Standard Edition y los grupos de servidores front-end para todas la comunicaciones SIP internas entre los servidores (MTLS), para las comunicaciones SIP entre el cliente y del servidor (TLS) y para las comunicaciones entre los servidores front-end y los servidores de mediación (MTLS). También se usa para las comunicaciones con el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="f2401-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-137">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-138">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f2401-139">444</span><span class="sxs-lookup"><span data-stu-id="f2401-139">444</span></span></p></td>
<td><p><span data-ttu-id="f2401-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2401-140">HTTPS</span></span></p>
<p><span data-ttu-id="f2401-141">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-142">Se usa para la comunicación HTTPS entre el foco (el componente de Lync Server que administra el estado de conferencia) y los servidores individuales.</span><span class="sxs-lookup"><span data-stu-id="f2401-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="f2401-143">Este puerto también se usa para la comunicación TCP entre las aplicaciones de sucursal con funciones de supervivencia y los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f2401-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-144">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-145">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f2401-146">135</span><span class="sxs-lookup"><span data-stu-id="f2401-146">135</span></span></p></td>
<td><p><span data-ttu-id="f2401-147">DCOM y llamada a procedimiento remoto (RPC)</span><span class="sxs-lookup"><span data-stu-id="f2401-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="f2401-148">Se usa para operaciones basadas en DCOM como la migración de los usuarios, la sincronización del replicador de usuarios y la sincronización de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="f2401-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-149">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-150">Servicio de conferencia de mensajería instantánea de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f2401-151">5062</span><span class="sxs-lookup"><span data-stu-id="f2401-151">5062</span></span></p></td>
<td><p><span data-ttu-id="f2401-152">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-153">Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="f2401-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-154">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-155">Servicio de conferencia Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f2401-156">8057</span><span class="sxs-lookup"><span data-stu-id="f2401-156">8057</span></span></p></td>
<td><p><span data-ttu-id="f2401-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-158">Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.</span><span class="sxs-lookup"><span data-stu-id="f2401-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-159">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-160">Servicio de compatibilidad con conferencias web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f2401-161">8058</span><span class="sxs-lookup"><span data-stu-id="f2401-161">8058</span></span></p></td>
<td><p><span data-ttu-id="f2401-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-163">Se usa para escuchar las conexiones del modelo de objetos compartidos persistentes (PSOM) desde el cliente de Live Meeting y las versiones anteriores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2401-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-164">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-165">Servicio de conferencia de audio y vídeo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f2401-166">5063</span><span class="sxs-lookup"><span data-stu-id="f2401-166">5063</span></span></p></td>
<td><p><span data-ttu-id="f2401-167">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-168">Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="f2401-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-169">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-170">Servicio de conferencia de audio y vídeo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f2401-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="f2401-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="f2401-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f2401-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f2401-173">Intervalo de puerto de medios usado para conferencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f2401-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-174">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-175">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f2401-176">80</span><span class="sxs-lookup"><span data-stu-id="f2401-176">80</span></span></p></td>
<td><p><span data-ttu-id="f2401-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="f2401-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="f2401-178">Se usa para la comunicación entre los servidores front-end y los FQDN (direcciones URL usadas por los componentes web IIS) cuando no se usa HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f2401-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-179">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-180">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f2401-181">443</span><span class="sxs-lookup"><span data-stu-id="f2401-181">443</span></span></p></td>
<td><p><span data-ttu-id="f2401-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2401-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="f2401-183">Se usa para la comunicación entre los servidores front-end y los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS).</span><span class="sxs-lookup"><span data-stu-id="f2401-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-184">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-185">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f2401-186">8080</span><span class="sxs-lookup"><span data-stu-id="f2401-186">8080</span></span></p></td>
<td><p><span data-ttu-id="f2401-187">TCP y HTTP</span><span class="sxs-lookup"><span data-stu-id="f2401-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="f2401-188">Lo usan los componentes Web para el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="f2401-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-189">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-190">Componente del servidor Web</span><span class="sxs-lookup"><span data-stu-id="f2401-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="f2401-191">4443</span><span class="sxs-lookup"><span data-stu-id="f2401-191">4443</span></span></p></td>
<td><p><span data-ttu-id="f2401-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2401-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="f2401-193">HTTPS (desde proxy inverso) y comunicaciones entre grupos de servidores front-end de HTTPS para el inicio de sesión con detección automática.</span><span class="sxs-lookup"><span data-stu-id="f2401-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-194">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-195">Componente del servidor Web</span><span class="sxs-lookup"><span data-stu-id="f2401-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="f2401-196">8060</span><span class="sxs-lookup"><span data-stu-id="f2401-196">8060</span></span></p></td>
<td><p><span data-ttu-id="f2401-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-198">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-199">Componente del servidor Web</span><span class="sxs-lookup"><span data-stu-id="f2401-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="f2401-200">8061</span><span class="sxs-lookup"><span data-stu-id="f2401-200">8061</span></span></p></td>
<td><p><span data-ttu-id="f2401-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-202">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-203">Componente de servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="f2401-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="f2401-204">5086</span><span class="sxs-lookup"><span data-stu-id="f2401-204">5086</span></span></p></td>
<td><p><span data-ttu-id="f2401-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-206">Puerto SIP usado por los procesos internos de Mobility Services</span><span class="sxs-lookup"><span data-stu-id="f2401-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-207">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-208">Componente de servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="f2401-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="f2401-209">5087</span><span class="sxs-lookup"><span data-stu-id="f2401-209">5087</span></span></p></td>
<td><p><span data-ttu-id="f2401-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-211">Puerto SIP usado por los procesos internos de Mobility Services</span><span class="sxs-lookup"><span data-stu-id="f2401-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-212">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-213">Componente de servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="f2401-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="f2401-214">443</span><span class="sxs-lookup"><span data-stu-id="f2401-214">443</span></span></p></td>
<td><p><span data-ttu-id="f2401-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2401-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-216">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-217">Servicio de operador de conferencia de Lync Server (Conferencia de acceso telefónico local)</span><span class="sxs-lookup"><span data-stu-id="f2401-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="f2401-218">5064</span><span class="sxs-lookup"><span data-stu-id="f2401-218">5064</span></span></p></td>
<td><p><span data-ttu-id="f2401-219">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-220">Se usa para las solicitudes SIP entrantes de las conferencias telefónicas.</span><span class="sxs-lookup"><span data-stu-id="f2401-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-221">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-222">Servicio de operador de conferencia de Lync Server (Conferencia de acceso telefónico local)</span><span class="sxs-lookup"><span data-stu-id="f2401-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="f2401-223">5072</span><span class="sxs-lookup"><span data-stu-id="f2401-223">5072</span></span></p></td>
<td><p><span data-ttu-id="f2401-224">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-225">Se usa para las solicitudes SIP entrantes para el operador (llamadas de conferencia de acceso telefónico local).</span><span class="sxs-lookup"><span data-stu-id="f2401-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-226">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="f2401-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f2401-227">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f2401-228">5070</span><span class="sxs-lookup"><span data-stu-id="f2401-228">5070</span></span></p></td>
<td><p><span data-ttu-id="f2401-229">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-230">Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="f2401-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-231">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="f2401-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f2401-232">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f2401-233">5067</span><span class="sxs-lookup"><span data-stu-id="f2401-233">5067</span></span></p></td>
<td><p><span data-ttu-id="f2401-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-235">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="f2401-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-236">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="f2401-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f2401-237">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f2401-238">5068</span><span class="sxs-lookup"><span data-stu-id="f2401-238">5068</span></span></p></td>
<td><p><span data-ttu-id="f2401-239">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-240">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="f2401-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-241">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="f2401-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f2401-242">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f2401-243">5081</span><span class="sxs-lookup"><span data-stu-id="f2401-243">5081</span></span></p></td>
<td><p><span data-ttu-id="f2401-244">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-245">Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="f2401-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-246">Servidores front-end que también ejecutan un servidor de mediación instalado</span><span class="sxs-lookup"><span data-stu-id="f2401-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f2401-247">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f2401-248">5082</span><span class="sxs-lookup"><span data-stu-id="f2401-248">5082</span></span></p></td>
<td><p><span data-ttu-id="f2401-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-250">Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="f2401-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-251">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-252">Servicio de uso compartido de aplicaciones de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="f2401-253">5065</span><span class="sxs-lookup"><span data-stu-id="f2401-253">5065</span></span></p></td>
<td><p><span data-ttu-id="f2401-254">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-255">Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f2401-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-256">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-257">Servicio de uso compartido de aplicaciones de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="f2401-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="f2401-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="f2401-259">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-260">Intervalo de puerto de medios usado para compartir aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f2401-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-261">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-262">Servicio de anuncio de conferencia de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="f2401-263">5073</span><span class="sxs-lookup"><span data-stu-id="f2401-263">5073</span></span></p></td>
<td><p><span data-ttu-id="f2401-264">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-265">Se usa para las solicitudes SIP entrantes para el servicio de anuncio de conferencia de Lync Server (es decir, para las conferencias de acceso telefónico local).</span><span class="sxs-lookup"><span data-stu-id="f2401-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-266">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-267">Servicio de estacionamiento de llamadas de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="f2401-268">5075</span><span class="sxs-lookup"><span data-stu-id="f2401-268">5075</span></span></p></td>
<td><p><span data-ttu-id="f2401-269">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-270">Se usa para las solicitudes SIP entrantes de la aplicación Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2401-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-271">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-272">Servicio de prueba de audio de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="f2401-273">5076</span><span class="sxs-lookup"><span data-stu-id="f2401-273">5076</span></span></p></td>
<td><p><span data-ttu-id="f2401-274">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-275">Se usa para las solicitudes SIP entrantes del servicio de prueba de audio.</span><span class="sxs-lookup"><span data-stu-id="f2401-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-276">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-277">No aplicable</span><span class="sxs-lookup"><span data-stu-id="f2401-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="f2401-278">5066</span><span class="sxs-lookup"><span data-stu-id="f2401-278">5066</span></span></p></td>
<td><p><span data-ttu-id="f2401-279">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-280">Se usa para la puerta de enlace 9-1-1 mejorado (E9-1-1) saliente</span><span class="sxs-lookup"><span data-stu-id="f2401-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-281">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-282">Servicio de grupo de respuesta de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="f2401-283">5071</span><span class="sxs-lookup"><span data-stu-id="f2401-283">5071</span></span></p></td>
<td><p><span data-ttu-id="f2401-284">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-285">Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f2401-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-286">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-287">Servicio de grupo de respuesta de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="f2401-288">8404</span><span class="sxs-lookup"><span data-stu-id="f2401-288">8404</span></span></p></td>
<td><p><span data-ttu-id="f2401-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-290">Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f2401-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-291">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-292">Servicio de directiva de ancho de banda de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="f2401-293">5080</span><span class="sxs-lookup"><span data-stu-id="f2401-293">5080</span></span></p></td>
<td><p><span data-ttu-id="f2401-294">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-295">Lo usa el servicio de directiva de ancho de banda del tráfico TURN perimetral A/V para el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2401-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-296">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-297">Servicio de directiva de ancho de banda de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="f2401-298">448</span><span class="sxs-lookup"><span data-stu-id="f2401-298">448</span></span></p></td>
<td><p><span data-ttu-id="f2401-299">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-300">Se usa para el control de admisión de llamadas por el servicio de directiva de ancho de banda de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2401-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-301">Servidores front-end donde reside el almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="f2401-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="f2401-302">Agente de replicador maestro de Microsoft Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="f2401-303">445</span><span class="sxs-lookup"><span data-stu-id="f2401-303">445</span></span></p></td>
<td><p><span data-ttu-id="f2401-304">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-305">Se usa para insertar los datos de configuración desde el almacén de administración central en los servidores que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2401-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-306">Todos los servidores</span><span class="sxs-lookup"><span data-stu-id="f2401-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-307">Explorador SQL</span><span class="sxs-lookup"><span data-stu-id="f2401-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="f2401-308">1434</span><span class="sxs-lookup"><span data-stu-id="f2401-308">1434</span></span></p></td>
<td><p><span data-ttu-id="f2401-309">UDP</span><span class="sxs-lookup"><span data-stu-id="f2401-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="f2401-310">Explorador SQL para la copia replicada local de los datos del almacén de administración central en la instancia local de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f2401-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-311">Todos los usuarios internos</span><span class="sxs-lookup"><span data-stu-id="f2401-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-312">Varios</span><span class="sxs-lookup"><span data-stu-id="f2401-312">Various</span></span></p></td>
<td><p><span data-ttu-id="f2401-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="f2401-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="f2401-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f2401-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f2401-315">El intervalo de puerto de medios se usa para audioconferencias en todos los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="f2401-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="f2401-316">Usada por todos los servidores que terminan audio: servidores front-end (para el servicio de operador de conferencia de Lync Server, el servicio de anuncio de conferencia de Lync Server y el servicio de conferencia de audio y vídeo de Lync Server) y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="f2401-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-317">Servidores de Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="f2401-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2401-318">443</span><span class="sxs-lookup"><span data-stu-id="f2401-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2401-319">Se usa en Lync Server 2013 para conectarse a Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="f2401-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-320">Reparto</span><span class="sxs-lookup"><span data-stu-id="f2401-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="f2401-321">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f2401-322">5060</span><span class="sxs-lookup"><span data-stu-id="f2401-322">5060</span></span></p></td>
<td><p><span data-ttu-id="f2401-323">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-324">Se usa opcionalmente para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2401-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-325">Reparto</span><span class="sxs-lookup"><span data-stu-id="f2401-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="f2401-326">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f2401-327">444</span><span class="sxs-lookup"><span data-stu-id="f2401-327">444</span></span></p></td>
<td><p><span data-ttu-id="f2401-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2401-328">HTTPS</span></span></p>
<p><span data-ttu-id="f2401-329">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-330">Comunicación entre servidores front-end y director.</span><span class="sxs-lookup"><span data-stu-id="f2401-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="f2401-331">Además, la publicación de certificados de cliente (para los servidores front-end) o la validación si ya se ha publicado el certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="f2401-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-332">Reparto</span><span class="sxs-lookup"><span data-stu-id="f2401-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="f2401-333">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f2401-334">80</span><span class="sxs-lookup"><span data-stu-id="f2401-334">80</span></span></p></td>
<td><p><span data-ttu-id="f2401-335">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-p105">Se usa para la comunicación inicial desde los directores a los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS). En condiciones normales, cambiará a tráfico HTTPS usando el puerto 443 y el tipo de protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="f2401-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-338">Reparto</span><span class="sxs-lookup"><span data-stu-id="f2401-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="f2401-339">Servicio de compatibilidad Web de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f2401-340">443</span><span class="sxs-lookup"><span data-stu-id="f2401-340">443</span></span></p></td>
<td><p><span data-ttu-id="f2401-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2401-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="f2401-342">Se usa para la comunicación desde los directores a los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS).</span><span class="sxs-lookup"><span data-stu-id="f2401-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-343">Reparto</span><span class="sxs-lookup"><span data-stu-id="f2401-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="f2401-344">Servicio de Front-End de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f2401-345">5061</span><span class="sxs-lookup"><span data-stu-id="f2401-345">5061</span></span></p></td>
<td><p><span data-ttu-id="f2401-346">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-347">Se usa para comunicaciones internas entre servidores y para conexiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="f2401-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-348">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="f2401-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-349">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f2401-350">5070</span><span class="sxs-lookup"><span data-stu-id="f2401-350">5070</span></span></p></td>
<td><p><span data-ttu-id="f2401-351">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-352">Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f2401-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-353">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="f2401-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-354">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f2401-355">5067</span><span class="sxs-lookup"><span data-stu-id="f2401-355">5067</span></span></p></td>
<td><p><span data-ttu-id="f2401-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-357">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="f2401-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-358">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="f2401-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-359">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f2401-360">5068</span><span class="sxs-lookup"><span data-stu-id="f2401-360">5068</span></span></p></td>
<td><p><span data-ttu-id="f2401-361">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-362">Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="f2401-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-363">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="f2401-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f2401-364">Servicio de mediación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f2401-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f2401-365">5070</span><span class="sxs-lookup"><span data-stu-id="f2401-365">5070</span></span></p></td>
<td><p><span data-ttu-id="f2401-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-367">Se usa para solicitudes SIP desde los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f2401-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-368">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="f2401-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="f2401-369">SIP de chat persistente</span><span class="sxs-lookup"><span data-stu-id="f2401-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="f2401-370">5041</span><span class="sxs-lookup"><span data-stu-id="f2401-370">5041</span></span></p></td>
<td><p><span data-ttu-id="f2401-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-372">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="f2401-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="f2401-373">Chat persistente Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="f2401-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="f2401-374">881</span><span class="sxs-lookup"><span data-stu-id="f2401-374">881</span></span></p></td>
<td><p><span data-ttu-id="f2401-375">TCP (TLS) y TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-376">Servidor front-end de chat persistente</span><span class="sxs-lookup"><span data-stu-id="f2401-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="f2401-377">Servicio de transferencia de archivos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="f2401-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="f2401-378">443</span><span class="sxs-lookup"><span data-stu-id="f2401-378">443</span></span></p></td>
<td><p><span data-ttu-id="f2401-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f2401-380">Algunos escenarios de control remoto de llamadas requieren una conexión entre el servidor front-end o el director y la PBX.</span><span class="sxs-lookup"><span data-stu-id="f2401-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="f2401-381">Aunque Lync Server ya no usa el puerto TCP 5060, durante la implementación de control remoto de llamadas, se crea una configuración de servidor de confianza, que asocia el FQDN del servidor de línea RCC con el puerto TCP que el director o el servidor front-end usará para conectarse al sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="f2401-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="f2401-382">Para obtener más información, consulte el cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2401-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="f2401-383">Para los grupos de servidores que solo usan equilibrio de carga de hardware (no equilibrio de carga de DNS), en la siguiente tabla se muestran los puertos que necesitan para abrir los equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="f2401-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="f2401-384">Puertos del equilibrador de carga de hardware si solo usa equilibrio de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="f2401-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2401-385">Equilibrador de carga</span><span class="sxs-lookup"><span data-stu-id="f2401-385">Load Balancer</span></span></th>
<th><span data-ttu-id="f2401-386">Puerto</span><span class="sxs-lookup"><span data-stu-id="f2401-386">Port</span></span></th>
<th><span data-ttu-id="f2401-387">Protocolo</span><span class="sxs-lookup"><span data-stu-id="f2401-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2401-388">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-389">5061</span><span class="sxs-lookup"><span data-stu-id="f2401-389">5061</span></span></p></td>
<td><p><span data-ttu-id="f2401-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-391">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-392">444</span><span class="sxs-lookup"><span data-stu-id="f2401-392">444</span></span></p></td>
<td><p><span data-ttu-id="f2401-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2401-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-394">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-395">135</span><span class="sxs-lookup"><span data-stu-id="f2401-395">135</span></span></p></td>
<td><p><span data-ttu-id="f2401-396">DCOM y llamada a procedimiento remoto (RPC)</span><span class="sxs-lookup"><span data-stu-id="f2401-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-397">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-398">80</span><span class="sxs-lookup"><span data-stu-id="f2401-398">80</span></span></p></td>
<td><p><span data-ttu-id="f2401-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="f2401-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-400">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-401">8080</span><span class="sxs-lookup"><span data-stu-id="f2401-401">8080</span></span></p></td>
<td><p><span data-ttu-id="f2401-402">TCP - Recuperación cliente y dispositivo del certificado raíz del servidor de front-end – clientes y dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="f2401-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-403">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-404">443</span><span class="sxs-lookup"><span data-stu-id="f2401-404">443</span></span></p></td>
<td><p><span data-ttu-id="f2401-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2401-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-406">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-407">4443</span><span class="sxs-lookup"><span data-stu-id="f2401-407">4443</span></span></p></td>
<td><p><span data-ttu-id="f2401-408">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="f2401-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-409">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-410">5072</span><span class="sxs-lookup"><span data-stu-id="f2401-410">5072</span></span></p></td>
<td><p><span data-ttu-id="f2401-411">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-412">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-413">5073</span><span class="sxs-lookup"><span data-stu-id="f2401-413">5073</span></span></p></td>
<td><p><span data-ttu-id="f2401-414">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-415">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-416">5075</span><span class="sxs-lookup"><span data-stu-id="f2401-416">5075</span></span></p></td>
<td><p><span data-ttu-id="f2401-417">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-418">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-419">5076</span><span class="sxs-lookup"><span data-stu-id="f2401-419">5076</span></span></p></td>
<td><p><span data-ttu-id="f2401-420">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-421">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-422">5071</span><span class="sxs-lookup"><span data-stu-id="f2401-422">5071</span></span></p></td>
<td><p><span data-ttu-id="f2401-423">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-424">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-425">5080</span><span class="sxs-lookup"><span data-stu-id="f2401-425">5080</span></span></p></td>
<td><p><span data-ttu-id="f2401-426">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-427">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-428">448</span><span class="sxs-lookup"><span data-stu-id="f2401-428">448</span></span></p></td>
<td><p><span data-ttu-id="f2401-429">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-430">Equilibrador de carga del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="f2401-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-431">5070</span><span class="sxs-lookup"><span data-stu-id="f2401-431">5070</span></span></p></td>
<td><p><span data-ttu-id="f2401-432">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-433">Equilibrador de carga del servidor front-end (si el grupo también ejecuta el servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="f2401-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="f2401-434">5070</span><span class="sxs-lookup"><span data-stu-id="f2401-434">5070</span></span></p></td>
<td><p><span data-ttu-id="f2401-435">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-436">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="f2401-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-437">443</span><span class="sxs-lookup"><span data-stu-id="f2401-437">443</span></span></p></td>
<td><p><span data-ttu-id="f2401-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2401-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-439">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="f2401-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-440">444</span><span class="sxs-lookup"><span data-stu-id="f2401-440">444</span></span></p></td>
<td><p><span data-ttu-id="f2401-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2401-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-442">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="f2401-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-443">5061</span><span class="sxs-lookup"><span data-stu-id="f2401-443">5061</span></span></p></td>
<td><p><span data-ttu-id="f2401-444">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-445">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="f2401-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-446">4443</span><span class="sxs-lookup"><span data-stu-id="f2401-446">4443</span></span></p></td>
<td><p><span data-ttu-id="f2401-447">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="f2401-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2401-p107">Los grupos de servidores front-end y de directores que usan equilibrio de carga de DNS también deben tener implementado un equilibrador de carga de hardware. En la siguiente tabla se muestran los puertos que se deben abrir en estos equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="f2401-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="f2401-450">Puertos del equilibrador de carga de hardware si usa equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="f2401-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2401-451">Equilibrador de carga</span><span class="sxs-lookup"><span data-stu-id="f2401-451">Load Balancer</span></span></th>
<th><span data-ttu-id="f2401-452">Puerto</span><span class="sxs-lookup"><span data-stu-id="f2401-452">Port</span></span></th>
<th><span data-ttu-id="f2401-453">Protocolo</span><span class="sxs-lookup"><span data-stu-id="f2401-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2401-454">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-455">80</span><span class="sxs-lookup"><span data-stu-id="f2401-455">80</span></span></p></td>
<td><p><span data-ttu-id="f2401-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="f2401-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-457">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-458">443</span><span class="sxs-lookup"><span data-stu-id="f2401-458">443</span></span></p></td>
<td><p><span data-ttu-id="f2401-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2401-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-460">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-461">8080</span><span class="sxs-lookup"><span data-stu-id="f2401-461">8080</span></span></p></td>
<td><p><span data-ttu-id="f2401-462">TCP - Recuperación cliente y dispositivo del certificado raíz del servidor de front-end – clientes y dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="f2401-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-463">Equilibrador de carga del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f2401-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-464">4443</span><span class="sxs-lookup"><span data-stu-id="f2401-464">4443</span></span></p></td>
<td><p><span data-ttu-id="f2401-465">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="f2401-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-466">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="f2401-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-467">443</span><span class="sxs-lookup"><span data-stu-id="f2401-467">443</span></span></p></td>
<td><p><span data-ttu-id="f2401-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2401-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-469">Equilibrador de carga del director</span><span class="sxs-lookup"><span data-stu-id="f2401-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f2401-470">4443</span><span class="sxs-lookup"><span data-stu-id="f2401-470">4443</span></span></p></td>
<td><p><span data-ttu-id="f2401-471">HTTPS (desde proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="f2401-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="f2401-472">Puertos de cliente requeridos</span><span class="sxs-lookup"><span data-stu-id="f2401-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2401-473">Componente</span><span class="sxs-lookup"><span data-stu-id="f2401-473">Component</span></span></th>
<th><span data-ttu-id="f2401-474">Puerto</span><span class="sxs-lookup"><span data-stu-id="f2401-474">Port</span></span></th>
<th><span data-ttu-id="f2401-475">Protocolo</span><span class="sxs-lookup"><span data-stu-id="f2401-475">Protocol</span></span></th>
<th><span data-ttu-id="f2401-476">Notas</span><span class="sxs-lookup"><span data-stu-id="f2401-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2401-477">Clientes</span><span class="sxs-lookup"><span data-stu-id="f2401-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="f2401-478">67/68</span><span class="sxs-lookup"><span data-stu-id="f2401-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="f2401-479">DCHP</span><span class="sxs-lookup"><span data-stu-id="f2401-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-480">Lo usa Lync Server para buscar el FQDN del registrador (es decir, si se produce un error en el SRV de DNS y no se configura la configuración manual).</span><span class="sxs-lookup"><span data-stu-id="f2401-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-481">Clientes</span><span class="sxs-lookup"><span data-stu-id="f2401-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="f2401-482">443</span><span class="sxs-lookup"><span data-stu-id="f2401-482">443</span></span></p></td>
<td><p><span data-ttu-id="f2401-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-484">Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="f2401-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-485">Clientes</span><span class="sxs-lookup"><span data-stu-id="f2401-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="f2401-486">443</span><span class="sxs-lookup"><span data-stu-id="f2401-486">443</span></span></p></td>
<td><p><span data-ttu-id="f2401-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-488">Se usa para el acceso de usuarios externos a las sesiones de conferencia web.</span><span class="sxs-lookup"><span data-stu-id="f2401-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-489">Clientes</span><span class="sxs-lookup"><span data-stu-id="f2401-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="f2401-490">443</span><span class="sxs-lookup"><span data-stu-id="f2401-490">443</span></span></p></td>
<td><p><span data-ttu-id="f2401-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="f2401-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="f2401-492">Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP)</span><span class="sxs-lookup"><span data-stu-id="f2401-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-493">Clientes</span><span class="sxs-lookup"><span data-stu-id="f2401-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="f2401-494">3478</span><span class="sxs-lookup"><span data-stu-id="f2401-494">3478</span></span></p></td>
<td><p><span data-ttu-id="f2401-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="f2401-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="f2401-496">Se usa para el acceso de usuarios externos a las sesiones y los medios de a/V (UDP)</span><span class="sxs-lookup"><span data-stu-id="f2401-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-497">Clientes</span><span class="sxs-lookup"><span data-stu-id="f2401-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="f2401-498">5061</span><span class="sxs-lookup"><span data-stu-id="f2401-498">5061</span></span></p></td>
<td><p><span data-ttu-id="f2401-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f2401-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f2401-500">Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="f2401-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-501">Clientes</span><span class="sxs-lookup"><span data-stu-id="f2401-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="f2401-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="f2401-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="f2401-503">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-504">Se usa para la transferencia de archivos entre clientes de Lync y clientes anteriores (clientes de Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 y Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="f2401-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-505">Clientes</span><span class="sxs-lookup"><span data-stu-id="f2401-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="f2401-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f2401-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f2401-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f2401-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f2401-508">Intervalo de puertos de audio (se requieren 20 puertos como mínimo)</span><span class="sxs-lookup"><span data-stu-id="f2401-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-509">Clientes</span><span class="sxs-lookup"><span data-stu-id="f2401-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="f2401-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f2401-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f2401-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f2401-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f2401-512">Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo)</span><span class="sxs-lookup"><span data-stu-id="f2401-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-513">Clientes</span><span class="sxs-lookup"><span data-stu-id="f2401-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="f2401-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f2401-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f2401-515">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-516">Transferencias de archivos de punto a punto (para la transferencia de archivos de conferencia, los clientes usan PSOM).</span><span class="sxs-lookup"><span data-stu-id="f2401-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2401-517">Clientes</span><span class="sxs-lookup"><span data-stu-id="f2401-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="f2401-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f2401-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f2401-519">TCP</span><span class="sxs-lookup"><span data-stu-id="f2401-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-520">Uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f2401-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2401-521">Teléfono de área común Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="f2401-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="f2401-522">Teléfono de escritorio Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="f2401-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="f2401-523">HP 4110 IP Phone (teléfono de área común)</span><span class="sxs-lookup"><span data-stu-id="f2401-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="f2401-524">HP 4120 IP Phone (teléfono de escritorio)</span><span class="sxs-lookup"><span data-stu-id="f2401-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="f2401-525">Teléfono de área común Polycom CX500 IP</span><span class="sxs-lookup"><span data-stu-id="f2401-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="f2401-526">Teléfono de escritorio Polycom CX600 IP</span><span class="sxs-lookup"><span data-stu-id="f2401-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="f2401-527">Teléfono de escritorio Polycom CX700 IP</span><span class="sxs-lookup"><span data-stu-id="f2401-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="f2401-528">Teléfono de conferencia Polycom CX3000 IP</span><span class="sxs-lookup"><span data-stu-id="f2401-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="f2401-529">67/68</span><span class="sxs-lookup"><span data-stu-id="f2401-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="f2401-530">DCHP</span><span class="sxs-lookup"><span data-stu-id="f2401-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="f2401-531">Usada por los dispositivos enumerados para buscar el certificado de Lync Server, el FQDN de aprovisionamiento y el FQDN del registrador.</span><span class="sxs-lookup"><span data-stu-id="f2401-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2401-532">**\*** Para configurar los puertos específicos para estos tipos de medios, use el cmdlet CsConferencingConfiguration (los parámetros clientmediaportrangeenabled, ClientMediaPort y ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="f2401-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2401-533">Los clientes de set programs for Lync crean automáticamente las excepciones de firewall del sistema operativo necesarias en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="f2401-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f2401-534">Los puertos que se utilizan para el acceso de usuarios externos son necesarios en cualquier escenario en el que el cliente deba atravesar el firewall de la organización (por ejemplo, las comunicaciones o reuniones externas alojadas por otras organizaciones).</span><span class="sxs-lookup"><span data-stu-id="f2401-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

