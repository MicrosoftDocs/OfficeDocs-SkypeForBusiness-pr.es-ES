---
title: 'Lync Server 2013: Configurar el enrutamiento basado en ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a682f6b550f982f929a83bc8c2f430e89b9452fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="76e86-102">Configurar el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76e86-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76e86-103">_**Última modificación del tema:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="76e86-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="76e86-104">Lync Server 2013 CU1, el enrutamiento basado en la ubicación es una característica de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="76e86-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="76e86-105">El enrutamiento basado en la ubicación es una característica de administración de llamadas que controla cómo Lync Server 2013 CU1 dirige las llamadas.</span><span class="sxs-lookup"><span data-stu-id="76e86-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="76e86-106">Aplica restricciones sobre si las llamadas se pueden enrutar a destinos de PBX o RTC en función de la ubicación de la persona que llama de Lync.</span><span class="sxs-lookup"><span data-stu-id="76e86-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="76e86-107">El enrutamiento basado en la ubicación aplica las reglas de autorización de llamadas a llamadas RTC en función de la ubicación de red de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="76e86-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="76e86-108">La ubicación de la persona que llama se determina en función del sitio de red asociado a la subred de red en la que está conectada la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="76e86-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="76e86-109">Configurar el enrutamiento basado en la ubicación requiere implementar primero Enterprise Voice y, a continuación, configurar regiones, sitios y subredes de la red.</span><span class="sxs-lookup"><span data-stu-id="76e86-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="76e86-110">Esto configura la base para habilitar el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="76e86-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="76e86-111">Antes de implementar el enrutamiento basado en la ubicación, primero debe implementar Enterprise Voice y configurar regiones y sitios de red, y asociar subredes de red a los sitios de red.</span><span class="sxs-lookup"><span data-stu-id="76e86-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="76e86-112">Una vez completado, puede configurar el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="76e86-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="76e86-113">Para conocer los pasos sobre cómo configurar regiones de red, sitios y subredes, consulte [implementar características avanzadas de telefonía empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="76e86-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="76e86-114">Esta sección le guiará a través de la configuración de enrutamiento basado en la ubicación con el ejemplo siguiente como ilustración.</span><span class="sxs-lookup"><span data-stu-id="76e86-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="76e86-115">![Ejemplo de enrutamiento basado en la ubicación de voz empresarial] (images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Ejemplo de enrutamiento basado en la ubicación de voz empresarial")</span><span class="sxs-lookup"><span data-stu-id="76e86-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="76e86-116">En la tabla siguiente se representan los usuarios definidos en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="76e86-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76e86-117">Tipo de extremo</span><span class="sxs-lookup"><span data-stu-id="76e86-117">Endpoint type</span></span></th>
<th><span data-ttu-id="76e86-118">Ubicación</span><span class="sxs-lookup"><span data-stu-id="76e86-118">Location</span></span></th>
<th><span data-ttu-id="76e86-119">Usuarios</span><span class="sxs-lookup"><span data-stu-id="76e86-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76e86-120">Lync</span><span class="sxs-lookup"><span data-stu-id="76e86-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="76e86-121">Oficina corporativa de Delhi</span><span class="sxs-lookup"><span data-stu-id="76e86-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="76e86-122">DE-LYNC-1, DE-LYNC-2, DE-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="76e86-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e86-123">Lync</span><span class="sxs-lookup"><span data-stu-id="76e86-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="76e86-124">Oficina corporativa de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="76e86-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="76e86-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="76e86-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e86-126">Lync</span><span class="sxs-lookup"><span data-stu-id="76e86-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="76e86-127">Desconocido (es decir, Hotel)</span><span class="sxs-lookup"><span data-stu-id="76e86-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="76e86-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="76e86-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e86-129">PBX</span><span class="sxs-lookup"><span data-stu-id="76e86-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="76e86-130">Oficina corporativa de Delhi</span><span class="sxs-lookup"><span data-stu-id="76e86-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="76e86-131">DEL-PBX-1, DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="76e86-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e86-132">PBX</span><span class="sxs-lookup"><span data-stu-id="76e86-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="76e86-133">Oficina corporativa de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="76e86-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="76e86-134">HYD-PBX-1, HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="76e86-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e86-135">RTC</span><span class="sxs-lookup"><span data-stu-id="76e86-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="76e86-136">Reconoce</span><span class="sxs-lookup"><span data-stu-id="76e86-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="76e86-137">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="76e86-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="76e86-138">La tabla siguiente representa los sistemas que se muestran en este entorno de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="76e86-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76e86-139">Sistemas</span><span class="sxs-lookup"><span data-stu-id="76e86-139">System</span></span></th>
<th><span data-ttu-id="76e86-140">Ubicación</span><span class="sxs-lookup"><span data-stu-id="76e86-140">Location</span></span></th>
<th><span data-ttu-id="76e86-141">Nombre</span><span class="sxs-lookup"><span data-stu-id="76e86-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76e86-142">Grupo de 2013 de Lync Server CU1</span><span class="sxs-lookup"><span data-stu-id="76e86-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="76e86-143">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="76e86-143">any</span></span></p></td>
<td><p><span data-ttu-id="76e86-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="76e86-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e86-145">Lync Server 2013 CU1, servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="76e86-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="76e86-146">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="76e86-146">any</span></span></p></td>
<td><p><span data-ttu-id="76e86-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="76e86-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e86-148">Puerta de enlace PSTN 1</span><span class="sxs-lookup"><span data-stu-id="76e86-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="76e86-149">Delhi</span><span class="sxs-lookup"><span data-stu-id="76e86-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="76e86-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="76e86-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e86-151">Puerta de enlace PSTN 2</span><span class="sxs-lookup"><span data-stu-id="76e86-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="76e86-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="76e86-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="76e86-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="76e86-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e86-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="76e86-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="76e86-155">Delhi</span><span class="sxs-lookup"><span data-stu-id="76e86-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="76e86-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="76e86-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e86-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="76e86-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="76e86-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="76e86-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="76e86-159">RED PBX ROJA</span><span class="sxs-lookup"><span data-stu-id="76e86-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="76e86-160">En esta sección</span><span class="sxs-lookup"><span data-stu-id="76e86-160">In This Section</span></span>

  - [<span data-ttu-id="76e86-161">Configurar la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76e86-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="76e86-162">Implementar regiones, sitios y subredes de la red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76e86-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="76e86-163">Habilitar el enrutamiento basado en la ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76e86-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76e86-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="76e86-164">See Also</span></span>


[<span data-ttu-id="76e86-165">Implementación de características avanzadas de telefonía empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76e86-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

