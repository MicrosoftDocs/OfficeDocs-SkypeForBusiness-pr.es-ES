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
ms.openlocfilehash: dfad0cf4b8b863cd19d4d4113241477de1a50aaf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="29205-102">Cambios realizados por Grant-CsOUPermission en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29205-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29205-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="29205-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="29205-104">Para delegar la administración de Lync Server 2013, puede Agregar permisos a unidades organizativas especificadas para que los miembros de los grupos de RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="29205-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="29205-105">El cmdlet **Grant-CsOuPermission** concede permisos a objetos en la unidad organizativa especificada como se indica en las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="29205-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="29205-106">Concesión de permisos para objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="29205-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="29205-107">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de usuario en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="29205-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="29205-108">Permisos concedidos para objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="29205-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29205-109">Grupo</span><span class="sxs-lookup"><span data-stu-id="29205-109">Group</span></span></th>
<th><span data-ttu-id="29205-110">Permiso</span><span class="sxs-lookup"><span data-stu-id="29205-110">Permission</span></span></th>
<th><span data-ttu-id="29205-111">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="29205-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29205-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="29205-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="29205-113">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="29205-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="29205-114">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29205-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-116">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="29205-116">List contents</span></span></p>
<p><span data-ttu-id="29205-117">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="29205-117">Read all properties</span></span></p>
<p><span data-ttu-id="29205-118">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="29205-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="29205-119">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29205-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-121">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="29205-121">List contents</span></span></p>
<p><span data-ttu-id="29205-122">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="29205-122">Read all properties</span></span></p>
<p><span data-ttu-id="29205-123">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="29205-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="29205-124">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29205-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-126">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="29205-127">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="29205-128">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="29205-129">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="29205-130">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-130">Read General-Information</span></span></p>
<p><span data-ttu-id="29205-131">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="29205-132">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="29205-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29205-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="29205-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="29205-134">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="29205-135">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="29205-136">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="29205-137">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="29205-138">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="29205-139">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="29205-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="29205-140">Concesión de permisos para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="29205-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="29205-141">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de equipo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente</span><span class="sxs-lookup"><span data-stu-id="29205-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="29205-142">Permisos concedidos para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="29205-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29205-143">Grupo</span><span class="sxs-lookup"><span data-stu-id="29205-143">Group</span></span></th>
<th><span data-ttu-id="29205-144">Permiso</span><span class="sxs-lookup"><span data-stu-id="29205-144">Permission</span></span></th>
<th><span data-ttu-id="29205-145">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="29205-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29205-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="29205-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="29205-147">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="29205-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="29205-148">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29205-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-150">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="29205-150">List contents</span></span></p>
<p><span data-ttu-id="29205-151">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="29205-151">Read all properties</span></span></p>
<p><span data-ttu-id="29205-152">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="29205-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="29205-153">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29205-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-155">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="29205-155">List contents</span></span></p>
<p><span data-ttu-id="29205-156">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="29205-156">Read all properties</span></span></p>
<p><span data-ttu-id="29205-157">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="29205-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="29205-158">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29205-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-160">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="29205-161">Validated-DNS-Host-Name de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="29205-162">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="29205-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29205-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="29205-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="29205-164">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="29205-165">Validated-DNS-Host-Name de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="29205-166">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="29205-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="29205-167">Concesión de permisos para objetos Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="29205-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="29205-168">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos Contact u objetos AppContact en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="29205-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="29205-169">Permisos concedidos para objetos Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="29205-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29205-170">Grupo</span><span class="sxs-lookup"><span data-stu-id="29205-170">Group</span></span></th>
<th><span data-ttu-id="29205-171">Permiso</span><span class="sxs-lookup"><span data-stu-id="29205-171">Permission</span></span></th>
<th><span data-ttu-id="29205-172">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="29205-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29205-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="29205-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="29205-174">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="29205-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="29205-175">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29205-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-177">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="29205-177">List contents</span></span></p>
<p><span data-ttu-id="29205-178">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="29205-178">Read all properties</span></span></p>
<p><span data-ttu-id="29205-179">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="29205-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="29205-180">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29205-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-182">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="29205-182">List contents</span></span></p>
<p><span data-ttu-id="29205-183">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="29205-183">Read all properties</span></span></p>
<p><span data-ttu-id="29205-184">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="29205-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="29205-185">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29205-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-187">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="29205-188">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="29205-189">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="29205-190">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="29205-191">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-191">Read General-Information</span></span></p>
<p><span data-ttu-id="29205-192">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="29205-193">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="29205-194">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="29205-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29205-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="29205-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="29205-196">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="29205-197">otherIpPhone de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="29205-198">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-198">Write displayName</span></span></p>
<p><span data-ttu-id="29205-199">description de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-199">Write description</span></span></p>
<p><span data-ttu-id="29205-200">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="29205-201">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="29205-202">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="29205-203">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="29205-204">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="29205-205">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="29205-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="29205-206">Concesión de permisos para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="29205-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="29205-207">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de dispositivo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="29205-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="29205-208">Permisos concedidos para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="29205-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29205-209">Grupo</span><span class="sxs-lookup"><span data-stu-id="29205-209">Group</span></span></th>
<th><span data-ttu-id="29205-210">Permiso</span><span class="sxs-lookup"><span data-stu-id="29205-210">Permission</span></span></th>
<th><span data-ttu-id="29205-211">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="29205-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29205-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="29205-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="29205-213">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="29205-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="29205-214">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29205-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-216">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="29205-216">List contents</span></span></p>
<p><span data-ttu-id="29205-217">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="29205-217">Read all properties</span></span></p>
<p><span data-ttu-id="29205-218">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="29205-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="29205-219">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29205-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-221">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="29205-221">List contents</span></span></p>
<p><span data-ttu-id="29205-222">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="29205-222">Read all properties</span></span></p>
<p><span data-ttu-id="29205-223">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="29205-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="29205-224">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29205-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-226">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="29205-227">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="29205-228">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="29205-229">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="29205-230">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="29205-231">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-231">Read General-Information</span></span></p>
<p><span data-ttu-id="29205-232">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="29205-233">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="29205-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29205-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="29205-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="29205-235">Crear secundario</span><span class="sxs-lookup"><span data-stu-id="29205-235">Create child</span></span></p>
<p><span data-ttu-id="29205-236">Eliminar secundario</span><span class="sxs-lookup"><span data-stu-id="29205-236">Delete child</span></span></p>
<p><span data-ttu-id="29205-237">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="29205-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="29205-238">Contacto</span><span class="sxs-lookup"><span data-stu-id="29205-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29205-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="29205-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="29205-240">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-240">Write displayName</span></span></p>
<p><span data-ttu-id="29205-241">description de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-241">Write description</span></span></p>
<p><span data-ttu-id="29205-242">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="29205-243">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="29205-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29205-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="29205-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="29205-245">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="29205-246">otherIpPhone de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="29205-247">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-247">Write displayName</span></span></p>
<p><span data-ttu-id="29205-248">description de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-248">Write description</span></span></p>
<p><span data-ttu-id="29205-249">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="29205-250">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="29205-251">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="29205-252">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="29205-253">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="29205-254">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="29205-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="29205-255">Concesión de permisos para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="29205-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="29205-256">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="29205-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="29205-257">Permisos concedidos para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="29205-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29205-258">Grupo</span><span class="sxs-lookup"><span data-stu-id="29205-258">Group</span></span></th>
<th><span data-ttu-id="29205-259">Permiso</span><span class="sxs-lookup"><span data-stu-id="29205-259">Permission</span></span></th>
<th><span data-ttu-id="29205-260">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="29205-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29205-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="29205-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="29205-262">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="29205-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="29205-263">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29205-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-265">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="29205-265">List contents</span></span></p>
<p><span data-ttu-id="29205-266">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="29205-266">Read all properties</span></span></p>
<p><span data-ttu-id="29205-267">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="29205-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="29205-268">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29205-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-270">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="29205-270">List contents</span></span></p>
<p><span data-ttu-id="29205-271">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="29205-271">Read all properties</span></span></p>
<p><span data-ttu-id="29205-272">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="29205-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="29205-273">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="29205-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29205-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="29205-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="29205-275">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="29205-276">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="29205-277">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="29205-278">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="29205-279">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="29205-280">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-280">Read General-Information</span></span></p>
<p><span data-ttu-id="29205-281">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="29205-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="29205-282">Objetos inetOrgPerson descendientes</span><span class="sxs-lookup"><span data-stu-id="29205-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29205-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="29205-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="29205-284">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="29205-285">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="29205-286">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="29205-287">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="29205-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="29205-288">Objetos inetOrgPerson descendientes</span><span class="sxs-lookup"><span data-stu-id="29205-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

