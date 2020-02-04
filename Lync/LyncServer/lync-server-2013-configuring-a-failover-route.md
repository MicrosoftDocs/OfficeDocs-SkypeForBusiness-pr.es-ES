---
title: 'Lync Server 2013: Configurar una ruta de conmutación por error'
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
ms.openlocfilehash: 22ebdf359a8cdf5f20ada8740a589b0181c3cc93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="6b65f-102">Configurar una ruta de conmutación por error en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b65f-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b65f-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6b65f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6b65f-104">En el ejemplo siguiente se muestra cómo un administrador puede definir una ruta de conmutación por error para su uso si la GW1 de Dallas está desactivada para su mantenimiento o no está disponible.</span><span class="sxs-lookup"><span data-stu-id="6b65f-104">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable.</span></span> <span data-ttu-id="6b65f-105">En las siguientes tablas se muestra el cambio de configuración requerido.</span><span class="sxs-lookup"><span data-stu-id="6b65f-105">The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="6b65f-106">Tabla 1.</span><span class="sxs-lookup"><span data-stu-id="6b65f-106">Table 1.</span></span> <span data-ttu-id="6b65f-107">Directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="6b65f-107">User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b65f-108">Directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="6b65f-108">User policy</span></span></th>
<th><span data-ttu-id="6b65f-109">Uso del teléfono</span><span class="sxs-lookup"><span data-stu-id="6b65f-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b65f-110">Directiva de llamadas predeterminada</span><span class="sxs-lookup"><span data-stu-id="6b65f-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="6b65f-111">Local</span><span class="sxs-lookup"><span data-stu-id="6b65f-111">Local</span></span></p>
<p><span data-ttu-id="6b65f-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="6b65f-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b65f-113">Directiva local de Redmond</span><span class="sxs-lookup"><span data-stu-id="6b65f-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="6b65f-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="6b65f-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b65f-115">Política de llamadas de Dallas</span><span class="sxs-lookup"><span data-stu-id="6b65f-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="6b65f-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="6b65f-116">DallasUsers</span></span></p>
<p><span data-ttu-id="6b65f-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="6b65f-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="6b65f-118">Tabla 2.</span><span class="sxs-lookup"><span data-stu-id="6b65f-118">Table 2.</span></span> <span data-ttu-id="6b65f-119">Redirige</span><span class="sxs-lookup"><span data-stu-id="6b65f-119">Routes</span></span>

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
<th><span data-ttu-id="6b65f-120">Nombre de la ruta</span><span class="sxs-lookup"><span data-stu-id="6b65f-120">Route name</span></span></th>
<th><span data-ttu-id="6b65f-121">Patrón de números</span><span class="sxs-lookup"><span data-stu-id="6b65f-121">Number pattern</span></span></th>
<th><span data-ttu-id="6b65f-122">Uso del teléfono</span><span class="sxs-lookup"><span data-stu-id="6b65f-122">Phone usage</span></span></th>
<th><span data-ttu-id="6b65f-123">Tronco</span><span class="sxs-lookup"><span data-stu-id="6b65f-123">Trunk</span></span></th>
<th><span data-ttu-id="6b65f-124">Puerta</span><span class="sxs-lookup"><span data-stu-id="6b65f-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b65f-125">Camino local de Redmond</span><span class="sxs-lookup"><span data-stu-id="6b65f-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="6b65f-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="6b65f-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="6b65f-127">Local</span><span class="sxs-lookup"><span data-stu-id="6b65f-127">Local</span></span></p>
<p><span data-ttu-id="6b65f-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="6b65f-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="6b65f-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="6b65f-129">Trunk1</span></span></p>
<p><span data-ttu-id="6b65f-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="6b65f-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="6b65f-131">Rojo: GW1</span><span class="sxs-lookup"><span data-stu-id="6b65f-131">Red-GW1</span></span></p>
<p><span data-ttu-id="6b65f-132">Rojo: GW2</span><span class="sxs-lookup"><span data-stu-id="6b65f-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b65f-133">Ruta local de Dallas</span><span class="sxs-lookup"><span data-stu-id="6b65f-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="6b65f-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="6b65f-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="6b65f-135">Local</span><span class="sxs-lookup"><span data-stu-id="6b65f-135">Local</span></span></p></td>
<td><p><span data-ttu-id="6b65f-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="6b65f-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="6b65f-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="6b65f-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b65f-138">Ruta universal</span><span class="sxs-lookup"><span data-stu-id="6b65f-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="6b65f-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="6b65f-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="6b65f-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="6b65f-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="6b65f-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="6b65f-141">Trunk1</span></span></p>
<p><span data-ttu-id="6b65f-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="6b65f-142">Trunk2</span></span></p>
<p><span data-ttu-id="6b65f-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="6b65f-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="6b65f-144">Rojo: GW1</span><span class="sxs-lookup"><span data-stu-id="6b65f-144">Red-GW1</span></span></p>
<p><span data-ttu-id="6b65f-145">Rojo: GW2</span><span class="sxs-lookup"><span data-stu-id="6b65f-145">Red-GW2</span></span></p>
<p><span data-ttu-id="6b65f-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="6b65f-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b65f-147">Ruta de usuarios de Dallas</span><span class="sxs-lookup"><span data-stu-id="6b65f-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="6b65f-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="6b65f-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="6b65f-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="6b65f-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="6b65f-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="6b65f-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="6b65f-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="6b65f-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6b65f-152">En la tabla 1, se agrega un uso de teléfono de GlobalPSTNHopoff después del uso del teléfono DallasUsers en la política de llamadas de Dallas.</span><span class="sxs-lookup"><span data-stu-id="6b65f-152">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy.</span></span> <span data-ttu-id="6b65f-153">Esto permite que las llamadas con la Directiva de llamadas de Dallas usen rutas configuradas para el uso del teléfono GlobalPSTNHopoff si una ruta para el uso del teléfono DallasUsers no está disponible.</span><span class="sxs-lookup"><span data-stu-id="6b65f-153">This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

