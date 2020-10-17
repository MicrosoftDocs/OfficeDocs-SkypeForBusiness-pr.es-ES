---
title: 'Lync Server 2013: Resumen de Puerto-grupo de Director escalado, equilibrador de carga de hardware'
description: 'Lync Server 2013: Resumen de Puerto-grupo de Director escalado, equilibrador de carga de hardware.'
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
ms.openlocfilehash: 10bfb3a3ad3a38b6cb0e46414bf22deecc71d7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564556"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="653eb-103">Resumen de Puerto-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="653eb-103">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="653eb-104">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="653eb-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="653eb-105">Los requisitos de puertos de Firewall para un grupo de directores constan de los puertos que se usan para establecer la comunicación con el director desde la interfaz interna del servidor perimetral o la interfaz de conexión interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="653eb-105">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="653eb-106">De forma predeterminada, Microsoft Lync Server 2013 espera que se abran los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 desde el proxy inverso al Director, así como al grupo de servidores front-end y al servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="653eb-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="653eb-107">Además, debe haber comunicación del Protocolo de inicio de sesión (SIP) desde la interfaz interna del servidor perimetral hasta el director y el grupo de servidores front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="653eb-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="653eb-108">El protocolo SIP utiliza SIP/MTLS/TCP 5061 del servidor perimetral para el grupo de servidores front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="653eb-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="653eb-109">También se debe crear una regla que permita la comunicación SIP/MTLS/TCP 5061 desde el director, el grupo de servidores front-end y el servidor front-end hacia la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="653eb-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="653eb-110">Protocolos y puertos del Director para la definición de puertos</span><span class="sxs-lookup"><span data-stu-id="653eb-110">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="653eb-111">Rol/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="653eb-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="653eb-112">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="653eb-112">Source IP address</span></span></th>
<th><span data-ttu-id="653eb-113">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="653eb-113">Destination IP address</span></span></th>
<th><span data-ttu-id="653eb-114">Notas</span><span class="sxs-lookup"><span data-stu-id="653eb-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="653eb-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="653eb-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="653eb-116">Interfaz interna de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="653eb-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="653eb-117">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="653eb-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="653eb-118">Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios Web de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="653eb-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="653eb-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="653eb-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="653eb-120">Interfaz interna de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="653eb-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="653eb-121">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="653eb-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="653eb-122">Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios Web de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="653eb-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="653eb-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="653eb-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="653eb-124">Director</span><span class="sxs-lookup"><span data-stu-id="653eb-124">Director</span></span></p></td>
<td><p><span data-ttu-id="653eb-125">Servidor front-end o grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="653eb-125">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="653eb-126">Comunicación entre servidores entre el director HLB VIP y los servidores front-end</span><span class="sxs-lookup"><span data-stu-id="653eb-126">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="653eb-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="653eb-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="653eb-128">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="653eb-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="653eb-129">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="653eb-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="653eb-130">El director proporciona servicios web a clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="653eb-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="653eb-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="653eb-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="653eb-132">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="653eb-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="653eb-133">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="653eb-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="653eb-134">El director proporciona servicios web a clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="653eb-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="653eb-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="653eb-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="653eb-136">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="653eb-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="653eb-137">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="653eb-137">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="653eb-138">Comunicación SIP del servidor perimetral al Director y a los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="653eb-138">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="653eb-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="653eb-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="653eb-140">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="653eb-140">Any</span></span></p></td>
<td><p><span data-ttu-id="653eb-141">Director</span><span class="sxs-lookup"><span data-stu-id="653eb-141">Director</span></span></p></td>
<td><p><span data-ttu-id="653eb-142">Controlador del servicio de registro centralizado (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registros</span><span class="sxs-lookup"><span data-stu-id="653eb-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="653eb-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="653eb-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="653eb-144">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="653eb-144">Any</span></span></p></td>
<td><p><span data-ttu-id="653eb-145">Director</span><span class="sxs-lookup"><span data-stu-id="653eb-145">Director</span></span></p></td>
<td><p><span data-ttu-id="653eb-146">Controlador del servicio de registro centralizado (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registros</span><span class="sxs-lookup"><span data-stu-id="653eb-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="653eb-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="653eb-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="653eb-148">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="653eb-148">Any</span></span></p></td>
<td><p><span data-ttu-id="653eb-149">Director</span><span class="sxs-lookup"><span data-stu-id="653eb-149">Director</span></span></p></td>
<td><p><span data-ttu-id="653eb-150">Controlador del servicio de registro centralizado (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registros</span><span class="sxs-lookup"><span data-stu-id="653eb-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

