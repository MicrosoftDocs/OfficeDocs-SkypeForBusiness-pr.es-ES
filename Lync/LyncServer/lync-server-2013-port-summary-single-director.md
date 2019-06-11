---
title: 'Lync Server 2013: Resumen del puerto - Director único'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5568a37093f161caef6717df5d3a3f09be6f18c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="e74a2-102">Resumen del puerto - Director único en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74a2-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e74a2-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e74a2-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e74a2-104">Los requisitos del puerto de Firewall para un único Director son los puertos que se usan para establecer comunicación con el director desde la interfaz interna o la red interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="e74a2-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="e74a2-105">Microsoft Lync Server 2013 espera de forma predeterminada que los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 se abran desde el proxy inverso al Director, así como el servidor front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e74a2-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="e74a2-106">Además, debe haber comunicación del Protocolo de inicio de sesión (SIP) desde la interfaz interna del servidor perimetral al Director y al grupo de servidores front-end y front-end.</span><span class="sxs-lookup"><span data-stu-id="e74a2-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="e74a2-107">El protocolo SIP usa SIP/MTLS/TCP 5061 del servidor perimetral al grupo front-end y al servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e74a2-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="e74a2-108">También se debe crear una regla que permita la comunicación SIP/MTLS/TCP 5061 desde el director, el grupo de servidores front-end y el servidor front-end a la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="e74a2-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="e74a2-109">Puertos y protocolos de un solo Director para definiciones de Firewall</span><span class="sxs-lookup"><span data-stu-id="e74a2-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e74a2-110">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="e74a2-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e74a2-111">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="e74a2-111">Source IP address</span></span></th>
<th><span data-ttu-id="e74a2-112">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="e74a2-112">Destination IP address</span></span></th>
<th><span data-ttu-id="e74a2-113">Notas</span><span class="sxs-lookup"><span data-stu-id="e74a2-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e74a2-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="e74a2-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="e74a2-115">Interfaz interna de proxy invertida</span><span class="sxs-lookup"><span data-stu-id="e74a2-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="e74a2-116">Director</span><span class="sxs-lookup"><span data-stu-id="e74a2-116">Director</span></span></p></td>
<td><p><span data-ttu-id="e74a2-117">Inicialmente recibido por el lado externo del proxy inverso, la comunicación se envía al Director y a los servicios Web de servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e74a2-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74a2-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="e74a2-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="e74a2-119">Interfaz interna de proxy invertida</span><span class="sxs-lookup"><span data-stu-id="e74a2-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="e74a2-120">Director</span><span class="sxs-lookup"><span data-stu-id="e74a2-120">Director</span></span></p></td>
<td><p><span data-ttu-id="e74a2-121">Inicialmente recibido por el lado externo del proxy inverso, la comunicación se envía al Director y a los servicios Web de servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e74a2-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74a2-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="e74a2-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="e74a2-123">Director</span><span class="sxs-lookup"><span data-stu-id="e74a2-123">Director</span></span></p></td>
<td><p><span data-ttu-id="e74a2-124">Servidor front-end o grupo front-end</span><span class="sxs-lookup"><span data-stu-id="e74a2-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="e74a2-125">Comunicación entre servidores entre el director y el servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e74a2-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74a2-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="e74a2-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="e74a2-127">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="e74a2-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="e74a2-128">Servicios Web de Director</span><span class="sxs-lookup"><span data-stu-id="e74a2-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="e74a2-129">El director proporciona servicios web a clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="e74a2-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74a2-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="e74a2-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="e74a2-131">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="e74a2-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="e74a2-132">Servicios Web de Director</span><span class="sxs-lookup"><span data-stu-id="e74a2-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="e74a2-133">El director proporciona servicios web a clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="e74a2-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74a2-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="e74a2-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="e74a2-135">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e74a2-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e74a2-136">Director</span><span class="sxs-lookup"><span data-stu-id="e74a2-136">Director</span></span></p></td>
<td><p><span data-ttu-id="e74a2-137">Comunicación SIP desde el servidor perimetral al Director y al servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e74a2-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74a2-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="e74a2-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="e74a2-139">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e74a2-139">Any</span></span></p></td>
<td><p><span data-ttu-id="e74a2-140">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e74a2-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e74a2-141">Comandos del controlador de registro centralizado (ClsController. exe) o agente (ClasAgent. exe) y recopilación de registros</span><span class="sxs-lookup"><span data-stu-id="e74a2-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74a2-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="e74a2-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="e74a2-143">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e74a2-143">Any</span></span></p></td>
<td><p><span data-ttu-id="e74a2-144">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e74a2-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e74a2-145">Comandos del controlador de registro centralizado (ClsController. exe) o agente (ClasAgent. exe) y recopilación de registros</span><span class="sxs-lookup"><span data-stu-id="e74a2-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74a2-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="e74a2-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="e74a2-147">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e74a2-147">Any</span></span></p></td>
<td><p><span data-ttu-id="e74a2-148">Interfaz interna de Edge Server</span><span class="sxs-lookup"><span data-stu-id="e74a2-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e74a2-149">Comandos del controlador de registro centralizado (ClsController. exe) o agente (ClasAgent. exe) y recopilación de registros</span><span class="sxs-lookup"><span data-stu-id="e74a2-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

