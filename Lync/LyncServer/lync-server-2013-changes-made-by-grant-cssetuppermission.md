---
title: 'Lync Server 2013: cambios realizados por Grant-CsSetupPermission'
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
ms.openlocfilehash: 23547ebc7faf594ee3ea72ef7d0c094846ac94b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="3e5b1-102">Cambios realizados por Grant-CsSetupPermission en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e5b1-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e5b1-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="3e5b1-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="3e5b1-104">Para delegar la configuración, puede conceder permisos al grupo universal RTCUniversalServerAdmins de una unidad organizativa (OU) de Active Directory específica, habilitando a los miembros del grupo RTCUniversalServerAdmins en dicha unidad organizativa que instalen Lync Server 2013 en el directorio especificado. dominio sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="3e5b1-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="3e5b1-105">El cmdlet **Grant-CsSetupPermission** otorga los permisos del grupo RTCUniversalServerAdmins en una unidad organizativa, como se especifica en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="3e5b1-106">Permisos otorgados a los objetos en la unidad organizativa</span><span class="sxs-lookup"><span data-stu-id="3e5b1-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e5b1-107">Los permisos se aplican a:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="3e5b1-108">Los permisos otorgados son:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e5b1-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3e5b1-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="3e5b1-110">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5b1-111">Leer servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="3e5b1-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-112">Escribir servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="3e5b1-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-113">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="3e5b1-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-114">Cambios de directorio de replicación</span><span class="sxs-lookup"><span data-stu-id="3e5b1-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e5b1-115">Objetos serviceConnectionPoint descendientes</span><span class="sxs-lookup"><span data-stu-id="3e5b1-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="3e5b1-116">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5b1-117">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="3e5b1-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-118">Escribir permisos</span><span class="sxs-lookup"><span data-stu-id="3e5b1-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-119">Crear elemento secundario</span><span class="sxs-lookup"><span data-stu-id="3e5b1-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-120">Eliminar elemento secundario</span><span class="sxs-lookup"><span data-stu-id="3e5b1-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-121">Mostrar contenido</span><span class="sxs-lookup"><span data-stu-id="3e5b1-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-122">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-123">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-124">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="3e5b1-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e5b1-125">Objetos msRTCSIP-Server descendientes</span><span class="sxs-lookup"><span data-stu-id="3e5b1-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="3e5b1-126">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5b1-127">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-128">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-129">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="3e5b1-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e5b1-130">Objetos msRTCSIP-WebComponents descendientes</span><span class="sxs-lookup"><span data-stu-id="3e5b1-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="3e5b1-131">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5b1-132">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-133">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-134">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="3e5b1-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e5b1-135">Objetos msRTCSIP-MCU descendientes</span><span class="sxs-lookup"><span data-stu-id="3e5b1-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="3e5b1-136">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5b1-137">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-138">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-139">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="3e5b1-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e5b1-140">Objetos msRTCSIP-MediationServer descendientes</span><span class="sxs-lookup"><span data-stu-id="3e5b1-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="3e5b1-141">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5b1-142">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-143">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-144">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="3e5b1-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e5b1-145">Objetos msRTCSIP-ApplicationServer descendientes</span><span class="sxs-lookup"><span data-stu-id="3e5b1-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="3e5b1-146">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5b1-147">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-148">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-149">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="3e5b1-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e5b1-150">Objetos msRTCSIP-ConnectionPoint descendientes</span><span class="sxs-lookup"><span data-stu-id="3e5b1-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="3e5b1-151">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5b1-152">Escribir propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-153">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-154">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="3e5b1-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e5b1-155">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="3e5b1-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="3e5b1-156">Acceso especial para serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5b1-157">Crear objetos secundarios</span><span class="sxs-lookup"><span data-stu-id="3e5b1-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-158">Eliminar objetos secundarios</span><span class="sxs-lookup"><span data-stu-id="3e5b1-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="3e5b1-159">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="3e5b1-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="3e5b1-160">Acceso especial a la información pública:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5b1-161">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="3e5b1-162">Acceso especial para el nombre de host DNS:</span><span class="sxs-lookup"><span data-stu-id="3e5b1-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e5b1-163">Leer propiedad</span><span class="sxs-lookup"><span data-stu-id="3e5b1-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

