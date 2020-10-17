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
ms.openlocfilehash: 0ff916c0b4e284f9c6ce4d5dbaf9c2e196ed4bc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529437"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="feda2-102">Cambios realizados por Grant-CsOUPermission en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="feda2-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="feda2-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="feda2-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="feda2-104">Para delegar la administración de Lync Server 2013, puede Agregar permisos a unidades organizativas especificadas para que los miembros de los grupos de RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="feda2-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="feda2-105">El cmdlet **Grant-CsOuPermission** concede permisos a objetos en la unidad organizativa especificada como se indica en las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="feda2-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="feda2-106">Concesión de permisos para objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="feda2-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="feda2-107">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de usuario en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="feda2-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="feda2-108">Permisos concedidos para objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="feda2-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feda2-109">Grupo</span><span class="sxs-lookup"><span data-stu-id="feda2-109">Group</span></span></th>
<th><span data-ttu-id="feda2-110">Permiso</span><span class="sxs-lookup"><span data-stu-id="feda2-110">Permission</span></span></th>
<th><span data-ttu-id="feda2-111">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="feda2-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feda2-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="feda2-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="feda2-113">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="feda2-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="feda2-114">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feda2-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-116">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="feda2-116">List contents</span></span></p>
<p><span data-ttu-id="feda2-117">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="feda2-117">Read all properties</span></span></p>
<p><span data-ttu-id="feda2-118">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="feda2-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="feda2-119">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feda2-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-121">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="feda2-121">List contents</span></span></p>
<p><span data-ttu-id="feda2-122">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="feda2-122">Read all properties</span></span></p>
<p><span data-ttu-id="feda2-123">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="feda2-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="feda2-124">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feda2-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-126">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="feda2-127">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="feda2-128">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="feda2-129">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="feda2-130">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-130">Read General-Information</span></span></p>
<p><span data-ttu-id="feda2-131">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="feda2-132">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="feda2-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feda2-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="feda2-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="feda2-134">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="feda2-135">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="feda2-136">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="feda2-137">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="feda2-138">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="feda2-139">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="feda2-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="feda2-140">Concesión de permisos para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="feda2-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="feda2-141">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de equipo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente</span><span class="sxs-lookup"><span data-stu-id="feda2-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="feda2-142">Permisos concedidos para objetos de equipo</span><span class="sxs-lookup"><span data-stu-id="feda2-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feda2-143">Grupo</span><span class="sxs-lookup"><span data-stu-id="feda2-143">Group</span></span></th>
<th><span data-ttu-id="feda2-144">Permiso</span><span class="sxs-lookup"><span data-stu-id="feda2-144">Permission</span></span></th>
<th><span data-ttu-id="feda2-145">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="feda2-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feda2-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="feda2-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="feda2-147">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="feda2-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="feda2-148">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feda2-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-150">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="feda2-150">List contents</span></span></p>
<p><span data-ttu-id="feda2-151">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="feda2-151">Read all properties</span></span></p>
<p><span data-ttu-id="feda2-152">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="feda2-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="feda2-153">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feda2-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-155">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="feda2-155">List contents</span></span></p>
<p><span data-ttu-id="feda2-156">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="feda2-156">Read all properties</span></span></p>
<p><span data-ttu-id="feda2-157">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="feda2-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="feda2-158">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feda2-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-160">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="feda2-161">Validated-DNS-Host-Name de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="feda2-162">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="feda2-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feda2-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="feda2-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="feda2-164">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="feda2-165">Validated-DNS-Host-Name de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="feda2-166">Objetos de equipo descendientes</span><span class="sxs-lookup"><span data-stu-id="feda2-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="feda2-167">Concesión de permisos para objetos Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="feda2-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="feda2-168">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos Contact u objetos AppContact en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="feda2-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="feda2-169">Permisos concedidos para objetos Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="feda2-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feda2-170">Grupo</span><span class="sxs-lookup"><span data-stu-id="feda2-170">Group</span></span></th>
<th><span data-ttu-id="feda2-171">Permiso</span><span class="sxs-lookup"><span data-stu-id="feda2-171">Permission</span></span></th>
<th><span data-ttu-id="feda2-172">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="feda2-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feda2-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="feda2-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="feda2-174">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="feda2-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="feda2-175">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feda2-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-177">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="feda2-177">List contents</span></span></p>
<p><span data-ttu-id="feda2-178">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="feda2-178">Read all properties</span></span></p>
<p><span data-ttu-id="feda2-179">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="feda2-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="feda2-180">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feda2-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-182">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="feda2-182">List contents</span></span></p>
<p><span data-ttu-id="feda2-183">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="feda2-183">Read all properties</span></span></p>
<p><span data-ttu-id="feda2-184">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="feda2-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="feda2-185">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feda2-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-187">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="feda2-188">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="feda2-189">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="feda2-190">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="feda2-191">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-191">Read General-Information</span></span></p>
<p><span data-ttu-id="feda2-192">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="feda2-193">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="feda2-194">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="feda2-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feda2-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="feda2-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="feda2-196">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="feda2-197">otherIpPhone de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="feda2-198">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-198">Write displayName</span></span></p>
<p><span data-ttu-id="feda2-199">description de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-199">Write description</span></span></p>
<p><span data-ttu-id="feda2-200">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="feda2-201">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="feda2-202">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="feda2-203">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="feda2-204">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="feda2-205">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="feda2-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="feda2-206">Concesión de permisos para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="feda2-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="feda2-207">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de dispositivo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="feda2-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="feda2-208">Permisos concedidos para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="feda2-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feda2-209">Grupo</span><span class="sxs-lookup"><span data-stu-id="feda2-209">Group</span></span></th>
<th><span data-ttu-id="feda2-210">Permiso</span><span class="sxs-lookup"><span data-stu-id="feda2-210">Permission</span></span></th>
<th><span data-ttu-id="feda2-211">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="feda2-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feda2-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="feda2-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="feda2-213">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="feda2-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="feda2-214">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feda2-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-216">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="feda2-216">List contents</span></span></p>
<p><span data-ttu-id="feda2-217">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="feda2-217">Read all properties</span></span></p>
<p><span data-ttu-id="feda2-218">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="feda2-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="feda2-219">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feda2-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-221">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="feda2-221">List contents</span></span></p>
<p><span data-ttu-id="feda2-222">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="feda2-222">Read all properties</span></span></p>
<p><span data-ttu-id="feda2-223">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="feda2-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="feda2-224">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feda2-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-226">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="feda2-227">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="feda2-228">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="feda2-229">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="feda2-230">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="feda2-231">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-231">Read General-Information</span></span></p>
<p><span data-ttu-id="feda2-232">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="feda2-233">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="feda2-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feda2-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="feda2-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="feda2-235">Crear secundario</span><span class="sxs-lookup"><span data-stu-id="feda2-235">Create child</span></span></p>
<p><span data-ttu-id="feda2-236">Eliminar secundario</span><span class="sxs-lookup"><span data-stu-id="feda2-236">Delete child</span></span></p>
<p><span data-ttu-id="feda2-237">Eliminar árbol</span><span class="sxs-lookup"><span data-stu-id="feda2-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="feda2-238">Contacto</span><span class="sxs-lookup"><span data-stu-id="feda2-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feda2-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="feda2-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="feda2-240">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-240">Write displayName</span></span></p>
<p><span data-ttu-id="feda2-241">description de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-241">Write description</span></span></p>
<p><span data-ttu-id="feda2-242">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="feda2-243">Objetos de usuario descendientes</span><span class="sxs-lookup"><span data-stu-id="feda2-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feda2-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="feda2-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="feda2-245">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="feda2-246">otherIpPhone de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="feda2-247">displayName de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-247">Write displayName</span></span></p>
<p><span data-ttu-id="feda2-248">description de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-248">Write description</span></span></p>
<p><span data-ttu-id="feda2-249">telephoneNumber de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="feda2-250">msExchUCVoiceMailSettings de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="feda2-251">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="feda2-252">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="feda2-253">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="feda2-254">Objetos de contacto descendientes</span><span class="sxs-lookup"><span data-stu-id="feda2-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="feda2-255">Concesión de permisos para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="feda2-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="feda2-256">Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="feda2-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="feda2-257">Permisos concedidos para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="feda2-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="feda2-258">Grupo</span><span class="sxs-lookup"><span data-stu-id="feda2-258">Group</span></span></th>
<th><span data-ttu-id="feda2-259">Permiso</span><span class="sxs-lookup"><span data-stu-id="feda2-259">Permission</span></span></th>
<th><span data-ttu-id="feda2-260">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="feda2-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feda2-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="feda2-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="feda2-262">Replicar los cambios de directorio</span><span class="sxs-lookup"><span data-stu-id="feda2-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="feda2-263">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feda2-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-265">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="feda2-265">List contents</span></span></p>
<p><span data-ttu-id="feda2-266">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="feda2-266">Read all properties</span></span></p>
<p><span data-ttu-id="feda2-267">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="feda2-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="feda2-268">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feda2-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-270">Contenidos de la lista</span><span class="sxs-lookup"><span data-stu-id="feda2-270">List contents</span></span></p>
<p><span data-ttu-id="feda2-271">Leer todas las propiedades</span><span class="sxs-lookup"><span data-stu-id="feda2-271">Read all properties</span></span></p>
<p><span data-ttu-id="feda2-272">Leer permisos</span><span class="sxs-lookup"><span data-stu-id="feda2-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="feda2-273">Solo este objeto</span><span class="sxs-lookup"><span data-stu-id="feda2-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="feda2-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="feda2-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="feda2-275">RTCUserSearchPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="feda2-276">RTCUserProvisioningPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="feda2-277">RTCPropertySet de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="feda2-278">Personal-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="feda2-279">Public-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="feda2-280">General-Information de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-280">Read General-Information</span></span></p>
<p><span data-ttu-id="feda2-281">User-Account-Restrictions de lectura</span><span class="sxs-lookup"><span data-stu-id="feda2-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="feda2-282">Objetos inetOrgPerson descendientes</span><span class="sxs-lookup"><span data-stu-id="feda2-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="feda2-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="feda2-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="feda2-284">RTCUserSearchPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="feda2-285">RTCUserProvisioningPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="feda2-286">RTCPropertySet de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="feda2-287">proxyAddresses de escritura</span><span class="sxs-lookup"><span data-stu-id="feda2-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="feda2-288">Objetos inetOrgPerson descendientes</span><span class="sxs-lookup"><span data-stu-id="feda2-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

