---
title: 'Lync Server 2013: Resumen de Puerto-grupo de Director escalado, equilibrador de carga de hardware'
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
ms.openlocfilehash: 18c0957d66d9b877a67819b8fd8d46d4e614cdad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="2b260-102">Resumen de Puerto-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b260-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b260-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="2b260-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="2b260-104">Los requisitos de puertos de Firewall para un grupo de directores constan de los puertos que se usan para establecer la comunicación con el director desde la interfaz interna del servidor perimetral o la interfaz de conexión interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="2b260-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="2b260-105">De forma predeterminada, Microsoft Lync Server 2013 espera que se abran los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 desde el proxy inverso al Director, así como al grupo de servidores front-end y al servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="2b260-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="2b260-106">Además, debe haber comunicación del Protocolo de inicio de sesión (SIP) desde la interfaz interna del servidor perimetral hasta el director y el grupo de servidores front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="2b260-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="2b260-107">El protocolo SIP utiliza SIP/MTLS/TCP 5061 del servidor perimetral para el grupo de servidores front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="2b260-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="2b260-108">También se debe crear una regla que permita la comunicación SIP/MTLS/TCP 5061 desde el director, el grupo de servidores front-end y el servidor front-end hacia la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="2b260-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="2b260-109">Protocolos y puertos del Director para la definición de puertos</span><span class="sxs-lookup"><span data-stu-id="2b260-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b260-110">Rol/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="2b260-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="2b260-111">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="2b260-111">Source IP address</span></span></th>
<th><span data-ttu-id="2b260-112">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="2b260-112">Destination IP address</span></span></th>
<th><span data-ttu-id="2b260-113">Notas</span><span class="sxs-lookup"><span data-stu-id="2b260-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b260-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="2b260-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="2b260-115">Interfaz interna de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="2b260-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="2b260-116">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="2b260-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="2b260-117">Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios Web de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="2b260-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b260-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="2b260-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="2b260-119">Interfaz interna de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="2b260-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="2b260-120">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="2b260-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="2b260-121">Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios Web de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="2b260-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b260-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="2b260-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="2b260-123">Dirección</span><span class="sxs-lookup"><span data-stu-id="2b260-123">Director</span></span></p></td>
<td><p><span data-ttu-id="2b260-124">Servidor front-end o grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="2b260-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="2b260-125">Comunicación entre servidores entre el director HLB VIP y los servidores front-end</span><span class="sxs-lookup"><span data-stu-id="2b260-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b260-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="2b260-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="2b260-127">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="2b260-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="2b260-128">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="2b260-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="2b260-129">El director proporciona servicios web a clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="2b260-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b260-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="2b260-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="2b260-131">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="2b260-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="2b260-132">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="2b260-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="2b260-133">El director proporciona servicios web a clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="2b260-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b260-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="2b260-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="2b260-135">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="2b260-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2b260-136">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="2b260-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="2b260-137">Comunicación SIP del servidor perimetral al Director y a los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2b260-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b260-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="2b260-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="2b260-139">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="2b260-139">Any</span></span></p></td>
<td><p><span data-ttu-id="2b260-140">Dirección</span><span class="sxs-lookup"><span data-stu-id="2b260-140">Director</span></span></p></td>
<td><p><span data-ttu-id="2b260-141">Controlador del servicio de registro centralizado (ClsController. exe) o comandos del agente (ClsAgent. exe) y colección de registros</span><span class="sxs-lookup"><span data-stu-id="2b260-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b260-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="2b260-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="2b260-143">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="2b260-143">Any</span></span></p></td>
<td><p><span data-ttu-id="2b260-144">Dirección</span><span class="sxs-lookup"><span data-stu-id="2b260-144">Director</span></span></p></td>
<td><p><span data-ttu-id="2b260-145">Controlador del servicio de registro centralizado (ClsController. exe) o comandos del agente (ClsAgent. exe) y colección de registros</span><span class="sxs-lookup"><span data-stu-id="2b260-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b260-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="2b260-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="2b260-147">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="2b260-147">Any</span></span></p></td>
<td><p><span data-ttu-id="2b260-148">Dirección</span><span class="sxs-lookup"><span data-stu-id="2b260-148">Director</span></span></p></td>
<td><p><span data-ttu-id="2b260-149">Controlador del servicio de registro centralizado (ClsController. exe) o comandos del agente (ClsAgent. exe) y colección de registros</span><span class="sxs-lookup"><span data-stu-id="2b260-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

