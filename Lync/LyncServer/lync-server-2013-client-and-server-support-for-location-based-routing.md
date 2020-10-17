---
title: 'Lync Server 2013: compatibilidad del cliente y el servidor con el enrutamiento Location-Based'
description: 'Lync Server 2013: compatibilidad del cliente y el servidor con el enrutamiento Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20dca7444f58ee62dbc36edbb7d9e1c976a97807
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549636"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="50630-103">Compatibilidad de cliente y servidor para el enrutamiento Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50630-103">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50630-104">_**Última modificación del tema:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="50630-104">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="50630-105">El enrutamiento de Location-Based es aplicado por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50630-105">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="50630-106">Lync Server puede identificar los sitios de red desde los que se conectan los usuarios de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="50630-106">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="50630-107">Como los usuarios remotos están fuera de la red corporativa, se considera que su ubicación es desconocida.</span><span class="sxs-lookup"><span data-stu-id="50630-107">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="50630-108">Compatibilidad con Lync Server</span><span class="sxs-lookup"><span data-stu-id="50630-108">Lync Server Support</span></span>

<span data-ttu-id="50630-109">El enrutamiento Location-Based requiere que Lync Server 2013 CU1 se implemente en todos los grupos de servidores front-end y servidores Standard Edition en una topología determinada.</span><span class="sxs-lookup"><span data-stu-id="50630-109">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="50630-110">Si Lync Server 2013 CU1 no está instalado en determinados componentes de Lync en la topología, Location-Based restricciones de enrutamiento no se pueden aplicar completamente.</span><span class="sxs-lookup"><span data-stu-id="50630-110">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="50630-111">En la siguiente tabla se identifica la combinación de roles de servidor y versiones compatibles con el enrutamiento Location-Based.</span><span class="sxs-lookup"><span data-stu-id="50630-111">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50630-112">Versión del grupo</span><span class="sxs-lookup"><span data-stu-id="50630-112">Pool version</span></span></th>
<th><span data-ttu-id="50630-113">Versión del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="50630-113">Mediation Server version</span></span></th>
<th><span data-ttu-id="50630-114">Compatible</span><span class="sxs-lookup"><span data-stu-id="50630-114">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50630-115">Lync Server 2013 a la actualización acumulativa de febrero de 2013</span><span class="sxs-lookup"><span data-stu-id="50630-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="50630-116">Lync Server 2013 a la actualización acumulativa de febrero de 2013</span><span class="sxs-lookup"><span data-stu-id="50630-116">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="50630-117">sí</span><span class="sxs-lookup"><span data-stu-id="50630-117">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50630-118">Lync Server 2013 a la actualización acumulativa de febrero de 2013</span><span class="sxs-lookup"><span data-stu-id="50630-118">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="50630-119">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50630-119">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="50630-120">no</span><span class="sxs-lookup"><span data-stu-id="50630-120">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50630-121">Lync Server 2013 a la actualización acumulativa de febrero de 2013</span><span class="sxs-lookup"><span data-stu-id="50630-121">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="50630-122">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="50630-122">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="50630-123">no</span><span class="sxs-lookup"><span data-stu-id="50630-123">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50630-124">Lync Server 2013 a la actualización acumulativa de febrero de 2013</span><span class="sxs-lookup"><span data-stu-id="50630-124">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="50630-125">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="50630-125">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="50630-126">no</span><span class="sxs-lookup"><span data-stu-id="50630-126">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50630-127">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50630-127">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="50630-128">cualquiera</span><span class="sxs-lookup"><span data-stu-id="50630-128">any</span></span></p></td>
<td><p><span data-ttu-id="50630-129">no</span><span class="sxs-lookup"><span data-stu-id="50630-129">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50630-130">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="50630-130">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="50630-131">cualquiera</span><span class="sxs-lookup"><span data-stu-id="50630-131">any</span></span></p></td>
<td><p><span data-ttu-id="50630-132">no</span><span class="sxs-lookup"><span data-stu-id="50630-132">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50630-133">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="50630-133">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="50630-134">cualquiera</span><span class="sxs-lookup"><span data-stu-id="50630-134">any</span></span></p></td>
<td><p><span data-ttu-id="50630-135">no</span><span class="sxs-lookup"><span data-stu-id="50630-135">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="50630-136">Compatibilidad con clientes de Lync</span><span class="sxs-lookup"><span data-stu-id="50630-136">Lync Client Support</span></span>

<span data-ttu-id="50630-137">En la tabla siguiente se identifican los clientes compatibles con el enrutamiento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="50630-137">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50630-138">Tipo de cliente</span><span class="sxs-lookup"><span data-stu-id="50630-138">Client type</span></span></th>
<th><span data-ttu-id="50630-139">Compatible</span><span class="sxs-lookup"><span data-stu-id="50630-139">Supported</span></span></th>
<th><span data-ttu-id="50630-140">Detalles</span><span class="sxs-lookup"><span data-stu-id="50630-140">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50630-141">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="50630-141">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="50630-142">sí</span><span class="sxs-lookup"><span data-stu-id="50630-142">yes</span></span></p></td>
<td><p><span data-ttu-id="50630-143">Inclusión de la actualización acumulativa de Lync 2013 febrero de 2013</span><span class="sxs-lookup"><span data-stu-id="50630-143">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50630-144">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="50630-144">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="50630-145">sí</span><span class="sxs-lookup"><span data-stu-id="50630-145">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50630-146">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="50630-146">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="50630-147">no</span><span class="sxs-lookup"><span data-stu-id="50630-147">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50630-148">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="50630-148">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="50630-149">sí</span><span class="sxs-lookup"><span data-stu-id="50630-149">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50630-150">Operador de Lync</span><span class="sxs-lookup"><span data-stu-id="50630-150">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="50630-151">sí</span><span class="sxs-lookup"><span data-stu-id="50630-151">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50630-152">Lync para Windows 8</span><span class="sxs-lookup"><span data-stu-id="50630-152">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="50630-153">no</span><span class="sxs-lookup"><span data-stu-id="50630-153">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50630-154">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="50630-154">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="50630-155">no</span><span class="sxs-lookup"><span data-stu-id="50630-155">no</span></span></p></td>
<td><p><span data-ttu-id="50630-156">VoIP debe estar deshabilitado para los clientes de Lync Mobile 2013 si lo usan los usuarios con el enrutamiento de Location-Based habilitado.</span><span class="sxs-lookup"><span data-stu-id="50630-156">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50630-157">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="50630-157">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="50630-158">sí</span><span class="sxs-lookup"><span data-stu-id="50630-158">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="50630-159">Para deshabilitar VoIP para los clientes de Lync Mobile 2013, asigne una directiva de movilidad con la configuración, audio/vídeo IP, deshabilitado para todos los usuarios habilitados para el enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="50630-159">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="50630-160">Para obtener más información sobre la Directiva de movilidad, vea <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="50630-160">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50630-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="50630-161">See Also</span></span>


[<span data-ttu-id="50630-162">Planeación del enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50630-162">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

