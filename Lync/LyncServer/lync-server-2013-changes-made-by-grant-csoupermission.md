---
title: 'Lync Server 2013: cambios realizados por Grant-CsOUPermission'
description: 'Lync Server 2013: cambios realizados por Grant-CsOUPermission.'
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
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543616"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="12b01-103">Cambios realizados por Grant-CsOUPermission en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12b01-103">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12b01-104">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="12b01-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="12b01-105">Para delegar la administración de Lync Server 2013, puede Agregar permisos a unidades organizativas especificadas para que los miembros de los grupos de RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="12b01-105">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="12b01-106">El cmdlet **Grant-CsOuPermission** concede permisos a objetos en la unidad organizativa especificada como se indica en las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="12b01-106">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="12b01-107">Concesión de permisos para objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="12b01-107">Granting Permission for User Objects</span></span>

<span data-ttu-id="12b01-108">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de usuario en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="12b01-108">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="12b01-109">Permisos concedidos para objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="12b01-109">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12b01-110">Grupo</span><span class="sxs-lookup"><span data-stu-id="12b01-110">Group</span></span></th>
<th><span data-ttu-id="12b01-111">Permiso</span><span class="sxs-lookup"><span data-stu-id="12b01-111">Permission</span></span></th>
<th><span data-ttu-id="12b01-112">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="12b01-112">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12b01-113">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="12b01-113">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="12b01-114">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="12b01-114">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="12b01-115">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-115">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12b01-116">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-116">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-117">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="12b01-117">List contents</span></span></p>
<p><span data-ttu-id="12b01-118">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="12b01-118">Read all properties</span></span></p>
<p><span data-ttu-id="12b01-119">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="12b01-119">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12b01-120">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-120">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12b01-121">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-121">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-122">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="12b01-122">List contents</span></span></p>
<p><span data-ttu-id="12b01-123">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="12b01-123">Read all properties</span></span></p>
<p><span data-ttu-id="12b01-124">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="12b01-124">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12b01-125">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-125">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12b01-126">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-126">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-127">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-127">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12b01-128">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-128">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12b01-129">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-129">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="12b01-130">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-130">Read Public-Information</span></span></p>
<p><span data-ttu-id="12b01-131">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-131">Read General-Information</span></span></p>
<p><span data-ttu-id="12b01-132">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-132">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="12b01-133">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="12b01-133">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12b01-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12b01-134">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12b01-135">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-135">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12b01-136">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-136">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="12b01-137">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-137">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12b01-138">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-138">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="12b01-139">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-139">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="12b01-140">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="12b01-140">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="12b01-141">Concesión de permisos para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="12b01-141">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="12b01-142">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de equipo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente</span><span class="sxs-lookup"><span data-stu-id="12b01-142">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="12b01-143">Permisos concedidos para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="12b01-143">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12b01-144">Grupo</span><span class="sxs-lookup"><span data-stu-id="12b01-144">Group</span></span></th>
<th><span data-ttu-id="12b01-145">Permiso</span><span class="sxs-lookup"><span data-stu-id="12b01-145">Permission</span></span></th>
<th><span data-ttu-id="12b01-146">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="12b01-146">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12b01-147">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="12b01-147">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="12b01-148">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="12b01-148">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="12b01-149">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-149">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12b01-150">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-150">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-151">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="12b01-151">List contents</span></span></p>
<p><span data-ttu-id="12b01-152">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="12b01-152">Read all properties</span></span></p>
<p><span data-ttu-id="12b01-153">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="12b01-153">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12b01-154">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-154">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12b01-155">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-155">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-156">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="12b01-156">List contents</span></span></p>
<p><span data-ttu-id="12b01-157">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="12b01-157">Read all properties</span></span></p>
<p><span data-ttu-id="12b01-158">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="12b01-158">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12b01-159">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-159">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12b01-160">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-160">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-161">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-161">Read Public-Information</span></span></p>
<p><span data-ttu-id="12b01-162">Validated-DNS-Host-Name de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-162">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="12b01-163">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="12b01-163">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12b01-164">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12b01-164">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12b01-165">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-165">Read Public-Information</span></span></p>
<p><span data-ttu-id="12b01-166">Validated-DNS-Host-Name de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-166">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="12b01-167">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="12b01-167">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="12b01-168">Concesión de permisos para objetos Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="12b01-168">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="12b01-169">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos Contact u objetos AppContact en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="12b01-169">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="12b01-170">Permisos concedidos para objetos Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="12b01-170">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12b01-171">Grupo</span><span class="sxs-lookup"><span data-stu-id="12b01-171">Group</span></span></th>
<th><span data-ttu-id="12b01-172">Permiso</span><span class="sxs-lookup"><span data-stu-id="12b01-172">Permission</span></span></th>
<th><span data-ttu-id="12b01-173">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="12b01-173">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12b01-174">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="12b01-174">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="12b01-175">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="12b01-175">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="12b01-176">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-176">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12b01-177">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-177">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-178">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="12b01-178">List contents</span></span></p>
<p><span data-ttu-id="12b01-179">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="12b01-179">Read all properties</span></span></p>
<p><span data-ttu-id="12b01-180">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="12b01-180">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12b01-181">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-181">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12b01-182">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-182">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-183">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="12b01-183">List contents</span></span></p>
<p><span data-ttu-id="12b01-184">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="12b01-184">Read all properties</span></span></p>
<p><span data-ttu-id="12b01-185">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="12b01-185">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12b01-186">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-186">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12b01-187">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-187">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-188">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-188">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12b01-189">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-189">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12b01-190">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-190">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="12b01-191">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-191">Read Public-Information</span></span></p>
<p><span data-ttu-id="12b01-192">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-192">Read General-Information</span></span></p>
<p><span data-ttu-id="12b01-193">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-193">Read Personal-Information</span></span></p>
<p><span data-ttu-id="12b01-194">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-194">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="12b01-195">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="12b01-195">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12b01-196">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12b01-196">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12b01-197">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-197">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12b01-198">otherIpPhone de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-198">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="12b01-199">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-199">Write displayName</span></span></p>
<p><span data-ttu-id="12b01-200">description de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-200">Write description</span></span></p>
<p><span data-ttu-id="12b01-201">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-201">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="12b01-202">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-202">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="12b01-203">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-203">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12b01-204">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-204">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="12b01-205">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-205">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="12b01-206">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="12b01-206">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="12b01-207">Concesión de permisos para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="12b01-207">Granting Permission for Device Objects</span></span>

