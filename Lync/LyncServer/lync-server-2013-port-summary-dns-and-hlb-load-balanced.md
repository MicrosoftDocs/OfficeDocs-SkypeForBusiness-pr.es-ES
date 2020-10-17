---
title: 'Lync Server 2013: Resumen de Puerto-carga equilibrada DNS y HLB'
description: 'Lync Server 2013: Resumen de Puerto-carga equilibrada DNS y HLB.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be2e8204e792fd9c4718cb9171e90784af2d0104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543136"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="1b7a3-103">Resumen de Puerto-carga equilibrada DNS y HLB en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b7a3-103">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b7a3-104">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1b7a3-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1b7a3-105">Los requisitos de puerto de Firewall para un solo Director constan de los puertos que se usan para establecer la comunicación con el director desde la interfaz interna o la red interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="1b7a3-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="1b7a3-106">De forma predeterminada, Microsoft Lync Server 2013 espera que se abran los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 desde el proxy inverso al Director, así como al grupo de servidores front-end y al servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1b7a3-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="1b7a3-107">Además, debe haber comunicación del Protocolo de inicio de sesión (SIP) desde la interfaz interna del servidor perimetral hasta el director y el grupo de servidores front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1b7a3-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="1b7a3-108">El protocolo SIP utiliza SIP/MTLS/TCP 5061 del servidor perimetral para el grupo de servidores front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1b7a3-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="1b7a3-109">También se debe crear una regla que permita la comunicación SIP/MTLS/TCP 5061 desde el director, el grupo de servidores front-end y el servidor front-end hacia la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="1b7a3-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="1b7a3-110">Puertos y protocolos de un solo Director para definiciones de Firewall</span><span class="sxs-lookup"><span data-stu-id="1b7a3-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b7a3-111">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="1b7a3-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1b7a3-112">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="1b7a3-112">Source IP address</span></span></th>
<th><span data-ttu-id="1b7a3-113">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="1b7a3-113">Destination IP address</span></span></th>
<th><span data-ttu-id="1b7a3-114">Notas</span><span class="sxs-lookup"><span data-stu-id="1b7a3-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b7a3-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="1b7a3-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-116">Interfaz interna de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="1b7a3-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-117">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="1b7a3-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-118">Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios web del servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1b7a3-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7a3-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="1b7a3-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-120">Interfaz interna de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="1b7a3-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-121">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="1b7a3-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-122">Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios web del servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1b7a3-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7a3-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="1b7a3-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-124">Director</span><span class="sxs-lookup"><span data-stu-id="1b7a3-124">Director</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-125">Grupo de servidores front-end o servidor front-end</span><span class="sxs-lookup"><span data-stu-id="1b7a3-125">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-126">Comunicación entre servidores entre el director HLB VIP y el servidor front-end o el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1b7a3-126">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7a3-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="1b7a3-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-128">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="1b7a3-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-129">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="1b7a3-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-130">El director proporciona servicios web a clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="1b7a3-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7a3-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="1b7a3-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-132">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="1b7a3-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-133">Director VIP del equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="1b7a3-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-134">El director proporciona servicios web a clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="1b7a3-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7a3-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="1b7a3-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-136">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="1b7a3-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-137">Director</span><span class="sxs-lookup"><span data-stu-id="1b7a3-137">Director</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-138">Comunicación SIP del servidor perimetral al Director, así como los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="1b7a3-138">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7a3-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="1b7a3-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-140">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="1b7a3-140">Any</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-141">Director</span><span class="sxs-lookup"><span data-stu-id="1b7a3-141">Director</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-142">Controlador del servicio de registro centralizado (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registros</span><span class="sxs-lookup"><span data-stu-id="1b7a3-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7a3-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="1b7a3-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-144">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="1b7a3-144">Any</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-145">Director</span><span class="sxs-lookup"><span data-stu-id="1b7a3-145">Director</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-146">Controlador del servicio de registro centralizado (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registros</span><span class="sxs-lookup"><span data-stu-id="1b7a3-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7a3-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="1b7a3-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-148">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="1b7a3-148">Any</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-149">Director</span><span class="sxs-lookup"><span data-stu-id="1b7a3-149">Director</span></span></p></td>
<td><p><span data-ttu-id="1b7a3-150">Controlador del servicio de registro centralizado (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registros</span><span class="sxs-lookup"><span data-stu-id="1b7a3-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

