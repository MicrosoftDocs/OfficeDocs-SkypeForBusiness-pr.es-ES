---
title: 'Lync Server 2013: configurar una ruta de conmutación por error'
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
ms.openlocfilehash: 17477c647d2e5dd5918225486c43b93a29509fb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="11d32-102">Configurar una ruta de conmutación por error en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11d32-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11d32-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="11d32-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="11d32-p101">En el siguiente ejemplo se muestra cómo puede un administrador definir una ruta de conmutación por error para usarla en caso de que se desconecte Dallas-GW1 por motivos de mantenimiento o no esté disponible. En las tablas siguientes se muestra el cambio de configuración necesario.</span><span class="sxs-lookup"><span data-stu-id="11d32-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="11d32-p102">Tabla 1. Directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="11d32-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11d32-108">Directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="11d32-108">User policy</span></span></th>
<th><span data-ttu-id="11d32-109">Uso de teléfono</span><span class="sxs-lookup"><span data-stu-id="11d32-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11d32-110">Directiva de llamada predeterminada</span><span class="sxs-lookup"><span data-stu-id="11d32-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="11d32-111">Local</span><span class="sxs-lookup"><span data-stu-id="11d32-111">Local</span></span></p>
<p><span data-ttu-id="11d32-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="11d32-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11d32-113">Directiva local de Redmond</span><span class="sxs-lookup"><span data-stu-id="11d32-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="11d32-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="11d32-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11d32-115">Directiva de llamada de Dallas</span><span class="sxs-lookup"><span data-stu-id="11d32-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="11d32-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="11d32-116">DallasUsers</span></span></p>
<p><span data-ttu-id="11d32-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="11d32-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="11d32-p103">Tabla 2. Rutas</span><span class="sxs-lookup"><span data-stu-id="11d32-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="11d32-120">Nombre de ruta</span><span class="sxs-lookup"><span data-stu-id="11d32-120">Route name</span></span></th>
<th><span data-ttu-id="11d32-121">Modelo de número</span><span class="sxs-lookup"><span data-stu-id="11d32-121">Number pattern</span></span></th>
<th><span data-ttu-id="11d32-122">Uso de teléfono</span><span class="sxs-lookup"><span data-stu-id="11d32-122">Phone usage</span></span></th>
<th><span data-ttu-id="11d32-123">Tronco</span><span class="sxs-lookup"><span data-stu-id="11d32-123">Trunk</span></span></th>
<th><span data-ttu-id="11d32-124">Puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="11d32-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11d32-125">Ruta local de Redmond</span><span class="sxs-lookup"><span data-stu-id="11d32-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="11d32-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="11d32-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="11d32-127">Local</span><span class="sxs-lookup"><span data-stu-id="11d32-127">Local</span></span></p>
<p><span data-ttu-id="11d32-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="11d32-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="11d32-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="11d32-129">Trunk1</span></span></p>
<p><span data-ttu-id="11d32-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="11d32-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="11d32-131">Rojo-GW1</span><span class="sxs-lookup"><span data-stu-id="11d32-131">Red-GW1</span></span></p>
<p><span data-ttu-id="11d32-132">Rojo-GW2</span><span class="sxs-lookup"><span data-stu-id="11d32-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11d32-133">Ruta local de Dallas</span><span class="sxs-lookup"><span data-stu-id="11d32-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="11d32-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="11d32-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="11d32-135">Local</span><span class="sxs-lookup"><span data-stu-id="11d32-135">Local</span></span></p></td>
<td><p><span data-ttu-id="11d32-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="11d32-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="11d32-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="11d32-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11d32-138">Ruta universal</span><span class="sxs-lookup"><span data-stu-id="11d32-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="11d32-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="11d32-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="11d32-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="11d32-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="11d32-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="11d32-141">Trunk1</span></span></p>
<p><span data-ttu-id="11d32-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="11d32-142">Trunk2</span></span></p>
<p><span data-ttu-id="11d32-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="11d32-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="11d32-144">Rojo-GW1</span><span class="sxs-lookup"><span data-stu-id="11d32-144">Red-GW1</span></span></p>
<p><span data-ttu-id="11d32-145">Rojo-GW2</span><span class="sxs-lookup"><span data-stu-id="11d32-145">Red-GW2</span></span></p>
<p><span data-ttu-id="11d32-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="11d32-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11d32-147">Ruta de usuarios de Dallas</span><span class="sxs-lookup"><span data-stu-id="11d32-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="11d32-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="11d32-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="11d32-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="11d32-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="11d32-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="11d32-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="11d32-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="11d32-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11d32-p104">En la Tabla 1, se agrega el uso de teléfono GlobalPSTNHopoff después del uso de teléfono DallasUsers en la directiva de llamada de Dallas. Esto permite que las llamadas con la directiva de llamada de Dallas usen las rutas configuradas para el uso de teléfono GlobalPSTNHopoff en caso de que una ruta para el uso telefónico DallasUsers no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="11d32-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

