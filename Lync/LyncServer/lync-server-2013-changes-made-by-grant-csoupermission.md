---
title: 'Lync Server 2013: cambios realizados por Grant-CsOUPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="d2aa7-102">Cambios realizados por Grant-CsOUPermission en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2aa7-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2aa7-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="d2aa7-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="d2aa7-104">Para delegar la administración de Lync Server 2013, puede Agregar permisos a unidades organizativas (OU) especificadas de modo que los miembros de los grupos RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="d2aa7-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="d2aa7-105">El cmdlet **Grant-CsOuPermission** otorga permisos a objetos en la ou especificada, tal como se especifica en las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="d2aa7-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="d2aa7-106">Conceder permisos a los objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="d2aa7-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="d2aa7-107">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de usuario en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2aa7-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="d2aa7-108">Permisos otorgados para objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="d2aa7-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2aa7-109">Mesa</span><span class="sxs-lookup"><span data-stu-id="d2aa7-109">Group</span></span></th>
<th><span data-ttu-id="d2aa7-110">Permiso</span><span class="sxs-lookup"><span data-stu-id="d2aa7-110">Permission</span></span></th>
<th><span data-ttu-id="d2aa7-111">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="d2aa7-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="d2aa7-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-113">Replicar cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="d2aa7-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-114">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2aa7-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-116">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="d2aa7-116">List contents</span></span></p>
<p><span data-ttu-id="d2aa7-117">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="d2aa7-117">Read all properties</span></span></p>
<p><span data-ttu-id="d2aa7-118">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="d2aa7-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-119">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-121">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="d2aa7-121">List contents</span></span></p>
<p><span data-ttu-id="d2aa7-122">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="d2aa7-122">Read all properties</span></span></p>
<p><span data-ttu-id="d2aa7-123">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="d2aa7-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-124">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2aa7-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-126">Leer RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-127">Leer RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-128">Leer RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-129">Leer información pública</span><span class="sxs-lookup"><span data-stu-id="d2aa7-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="d2aa7-130">Leer información general</span><span class="sxs-lookup"><span data-stu-id="d2aa7-130">Read General-Information</span></span></p>
<p><span data-ttu-id="d2aa7-131">Leer las restricciones de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="d2aa7-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-132">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="d2aa7-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="d2aa7-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-134">Escribir RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-135">Escribir msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="d2aa7-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="d2aa7-136">Escribir RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-137">Escribir RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-138">Escribir proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d2aa7-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-139">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="d2aa7-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="d2aa7-140">Concesión de permisos para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="d2aa7-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="d2aa7-141">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de equipo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2aa7-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="d2aa7-142">Permisos otorgados para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="d2aa7-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2aa7-143">Mesa</span><span class="sxs-lookup"><span data-stu-id="d2aa7-143">Group</span></span></th>
<th><span data-ttu-id="d2aa7-144">Permiso</span><span class="sxs-lookup"><span data-stu-id="d2aa7-144">Permission</span></span></th>
<th><span data-ttu-id="d2aa7-145">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="d2aa7-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="d2aa7-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-147">Replicar cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="d2aa7-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-148">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2aa7-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-150">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="d2aa7-150">List contents</span></span></p>
<p><span data-ttu-id="d2aa7-151">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="d2aa7-151">Read all properties</span></span></p>
<p><span data-ttu-id="d2aa7-152">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="d2aa7-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-153">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-155">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="d2aa7-155">List contents</span></span></p>
<p><span data-ttu-id="d2aa7-156">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="d2aa7-156">Read all properties</span></span></p>
<p><span data-ttu-id="d2aa7-157">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="d2aa7-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-158">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2aa7-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-160">Leer información pública</span><span class="sxs-lookup"><span data-stu-id="d2aa7-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="d2aa7-161">Lectura validada: nombre-DNS-host</span><span class="sxs-lookup"><span data-stu-id="d2aa7-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-162">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="d2aa7-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="d2aa7-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-164">Leer información pública</span><span class="sxs-lookup"><span data-stu-id="d2aa7-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="d2aa7-165">Lectura validada: nombre-DNS-host</span><span class="sxs-lookup"><span data-stu-id="d2aa7-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-166">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="d2aa7-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="d2aa7-167">Concesión de permisos para objetos de contacto o de AppContact</span><span class="sxs-lookup"><span data-stu-id="d2aa7-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="d2aa7-168">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de contacto o objetos de AppContact en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2aa7-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="d2aa7-169">Permisos concedidos para objetos de contacto o AppContact</span><span class="sxs-lookup"><span data-stu-id="d2aa7-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2aa7-170">Mesa</span><span class="sxs-lookup"><span data-stu-id="d2aa7-170">Group</span></span></th>
<th><span data-ttu-id="d2aa7-171">Permiso</span><span class="sxs-lookup"><span data-stu-id="d2aa7-171">Permission</span></span></th>
<th><span data-ttu-id="d2aa7-172">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="d2aa7-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="d2aa7-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-174">Replicar cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="d2aa7-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-175">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2aa7-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-177">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="d2aa7-177">List contents</span></span></p>
<p><span data-ttu-id="d2aa7-178">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="d2aa7-178">Read all properties</span></span></p>
<p><span data-ttu-id="d2aa7-179">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="d2aa7-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-180">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-182">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="d2aa7-182">List contents</span></span></p>
<p><span data-ttu-id="d2aa7-183">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="d2aa7-183">Read all properties</span></span></p>
<p><span data-ttu-id="d2aa7-184">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="d2aa7-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-185">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2aa7-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-187">Leer RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-188">Leer RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-189">Leer RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-190">Leer información pública</span><span class="sxs-lookup"><span data-stu-id="d2aa7-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="d2aa7-191">Leer información general</span><span class="sxs-lookup"><span data-stu-id="d2aa7-191">Read General-Information</span></span></p>
<p><span data-ttu-id="d2aa7-192">Leer información personal</span><span class="sxs-lookup"><span data-stu-id="d2aa7-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="d2aa7-193">Leer las restricciones de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="d2aa7-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-194">Objetos de contacto descendiente</span><span class="sxs-lookup"><span data-stu-id="d2aa7-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="d2aa7-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-196">Escribir RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-197">Escribir otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="d2aa7-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="d2aa7-198">Escribir displayName</span><span class="sxs-lookup"><span data-stu-id="d2aa7-198">Write displayName</span></span></p>
<p><span data-ttu-id="d2aa7-199">Escribir Descripción</span><span class="sxs-lookup"><span data-stu-id="d2aa7-199">Write description</span></span></p>
<p><span data-ttu-id="d2aa7-200">Escribir telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="d2aa7-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="d2aa7-201">Escribir msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="d2aa7-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="d2aa7-202">Escribir RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-203">Escribir RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-204">Escribir proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d2aa7-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-205">Objetos de contacto descendiente</span><span class="sxs-lookup"><span data-stu-id="d2aa7-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="d2aa7-206">Conceder permisos a objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="d2aa7-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="d2aa7-207">Al ejecutar el cmdlet **Grant-CsOuPermission** en una unidad organizativa, se conceden permisos a los grupos, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2aa7-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="d2aa7-208">Permisos concedidos para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="d2aa7-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2aa7-209">Mesa</span><span class="sxs-lookup"><span data-stu-id="d2aa7-209">Group</span></span></th>
<th><span data-ttu-id="d2aa7-210">Permiso</span><span class="sxs-lookup"><span data-stu-id="d2aa7-210">Permission</span></span></th>
<th><span data-ttu-id="d2aa7-211">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="d2aa7-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="d2aa7-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-213">Replicar cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="d2aa7-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-214">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2aa7-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-216">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="d2aa7-216">List contents</span></span></p>
<p><span data-ttu-id="d2aa7-217">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="d2aa7-217">Read all properties</span></span></p>
<p><span data-ttu-id="d2aa7-218">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="d2aa7-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-219">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-221">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="d2aa7-221">List contents</span></span></p>
<p><span data-ttu-id="d2aa7-222">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="d2aa7-222">Read all properties</span></span></p>
<p><span data-ttu-id="d2aa7-223">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="d2aa7-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-224">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2aa7-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-226">Leer RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-227">Leer RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-228">Leer RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-229">Leer información pública</span><span class="sxs-lookup"><span data-stu-id="d2aa7-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="d2aa7-230">Leer información personal</span><span class="sxs-lookup"><span data-stu-id="d2aa7-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="d2aa7-231">Leer información general</span><span class="sxs-lookup"><span data-stu-id="d2aa7-231">Read General-Information</span></span></p>
<p><span data-ttu-id="d2aa7-232">Leer las restricciones de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="d2aa7-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-233">Objetos de contacto descendiente</span><span class="sxs-lookup"><span data-stu-id="d2aa7-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="d2aa7-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-235">Crear elemento secundario</span><span class="sxs-lookup"><span data-stu-id="d2aa7-235">Create child</span></span></p>
<p><span data-ttu-id="d2aa7-236">Eliminar hijo</span><span class="sxs-lookup"><span data-stu-id="d2aa7-236">Delete child</span></span></p>
<p><span data-ttu-id="d2aa7-237">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="d2aa7-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-238">Con</span><span class="sxs-lookup"><span data-stu-id="d2aa7-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2aa7-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="d2aa7-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-240">Escribir displayName</span><span class="sxs-lookup"><span data-stu-id="d2aa7-240">Write displayName</span></span></p>
<p><span data-ttu-id="d2aa7-241">Escribir Descripción</span><span class="sxs-lookup"><span data-stu-id="d2aa7-241">Write description</span></span></p>
<p><span data-ttu-id="d2aa7-242">Escribir telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="d2aa7-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-243">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="d2aa7-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="d2aa7-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-245">Escribir RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-246">Escribir otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="d2aa7-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="d2aa7-247">Escribir displayName</span><span class="sxs-lookup"><span data-stu-id="d2aa7-247">Write displayName</span></span></p>
<p><span data-ttu-id="d2aa7-248">Escribir Descripción</span><span class="sxs-lookup"><span data-stu-id="d2aa7-248">Write description</span></span></p>
<p><span data-ttu-id="d2aa7-249">Escribir telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="d2aa7-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="d2aa7-250">Escribir msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="d2aa7-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="d2aa7-251">Escribir RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-252">Escribir RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-253">Escribir proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d2aa7-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-254">Objetos de contacto descendiente</span><span class="sxs-lookup"><span data-stu-id="d2aa7-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="d2aa7-255">Conceder permisos a objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="d2aa7-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="d2aa7-256">Al ejecutar el cmdlet **Grant-CsOuPermission** para los objetos InetOrgPerson de una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2aa7-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="d2aa7-257">Permisos otorgados a los objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="d2aa7-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2aa7-258">Mesa</span><span class="sxs-lookup"><span data-stu-id="d2aa7-258">Group</span></span></th>
<th><span data-ttu-id="d2aa7-259">Permiso</span><span class="sxs-lookup"><span data-stu-id="d2aa7-259">Permission</span></span></th>
<th><span data-ttu-id="d2aa7-260">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="d2aa7-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="d2aa7-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-262">Replicar cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="d2aa7-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-263">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2aa7-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-265">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="d2aa7-265">List contents</span></span></p>
<p><span data-ttu-id="d2aa7-266">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="d2aa7-266">Read all properties</span></span></p>
<p><span data-ttu-id="d2aa7-267">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="d2aa7-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-268">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-270">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="d2aa7-270">List contents</span></span></p>
<p><span data-ttu-id="d2aa7-271">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="d2aa7-271">Read all properties</span></span></p>
<p><span data-ttu-id="d2aa7-272">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="d2aa7-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-273">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="d2aa7-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2aa7-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d2aa7-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-275">Leer RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-276">Leer RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-277">Leer RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-278">Leer información personal</span><span class="sxs-lookup"><span data-stu-id="d2aa7-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="d2aa7-279">Leer información pública</span><span class="sxs-lookup"><span data-stu-id="d2aa7-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="d2aa7-280">Leer información general</span><span class="sxs-lookup"><span data-stu-id="d2aa7-280">Read General-Information</span></span></p>
<p><span data-ttu-id="d2aa7-281">Leer las restricciones de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="d2aa7-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-282">Objetos descendientes de inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="d2aa7-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2aa7-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="d2aa7-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-284">Escribir RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-285">Escribir RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-286">Escribir RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d2aa7-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="d2aa7-287">Escribir proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d2aa7-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="d2aa7-288">Objetos descendientes de inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="d2aa7-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

