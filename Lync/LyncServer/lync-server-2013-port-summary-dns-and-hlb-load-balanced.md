---
title: 'Lync Server 2013: Resumen de puerto - Carga equilibrada DNS y HLB'
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
ms.openlocfilehash: eb594057977fbe39f6be6a9a9c678806d7e2d8dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="95721-102">Resumen de puerto - Carga equilibrada DNS y HLB en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95721-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95721-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="95721-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="95721-104">Los requisitos del puerto de Firewall para un único Director son los puertos que se usan para establecer comunicación con el director desde la interfaz interna o la red interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="95721-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="95721-105">Microsoft Lync Server 2013 espera de forma predeterminada que los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 se abran desde el proxy inverso al Director, así como el servidor front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="95721-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="95721-106">Además, debe haber comunicación del Protocolo de inicio de sesión (SIP) desde la interfaz interna del servidor perimetral al Director y al grupo de servidores front-end y front-end.</span><span class="sxs-lookup"><span data-stu-id="95721-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="95721-107">El protocolo SIP usa SIP/MTLS/TCP 5061 del servidor perimetral al grupo front-end y al servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="95721-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="95721-108">También se debe crear una regla que permita la comunicación SIP/MTLS/TCP 5061 desde el director, el grupo de servidores front-end y el servidor front-end a la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="95721-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="95721-109">Puertos y protocolos de un solo Director para definiciones de Firewall</span><span class="sxs-lookup"><span data-stu-id="95721-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95721-110">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="95721-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="95721-111">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="95721-111">Source IP address</span></span></th>
<th><span data-ttu-id="95721-112">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="95721-112">Destination IP address</span></span></th>
<th><span data-ttu-id="95721-113">Notas</span><span class="sxs-lookup"><span data-stu-id="95721-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95721-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="95721-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="95721-115">Interfaz interna de proxy invertida</span><span class="sxs-lookup"><span data-stu-id="95721-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="95721-116">Director VIP de equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="95721-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="95721-117">Inicialmente recibido por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios Web de servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="95721-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95721-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="95721-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="95721-119">Interfaz interna de proxy invertida</span><span class="sxs-lookup"><span data-stu-id="95721-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="95721-120">Director VIP de equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="95721-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="95721-121">Inicialmente recibido por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios Web de servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="95721-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95721-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="95721-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="95721-123">Director</span><span class="sxs-lookup"><span data-stu-id="95721-123">Director</span></span></p></td>
<td><p><span data-ttu-id="95721-124">Grupo de servidores front-end o servidor front-end</span><span class="sxs-lookup"><span data-stu-id="95721-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="95721-125">Comunicación entre servidores entre el director HLB VIP y el servidor front-end o front-end.</span><span class="sxs-lookup"><span data-stu-id="95721-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95721-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="95721-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="95721-127">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="95721-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="95721-128">Director VIP de equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="95721-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="95721-129">El director proporciona servicios web a clientes externos y internos.</span><span class="sxs-lookup"><span data-stu-id="95721-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95721-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="95721-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="95721-131">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="95721-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="95721-132">Director VIP de equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="95721-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="95721-133">El director proporciona servicios web a clientes externos y internos.</span><span class="sxs-lookup"><span data-stu-id="95721-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95721-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="95721-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="95721-135">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="95721-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="95721-136">Director</span><span class="sxs-lookup"><span data-stu-id="95721-136">Director</span></span></p></td>
<td><p><span data-ttu-id="95721-137">Comunicación SIP desde el servidor perimetral al Director, así como a los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="95721-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95721-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="95721-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="95721-139">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="95721-139">Any</span></span></p></td>
<td><p><span data-ttu-id="95721-140">Director</span><span class="sxs-lookup"><span data-stu-id="95721-140">Director</span></span></p></td>
<td><p><span data-ttu-id="95721-141">Comandos del controlador de registro centralizado (ClsController. exe) o agente (ClsAgent. exe) y recopilación de registros</span><span class="sxs-lookup"><span data-stu-id="95721-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95721-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="95721-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="95721-143">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="95721-143">Any</span></span></p></td>
<td><p><span data-ttu-id="95721-144">Director</span><span class="sxs-lookup"><span data-stu-id="95721-144">Director</span></span></p></td>
<td><p><span data-ttu-id="95721-145">Comandos del controlador de registro centralizado (ClsController. exe) o agente (ClsAgent. exe) y recopilación de registros</span><span class="sxs-lookup"><span data-stu-id="95721-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95721-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="95721-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="95721-147">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="95721-147">Any</span></span></p></td>
<td><p><span data-ttu-id="95721-148">Director</span><span class="sxs-lookup"><span data-stu-id="95721-148">Director</span></span></p></td>
<td><p><span data-ttu-id="95721-149">Comandos del controlador de registro centralizado (ClsController. exe) o agente (ClsAgent. exe) y recopilación de registros</span><span class="sxs-lookup"><span data-stu-id="95721-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

