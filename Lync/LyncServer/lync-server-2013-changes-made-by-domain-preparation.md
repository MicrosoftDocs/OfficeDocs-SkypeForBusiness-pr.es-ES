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
ms.openlocfilehash: fb693f79470e7d68a1aaf662c9ab82b8bafa5c39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="d29c9-102">Cambios realizados por la preparación del dominio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d29c9-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d29c9-103">_**Última modificación del tema:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="d29c9-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="d29c9-p101">En la tabla siguiente se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. Todas las ACE se heredan, salvo que se indique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="d29c9-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="d29c9-106">Entradas ACE agregadas a la raíz del dominio</span><span class="sxs-lookup"><span data-stu-id="d29c9-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="d29c9-107">ACE</span><span class="sxs-lookup"><span data-stu-id="d29c9-107">ACE</span></span></th>
<th><span data-ttu-id="d29c9-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="d29c9-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="d29c9-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="d29c9-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="d29c9-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="d29c9-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="d29c9-111">RTCHSUniversal-servicios</span><span class="sxs-lookup"><span data-stu-id="d29c9-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="d29c9-112">Usuarios autenticados</span><span class="sxs-lookup"><span data-stu-id="d29c9-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d29c9-113">Read Container (no se hereda)</span><span class="sxs-lookup"><span data-stu-id="d29c9-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="d29c9-114"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-115"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-116">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-116">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-117">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-117">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-118">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d29c9-119">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="d29c9-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="d29c9-120"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-121">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-121">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-122">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-122">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-123">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-123">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-124">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d29c9-125">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="d29c9-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="d29c9-126"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-127">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-127">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-128">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-128">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-129">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-129">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-130">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d29c9-131">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="d29c9-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="d29c9-132"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-133">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-133">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-134">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-134">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-135">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-135">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-136">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d29c9-137">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="d29c9-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="d29c9-138"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-139">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-139">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-140">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-140">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-141">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-141">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-142">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d29c9-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="d29c9-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="d29c9-144"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-145">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-145">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-146">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-146">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-147">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-147">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-148"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d29c9-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d29c9-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="d29c9-150"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-151">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-151">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-152">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-152">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-153">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-153">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-154">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d29c9-155">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="d29c9-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="d29c9-156">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-156">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-157">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-157">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-158"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-159">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-159">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-160">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d29c9-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="d29c9-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="d29c9-162">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-162">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-163">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-163">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-164"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-165">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-165">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-166">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d29c9-167">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d29c9-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="d29c9-168">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-168">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-169">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-169">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-170"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-171">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-171">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-172">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d29c9-173">Read PropertySet DS-Replication-Get-Changes de todos los objetos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="d29c9-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="d29c9-174">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-174">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-175">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-175">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-176">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-176">No</span></span></p></td>
<td><p><span data-ttu-id="d29c9-177"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-178">No</span><span class="sxs-lookup"><span data-stu-id="d29c9-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d29c9-p102">En la tabla siguiente se enumeran las ACE que crea la preparación del dominio en los tres contenedores integrados: usuarios, equipos y controladores de dominio. Todas las ACE se heredan, salvo que se indique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="d29c9-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="d29c9-181">Entradas ACE agregadas a los contenedores integrados</span><span class="sxs-lookup"><span data-stu-id="d29c9-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d29c9-182">ACE</span><span class="sxs-lookup"><span data-stu-id="d29c9-182">ACE</span></span></th>
<th><span data-ttu-id="d29c9-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="d29c9-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="d29c9-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="d29c9-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d29c9-185">Read Container (no se hereda)</span><span class="sxs-lookup"><span data-stu-id="d29c9-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="d29c9-186"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d29c9-187"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="d29c9-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

