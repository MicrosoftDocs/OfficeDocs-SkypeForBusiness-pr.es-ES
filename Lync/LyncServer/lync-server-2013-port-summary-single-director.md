---
title: 'Lync Server 2013: Resumen de Puerto-Director único'
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
ms.openlocfilehash: 95ae1ada828ea4ad3c6bdd2c863333c911635ff8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="8d909-102">Resumen de Puerto-Director único en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d909-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d909-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="8d909-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="8d909-104">Los requisitos de puerto de Firewall para un solo Director constan de los puertos que se usan para establecer la comunicación con el director desde la interfaz interna o la red interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="8d909-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="8d909-105">De forma predeterminada, Microsoft Lync Server 2013 espera que se abran los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 desde el proxy inverso al Director, así como al grupo de servidores front-end y al servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="8d909-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="8d909-106">Además, debe haber comunicación del Protocolo de inicio de sesión (SIP) desde la interfaz interna del servidor perimetral hasta el director y el grupo de servidores front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="8d909-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="8d909-107">El protocolo SIP utiliza SIP/MTLS/TCP 5061 del servidor perimetral para el grupo de servidores front-end y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="8d909-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="8d909-108">También se debe crear una regla que permita la comunicación SIP/MTLS/TCP 5061 desde el director, el grupo de servidores front-end y el servidor front-end hacia la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="8d909-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="8d909-109">Puertos y protocolos de un solo Director para definiciones de Firewall</span><span class="sxs-lookup"><span data-stu-id="8d909-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d909-110">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="8d909-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8d909-111">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="8d909-111">Source IP address</span></span></th>
<th><span data-ttu-id="8d909-112">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="8d909-112">Destination IP address</span></span></th>
<th><span data-ttu-id="8d909-113">Notas</span><span class="sxs-lookup"><span data-stu-id="8d909-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d909-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="8d909-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="8d909-115">Interfaz interna de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="8d909-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d909-116">Dirección</span><span class="sxs-lookup"><span data-stu-id="8d909-116">Director</span></span></p></td>
<td><p><span data-ttu-id="8d909-117">Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director y a los servicios web del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="8d909-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d909-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="8d909-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="8d909-119">Interfaz interna de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="8d909-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d909-120">Dirección</span><span class="sxs-lookup"><span data-stu-id="8d909-120">Director</span></span></p></td>
<td><p><span data-ttu-id="8d909-121">Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director y a los servicios web del servidor front-end</span><span class="sxs-lookup"><span data-stu-id="8d909-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d909-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="8d909-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="8d909-123">Dirección</span><span class="sxs-lookup"><span data-stu-id="8d909-123">Director</span></span></p></td>
<td><p><span data-ttu-id="8d909-124">Servidor front-end o grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="8d909-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="8d909-125">Comunicación entre servidores entre el director y el servidor front-end</span><span class="sxs-lookup"><span data-stu-id="8d909-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d909-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="8d909-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="8d909-127">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="8d909-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="8d909-128">Servicios Web de Director</span><span class="sxs-lookup"><span data-stu-id="8d909-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="8d909-129">El director proporciona servicios web a los clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="8d909-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d909-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="8d909-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="8d909-131">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="8d909-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="8d909-132">Servicios Web de Director</span><span class="sxs-lookup"><span data-stu-id="8d909-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="8d909-133">El director proporciona servicios web a los clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="8d909-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d909-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="8d909-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="8d909-135">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8d909-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d909-136">Dirección</span><span class="sxs-lookup"><span data-stu-id="8d909-136">Director</span></span></p></td>
<td><p><span data-ttu-id="8d909-137">Comunicación SIP desde el servidor perimetral al Director y el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="8d909-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d909-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="8d909-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="8d909-139">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8d909-139">Any</span></span></p></td>
<td><p><span data-ttu-id="8d909-140">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8d909-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d909-141">Controlador del Servicio de registro centralizado (ClsController.exe) o comandos y colección de registro del agente (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="8d909-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d909-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="8d909-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="8d909-143">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8d909-143">Any</span></span></p></td>
<td><p><span data-ttu-id="8d909-144">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8d909-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d909-145">Comandos y recopilación de datos de registro del controlador del Servicio de registro centralizado (ClsController.exe) o el agente (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="8d909-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d909-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="8d909-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="8d909-147">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="8d909-147">Any</span></span></p></td>
<td><p><span data-ttu-id="8d909-148">Interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8d909-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d909-149">Controlador del Servicio de registro centralizado (ClsController.exe) o comandos y colección de registro del agente (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="8d909-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

