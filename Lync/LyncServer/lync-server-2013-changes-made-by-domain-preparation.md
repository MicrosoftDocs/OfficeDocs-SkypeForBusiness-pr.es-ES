---
title: 'Lync Server 2013: cambios realizados por la preparación del dominio'
description: 'Lync Server 2013: cambios realizados por la preparación del dominio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26400bd1c72c6ae3b8dc1f2d2d8f6c6906b80595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543696"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="8235e-103">Cambios realizados por la preparación del dominio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8235e-103">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8235e-104">_**Última modificación del tema:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="8235e-104">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="8235e-p101">En la tabla siguiente se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. Todas las ACE se heredan, salvo que se indique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="8235e-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="8235e-107">Entradas ACE agregadas a la raíz del dominio</span><span class="sxs-lookup"><span data-stu-id="8235e-107">ACEs Added to Domain Root</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8235e-108">ACE</span><span class="sxs-lookup"><span data-stu-id="8235e-108">ACE</span></span></th>
<th><span data-ttu-id="8235e-109">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="8235e-109">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="8235e-110">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="8235e-110">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="8235e-111">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="8235e-111">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="8235e-112">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="8235e-112">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="8235e-113">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="8235e-113">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8235e-114">Read Container (no se hereda)</span><span class="sxs-lookup"><span data-stu-id="8235e-114">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="8235e-115"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-116"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-116"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-117">No</span><span class="sxs-lookup"><span data-stu-id="8235e-117">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-118">No</span><span class="sxs-lookup"><span data-stu-id="8235e-118">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-119">No</span><span class="sxs-lookup"><span data-stu-id="8235e-119">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8235e-120">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="8235e-120">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8235e-121"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-121"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-122">No</span><span class="sxs-lookup"><span data-stu-id="8235e-122">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-123">No</span><span class="sxs-lookup"><span data-stu-id="8235e-123">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-124">No</span><span class="sxs-lookup"><span data-stu-id="8235e-124">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-125">No</span><span class="sxs-lookup"><span data-stu-id="8235e-125">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8235e-126">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="8235e-126">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="8235e-127"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-127"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-128">No</span><span class="sxs-lookup"><span data-stu-id="8235e-128">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-129">No</span><span class="sxs-lookup"><span data-stu-id="8235e-129">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-130">No</span><span class="sxs-lookup"><span data-stu-id="8235e-130">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-131">No</span><span class="sxs-lookup"><span data-stu-id="8235e-131">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8235e-132">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="8235e-132">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="8235e-133"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-133"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-134">No</span><span class="sxs-lookup"><span data-stu-id="8235e-134">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-135">No</span><span class="sxs-lookup"><span data-stu-id="8235e-135">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-136">No</span><span class="sxs-lookup"><span data-stu-id="8235e-136">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-137">No</span><span class="sxs-lookup"><span data-stu-id="8235e-137">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8235e-138">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="8235e-138">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="8235e-139"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-139"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-140">No</span><span class="sxs-lookup"><span data-stu-id="8235e-140">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-141">No</span><span class="sxs-lookup"><span data-stu-id="8235e-141">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-142">No</span><span class="sxs-lookup"><span data-stu-id="8235e-142">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-143">No</span><span class="sxs-lookup"><span data-stu-id="8235e-143">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8235e-144">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="8235e-144">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="8235e-145"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-145"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-146">No</span><span class="sxs-lookup"><span data-stu-id="8235e-146">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-147">No</span><span class="sxs-lookup"><span data-stu-id="8235e-147">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-148">No</span><span class="sxs-lookup"><span data-stu-id="8235e-148">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-149"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-149"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8235e-150">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="8235e-150">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="8235e-151"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-151"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-152">No</span><span class="sxs-lookup"><span data-stu-id="8235e-152">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-153">No</span><span class="sxs-lookup"><span data-stu-id="8235e-153">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-154">No</span><span class="sxs-lookup"><span data-stu-id="8235e-154">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-155">No</span><span class="sxs-lookup"><span data-stu-id="8235e-155">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8235e-156">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="8235e-156">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="8235e-157">No</span><span class="sxs-lookup"><span data-stu-id="8235e-157">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-158">No</span><span class="sxs-lookup"><span data-stu-id="8235e-158">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-159"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-159"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-160">No</span><span class="sxs-lookup"><span data-stu-id="8235e-160">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-161">No</span><span class="sxs-lookup"><span data-stu-id="8235e-161">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8235e-162">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="8235e-162">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="8235e-163">No</span><span class="sxs-lookup"><span data-stu-id="8235e-163">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-164">No</span><span class="sxs-lookup"><span data-stu-id="8235e-164">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-165"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-165"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-166">No</span><span class="sxs-lookup"><span data-stu-id="8235e-166">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-167">No</span><span class="sxs-lookup"><span data-stu-id="8235e-167">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8235e-168">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="8235e-168">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="8235e-169">No</span><span class="sxs-lookup"><span data-stu-id="8235e-169">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-170">No</span><span class="sxs-lookup"><span data-stu-id="8235e-170">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-171"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-171"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-172">No</span><span class="sxs-lookup"><span data-stu-id="8235e-172">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-173">No</span><span class="sxs-lookup"><span data-stu-id="8235e-173">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8235e-174">Read PropertySet DS-Replication-Get-Changes de todos los objetos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="8235e-174">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="8235e-175">No</span><span class="sxs-lookup"><span data-stu-id="8235e-175">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-176">No</span><span class="sxs-lookup"><span data-stu-id="8235e-176">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-177">No</span><span class="sxs-lookup"><span data-stu-id="8235e-177">No</span></span></p></td>
<td><p><span data-ttu-id="8235e-178"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-178"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-179">No</span><span class="sxs-lookup"><span data-stu-id="8235e-179">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8235e-p102">En la tabla siguiente se enumeran las ACE que crea la preparación del dominio en los tres contenedores integrados: usuarios, equipos y controladores de dominio. Todas las ACE se heredan, salvo que se indique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="8235e-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="8235e-182">Entradas ACE agregadas a los contenedores integrados</span><span class="sxs-lookup"><span data-stu-id="8235e-182">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8235e-183">ACE</span><span class="sxs-lookup"><span data-stu-id="8235e-183">ACE</span></span></th>
<th><span data-ttu-id="8235e-184">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="8235e-184">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="8235e-185">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="8235e-185">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8235e-186">Read Container (no se hereda)</span><span class="sxs-lookup"><span data-stu-id="8235e-186">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="8235e-187"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-187"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="8235e-188"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="8235e-188"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

