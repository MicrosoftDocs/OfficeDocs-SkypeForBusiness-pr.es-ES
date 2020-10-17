---
title: 'Lync Server 2013: configurar el enrutamiento de Location-Based'
description: 'Lync Server 2013: configurar el enrutamiento de Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 080c2a3a82a8714fc35ce882b0c6cb1630552f27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570886"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="7eb23-103">Configuración del enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7eb23-103">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7eb23-104">_**Última modificación del tema:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="7eb23-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="7eb23-105">Lync Server 2013 CU1, Location-Based Routing es una característica de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7eb23-105">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="7eb23-106">El enrutamiento Location-Based es una característica de administración de llamadas que controla cómo se enrutan las llamadas por parte de Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="7eb23-106">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="7eb23-107">Aplica restricciones en cuanto a si las llamadas se pueden enrutar a los destinos de PBX o RTC en función de la ubicación del autor de la llamada de Lync.</span><span class="sxs-lookup"><span data-stu-id="7eb23-107">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="7eb23-108">El enrutamiento Location-Based se aplica a las reglas de autorización de llamadas a RTC en función de la ubicación de red del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7eb23-108">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="7eb23-109">La ubicación del autor de la llamada se determina en función del sitio de red asociado a la subred de red en la que está conectado el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7eb23-109">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="7eb23-110">La configuración del enrutamiento de Location-Based requiere que se implemente primero la telefonía IP empresarial y, a continuación, la configuración de regiones de red, sitios y subredes.</span><span class="sxs-lookup"><span data-stu-id="7eb23-110">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="7eb23-111">De esta forma se establece la base para habilitar el enrutamiento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="7eb23-111">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="7eb23-112">Antes de implementar el enrutamiento de Location-Based, primero debe implementar Enterprise Voice y configurar regiones de red, sitios y asociar subredes de red a los sitios de red.</span><span class="sxs-lookup"><span data-stu-id="7eb23-112">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="7eb23-113">Una vez completada, puede configurar el enrutamiento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="7eb23-113">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="7eb23-114">Para conocer los pasos necesarios para configurar regiones de red, sitios y subredes, vea [Deploying Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="7eb23-114">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="7eb23-115">Esta sección le guiará a través de la configuración del enrutamiento de Location-Based mediante el siguiente ejemplo como ilustración.</span><span class="sxs-lookup"><span data-stu-id="7eb23-115">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="7eb23-116">![Ejemplo de enrutamiento basado en Enterprise Voice Location](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Ejemplo de enrutamiento basado en Enterprise Voice Location")</span><span class="sxs-lookup"><span data-stu-id="7eb23-116">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="7eb23-117">En la tabla siguiente se representan los usuarios definidos en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7eb23-117">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7eb23-118">Tipo de extremo</span><span class="sxs-lookup"><span data-stu-id="7eb23-118">Endpoint type</span></span></th>
<th><span data-ttu-id="7eb23-119">Ubicación</span><span class="sxs-lookup"><span data-stu-id="7eb23-119">Location</span></span></th>
<th><span data-ttu-id="7eb23-120">Usuarios</span><span class="sxs-lookup"><span data-stu-id="7eb23-120">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eb23-121">2015</span><span class="sxs-lookup"><span data-stu-id="7eb23-121">Lync</span></span></p></td>
<td><p><span data-ttu-id="7eb23-122">Oficina corporativa de Delhi</span><span class="sxs-lookup"><span data-stu-id="7eb23-122">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="7eb23-123">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="7eb23-123">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb23-124">2015</span><span class="sxs-lookup"><span data-stu-id="7eb23-124">Lync</span></span></p></td>
<td><p><span data-ttu-id="7eb23-125">Oficina corporativa de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="7eb23-125">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="7eb23-126">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="7eb23-126">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb23-127">2015</span><span class="sxs-lookup"><span data-stu-id="7eb23-127">Lync</span></span></p></td>
<td><p><span data-ttu-id="7eb23-128">Desconocido (por ejemplo, Hotel)</span><span class="sxs-lookup"><span data-stu-id="7eb23-128">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="7eb23-129">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="7eb23-129">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb23-130">PBX</span><span class="sxs-lookup"><span data-stu-id="7eb23-130">PBX</span></span></p></td>
<td><p><span data-ttu-id="7eb23-131">Oficina corporativa de Delhi</span><span class="sxs-lookup"><span data-stu-id="7eb23-131">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="7eb23-132">DEL-PBX-1, DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="7eb23-132">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb23-133">PBX</span><span class="sxs-lookup"><span data-stu-id="7eb23-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="7eb23-134">Oficina corporativa de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="7eb23-134">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="7eb23-135">HYD-PBX-1, HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="7eb23-135">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb23-136">RTC</span><span class="sxs-lookup"><span data-stu-id="7eb23-136">PSTN</span></span></p></td>
<td><p><span data-ttu-id="7eb23-137">Unknown</span><span class="sxs-lookup"><span data-stu-id="7eb23-137">Unknown</span></span></p></td>
<td><p><span data-ttu-id="7eb23-138">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="7eb23-138">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="7eb23-139">La siguiente tabla representa los sistemas que se ilustran en este entorno de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7eb23-139">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7eb23-140">Sistema</span><span class="sxs-lookup"><span data-stu-id="7eb23-140">System</span></span></th>
<th><span data-ttu-id="7eb23-141">Ubicación</span><span class="sxs-lookup"><span data-stu-id="7eb23-141">Location</span></span></th>
<th><span data-ttu-id="7eb23-142">Nombre</span><span class="sxs-lookup"><span data-stu-id="7eb23-142">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eb23-143">Grupo de servidores de Lync Server 2013 CU1</span><span class="sxs-lookup"><span data-stu-id="7eb23-143">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="7eb23-144">cualquiera</span><span class="sxs-lookup"><span data-stu-id="7eb23-144">any</span></span></p></td>
<td><p><span data-ttu-id="7eb23-145">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="7eb23-145">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb23-146">Lync Server 2013 CU1, servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="7eb23-146">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="7eb23-147">cualquiera</span><span class="sxs-lookup"><span data-stu-id="7eb23-147">any</span></span></p></td>
<td><p><span data-ttu-id="7eb23-148">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="7eb23-148">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb23-149">Puerta de enlace RTC 1</span><span class="sxs-lookup"><span data-stu-id="7eb23-149">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="7eb23-150">Delhi</span><span class="sxs-lookup"><span data-stu-id="7eb23-150">Delhi</span></span></p></td>
<td><p><span data-ttu-id="7eb23-151">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="7eb23-151">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb23-152">Puerta de enlace RTC 2</span><span class="sxs-lookup"><span data-stu-id="7eb23-152">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="7eb23-153">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="7eb23-153">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="7eb23-154">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="7eb23-154">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb23-155">PBX 1</span><span class="sxs-lookup"><span data-stu-id="7eb23-155">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="7eb23-156">Delhi</span><span class="sxs-lookup"><span data-stu-id="7eb23-156">Delhi</span></span></p></td>
<td><p><span data-ttu-id="7eb23-157">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="7eb23-157">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb23-158">PBX 2</span><span class="sxs-lookup"><span data-stu-id="7eb23-158">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="7eb23-159">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="7eb23-159">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="7eb23-160">PBX ROJA</span><span class="sxs-lookup"><span data-stu-id="7eb23-160">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="7eb23-161">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7eb23-161">In This Section</span></span>

  - [<span data-ttu-id="7eb23-162">Configurar la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7eb23-162">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="7eb23-163">Implementar regiones de red, sitios y subredes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7eb23-163">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="7eb23-164">Habilitación del enrutamiento Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7eb23-164">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7eb23-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7eb23-165">See Also</span></span>


[<span data-ttu-id="7eb23-166">Implementación de características avanzadas de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7eb23-166">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

