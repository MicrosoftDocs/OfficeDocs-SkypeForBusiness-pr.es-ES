---
title: 'Lync Server 2013: cambios realizados por Grant-CsSetupPermission'
description: 'Lync Server 2013: cambios realizados por Grant-CsSetupPermission.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2a9156c977c993dd32e38fc6816bd08d3f65c1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543606"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="66b95-103">Cambios realizados por Grant-CsSetupPermission en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66b95-103">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66b95-104">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="66b95-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="66b95-105">Para delegar la configuración, puede conceder permisos al grupo universal RTCUniversalServerAdmins de una unidad organizativa (OU) de Active Directory específica, habilitando a los miembros del grupo RTCUniversalServerAdmins en dicha unidad organizativa que instalen Lync Server 2013 en el dominio especificado sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="66b95-105">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="66b95-106">El cmdlet **Grant-CsSetupPermission** otorga los permisos del grupo RTCUniversalServerAdmins en una unidad organizativa, como se especifica en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="66b95-106">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="66b95-107">Permisos otorgados a los objetos en la unidad organizativa</span><span class="sxs-lookup"><span data-stu-id="66b95-107">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66b95-108">Los permisos se aplican a:</span><span class="sxs-lookup"><span data-stu-id="66b95-108">Permissions apply to:</span></span></th>
<th><span data-ttu-id="66b95-109">Los permisos otorgados son:</span><span class="sxs-lookup"><span data-stu-id="66b95-109">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66b95-110">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66b95-110">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="66b95-111">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="66b95-111">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="66b95-112">Leer servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="66b95-112">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="66b95-113">Escribir servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="66b95-113">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="66b95-114">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="66b95-114">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="66b95-115">Cambios de directorio de replicación</span><span class="sxs-lookup"><span data-stu-id="66b95-115">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66b95-116">Objetos serviceConnectionPoint descendientes</span><span class="sxs-lookup"><span data-stu-id="66b95-116">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="66b95-117">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="66b95-117">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="66b95-118">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="66b95-118">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="66b95-119">Escribir permisos</span><span class="sxs-lookup"><span data-stu-id="66b95-119">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="66b95-120">Crear elemento secundario</span><span class="sxs-lookup"><span data-stu-id="66b95-120">Create child</span></span></p></li>
<li><p><span data-ttu-id="66b95-121">Eliminar elemento secundario</span><span class="sxs-lookup"><span data-stu-id="66b95-121">Delete child</span></span></p></li>
<li><p><span data-ttu-id="66b95-122">Mostrar contenido</span><span class="sxs-lookup"><span data-stu-id="66b95-122">List contents</span></span></p></li>
<li><p><span data-ttu-id="66b95-123">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-123">Write property</span></span></p></li>
<li><p><span data-ttu-id="66b95-124">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-124">Read property</span></span></p></li>
<li><p><span data-ttu-id="66b95-125">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="66b95-125">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66b95-126">Objetos msRTCSIP-Server descendientes</span><span class="sxs-lookup"><span data-stu-id="66b95-126">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="66b95-127">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="66b95-127">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="66b95-128">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-128">Write property</span></span></p></li>
<li><p><span data-ttu-id="66b95-129">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-129">Read property</span></span></p></li>
<li><p><span data-ttu-id="66b95-130">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="66b95-130">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66b95-131">Objetos msRTCSIP-WebComponents descendientes</span><span class="sxs-lookup"><span data-stu-id="66b95-131">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="66b95-132">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="66b95-132">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="66b95-133">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-133">Write property</span></span></p></li>
<li><p><span data-ttu-id="66b95-134">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-134">Read property</span></span></p></li>
<li><p><span data-ttu-id="66b95-135">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="66b95-135">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66b95-136">Objetos msRTCSIP-MCU descendientes</span><span class="sxs-lookup"><span data-stu-id="66b95-136">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="66b95-137">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="66b95-137">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="66b95-138">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-138">Write property</span></span></p></li>
<li><p><span data-ttu-id="66b95-139">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-139">Read property</span></span></p></li>
<li><p><span data-ttu-id="66b95-140">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="66b95-140">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66b95-141">Objetos msRTCSIP-MediationServer descendientes</span><span class="sxs-lookup"><span data-stu-id="66b95-141">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="66b95-142">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="66b95-142">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="66b95-143">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-143">Write property</span></span></p></li>
<li><p><span data-ttu-id="66b95-144">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-144">Read property</span></span></p></li>
<li><p><span data-ttu-id="66b95-145">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="66b95-145">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66b95-146">Objetos msRTCSIP-ApplicationServer descendientes</span><span class="sxs-lookup"><span data-stu-id="66b95-146">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="66b95-147">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="66b95-147">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="66b95-148">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-148">Write property</span></span></p></li>
<li><p><span data-ttu-id="66b95-149">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-149">Read property</span></span></p></li>
<li><p><span data-ttu-id="66b95-150">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="66b95-150">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66b95-151">Objetos msRTCSIP-ConnectionPoint descendientes</span><span class="sxs-lookup"><span data-stu-id="66b95-151">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="66b95-152">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="66b95-152">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="66b95-153">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-153">Write property</span></span></p></li>
<li><p><span data-ttu-id="66b95-154">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-154">Read property</span></span></p></li>
<li><p><span data-ttu-id="66b95-155">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="66b95-155">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66b95-156">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="66b95-156">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="66b95-157">Acceso especial para serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="66b95-157">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="66b95-158">Crear objetos secundarios</span><span class="sxs-lookup"><span data-stu-id="66b95-158">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="66b95-159">Eliminar objetos secundarios</span><span class="sxs-lookup"><span data-stu-id="66b95-159">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="66b95-160">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="66b95-160">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="66b95-161">Acceso especial a la información pública:</span><span class="sxs-lookup"><span data-stu-id="66b95-161">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="66b95-162">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-162">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="66b95-163">Acceso especial para el nombre de host DNS:</span><span class="sxs-lookup"><span data-stu-id="66b95-163">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="66b95-164">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="66b95-164">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

