---
title: 'Lync Server 2013: cambios realizados por Grant-CsSetupPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc63cf814f2bd901ab9753fe0f4501e7f44e2189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="6771f-102">Cambios realizados por Grant-CsSetupPermission en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6771f-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6771f-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="6771f-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="6771f-104">Para delegar la configuración, puede conceder permisos al grupo universal RTCUniversalServerAdmins de una unidad organizativa de Active Directory específica, lo que permite a los miembros del grupo RTCUniversalServerAdmins de esa OU instalar Lync Server 2013 de la el dominio no es miembro del grupo de administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="6771f-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="6771f-105">El cmdlet **Grant-CsSetupPermission** concede los permisos de grupo RTCUniversalServerAdmins en una unidad organizativa, como se especifica en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="6771f-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="6771f-106">Permisos otorgados a objetos de la OU</span><span class="sxs-lookup"><span data-stu-id="6771f-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6771f-107">Los permisos se aplican a:</span><span class="sxs-lookup"><span data-stu-id="6771f-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="6771f-108">Los permisos concedidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6771f-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6771f-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6771f-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="6771f-110">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="6771f-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6771f-111">Leer servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="6771f-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="6771f-112">Escribir servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="6771f-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="6771f-113">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="6771f-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="6771f-114">Replicar cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="6771f-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6771f-115">Objetos serviceConnectionPoint descendientes</span><span class="sxs-lookup"><span data-stu-id="6771f-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="6771f-116">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="6771f-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6771f-117">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="6771f-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="6771f-118">Permisos de escritura</span><span class="sxs-lookup"><span data-stu-id="6771f-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="6771f-119">Crear elemento secundario</span><span class="sxs-lookup"><span data-stu-id="6771f-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="6771f-120">Eliminar hijo</span><span class="sxs-lookup"><span data-stu-id="6771f-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="6771f-121">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="6771f-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="6771f-122">Write (propiedad)</span><span class="sxs-lookup"><span data-stu-id="6771f-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="6771f-123">Propiedad de lectura</span><span class="sxs-lookup"><span data-stu-id="6771f-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="6771f-124">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="6771f-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6771f-125">Objetos descendientes msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="6771f-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="6771f-126">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="6771f-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6771f-127">Write (propiedad)</span><span class="sxs-lookup"><span data-stu-id="6771f-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="6771f-128">Propiedad de lectura</span><span class="sxs-lookup"><span data-stu-id="6771f-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="6771f-129">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="6771f-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6771f-130">Objetos descendientes msRTCSIP-webcomponents</span><span class="sxs-lookup"><span data-stu-id="6771f-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="6771f-131">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="6771f-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6771f-132">Write (propiedad)</span><span class="sxs-lookup"><span data-stu-id="6771f-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="6771f-133">Propiedad de lectura</span><span class="sxs-lookup"><span data-stu-id="6771f-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="6771f-134">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="6771f-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6771f-135">Objetos descendientes msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="6771f-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="6771f-136">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="6771f-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6771f-137">Write (propiedad)</span><span class="sxs-lookup"><span data-stu-id="6771f-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="6771f-138">Propiedad de lectura</span><span class="sxs-lookup"><span data-stu-id="6771f-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="6771f-139">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="6771f-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6771f-140">Objetos descendientes msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="6771f-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="6771f-141">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="6771f-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6771f-142">Write (propiedad)</span><span class="sxs-lookup"><span data-stu-id="6771f-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="6771f-143">Propiedad de lectura</span><span class="sxs-lookup"><span data-stu-id="6771f-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="6771f-144">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="6771f-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6771f-145">Objetos descendientes msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="6771f-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="6771f-146">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="6771f-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6771f-147">Write (propiedad)</span><span class="sxs-lookup"><span data-stu-id="6771f-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="6771f-148">Propiedad de lectura</span><span class="sxs-lookup"><span data-stu-id="6771f-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="6771f-149">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="6771f-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6771f-150">Objetos descendientes msRTCSIP-punto de la</span><span class="sxs-lookup"><span data-stu-id="6771f-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="6771f-151">Acceso especial:</span><span class="sxs-lookup"><span data-stu-id="6771f-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6771f-152">Write (propiedad)</span><span class="sxs-lookup"><span data-stu-id="6771f-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="6771f-153">Propiedad de lectura</span><span class="sxs-lookup"><span data-stu-id="6771f-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="6771f-154">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="6771f-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6771f-155">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="6771f-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="6771f-156">Acceso especial para serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="6771f-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="6771f-157">Crear objetos secundarios</span><span class="sxs-lookup"><span data-stu-id="6771f-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="6771f-158">Eliminar objetos secundarios</span><span class="sxs-lookup"><span data-stu-id="6771f-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="6771f-159">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="6771f-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="6771f-160">Acceso especial para información pública:</span><span class="sxs-lookup"><span data-stu-id="6771f-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="6771f-161">Propiedad de lectura</span><span class="sxs-lookup"><span data-stu-id="6771f-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="6771f-162">Acceso especial para el nombre de host DNS:</span><span class="sxs-lookup"><span data-stu-id="6771f-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="6771f-163">Propiedad de lectura</span><span class="sxs-lookup"><span data-stu-id="6771f-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

