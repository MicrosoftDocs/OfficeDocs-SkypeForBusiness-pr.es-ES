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
ms.openlocfilehash: c64c11ba999763a44105a68502e53fc4889af305
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="e9044-102">Cambios realizados por Grant-CsOUPermission en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9044-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9044-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="e9044-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="e9044-104">Para delegar la administración de Lync Server 2013, puede Agregar permisos a unidades organizativas especificadas para que los miembros de los grupos de RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="e9044-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="e9044-105">El cmdlet **Grant-CsOuPermission** concede permisos a objetos en la unidad organizativa especificada como se indica en las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="e9044-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="e9044-106">Concesión de permisos para objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="e9044-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="e9044-107">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de usuario en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e9044-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="e9044-108">Permisos concedidos para objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="e9044-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9044-109">Grupo</span><span class="sxs-lookup"><span data-stu-id="e9044-109">Group</span></span></th>
<th><span data-ttu-id="e9044-110">Permiso</span><span class="sxs-lookup"><span data-stu-id="e9044-110">Permission</span></span></th>
<th><span data-ttu-id="e9044-111">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="e9044-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9044-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e9044-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e9044-113">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="e9044-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e9044-114">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9044-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-116">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="e9044-116">List contents</span></span></p>
<p><span data-ttu-id="e9044-117">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="e9044-117">Read all properties</span></span></p>
<p><span data-ttu-id="e9044-118">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="e9044-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e9044-119">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9044-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-121">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="e9044-121">List contents</span></span></p>
<p><span data-ttu-id="e9044-122">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="e9044-122">Read all properties</span></span></p>
<p><span data-ttu-id="e9044-123">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="e9044-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e9044-124">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9044-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-126">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e9044-127">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e9044-128">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="e9044-129">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="e9044-130">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-130">Read General-Information</span></span></p>
<p><span data-ttu-id="e9044-131">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e9044-132">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="e9044-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9044-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e9044-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e9044-134">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e9044-135">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="e9044-136">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e9044-137">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="e9044-138">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e9044-139">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="e9044-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="e9044-140">Concesión de permisos para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="e9044-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="e9044-141">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de equipo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente</span><span class="sxs-lookup"><span data-stu-id="e9044-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="e9044-142">Permisos concedidos para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="e9044-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9044-143">Grupo</span><span class="sxs-lookup"><span data-stu-id="e9044-143">Group</span></span></th>
<th><span data-ttu-id="e9044-144">Permiso</span><span class="sxs-lookup"><span data-stu-id="e9044-144">Permission</span></span></th>
<th><span data-ttu-id="e9044-145">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="e9044-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9044-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e9044-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e9044-147">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="e9044-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e9044-148">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9044-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-150">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="e9044-150">List contents</span></span></p>
<p><span data-ttu-id="e9044-151">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="e9044-151">Read all properties</span></span></p>
<p><span data-ttu-id="e9044-152">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="e9044-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e9044-153">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9044-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-155">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="e9044-155">List contents</span></span></p>
<p><span data-ttu-id="e9044-156">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="e9044-156">Read all properties</span></span></p>
<p><span data-ttu-id="e9044-157">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="e9044-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e9044-158">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9044-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-160">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="e9044-161">Validated-DNS-Host-Name de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="e9044-162">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="e9044-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9044-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e9044-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e9044-164">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="e9044-165">Validated-DNS-Host-Name de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="e9044-166">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="e9044-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="e9044-167">Concesión de permisos para objetos Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="e9044-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="e9044-168">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos Contact u objetos AppContact en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e9044-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="e9044-169">Permisos concedidos para objetos Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="e9044-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9044-170">Grupo</span><span class="sxs-lookup"><span data-stu-id="e9044-170">Group</span></span></th>
<th><span data-ttu-id="e9044-171">Permiso</span><span class="sxs-lookup"><span data-stu-id="e9044-171">Permission</span></span></th>
<th><span data-ttu-id="e9044-172">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="e9044-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9044-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e9044-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e9044-174">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="e9044-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e9044-175">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9044-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-177">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="e9044-177">List contents</span></span></p>
<p><span data-ttu-id="e9044-178">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="e9044-178">Read all properties</span></span></p>
<p><span data-ttu-id="e9044-179">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="e9044-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e9044-180">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9044-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-182">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="e9044-182">List contents</span></span></p>
<p><span data-ttu-id="e9044-183">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="e9044-183">Read all properties</span></span></p>
<p><span data-ttu-id="e9044-184">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="e9044-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e9044-185">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9044-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-187">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e9044-188">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e9044-189">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="e9044-190">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="e9044-191">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-191">Read General-Information</span></span></p>
<p><span data-ttu-id="e9044-192">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="e9044-193">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e9044-194">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="e9044-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9044-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e9044-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e9044-196">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e9044-197">otherIpPhone de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="e9044-198">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-198">Write displayName</span></span></p>
<p><span data-ttu-id="e9044-199">description de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-199">Write description</span></span></p>
<p><span data-ttu-id="e9044-200">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="e9044-201">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="e9044-202">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e9044-203">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="e9044-204">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e9044-205">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="e9044-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="e9044-206">Concesión de permisos para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e9044-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="e9044-207">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de dispositivo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e9044-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="e9044-208">Permisos concedidos para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e9044-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9044-209">Grupo</span><span class="sxs-lookup"><span data-stu-id="e9044-209">Group</span></span></th>
<th><span data-ttu-id="e9044-210">Permiso</span><span class="sxs-lookup"><span data-stu-id="e9044-210">Permission</span></span></th>
<th><span data-ttu-id="e9044-211">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="e9044-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9044-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e9044-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e9044-213">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="e9044-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e9044-214">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9044-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-216">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="e9044-216">List contents</span></span></p>
<p><span data-ttu-id="e9044-217">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="e9044-217">Read all properties</span></span></p>
<p><span data-ttu-id="e9044-218">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="e9044-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e9044-219">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9044-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-221">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="e9044-221">List contents</span></span></p>
<p><span data-ttu-id="e9044-222">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="e9044-222">Read all properties</span></span></p>
<p><span data-ttu-id="e9044-223">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="e9044-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e9044-224">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9044-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-226">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e9044-227">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e9044-228">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="e9044-229">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="e9044-230">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="e9044-231">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-231">Read General-Information</span></span></p>
<p><span data-ttu-id="e9044-232">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e9044-233">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="e9044-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9044-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e9044-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e9044-235">Crear secundario</span><span class="sxs-lookup"><span data-stu-id="e9044-235">Create child</span></span></p>
<p><span data-ttu-id="e9044-236">Eliminar secundario</span><span class="sxs-lookup"><span data-stu-id="e9044-236">Delete child</span></span></p>
<p><span data-ttu-id="e9044-237">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="e9044-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="e9044-238">Contacto</span><span class="sxs-lookup"><span data-stu-id="e9044-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9044-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e9044-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e9044-240">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-240">Write displayName</span></span></p>
<p><span data-ttu-id="e9044-241">description de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-241">Write description</span></span></p>
<p><span data-ttu-id="e9044-242">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="e9044-243">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="e9044-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9044-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e9044-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e9044-245">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e9044-246">otherIpPhone de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="e9044-247">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-247">Write displayName</span></span></p>
<p><span data-ttu-id="e9044-248">description de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-248">Write description</span></span></p>
<p><span data-ttu-id="e9044-249">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="e9044-250">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="e9044-251">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e9044-252">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="e9044-253">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e9044-254">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="e9044-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="e9044-255">Concesión de permisos para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="e9044-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="e9044-256">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e9044-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="e9044-257">Permisos concedidos para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="e9044-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9044-258">Grupo</span><span class="sxs-lookup"><span data-stu-id="e9044-258">Group</span></span></th>
<th><span data-ttu-id="e9044-259">Permiso</span><span class="sxs-lookup"><span data-stu-id="e9044-259">Permission</span></span></th>
<th><span data-ttu-id="e9044-260">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="e9044-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9044-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e9044-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e9044-262">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="e9044-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e9044-263">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9044-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-265">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="e9044-265">List contents</span></span></p>
<p><span data-ttu-id="e9044-266">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="e9044-266">Read all properties</span></span></p>
<p><span data-ttu-id="e9044-267">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="e9044-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e9044-268">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9044-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-270">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="e9044-270">List contents</span></span></p>
<p><span data-ttu-id="e9044-271">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="e9044-271">Read all properties</span></span></p>
<p><span data-ttu-id="e9044-272">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="e9044-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e9044-273">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="e9044-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9044-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e9044-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e9044-275">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e9044-276">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e9044-277">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="e9044-278">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="e9044-279">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="e9044-280">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-280">Read General-Information</span></span></p>
<p><span data-ttu-id="e9044-281">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="e9044-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e9044-282">Objetos inetOrgPerson descendientes</span><span class="sxs-lookup"><span data-stu-id="e9044-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9044-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e9044-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e9044-284">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e9044-285">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e9044-286">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="e9044-287">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="e9044-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e9044-288">Objetos inetOrgPerson descendientes</span><span class="sxs-lookup"><span data-stu-id="e9044-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

