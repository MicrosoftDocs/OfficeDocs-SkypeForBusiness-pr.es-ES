---
title: 'Lync Server 2013: cambios realizados por Grant-CsOUPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="ba147-102">Cambios realizados por Grant-CsOUPermission en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba147-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba147-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="ba147-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="ba147-104">Para delegar la administración de Lync Server 2013, puede Agregar permisos a unidades organizativas (OU) especificadas de modo que los miembros de los grupos RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="ba147-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="ba147-105">El cmdlet **Grant-CsOuPermission** otorga permisos a objetos en la ou especificada, tal como se especifica en las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="ba147-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="ba147-106">Conceder permisos a los objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="ba147-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="ba147-107">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de usuario en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ba147-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="ba147-108">Permisos otorgados para objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="ba147-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba147-109">Mesa</span><span class="sxs-lookup"><span data-stu-id="ba147-109">Group</span></span></th>
<th><span data-ttu-id="ba147-110">Permiso</span><span class="sxs-lookup"><span data-stu-id="ba147-110">Permission</span></span></th>
<th><span data-ttu-id="ba147-111">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="ba147-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba147-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ba147-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ba147-113">Replicar cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="ba147-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ba147-114">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba147-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-116">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="ba147-116">List contents</span></span></p>
<p><span data-ttu-id="ba147-117">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="ba147-117">Read all properties</span></span></p>
<p><span data-ttu-id="ba147-118">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="ba147-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ba147-119">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba147-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-121">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="ba147-121">List contents</span></span></p>
<p><span data-ttu-id="ba147-122">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="ba147-122">Read all properties</span></span></p>
<p><span data-ttu-id="ba147-123">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="ba147-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ba147-124">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba147-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-126">Leer RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ba147-127">Leer RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ba147-128">Leer RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ba147-129">Leer información pública</span><span class="sxs-lookup"><span data-stu-id="ba147-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="ba147-130">Leer información general</span><span class="sxs-lookup"><span data-stu-id="ba147-130">Read General-Information</span></span></p>
<p><span data-ttu-id="ba147-131">Leer las restricciones de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="ba147-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ba147-132">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="ba147-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba147-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ba147-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ba147-134">Escribir RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ba147-135">Escribir msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="ba147-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="ba147-136">Escribir RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ba147-137">Escribir RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ba147-138">Escribir proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ba147-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ba147-139">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="ba147-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="ba147-140">Concesión de permisos para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="ba147-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="ba147-141">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de equipo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ba147-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="ba147-142">Permisos otorgados para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="ba147-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba147-143">Mesa</span><span class="sxs-lookup"><span data-stu-id="ba147-143">Group</span></span></th>
<th><span data-ttu-id="ba147-144">Permiso</span><span class="sxs-lookup"><span data-stu-id="ba147-144">Permission</span></span></th>
<th><span data-ttu-id="ba147-145">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="ba147-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba147-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ba147-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ba147-147">Replicar cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="ba147-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ba147-148">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba147-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-150">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="ba147-150">List contents</span></span></p>
<p><span data-ttu-id="ba147-151">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="ba147-151">Read all properties</span></span></p>
<p><span data-ttu-id="ba147-152">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="ba147-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ba147-153">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba147-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-155">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="ba147-155">List contents</span></span></p>
<p><span data-ttu-id="ba147-156">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="ba147-156">Read all properties</span></span></p>
<p><span data-ttu-id="ba147-157">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="ba147-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ba147-158">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba147-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-160">Leer información pública</span><span class="sxs-lookup"><span data-stu-id="ba147-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="ba147-161">Lectura validada: nombre-DNS-host</span><span class="sxs-lookup"><span data-stu-id="ba147-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="ba147-162">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="ba147-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba147-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ba147-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ba147-164">Leer información pública</span><span class="sxs-lookup"><span data-stu-id="ba147-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="ba147-165">Lectura validada: nombre-DNS-host</span><span class="sxs-lookup"><span data-stu-id="ba147-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="ba147-166">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="ba147-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="ba147-167">Concesión de permisos para objetos de contacto o de AppContact</span><span class="sxs-lookup"><span data-stu-id="ba147-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="ba147-168">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de contacto o objetos de AppContact en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ba147-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="ba147-169">Permisos concedidos para objetos de contacto o AppContact</span><span class="sxs-lookup"><span data-stu-id="ba147-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba147-170">Mesa</span><span class="sxs-lookup"><span data-stu-id="ba147-170">Group</span></span></th>
<th><span data-ttu-id="ba147-171">Permiso</span><span class="sxs-lookup"><span data-stu-id="ba147-171">Permission</span></span></th>
<th><span data-ttu-id="ba147-172">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="ba147-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba147-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ba147-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ba147-174">Replicar cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="ba147-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ba147-175">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba147-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-177">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="ba147-177">List contents</span></span></p>
<p><span data-ttu-id="ba147-178">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="ba147-178">Read all properties</span></span></p>
<p><span data-ttu-id="ba147-179">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="ba147-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ba147-180">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba147-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-182">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="ba147-182">List contents</span></span></p>
<p><span data-ttu-id="ba147-183">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="ba147-183">Read all properties</span></span></p>
<p><span data-ttu-id="ba147-184">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="ba147-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ba147-185">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba147-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-187">Leer RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ba147-188">Leer RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ba147-189">Leer RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ba147-190">Leer información pública</span><span class="sxs-lookup"><span data-stu-id="ba147-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="ba147-191">Leer información general</span><span class="sxs-lookup"><span data-stu-id="ba147-191">Read General-Information</span></span></p>
<p><span data-ttu-id="ba147-192">Leer información personal</span><span class="sxs-lookup"><span data-stu-id="ba147-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="ba147-193">Leer las restricciones de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="ba147-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ba147-194">Objetos de contacto descendiente</span><span class="sxs-lookup"><span data-stu-id="ba147-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba147-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ba147-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ba147-196">Escribir RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ba147-197">Escribir otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="ba147-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="ba147-198">Escribir displayName</span><span class="sxs-lookup"><span data-stu-id="ba147-198">Write displayName</span></span></p>
<p><span data-ttu-id="ba147-199">Escribir Descripción</span><span class="sxs-lookup"><span data-stu-id="ba147-199">Write description</span></span></p>
<p><span data-ttu-id="ba147-200">Escribir telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="ba147-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="ba147-201">Escribir msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="ba147-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="ba147-202">Escribir RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ba147-203">Escribir RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ba147-204">Escribir proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ba147-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ba147-205">Objetos de contacto descendiente</span><span class="sxs-lookup"><span data-stu-id="ba147-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="ba147-206">Conceder permisos a objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ba147-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="ba147-207">Al ejecutar el cmdlet **Grant-CsOuPermission** en una unidad organizativa, se conceden permisos a los grupos, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ba147-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="ba147-208">Permisos concedidos para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ba147-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba147-209">Mesa</span><span class="sxs-lookup"><span data-stu-id="ba147-209">Group</span></span></th>
<th><span data-ttu-id="ba147-210">Permiso</span><span class="sxs-lookup"><span data-stu-id="ba147-210">Permission</span></span></th>
<th><span data-ttu-id="ba147-211">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="ba147-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba147-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ba147-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ba147-213">Replicar cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="ba147-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ba147-214">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba147-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-216">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="ba147-216">List contents</span></span></p>
<p><span data-ttu-id="ba147-217">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="ba147-217">Read all properties</span></span></p>
<p><span data-ttu-id="ba147-218">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="ba147-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ba147-219">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba147-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-221">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="ba147-221">List contents</span></span></p>
<p><span data-ttu-id="ba147-222">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="ba147-222">Read all properties</span></span></p>
<p><span data-ttu-id="ba147-223">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="ba147-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ba147-224">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba147-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-226">Leer RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ba147-227">Leer RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ba147-228">Leer RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ba147-229">Leer información pública</span><span class="sxs-lookup"><span data-stu-id="ba147-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="ba147-230">Leer información personal</span><span class="sxs-lookup"><span data-stu-id="ba147-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="ba147-231">Leer información general</span><span class="sxs-lookup"><span data-stu-id="ba147-231">Read General-Information</span></span></p>
<p><span data-ttu-id="ba147-232">Leer las restricciones de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="ba147-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ba147-233">Objetos de contacto descendiente</span><span class="sxs-lookup"><span data-stu-id="ba147-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba147-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ba147-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ba147-235">Crear elemento secundario</span><span class="sxs-lookup"><span data-stu-id="ba147-235">Create child</span></span></p>
<p><span data-ttu-id="ba147-236">Eliminar hijo</span><span class="sxs-lookup"><span data-stu-id="ba147-236">Delete child</span></span></p>
<p><span data-ttu-id="ba147-237">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="ba147-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="ba147-238">Con</span><span class="sxs-lookup"><span data-stu-id="ba147-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba147-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ba147-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ba147-240">Escribir displayName</span><span class="sxs-lookup"><span data-stu-id="ba147-240">Write displayName</span></span></p>
<p><span data-ttu-id="ba147-241">Escribir Descripción</span><span class="sxs-lookup"><span data-stu-id="ba147-241">Write description</span></span></p>
<p><span data-ttu-id="ba147-242">Escribir telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="ba147-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="ba147-243">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="ba147-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba147-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ba147-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ba147-245">Escribir RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ba147-246">Escribir otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="ba147-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="ba147-247">Escribir displayName</span><span class="sxs-lookup"><span data-stu-id="ba147-247">Write displayName</span></span></p>
<p><span data-ttu-id="ba147-248">Escribir Descripción</span><span class="sxs-lookup"><span data-stu-id="ba147-248">Write description</span></span></p>
<p><span data-ttu-id="ba147-249">Escribir telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="ba147-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="ba147-250">Escribir msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="ba147-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="ba147-251">Escribir RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ba147-252">Escribir RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ba147-253">Escribir proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ba147-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ba147-254">Objetos de contacto descendiente</span><span class="sxs-lookup"><span data-stu-id="ba147-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="ba147-255">Conceder permisos a objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="ba147-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="ba147-256">Al ejecutar el cmdlet **Grant-CsOuPermission** para los objetos InetOrgPerson de una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ba147-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="ba147-257">Permisos otorgados a los objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="ba147-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba147-258">Mesa</span><span class="sxs-lookup"><span data-stu-id="ba147-258">Group</span></span></th>
<th><span data-ttu-id="ba147-259">Permiso</span><span class="sxs-lookup"><span data-stu-id="ba147-259">Permission</span></span></th>
<th><span data-ttu-id="ba147-260">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="ba147-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba147-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="ba147-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="ba147-262">Replicar cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="ba147-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="ba147-263">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba147-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-265">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="ba147-265">List contents</span></span></p>
<p><span data-ttu-id="ba147-266">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="ba147-266">Read all properties</span></span></p>
<p><span data-ttu-id="ba147-267">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="ba147-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ba147-268">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba147-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-270">Contenido de la lista</span><span class="sxs-lookup"><span data-stu-id="ba147-270">List contents</span></span></p>
<p><span data-ttu-id="ba147-271">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="ba147-271">Read all properties</span></span></p>
<p><span data-ttu-id="ba147-272">Permisos de lectura</span><span class="sxs-lookup"><span data-stu-id="ba147-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="ba147-273">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="ba147-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba147-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="ba147-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="ba147-275">Leer RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ba147-276">Leer RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ba147-277">Leer RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="ba147-278">Leer información personal</span><span class="sxs-lookup"><span data-stu-id="ba147-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="ba147-279">Leer información pública</span><span class="sxs-lookup"><span data-stu-id="ba147-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="ba147-280">Leer información general</span><span class="sxs-lookup"><span data-stu-id="ba147-280">Read General-Information</span></span></p>
<p><span data-ttu-id="ba147-281">Leer las restricciones de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="ba147-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="ba147-282">Objetos descendientes de inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="ba147-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba147-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ba147-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="ba147-284">Escribir RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="ba147-285">Escribir RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="ba147-286">Escribir RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="ba147-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="ba147-287">Escribir proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ba147-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="ba147-288">Objetos descendientes de inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="ba147-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

