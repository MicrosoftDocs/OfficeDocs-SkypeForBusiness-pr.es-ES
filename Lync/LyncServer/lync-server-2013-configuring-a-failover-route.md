---
title: 'Lync Server 2013: configurar una ruta de conmutación por error'
description: 'Lync Server 2013: configurar una ruta de conmutación por error.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7cfc45276931685a2d42103b1b7f1d5015dcd7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560496"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="66bae-103">Configurar una ruta de conmutación por error en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66bae-103">Configuring a failover route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66bae-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="66bae-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="66bae-p101">En el siguiente ejemplo se muestra cómo puede un administrador definir una ruta de conmutación por error para usarla en caso de que se desconecte Dallas-GW1 por motivos de mantenimiento o no esté disponible. En las tablas siguientes se muestra el cambio de configuración necesario.</span><span class="sxs-lookup"><span data-stu-id="66bae-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="66bae-p102">Tabla 1. Directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="66bae-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66bae-109">Directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="66bae-109">User policy</span></span></th>
<th><span data-ttu-id="66bae-110">Uso de teléfono</span><span class="sxs-lookup"><span data-stu-id="66bae-110">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66bae-111">Directiva de llamada predeterminada</span><span class="sxs-lookup"><span data-stu-id="66bae-111">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="66bae-112">Local</span><span class="sxs-lookup"><span data-stu-id="66bae-112">Local</span></span></p>
<p><span data-ttu-id="66bae-113">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="66bae-113">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bae-114">Directiva local de Redmond</span><span class="sxs-lookup"><span data-stu-id="66bae-114">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="66bae-115">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="66bae-115">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bae-116">Directiva de llamada de Dallas</span><span class="sxs-lookup"><span data-stu-id="66bae-116">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="66bae-117">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="66bae-117">DallasUsers</span></span></p>
<p><span data-ttu-id="66bae-118">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="66bae-118">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="66bae-p103">Tabla 2. Rutas</span><span class="sxs-lookup"><span data-stu-id="66bae-p103">Table 2. Routes</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66bae-121">Nombre de ruta</span><span class="sxs-lookup"><span data-stu-id="66bae-121">Route name</span></span></th>
<th><span data-ttu-id="66bae-122">Modelo de número</span><span class="sxs-lookup"><span data-stu-id="66bae-122">Number pattern</span></span></th>
<th><span data-ttu-id="66bae-123">Uso de teléfono</span><span class="sxs-lookup"><span data-stu-id="66bae-123">Phone usage</span></span></th>
<th><span data-ttu-id="66bae-124">Tronco</span><span class="sxs-lookup"><span data-stu-id="66bae-124">Trunk</span></span></th>
<th><span data-ttu-id="66bae-125">Puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="66bae-125">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66bae-126">Ruta local de Redmond</span><span class="sxs-lookup"><span data-stu-id="66bae-126">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="66bae-127">^\+1 (425 | 206 | 253) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="66bae-127">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="66bae-128">Local</span><span class="sxs-lookup"><span data-stu-id="66bae-128">Local</span></span></p>
<p><span data-ttu-id="66bae-129">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="66bae-129">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="66bae-130">Trunk1</span><span class="sxs-lookup"><span data-stu-id="66bae-130">Trunk1</span></span></p>
<p><span data-ttu-id="66bae-131">Trunk2</span><span class="sxs-lookup"><span data-stu-id="66bae-131">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="66bae-132">Rojo-GW1</span><span class="sxs-lookup"><span data-stu-id="66bae-132">Red-GW1</span></span></p>
<p><span data-ttu-id="66bae-133">Rojo-GW2</span><span class="sxs-lookup"><span data-stu-id="66bae-133">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bae-134">Ruta local de Dallas</span><span class="sxs-lookup"><span data-stu-id="66bae-134">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="66bae-135">^\+1 (972 | 214 | 469) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="66bae-135">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="66bae-136">Local</span><span class="sxs-lookup"><span data-stu-id="66bae-136">Local</span></span></p></td>
<td><p><span data-ttu-id="66bae-137">Trunk3</span><span class="sxs-lookup"><span data-stu-id="66bae-137">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="66bae-138">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="66bae-138">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66bae-139">Ruta universal</span><span class="sxs-lookup"><span data-stu-id="66bae-139">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="66bae-140">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="66bae-140">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="66bae-141">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="66bae-141">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="66bae-142">Trunk1</span><span class="sxs-lookup"><span data-stu-id="66bae-142">Trunk1</span></span></p>
<p><span data-ttu-id="66bae-143">Trunk2</span><span class="sxs-lookup"><span data-stu-id="66bae-143">Trunk2</span></span></p>
<p><span data-ttu-id="66bae-144">Trunk3</span><span class="sxs-lookup"><span data-stu-id="66bae-144">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="66bae-145">Rojo-GW1</span><span class="sxs-lookup"><span data-stu-id="66bae-145">Red-GW1</span></span></p>
<p><span data-ttu-id="66bae-146">Rojo-GW2</span><span class="sxs-lookup"><span data-stu-id="66bae-146">Red-GW2</span></span></p>
<p><span data-ttu-id="66bae-147">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="66bae-147">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66bae-148">Ruta de usuarios de Dallas</span><span class="sxs-lookup"><span data-stu-id="66bae-148">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="66bae-149">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="66bae-149">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="66bae-150">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="66bae-150">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="66bae-151">Trunk3</span><span class="sxs-lookup"><span data-stu-id="66bae-151">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="66bae-152">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="66bae-152">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="66bae-p104">En la Tabla 1, se agrega el uso de teléfono GlobalPSTNHopoff después del uso de teléfono DallasUsers en la directiva de llamada de Dallas. Esto permite que las llamadas con la directiva de llamada de Dallas usen las rutas configuradas para el uso de teléfono GlobalPSTNHopoff en caso de que una ruta para el uso telefónico DallasUsers no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="66bae-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