<span data-ttu-id="12b01-208">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de dispositivo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="12b01-208">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="12b01-209">Permisos concedidos para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="12b01-209">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12b01-210">Grupo</span><span class="sxs-lookup"><span data-stu-id="12b01-210">Group</span></span></th>
<th><span data-ttu-id="12b01-211">Permiso</span><span class="sxs-lookup"><span data-stu-id="12b01-211">Permission</span></span></th>
<th><span data-ttu-id="12b01-212">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="12b01-212">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12b01-213">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="12b01-213">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="12b01-214">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="12b01-214">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="12b01-215">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-215">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12b01-216">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-216">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-217">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="12b01-217">List contents</span></span></p>
<p><span data-ttu-id="12b01-218">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="12b01-218">Read all properties</span></span></p>
<p><span data-ttu-id="12b01-219">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="12b01-219">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12b01-220">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-220">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12b01-221">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-221">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-222">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="12b01-222">List contents</span></span></p>
<p><span data-ttu-id="12b01-223">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="12b01-223">Read all properties</span></span></p>
<p><span data-ttu-id="12b01-224">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="12b01-224">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12b01-225">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-225">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12b01-226">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-226">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-227">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-227">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12b01-228">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-228">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12b01-229">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-229">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="12b01-230">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-230">Read Public-Information</span></span></p>
<p><span data-ttu-id="12b01-231">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-231">Read Personal-Information</span></span></p>
<p><span data-ttu-id="12b01-232">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-232">Read General-Information</span></span></p>
<p><span data-ttu-id="12b01-233">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-233">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="12b01-234">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="12b01-234">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12b01-235">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12b01-235">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12b01-236">Crear secundario</span><span class="sxs-lookup"><span data-stu-id="12b01-236">Create child</span></span></p>
<p><span data-ttu-id="12b01-237">Eliminar secundario</span><span class="sxs-lookup"><span data-stu-id="12b01-237">Delete child</span></span></p>
<p><span data-ttu-id="12b01-238">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="12b01-238">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="12b01-239">Contacto</span><span class="sxs-lookup"><span data-stu-id="12b01-239">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12b01-240">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12b01-240">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12b01-241">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-241">Write displayName</span></span></p>
<p><span data-ttu-id="12b01-242">description de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-242">Write description</span></span></p>
<p><span data-ttu-id="12b01-243">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-243">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="12b01-244">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="12b01-244">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12b01-245">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12b01-245">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12b01-246">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-246">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12b01-247">otherIpPhone de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-247">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="12b01-248">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-248">Write displayName</span></span></p>
<p><span data-ttu-id="12b01-249">description de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-249">Write description</span></span></p>
<p><span data-ttu-id="12b01-250">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-250">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="12b01-251">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-251">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="12b01-252">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-252">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12b01-253">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-253">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="12b01-254">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-254">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="12b01-255">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="12b01-255">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="12b01-256">Concesión de permisos para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="12b01-256">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="12b01-257">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="12b01-257">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="12b01-258">Permisos concedidos para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="12b01-258">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12b01-259">Grupo</span><span class="sxs-lookup"><span data-stu-id="12b01-259">Group</span></span></th>
<th><span data-ttu-id="12b01-260">Permiso</span><span class="sxs-lookup"><span data-stu-id="12b01-260">Permission</span></span></th>
<th><span data-ttu-id="12b01-261">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="12b01-261">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12b01-262">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="12b01-262">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="12b01-263">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="12b01-263">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="12b01-264">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-264">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12b01-265">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-265">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-266">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="12b01-266">List contents</span></span></p>
<p><span data-ttu-id="12b01-267">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="12b01-267">Read all properties</span></span></p>
<p><span data-ttu-id="12b01-268">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="12b01-268">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12b01-269">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-269">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12b01-270">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-270">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-271">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="12b01-271">List contents</span></span></p>
<p><span data-ttu-id="12b01-272">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="12b01-272">Read all properties</span></span></p>
<p><span data-ttu-id="12b01-273">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="12b01-273">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12b01-274">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="12b01-274">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12b01-275">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12b01-275">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12b01-276">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-276">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12b01-277">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-277">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12b01-278">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-278">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="12b01-279">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-279">Read Personal-Information</span></span></p>
<p><span data-ttu-id="12b01-280">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-280">Read Public-Information</span></span></p>
<p><span data-ttu-id="12b01-281">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-281">Read General-Information</span></span></p>
<p><span data-ttu-id="12b01-282">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="12b01-282">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="12b01-283">Objetos inetOrgPerson descendientes</span><span class="sxs-lookup"><span data-stu-id="12b01-283">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12b01-284">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12b01-284">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12b01-285">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-285">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12b01-286">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-286">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12b01-287">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-287">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="12b01-288">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="12b01-288">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="12b01-289">Objetos inetOrgPerson descendientes</span><span class="sxs-lookup"><span data-stu-id="12b01-289">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

