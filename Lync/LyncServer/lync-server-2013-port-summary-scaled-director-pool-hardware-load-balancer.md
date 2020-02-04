---
title: 'Lync Server 2013: Resumen de puerto - Grupo de director escalado, equilibrador de carga de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdf054ee603f2c0917e35bdd2f19d108094c7c78
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="25402-102">Resumen de puerto - Grupo de director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25402-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25402-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="25402-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="25402-104">Los requisitos de puerto de Firewall para un grupo de directores consisten en los puertos que se usan para establecer comunicación con el director desde la interfaz interna del servidor perimetral o la interfaz interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="25402-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="25402-105">Microsoft Lync Server 2013 espera de forma predeterminada que los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 se abran desde el proxy inverso al Director, así como el servidor front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="25402-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="25402-106">Además, debe haber comunicación del Protocolo de inicio de sesión (SIP) desde la interfaz interna del servidor perimetral al Director y al grupo de servidores front-end y front-end.</span><span class="sxs-lookup"><span data-stu-id="25402-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="25402-107">El protocolo SIP usa SIP/MTLS/TCP 5061 del servidor perimetral al grupo front-end y al servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="25402-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="25402-108">También se debe crear una regla que permita la comunicación SIP/MTLS/TCP 5061 desde el director, el grupo de servidores front-end y el servidor front-end a la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="25402-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="25402-109">Puertos y protocolos de directores para definiciones de Firewall</span><span class="sxs-lookup"><span data-stu-id="25402-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25402-110">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="25402-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="25402-111">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="25402-111">Source IP address</span></span></th>
<th><span data-ttu-id="25402-112">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="25402-112">Destination IP address</span></span></th>
<th><span data-ttu-id="25402-113">Notas</span><span class="sxs-lookup"><span data-stu-id="25402-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25402-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="25402-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="25402-115">Interfaz interna de proxy invertida</span><span class="sxs-lookup"><span data-stu-id="25402-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="25402-116">Director VIP de equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="25402-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="25402-117">Inicialmente recibido por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios Web de los servidores front-end</span><span class="sxs-lookup"><span data-stu-id="25402-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25402-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="25402-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="25402-119">Interfaz interna de proxy invertida</span><span class="sxs-lookup"><span data-stu-id="25402-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="25402-120">Director VIP de equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="25402-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="25402-121">Inicialmente recibido por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios Web de los servidores front-end</span><span class="sxs-lookup"><span data-stu-id="25402-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25402-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="25402-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="25402-123">Director</span><span class="sxs-lookup"><span data-stu-id="25402-123">Director</span></span></p></td>
<td><p><span data-ttu-id="25402-124">Servidor front-end o grupo front-end</span><span class="sxs-lookup"><span data-stu-id="25402-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="25402-125">Comunicación entre servidores entre el director HLB VIP y los servidores front-end</span><span class="sxs-lookup"><span data-stu-id="25402-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25402-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="25402-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="25402-127">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="25402-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="25402-128">Director VIP de equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="25402-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="25402-129">El director proporciona servicios web a clientes externos y internos.</span><span class="sxs-lookup"><span data-stu-id="25402-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25402-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="25402-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="25402-131">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="25402-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="25402-132">Director VIP de equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="25402-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="25402-133">El director proporciona servicios web a clientes externos y internos.</span><span class="sxs-lookup"><span data-stu-id="25402-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25402-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="25402-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="25402-135">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="25402-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="25402-136">Director VIP de equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="25402-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="25402-137">Comunicación SIP desde el servidor perimetral al Director y a los servidores de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="25402-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25402-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="25402-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="25402-139">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="25402-139">Any</span></span></p></td>
<td><p><span data-ttu-id="25402-140">Director</span><span class="sxs-lookup"><span data-stu-id="25402-140">Director</span></span></p></td>
<td><p><span data-ttu-id="25402-141">Comandos del controlador de registro centralizado (ClsController. exe) o agente (ClsAgent. exe) y recopilación de registros</span><span class="sxs-lookup"><span data-stu-id="25402-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25402-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="25402-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="25402-143">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="25402-143">Any</span></span></p></td>
<td><p><span data-ttu-id="25402-144">Director</span><span class="sxs-lookup"><span data-stu-id="25402-144">Director</span></span></p></td>
<td><p><span data-ttu-id="25402-145">Comandos del controlador de registro centralizado (ClsController. exe) o agente (ClsAgent. exe) y recopilación de registros</span><span class="sxs-lookup"><span data-stu-id="25402-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25402-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="25402-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="25402-147">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="25402-147">Any</span></span></p></td>
<td><p><span data-ttu-id="25402-148">Director</span><span class="sxs-lookup"><span data-stu-id="25402-148">Director</span></span></p></td>
<td><p><span data-ttu-id="25402-149">Comandos del controlador de registro centralizado (ClsController. exe) o agente (ClsAgent. exe) y recopilación de registros</span><span class="sxs-lookup"><span data-stu-id="25402-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

