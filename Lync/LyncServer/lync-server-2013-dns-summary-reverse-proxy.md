---
title: 'Lync Server 2013: Resumen de DNS-proxy inverso'
description: 'Lync Server 2013: Resumen de DNS-proxy inverso.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc2d806893786a11317be1eff9bfdc08c9230bf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544796"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="77712-103">Resumen de DNS-proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77712-103">DNS summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77712-104">_**Última modificación del tema:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="77712-104">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="77712-105">Puede configurar dos adaptadores de red en el proxy inverso de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="77712-105">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="77712-106">Requisitos del adaptador de red con proxy inverso</span><span class="sxs-lookup"><span data-stu-id="77712-106">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="77712-107">Ejemplo de **adaptador de red 1 (Interfaz interna)**</span><span class="sxs-lookup"><span data-stu-id="77712-107">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="77712-108">Interfaz interna con 172.25.33.40 asignada.</span><span class="sxs-lookup"><span data-stu-id="77712-108">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="77712-109">No se ha definido ninguna puerta de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="77712-109">No default gateway is defined.</span></span>
    
    <span data-ttu-id="77712-110">Asegúrese de que existe una ruta desde la red que contiene la interfaz interna del proxy inverso a cualquier red que contenga servidores de grupo de servidores front-end de Lync Server (por ejemplo, de 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="77712-110">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="77712-111">Ejemplo de **adaptador de red 2 (Interfaz externa)**</span><span class="sxs-lookup"><span data-stu-id="77712-111">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="77712-112">Se asigna un mínimo de una dirección IP pública a este adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="77712-112">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="77712-p101">Se ha definido la puerta de enlace para señalar al enrutador o al firewall integrado de su perímetro exterior. (10.45.16.1 en los ejemplos del escenario)</span><span class="sxs-lookup"><span data-stu-id="77712-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="77712-115">Registros DNS requeridos para proxy inverso</span><span class="sxs-lookup"><span data-stu-id="77712-115">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77712-116">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="77712-116">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="77712-117">FQDN</span><span class="sxs-lookup"><span data-stu-id="77712-117">FQDN</span></span></th>
<th><span data-ttu-id="77712-118">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="77712-118">IP address</span></span></th>
<th><span data-ttu-id="77712-119">Asignado a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="77712-119">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77712-120">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="77712-120">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="77712-121">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77712-121">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="77712-122">Escucha asignada para los recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="77712-122">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="77712-p102">Servicios web externos desde la implementación interna. Se pueden definir y crear registros adicionales para todos los grupos de servidores y servidores únicos para cualquier dominio de SIP que use este proxy inverso y tenga definidos servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="77712-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77712-125">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="77712-125">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="77712-126">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77712-126">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="77712-127">Escucha asignada para los recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="77712-127">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="77712-128">Servicios web externos para los directores o grupos de directores en su implementación de.</span><span class="sxs-lookup"><span data-stu-id="77712-128">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="77712-129">Puede definir tantos directores como un número de directores distintos, de los cuales se pueden asociar a otros dominios SIP.</span><span class="sxs-lookup"><span data-stu-id="77712-129">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="77712-130">La definición de los registros DNS para y la publicación de los directores no es un grupo de servidores front-end ni la decisión de director.</span><span class="sxs-lookup"><span data-stu-id="77712-130">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="77712-131">Si usa directores, debe definir y publicar el director y los servicios web externos del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="77712-131">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="77712-132">Los tipos de tráfico específicos (para la autenticación y otros usos) se enviarán primero al Director, si está definido en la topología.</span><span class="sxs-lookup"><span data-stu-id="77712-132">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77712-133">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="77712-133">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="77712-134">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77712-134">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="77712-135">Escucha asignada para los recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="77712-135">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="77712-136">Conferencias de acceso telefónico local publicadas externamente</span><span class="sxs-lookup"><span data-stu-id="77712-136">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77712-137">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="77712-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="77712-138">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77712-138">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="77712-139">Escucha asignada para los recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="77712-139">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="77712-140">Conferencias publicadas externamente</span><span class="sxs-lookup"><span data-stu-id="77712-140">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77712-141">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="77712-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="77712-142">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77712-142">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="77712-143">Escucha asignada para Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="77712-143">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="77712-144">Office Web Apps Server implementado internamente o en el perímetro, y publicado para el acceso de clientes externos</span><span class="sxs-lookup"><span data-stu-id="77712-144">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77712-145">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="77712-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="77712-146">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77712-146">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="77712-147">Escucha asignada para los recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="77712-147">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="77712-148">Registro externo de detección de Lync para la detección automática publicada externamente e incluye movilidad, aplicación Web de Microsoft Lync y aplicación Web de programador</span><span class="sxs-lookup"><span data-stu-id="77712-148">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

