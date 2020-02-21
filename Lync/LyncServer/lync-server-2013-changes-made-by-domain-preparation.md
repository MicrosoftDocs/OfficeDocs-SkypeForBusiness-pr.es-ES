---
title: 'Lync Server 2013: cambios realizados por la preparación del dominio'
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
ms.openlocfilehash: 74fe383cf773e1cdfa645a3f8513167fd7472958
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="c6453-102">Cambios realizados por la preparación del dominio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6453-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6453-103">_**Última modificación del tema:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="c6453-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="c6453-p101">En la tabla siguiente se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. Todas las ACE se heredan, salvo que se indique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="c6453-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="c6453-106">Entradas ACE agregadas a la raíz del dominio</span><span class="sxs-lookup"><span data-stu-id="c6453-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="c6453-107">ACE</span><span class="sxs-lookup"><span data-stu-id="c6453-107">ACE</span></span></th>
<th><span data-ttu-id="c6453-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="c6453-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="c6453-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="c6453-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="c6453-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="c6453-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="c6453-111">RTCHSUniversal-servicios</span><span class="sxs-lookup"><span data-stu-id="c6453-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="c6453-112">Usuarios autenticados</span><span class="sxs-lookup"><span data-stu-id="c6453-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6453-113">Read Container (no se hereda)</span><span class="sxs-lookup"><span data-stu-id="c6453-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="c6453-114"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-115"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-116">No</span><span class="sxs-lookup"><span data-stu-id="c6453-116">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-117">No</span><span class="sxs-lookup"><span data-stu-id="c6453-117">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-118">No</span><span class="sxs-lookup"><span data-stu-id="c6453-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6453-119">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="c6453-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="c6453-120"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-121">No</span><span class="sxs-lookup"><span data-stu-id="c6453-121">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-122">No</span><span class="sxs-lookup"><span data-stu-id="c6453-122">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-123">No</span><span class="sxs-lookup"><span data-stu-id="c6453-123">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-124">No</span><span class="sxs-lookup"><span data-stu-id="c6453-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6453-125">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="c6453-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="c6453-126"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-127">No</span><span class="sxs-lookup"><span data-stu-id="c6453-127">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-128">No</span><span class="sxs-lookup"><span data-stu-id="c6453-128">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-129">No</span><span class="sxs-lookup"><span data-stu-id="c6453-129">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-130">No</span><span class="sxs-lookup"><span data-stu-id="c6453-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6453-131">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="c6453-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="c6453-132"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-133">No</span><span class="sxs-lookup"><span data-stu-id="c6453-133">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-134">No</span><span class="sxs-lookup"><span data-stu-id="c6453-134">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-135">No</span><span class="sxs-lookup"><span data-stu-id="c6453-135">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-136">No</span><span class="sxs-lookup"><span data-stu-id="c6453-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6453-137">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="c6453-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="c6453-138"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-139">No</span><span class="sxs-lookup"><span data-stu-id="c6453-139">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-140">No</span><span class="sxs-lookup"><span data-stu-id="c6453-140">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-141">No</span><span class="sxs-lookup"><span data-stu-id="c6453-141">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-142">No</span><span class="sxs-lookup"><span data-stu-id="c6453-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6453-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="c6453-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="c6453-144"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-145">No</span><span class="sxs-lookup"><span data-stu-id="c6453-145">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-146">No</span><span class="sxs-lookup"><span data-stu-id="c6453-146">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-147">No</span><span class="sxs-lookup"><span data-stu-id="c6453-147">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-148"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6453-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c6453-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="c6453-150"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-151">No</span><span class="sxs-lookup"><span data-stu-id="c6453-151">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-152">No</span><span class="sxs-lookup"><span data-stu-id="c6453-152">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-153">No</span><span class="sxs-lookup"><span data-stu-id="c6453-153">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-154">No</span><span class="sxs-lookup"><span data-stu-id="c6453-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6453-155">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="c6453-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="c6453-156">No</span><span class="sxs-lookup"><span data-stu-id="c6453-156">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-157">No</span><span class="sxs-lookup"><span data-stu-id="c6453-157">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-158"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-159">No</span><span class="sxs-lookup"><span data-stu-id="c6453-159">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-160">No</span><span class="sxs-lookup"><span data-stu-id="c6453-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6453-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="c6453-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="c6453-162">No</span><span class="sxs-lookup"><span data-stu-id="c6453-162">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-163">No</span><span class="sxs-lookup"><span data-stu-id="c6453-163">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-164"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-165">No</span><span class="sxs-lookup"><span data-stu-id="c6453-165">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-166">No</span><span class="sxs-lookup"><span data-stu-id="c6453-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6453-167">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c6453-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="c6453-168">No</span><span class="sxs-lookup"><span data-stu-id="c6453-168">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-169">No</span><span class="sxs-lookup"><span data-stu-id="c6453-169">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-170"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-171">No</span><span class="sxs-lookup"><span data-stu-id="c6453-171">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-172">No</span><span class="sxs-lookup"><span data-stu-id="c6453-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6453-173">Read PropertySet DS-Replication-Get-Changes de todos los objetos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="c6453-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="c6453-174">No</span><span class="sxs-lookup"><span data-stu-id="c6453-174">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-175">No</span><span class="sxs-lookup"><span data-stu-id="c6453-175">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-176">No</span><span class="sxs-lookup"><span data-stu-id="c6453-176">No</span></span></p></td>
<td><p><span data-ttu-id="c6453-177"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-178">No</span><span class="sxs-lookup"><span data-stu-id="c6453-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6453-p102">En la tabla siguiente se enumeran las ACE que crea la preparación del dominio en los tres contenedores integrados: usuarios, equipos y controladores de dominio. Todas las ACE se heredan, salvo que se indique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="c6453-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="c6453-181">Entradas ACE agregadas a los contenedores integrados</span><span class="sxs-lookup"><span data-stu-id="c6453-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6453-182">ACE</span><span class="sxs-lookup"><span data-stu-id="c6453-182">ACE</span></span></th>
<th><span data-ttu-id="c6453-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="c6453-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="c6453-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="c6453-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6453-185">Read Container (no se hereda)</span><span class="sxs-lookup"><span data-stu-id="c6453-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="c6453-186"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6453-187"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="c6453-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

