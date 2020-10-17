---
title: 'Lync Server 2013: Resumen de Puerto-Director único'
description: 'Lync Server 2013: Resumen de Puerto-Director único.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a46e394121dbc7dd6158016d39511e9487cec1ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566376"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="fab4c-103">Resumen de Puerto-Director único en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fab4c-103">Port summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fab4c-104">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="fab4c-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="fab4c-105">Los requisitos de puerto de Firewall para un solo Director constan de los puertos que se usan para establecer la comunicación con el director desde la interfaz interna o la red interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="fab4c-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="fab4c-106">De forma predeterminada, Microsoft Lync Server 2013 espera que se abran los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 desde el proxy inverso al Director, así como al grupo de servidores front-end y al servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="fab4c-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="fab4c-107">Además, debe haber comunicación del Protocolo de inicio de sesión (SIP) desde la interfaz interna del servidor perimetral hasta el director y el grupo de servidores front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="fab4c-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="fab4c-108">El protocolo SIP utiliza SIP/MTLS/TCP 5061 del servidor perimetral para el grupo de servidores front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="fab4c-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="fab4c-109">También se debe crear una regla que permita la comunicación SIP/MTLS/TCP 5061 desde el director, el grupo de servidores front-end y el servidor front-end hacia la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="fab4c-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="fab4c-110">Puertos y protocolos de un solo Director para definiciones de Firewall</span><span class="sxs-lookup"><span data-stu-id="fab4c-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fab4c-111">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="fab4c-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="fab4c-112">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="fab4c-112">Source IP address</span></span></th>
<th><span data-ttu-id="fab4c-113">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="fab4c-113">Destination IP address</span></span></th>
<th><span data-ttu-id="fab4c-114">Notas</span><span class="sxs-lookup"><span data-stu-id="fab4c-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fab4c-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="fab4c-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="fab4c-116">Interfaz interna de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="fab4c-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="fab4c-117">Director</span><span class="sxs-lookup"><span data-stu-id="fab4c-117">Director</span></span></p></td>
<td><p><span data-ttu-id="fab4c-118">Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director y a los servicios web del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="fab4c-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab4c-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="fab4c-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="fab4c-120">Interfaz interna de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="fab4c-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="fab4c-121">Director</span><span class="sxs-lookup"><span data-stu-id="fab4c-121">Director</span></span></p></td>
<td><p><span data-ttu-id="fab4c-122">Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director y a los servicios web del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="fab4c-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab4c-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="fab4c-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="fab4c-124">Director</span><span class="sxs-lookup"><span data-stu-id="fab4c-124">Director</span></span></p></td>
<td><p><span data-ttu-id="fab4c-125">Servidor front-end o grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="fab4c-125">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="fab4c-126">Comunicación entre servidores entre el director y el servidor front-end</span><span class="sxs-lookup"><span data-stu-id="fab4c-126">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab4c-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="fab4c-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="fab4c-128">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="fab4c-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="fab4c-129">Servicios Web de Director</span><span class="sxs-lookup"><span data-stu-id="fab4c-129">Director web services</span></span></p></td>
<td><p><span data-ttu-id="fab4c-130">El director proporciona servicios web a los clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="fab4c-130">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab4c-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="fab4c-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="fab4c-132">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="fab4c-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="fab4c-133">Servicios Web de Director</span><span class="sxs-lookup"><span data-stu-id="fab4c-133">Director web services</span></span></p></td>
<td><p><span data-ttu-id="fab4c-134">El director proporciona servicios web a los clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="fab4c-134">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab4c-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="fab4c-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="fab4c-136">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="fab4c-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fab4c-137">Director</span><span class="sxs-lookup"><span data-stu-id="fab4c-137">Director</span></span></p></td>
<td><p><span data-ttu-id="fab4c-138">Comunicación SIP desde el servidor perimetral al Director y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="fab4c-138">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab4c-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="fab4c-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="fab4c-140">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="fab4c-140">Any</span></span></p></td>
<td><p><span data-ttu-id="fab4c-141">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="fab4c-141">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fab4c-142">Controlador del Servicio de registro centralizado (ClsController.exe) o comandos y colección de registro del agente (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="fab4c-142">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab4c-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="fab4c-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="fab4c-144">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="fab4c-144">Any</span></span></p></td>
<td><p><span data-ttu-id="fab4c-145">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="fab4c-145">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fab4c-146">Comandos y recopilación de datos de registro del controlador del Servicio de registro centralizado (ClsController.exe) o el agente (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="fab4c-146">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab4c-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="fab4c-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="fab4c-148">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="fab4c-148">Any</span></span></p></td>
<td><p><span data-ttu-id="fab4c-149">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="fab4c-149">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fab4c-150">Controlador del Servicio de registro centralizado (ClsController.exe) o comandos y colección de registro del agente (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="fab4c-150">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

