---
title: 'Lync Server 2013: Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación'
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
ms.openlocfilehash: 5ad7ead20eb9961180fec9204a84b3392b7fa96f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="6af33-102">Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af33-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6af33-103">_**Última modificación del tema:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="6af33-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="6af33-104">El enrutamiento basado en la ubicación es exigido por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6af33-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="6af33-105">Lync Server puede identificar los sitios de red desde los que se conectan los usuarios dentro de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="6af33-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="6af33-106">Dado que los usuarios remotos están fuera de la red corporativa, su ubicación se considera como desconocida.</span><span class="sxs-lookup"><span data-stu-id="6af33-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="6af33-107">Soporte técnico de Lync Server</span><span class="sxs-lookup"><span data-stu-id="6af33-107">Lync Server Support</span></span>

<span data-ttu-id="6af33-108">El enrutamiento basado en la ubicación requiere que Lync Server 2013 CU1 se implemente en todas las agrupaciones front end y servidores Standard Edition en una topología determinada.</span><span class="sxs-lookup"><span data-stu-id="6af33-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="6af33-109">Si Lync Server 2013 CU1 no está instalado en ciertos componentes de Lync en la topología, las restricciones de enrutamiento basadas en la ubicación no se pueden aplicar por completo.</span><span class="sxs-lookup"><span data-stu-id="6af33-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="6af33-110">En la siguiente tabla se identifica la combinación de las versiones y los roles de servidor que se admiten para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="6af33-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6af33-111">Versión del grupo</span><span class="sxs-lookup"><span data-stu-id="6af33-111">Pool version</span></span></th>
<th><span data-ttu-id="6af33-112">Versión del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="6af33-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="6af33-113">Compatible</span><span class="sxs-lookup"><span data-stu-id="6af33-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6af33-114">Lync Server 2013, actualización acumulativa de febrero 2013</span><span class="sxs-lookup"><span data-stu-id="6af33-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="6af33-115">Lync Server 2013, actualización acumulativa de febrero 2013</span><span class="sxs-lookup"><span data-stu-id="6af33-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="6af33-116">sí</span><span class="sxs-lookup"><span data-stu-id="6af33-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af33-117">Lync Server 2013, actualización acumulativa de febrero 2013</span><span class="sxs-lookup"><span data-stu-id="6af33-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="6af33-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af33-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="6af33-119">no</span><span class="sxs-lookup"><span data-stu-id="6af33-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af33-120">Lync Server 2013, actualización acumulativa de febrero 2013</span><span class="sxs-lookup"><span data-stu-id="6af33-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="6af33-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6af33-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="6af33-122">no</span><span class="sxs-lookup"><span data-stu-id="6af33-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af33-123">Lync Server 2013, actualización acumulativa de febrero 2013</span><span class="sxs-lookup"><span data-stu-id="6af33-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="6af33-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6af33-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="6af33-125">no</span><span class="sxs-lookup"><span data-stu-id="6af33-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af33-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af33-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="6af33-127">cualquiera</span><span class="sxs-lookup"><span data-stu-id="6af33-127">any</span></span></p></td>
<td><p><span data-ttu-id="6af33-128">no</span><span class="sxs-lookup"><span data-stu-id="6af33-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af33-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6af33-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="6af33-130">cualquiera</span><span class="sxs-lookup"><span data-stu-id="6af33-130">any</span></span></p></td>
<td><p><span data-ttu-id="6af33-131">no</span><span class="sxs-lookup"><span data-stu-id="6af33-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af33-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6af33-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="6af33-133">cualquiera</span><span class="sxs-lookup"><span data-stu-id="6af33-133">any</span></span></p></td>
<td><p><span data-ttu-id="6af33-134">no</span><span class="sxs-lookup"><span data-stu-id="6af33-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="6af33-135">Compatibilidad con clientes de Lync</span><span class="sxs-lookup"><span data-stu-id="6af33-135">Lync Client Support</span></span>

<span data-ttu-id="6af33-136">La siguiente tabla identifica los clientes que admite el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="6af33-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6af33-137">Tipo de cliente</span><span class="sxs-lookup"><span data-stu-id="6af33-137">Client type</span></span></th>
<th><span data-ttu-id="6af33-138">Compatible</span><span class="sxs-lookup"><span data-stu-id="6af33-138">Supported</span></span></th>
<th><span data-ttu-id="6af33-139">Detalles</span><span class="sxs-lookup"><span data-stu-id="6af33-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6af33-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6af33-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="6af33-141">sí</span><span class="sxs-lookup"><span data-stu-id="6af33-141">yes</span></span></p></td>
<td><p><span data-ttu-id="6af33-142">Incluidas las actualizaciones acumulativas de Lync 2013 de febrero de 2013</span><span class="sxs-lookup"><span data-stu-id="6af33-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af33-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="6af33-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="6af33-144">sí</span><span class="sxs-lookup"><span data-stu-id="6af33-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af33-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6af33-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="6af33-146">no</span><span class="sxs-lookup"><span data-stu-id="6af33-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af33-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="6af33-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="6af33-148">sí</span><span class="sxs-lookup"><span data-stu-id="6af33-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af33-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="6af33-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="6af33-150">sí</span><span class="sxs-lookup"><span data-stu-id="6af33-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af33-151">Lync para Windows 8</span><span class="sxs-lookup"><span data-stu-id="6af33-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="6af33-152">no</span><span class="sxs-lookup"><span data-stu-id="6af33-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af33-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="6af33-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="6af33-154">no</span><span class="sxs-lookup"><span data-stu-id="6af33-154">no</span></span></p></td>
<td><p><span data-ttu-id="6af33-155">El VoIP debe estar deshabilitado para los clientes de Lync Mobile 2013 si lo usan los usuarios con el enrutamiento basado en la ubicación habilitado.</span><span class="sxs-lookup"><span data-stu-id="6af33-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af33-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="6af33-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="6af33-157">sí</span><span class="sxs-lookup"><span data-stu-id="6af33-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="6af33-158">Para deshabilitar VoIP para Lync Mobile 2013 clientes, asigne una directiva de movilidad con la configuración, audio/vídeo IP, deshabilitado para todos los usuarios habilitados para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="6af33-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="6af33-159">Para obtener más detalles sobre la directiva de movilidad, mira <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="6af33-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6af33-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="6af33-160">See Also</span></span>


[<span data-ttu-id="6af33-161">Planificar el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af33-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

