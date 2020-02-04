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
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="b00b6-102">Cambios realizados por la preparación del dominio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b00b6-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b00b6-103">_**Última modificación del tema:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="b00b6-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="b00b6-104">En la siguiente tabla se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio.</span><span class="sxs-lookup"><span data-stu-id="b00b6-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="b00b6-105">A menos que se indique lo contrario, se heredan todas las ACE.</span><span class="sxs-lookup"><span data-stu-id="b00b6-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="b00b6-106">Entradas ACE agregadas a la raíz del dominio</span><span class="sxs-lookup"><span data-stu-id="b00b6-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="b00b6-107">ENTRADA</span><span class="sxs-lookup"><span data-stu-id="b00b6-107">ACE</span></span></th>
<th><span data-ttu-id="b00b6-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="b00b6-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="b00b6-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="b00b6-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="b00b6-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="b00b6-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="b00b6-111">RTCHSUniversal-servicios</span><span class="sxs-lookup"><span data-stu-id="b00b6-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="b00b6-112">Autenticados: usuarios</span><span class="sxs-lookup"><span data-stu-id="b00b6-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b00b6-113">Leer contenedor (no heredado)</span><span class="sxs-lookup"><span data-stu-id="b00b6-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="b00b6-114"><strong>Afirmativa</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-115"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-116">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-116">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-117">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-117">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-118">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b00b6-119">Leer usuario de la PropertySet de la cuenta de usuario-restricciones</span><span class="sxs-lookup"><span data-stu-id="b00b6-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="b00b6-120"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-121">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-121">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-122">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-122">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-123">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-123">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-124">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b00b6-125">Leer usuario PropertySet información personal</span><span class="sxs-lookup"><span data-stu-id="b00b6-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="b00b6-126"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-127">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-127">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-128">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-128">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-129">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-129">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-130">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b00b6-131">Leer usuario de la petición general-información</span><span class="sxs-lookup"><span data-stu-id="b00b6-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="b00b6-132"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-133">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-133">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-134">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-134">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-135">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-135">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-136">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b00b6-137">Leer usuario PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="b00b6-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="b00b6-138"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-139">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-139">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-140">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-140">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-141">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-141">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-142">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b00b6-143">Leer usuario PropertySet RTCUserSearchProperty-set</span><span class="sxs-lookup"><span data-stu-id="b00b6-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="b00b6-144"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-145">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-145">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-146">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-146">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-147">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-147">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-148"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b00b6-149">Leer el usuario PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="b00b6-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="b00b6-150"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-151">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-151">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-152">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-152">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-153">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-153">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-154">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b00b6-155">Escribir propiedad de usuario proxy: direcciones</span><span class="sxs-lookup"><span data-stu-id="b00b6-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="b00b6-156">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-156">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-157">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-157">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-158"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-159">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-159">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-160">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b00b6-161">Escribir el usuario de la RTCUserSearchProperty</span><span class="sxs-lookup"><span data-stu-id="b00b6-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="b00b6-162">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-162">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-163">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-163">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-164"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-165">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-165">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-166">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b00b6-167">Escribir el usuario PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="b00b6-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="b00b6-168">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-168">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-169">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-169">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-170"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-171">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-171">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-172">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b00b6-173">Lea el complemento de DS-replicación-obtener-cambios de todos los objetos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="b00b6-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="b00b6-174">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-174">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-175">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-175">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-176">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-176">No</span></span></p></td>
<td><p><span data-ttu-id="b00b6-177"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-178">No</span><span class="sxs-lookup"><span data-stu-id="b00b6-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b00b6-179">En la tabla siguiente se enumeran las ACE que crea el dominio de preparación en los tres contenedores integrados: usuarios, equipos y controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="b00b6-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="b00b6-180">A menos que se indique lo contrario, se heredan todas las ACE.</span><span class="sxs-lookup"><span data-stu-id="b00b6-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="b00b6-181">Entradas ACE agregadas a contenedores integrados</span><span class="sxs-lookup"><span data-stu-id="b00b6-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b00b6-182">ENTRADA</span><span class="sxs-lookup"><span data-stu-id="b00b6-182">ACE</span></span></th>
<th><span data-ttu-id="b00b6-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="b00b6-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="b00b6-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="b00b6-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b00b6-185">Leer contenedor (no heredado)</span><span class="sxs-lookup"><span data-stu-id="b00b6-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="b00b6-186"><strong>Afirmativa</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b00b6-187"><strong>Sí</strong></span><span class="sxs-lookup"><span data-stu-id="b00b6-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

