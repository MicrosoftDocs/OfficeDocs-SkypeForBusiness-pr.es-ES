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
ms.openlocfilehash: 6143310797c7372a30665cd380d7fb07340ebaf9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="bdb55-102">Cambios realizados por Grant-CsOUPermission en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdb55-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdb55-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="bdb55-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="bdb55-104">Para delegar la administración de Lync Server 2013, puede Agregar permisos a unidades organizativas especificadas para que los miembros de los grupos de RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="bdb55-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="bdb55-105">El cmdlet **Grant-CsOuPermission** concede permisos a objetos en la unidad organizativa especificada como se indica en las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="bdb55-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="bdb55-106">Concesión de permisos para objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="bdb55-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="bdb55-107">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de usuario en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="bdb55-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="bdb55-108">Permisos concedidos para objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="bdb55-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdb55-109">Group</span><span class="sxs-lookup"><span data-stu-id="bdb55-109">Group</span></span></th>
<th><span data-ttu-id="bdb55-110">Permiso</span><span class="sxs-lookup"><span data-stu-id="bdb55-110">Permission</span></span></th>
<th><span data-ttu-id="bdb55-111">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="bdb55-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="bdb55-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="bdb55-113">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="bdb55-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="bdb55-114">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb55-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-116">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="bdb55-116">List contents</span></span></p>
<p><span data-ttu-id="bdb55-117">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="bdb55-117">Read all properties</span></span></p>
<p><span data-ttu-id="bdb55-118">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="bdb55-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-119">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-121">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="bdb55-121">List contents</span></span></p>
<p><span data-ttu-id="bdb55-122">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="bdb55-122">Read all properties</span></span></p>
<p><span data-ttu-id="bdb55-123">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="bdb55-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-124">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb55-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-126">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-127">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-128">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-129">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="bdb55-130">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-130">Read General-Information</span></span></p>
<p><span data-ttu-id="bdb55-131">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-132">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="bdb55-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="bdb55-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="bdb55-134">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-135">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="bdb55-136">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-137">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-138">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="bdb55-139">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="bdb55-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="bdb55-140">Concesión de permisos para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="bdb55-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="bdb55-141">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de equipo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente</span><span class="sxs-lookup"><span data-stu-id="bdb55-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="bdb55-142">Permisos concedidos para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="bdb55-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdb55-143">Group</span><span class="sxs-lookup"><span data-stu-id="bdb55-143">Group</span></span></th>
<th><span data-ttu-id="bdb55-144">Permiso</span><span class="sxs-lookup"><span data-stu-id="bdb55-144">Permission</span></span></th>
<th><span data-ttu-id="bdb55-145">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="bdb55-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="bdb55-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="bdb55-147">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="bdb55-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="bdb55-148">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb55-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-150">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="bdb55-150">List contents</span></span></p>
<p><span data-ttu-id="bdb55-151">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="bdb55-151">Read all properties</span></span></p>
<p><span data-ttu-id="bdb55-152">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="bdb55-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-153">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-155">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="bdb55-155">List contents</span></span></p>
<p><span data-ttu-id="bdb55-156">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="bdb55-156">Read all properties</span></span></p>
<p><span data-ttu-id="bdb55-157">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="bdb55-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-158">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb55-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-160">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="bdb55-161">Validated-DNS-Host-Name de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="bdb55-162">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="bdb55-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="bdb55-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="bdb55-164">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="bdb55-165">Validated-DNS-Host-Name de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="bdb55-166">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="bdb55-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="bdb55-167">Concesión de permisos para objetos Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="bdb55-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="bdb55-168">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos Contact u objetos AppContact en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="bdb55-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="bdb55-169">Permisos concedidos para objetos Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="bdb55-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdb55-170">Group</span><span class="sxs-lookup"><span data-stu-id="bdb55-170">Group</span></span></th>
<th><span data-ttu-id="bdb55-171">Permiso</span><span class="sxs-lookup"><span data-stu-id="bdb55-171">Permission</span></span></th>
<th><span data-ttu-id="bdb55-172">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="bdb55-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="bdb55-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="bdb55-174">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="bdb55-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="bdb55-175">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb55-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-177">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="bdb55-177">List contents</span></span></p>
<p><span data-ttu-id="bdb55-178">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="bdb55-178">Read all properties</span></span></p>
<p><span data-ttu-id="bdb55-179">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="bdb55-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-180">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-182">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="bdb55-182">List contents</span></span></p>
<p><span data-ttu-id="bdb55-183">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="bdb55-183">Read all properties</span></span></p>
<p><span data-ttu-id="bdb55-184">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="bdb55-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-185">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb55-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-187">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-188">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-189">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-190">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="bdb55-191">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-191">Read General-Information</span></span></p>
<p><span data-ttu-id="bdb55-192">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="bdb55-193">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-194">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="bdb55-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="bdb55-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="bdb55-196">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-197">otherIpPhone de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="bdb55-198">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-198">Write displayName</span></span></p>
<p><span data-ttu-id="bdb55-199">description de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-199">Write description</span></span></p>
<p><span data-ttu-id="bdb55-200">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="bdb55-201">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="bdb55-202">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-203">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-204">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="bdb55-205">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="bdb55-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="bdb55-206">Concesión de permisos para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="bdb55-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="bdb55-207">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de dispositivo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="bdb55-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="bdb55-208">Permisos concedidos para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="bdb55-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdb55-209">Group</span><span class="sxs-lookup"><span data-stu-id="bdb55-209">Group</span></span></th>
<th><span data-ttu-id="bdb55-210">Permiso</span><span class="sxs-lookup"><span data-stu-id="bdb55-210">Permission</span></span></th>
<th><span data-ttu-id="bdb55-211">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="bdb55-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="bdb55-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="bdb55-213">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="bdb55-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="bdb55-214">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb55-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-216">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="bdb55-216">List contents</span></span></p>
<p><span data-ttu-id="bdb55-217">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="bdb55-217">Read all properties</span></span></p>
<p><span data-ttu-id="bdb55-218">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="bdb55-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-219">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-221">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="bdb55-221">List contents</span></span></p>
<p><span data-ttu-id="bdb55-222">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="bdb55-222">Read all properties</span></span></p>
<p><span data-ttu-id="bdb55-223">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="bdb55-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-224">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb55-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-226">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-227">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-228">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-229">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="bdb55-230">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="bdb55-231">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-231">Read General-Information</span></span></p>
<p><span data-ttu-id="bdb55-232">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-233">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="bdb55-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="bdb55-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="bdb55-235">Crear secundario</span><span class="sxs-lookup"><span data-stu-id="bdb55-235">Create child</span></span></p>
<p><span data-ttu-id="bdb55-236">Eliminar secundario</span><span class="sxs-lookup"><span data-stu-id="bdb55-236">Delete child</span></span></p>
<p><span data-ttu-id="bdb55-237">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="bdb55-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="bdb55-238">Contacto</span><span class="sxs-lookup"><span data-stu-id="bdb55-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb55-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="bdb55-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="bdb55-240">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-240">Write displayName</span></span></p>
<p><span data-ttu-id="bdb55-241">description de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-241">Write description</span></span></p>
<p><span data-ttu-id="bdb55-242">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="bdb55-243">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="bdb55-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="bdb55-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="bdb55-245">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-246">otherIpPhone de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="bdb55-247">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-247">Write displayName</span></span></p>
<p><span data-ttu-id="bdb55-248">description de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-248">Write description</span></span></p>
<p><span data-ttu-id="bdb55-249">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="bdb55-250">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="bdb55-251">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-252">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-253">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="bdb55-254">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="bdb55-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="bdb55-255">Concesión de permisos para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="bdb55-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="bdb55-256">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="bdb55-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="bdb55-257">Permisos concedidos para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="bdb55-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdb55-258">Group</span><span class="sxs-lookup"><span data-stu-id="bdb55-258">Group</span></span></th>
<th><span data-ttu-id="bdb55-259">Permiso</span><span class="sxs-lookup"><span data-stu-id="bdb55-259">Permission</span></span></th>
<th><span data-ttu-id="bdb55-260">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="bdb55-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="bdb55-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="bdb55-262">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="bdb55-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="bdb55-263">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb55-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-265">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="bdb55-265">List contents</span></span></p>
<p><span data-ttu-id="bdb55-266">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="bdb55-266">Read all properties</span></span></p>
<p><span data-ttu-id="bdb55-267">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="bdb55-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-268">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-270">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="bdb55-270">List contents</span></span></p>
<p><span data-ttu-id="bdb55-271">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="bdb55-271">Read all properties</span></span></p>
<p><span data-ttu-id="bdb55-272">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="bdb55-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-273">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="bdb55-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb55-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bdb55-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bdb55-275">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-276">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-277">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-278">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="bdb55-279">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="bdb55-280">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-280">Read General-Information</span></span></p>
<p><span data-ttu-id="bdb55-281">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="bdb55-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="bdb55-282">Objetos inetOrgPerson descendientes</span><span class="sxs-lookup"><span data-stu-id="bdb55-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb55-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="bdb55-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="bdb55-284">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-285">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-286">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="bdb55-287">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="bdb55-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="bdb55-288">Objetos inetOrgPerson descendientes</span><span class="sxs-lookup"><span data-stu-id="bdb55-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

