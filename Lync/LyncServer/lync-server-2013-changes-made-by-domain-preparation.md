---
title: 'Lync Server 2013: cambios realizados por la preparación del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b674e2c3d65aeda22838dca08ac5b016fa83359
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="50419-102">Cambios realizados por la preparación del dominio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50419-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50419-103">_**Última modificación del tema:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="50419-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="50419-104">En la siguiente tabla se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio.</span><span class="sxs-lookup"><span data-stu-id="50419-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="50419-105">A menos que se indique lo contrario, se heredan todas las ACE.</span><span class="sxs-lookup"><span data-stu-id="50419-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="50419-106">Entradas ACE agregadas a la raíz del dominio</span><span class="sxs-lookup"><span data-stu-id="50419-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="50419-107">ENTRADA</span><span class="sxs-lookup"><span data-stu-id="50419-107">ACE</span></span></th>
<th><span data-ttu-id="50419-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="50419-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="50419-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="50419-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="50419-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="50419-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="50419-111">RTCHSUniversal-servicios</span><span class="sxs-lookup"><span data-stu-id="50419-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="50419-112">Autenticados: usuarios</span><span class="sxs-lookup"><span data-stu-id="50419-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50419-113">Leer contenedor (no heredado)</span><span class="sxs-lookup"><span data-stu-id="50419-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="50419-114"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-115"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-116">No</span><span class="sxs-lookup"><span data-stu-id="50419-116">No</span></span></p></td>
<td><p><span data-ttu-id="50419-117">No</span><span class="sxs-lookup"><span data-stu-id="50419-117">No</span></span></p></td>
<td><p><span data-ttu-id="50419-118">No</span><span class="sxs-lookup"><span data-stu-id="50419-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50419-119">Leer usuario de la PropertySet de la cuenta de usuario-restricciones</span><span class="sxs-lookup"><span data-stu-id="50419-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="50419-120"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-121">No</span><span class="sxs-lookup"><span data-stu-id="50419-121">No</span></span></p></td>
<td><p><span data-ttu-id="50419-122">No</span><span class="sxs-lookup"><span data-stu-id="50419-122">No</span></span></p></td>
<td><p><span data-ttu-id="50419-123">No</span><span class="sxs-lookup"><span data-stu-id="50419-123">No</span></span></p></td>
<td><p><span data-ttu-id="50419-124">No</span><span class="sxs-lookup"><span data-stu-id="50419-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50419-125">Leer usuario PropertySet información personal</span><span class="sxs-lookup"><span data-stu-id="50419-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="50419-126"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-127">No</span><span class="sxs-lookup"><span data-stu-id="50419-127">No</span></span></p></td>
<td><p><span data-ttu-id="50419-128">No</span><span class="sxs-lookup"><span data-stu-id="50419-128">No</span></span></p></td>
<td><p><span data-ttu-id="50419-129">No</span><span class="sxs-lookup"><span data-stu-id="50419-129">No</span></span></p></td>
<td><p><span data-ttu-id="50419-130">No</span><span class="sxs-lookup"><span data-stu-id="50419-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50419-131">Leer usuario de la petición general-información</span><span class="sxs-lookup"><span data-stu-id="50419-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="50419-132"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-133">No</span><span class="sxs-lookup"><span data-stu-id="50419-133">No</span></span></p></td>
<td><p><span data-ttu-id="50419-134">No</span><span class="sxs-lookup"><span data-stu-id="50419-134">No</span></span></p></td>
<td><p><span data-ttu-id="50419-135">No</span><span class="sxs-lookup"><span data-stu-id="50419-135">No</span></span></p></td>
<td><p><span data-ttu-id="50419-136">No</span><span class="sxs-lookup"><span data-stu-id="50419-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50419-137">Leer usuario PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="50419-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="50419-138"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-139">No</span><span class="sxs-lookup"><span data-stu-id="50419-139">No</span></span></p></td>
<td><p><span data-ttu-id="50419-140">No</span><span class="sxs-lookup"><span data-stu-id="50419-140">No</span></span></p></td>
<td><p><span data-ttu-id="50419-141">No</span><span class="sxs-lookup"><span data-stu-id="50419-141">No</span></span></p></td>
<td><p><span data-ttu-id="50419-142">No</span><span class="sxs-lookup"><span data-stu-id="50419-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50419-143">Leer usuario PropertySet RTCUserSearchProperty-set</span><span class="sxs-lookup"><span data-stu-id="50419-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="50419-144"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-145">No</span><span class="sxs-lookup"><span data-stu-id="50419-145">No</span></span></p></td>
<td><p><span data-ttu-id="50419-146">No</span><span class="sxs-lookup"><span data-stu-id="50419-146">No</span></span></p></td>
<td><p><span data-ttu-id="50419-147">No</span><span class="sxs-lookup"><span data-stu-id="50419-147">No</span></span></p></td>
<td><p><span data-ttu-id="50419-148"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50419-149">Leer el usuario PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="50419-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="50419-150"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-151">No</span><span class="sxs-lookup"><span data-stu-id="50419-151">No</span></span></p></td>
<td><p><span data-ttu-id="50419-152">No</span><span class="sxs-lookup"><span data-stu-id="50419-152">No</span></span></p></td>
<td><p><span data-ttu-id="50419-153">No</span><span class="sxs-lookup"><span data-stu-id="50419-153">No</span></span></p></td>
<td><p><span data-ttu-id="50419-154">No</span><span class="sxs-lookup"><span data-stu-id="50419-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50419-155">Escribir propiedad de usuario proxy: direcciones</span><span class="sxs-lookup"><span data-stu-id="50419-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="50419-156">No</span><span class="sxs-lookup"><span data-stu-id="50419-156">No</span></span></p></td>
<td><p><span data-ttu-id="50419-157">No</span><span class="sxs-lookup"><span data-stu-id="50419-157">No</span></span></p></td>
<td><p><span data-ttu-id="50419-158"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-159">No</span><span class="sxs-lookup"><span data-stu-id="50419-159">No</span></span></p></td>
<td><p><span data-ttu-id="50419-160">No</span><span class="sxs-lookup"><span data-stu-id="50419-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50419-161">Escribir el usuario de la RTCUserSearchProperty</span><span class="sxs-lookup"><span data-stu-id="50419-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="50419-162">No</span><span class="sxs-lookup"><span data-stu-id="50419-162">No</span></span></p></td>
<td><p><span data-ttu-id="50419-163">No</span><span class="sxs-lookup"><span data-stu-id="50419-163">No</span></span></p></td>
<td><p><span data-ttu-id="50419-164"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-165">No</span><span class="sxs-lookup"><span data-stu-id="50419-165">No</span></span></p></td>
<td><p><span data-ttu-id="50419-166">No</span><span class="sxs-lookup"><span data-stu-id="50419-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50419-167">Escribir el usuario PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="50419-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="50419-168">No</span><span class="sxs-lookup"><span data-stu-id="50419-168">No</span></span></p></td>
<td><p><span data-ttu-id="50419-169">No</span><span class="sxs-lookup"><span data-stu-id="50419-169">No</span></span></p></td>
<td><p><span data-ttu-id="50419-170"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-171">No</span><span class="sxs-lookup"><span data-stu-id="50419-171">No</span></span></p></td>
<td><p><span data-ttu-id="50419-172">No</span><span class="sxs-lookup"><span data-stu-id="50419-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50419-173">Lea el complemento de DS-replicación-obtener-cambios de todos los objetos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="50419-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="50419-174">No</span><span class="sxs-lookup"><span data-stu-id="50419-174">No</span></span></p></td>
<td><p><span data-ttu-id="50419-175">No</span><span class="sxs-lookup"><span data-stu-id="50419-175">No</span></span></p></td>
<td><p><span data-ttu-id="50419-176">No</span><span class="sxs-lookup"><span data-stu-id="50419-176">No</span></span></p></td>
<td><p><span data-ttu-id="50419-177"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-178">No</span><span class="sxs-lookup"><span data-stu-id="50419-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="50419-179">En la tabla siguiente se enumeran las ACE que crea el dominio de preparación en los tres contenedores integrados: usuarios, equipos y controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="50419-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="50419-180">A menos que se indique lo contrario, se heredan todas las ACE.</span><span class="sxs-lookup"><span data-stu-id="50419-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="50419-181">Entradas ACE agregadas a contenedores integrados</span><span class="sxs-lookup"><span data-stu-id="50419-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50419-182">ENTRADA</span><span class="sxs-lookup"><span data-stu-id="50419-182">ACE</span></span></th>
<th><span data-ttu-id="50419-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="50419-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="50419-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="50419-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50419-185">Leer contenedor (no heredado)</span><span class="sxs-lookup"><span data-stu-id="50419-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="50419-186"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="50419-187"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="50419-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

