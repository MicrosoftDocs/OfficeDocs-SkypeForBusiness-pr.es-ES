---
title: 'Lync Server 2013: Resumen DNS - Proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47606fe71b271e01cc7fbefbcf319a2efe93f478
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="9c1ae-102">Resumen DNS - Proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c1ae-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c1ae-103">_**Última modificación del tema:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="9c1ae-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="9c1ae-104">Para configurar dos adaptadores de red en el proxy inverso, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9c1ae-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="9c1ae-105">Requisitos del adaptador de red de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="9c1ae-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="9c1ae-106">Ejemplo de **adaptador de red 1 (interfaz interna)**</span><span class="sxs-lookup"><span data-stu-id="9c1ae-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="9c1ae-107">Interfaz interna con 172.25.33.40 asignado.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="9c1ae-108">No hay ninguna puerta de enlace predeterminada definida.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="9c1ae-109">Asegúrese de que haya una ruta desde la red que contiene la interfaz interna de proxy inverso a cualquier red que contenga servidores de grupos de servidores de aplicaciones para el usuario de Lync Server (por ejemplo, de 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="9c1ae-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="9c1ae-110">Ejemplo de **adaptador de red 2 (interfaz externa)**</span><span class="sxs-lookup"><span data-stu-id="9c1ae-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="9c1ae-111">Se asigna al menos una dirección IP pública a este adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="9c1ae-112">La puerta de enlace está definida para señalar el router o el firewall integrado en el perímetro exterior.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-112">Gateway is defined to point to the router or integrated firewall in your outer perimeter.</span></span> <span data-ttu-id="9c1ae-113">(10.45.16.1 en el escenario ejemplos)</span><span class="sxs-lookup"><span data-stu-id="9c1ae-113">(10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="9c1ae-114">Registros DNS necesarios para el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="9c1ae-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c1ae-115">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="9c1ae-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="9c1ae-116">FQDN</span><span class="sxs-lookup"><span data-stu-id="9c1ae-116">FQDN</span></span></th>
<th><span data-ttu-id="9c1ae-117">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="9c1ae-117">IP address</span></span></th>
<th><span data-ttu-id="9c1ae-118">Se asigna a/comentarios</span><span class="sxs-lookup"><span data-stu-id="9c1ae-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c1ae-119">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="9c1ae-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c1ae-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-121">Escucha asignada para recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="9c1ae-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-122">Servicios web externos de la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-122">External web services from the internal deployment.</span></span> <span data-ttu-id="9c1ae-123">Se pueden definir y crear registros adicionales para todos los grupos y servidores únicos para cualquier dominio SIP que use este proxy inverso y para los que haya definido servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-123">Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c1ae-124">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="9c1ae-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c1ae-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-126">Escucha asignada para recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="9c1ae-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-127">Servicios web externos para los grupos de directores o directores de su implementación.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="9c1ae-128">Puede definir tantos directores como un número de directores distintos, de los cuales pueden estar asociados a otros dominios SIP.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="9c1ae-129">Definir los registros DNS para y publicar los directores no es una de las agrupaciones front-end ni la decisión de director.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="9c1ae-130">Si está usando directores, debe definir y publicar el director y los servicios web externos del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="9c1ae-131">Los tipos de tráfico específicos (para autenticación y otros usos) se enviarán primero al Director, si está definido en la topología.</span><span class="sxs-lookup"><span data-stu-id="9c1ae-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c1ae-132">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="9c1ae-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c1ae-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-134">Escucha asignada para recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="9c1ae-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-135">Conferencias de acceso telefónico local publicadas externamente</span><span class="sxs-lookup"><span data-stu-id="9c1ae-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c1ae-136">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="9c1ae-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c1ae-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-138">Escucha asignada para recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="9c1ae-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-139">Conferencias publicadas externamente</span><span class="sxs-lookup"><span data-stu-id="9c1ae-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c1ae-140">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="9c1ae-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c1ae-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-142">Escucha asignada para el servidor de Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="9c1ae-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-143">Office Web Apps Server implementado internamente o en el perímetro, y publicado para acceso externo de clientes</span><span class="sxs-lookup"><span data-stu-id="9c1ae-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c1ae-144">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="9c1ae-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c1ae-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-146">Escucha asignada para recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="9c1ae-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="9c1ae-147">Registro externo de detección de Lync para detección automática publicada externamente e incluye movilidad, Microsoft Lync Web App y la aplicación Web de programador</span><span class="sxs-lookup"><span data-stu-id="9c1ae-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

