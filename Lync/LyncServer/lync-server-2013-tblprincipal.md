---
title: 'Lync Server 2013: tblPrincipal'
description: 'Lync Server 2013: tblPrincipal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f07b37ac4c8ceed5c044b5c263eeee6370adfdc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547496"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="88397-103">tblPrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88397-103">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88397-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="88397-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="88397-105">La tabla tblPrincipal contiene todas las entidades de seguridad, incluidos usuarios, carpetas y grupos.</span><span class="sxs-lookup"><span data-stu-id="88397-105">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="88397-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="88397-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88397-107">Columna</span><span class="sxs-lookup"><span data-stu-id="88397-107">Column</span></span></th>
<th><span data-ttu-id="88397-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="88397-108">Type</span></span></th>
<th><span data-ttu-id="88397-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="88397-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88397-110">prinID</span><span class="sxs-lookup"><span data-stu-id="88397-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="88397-111">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="88397-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="88397-112">Identificador de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="88397-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88397-113">prinGuid</span><span class="sxs-lookup"><span data-stu-id="88397-113">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="88397-114">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="88397-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="88397-115">GUID de entidad de identidad.</span><span class="sxs-lookup"><span data-stu-id="88397-115">Principal GUID.</span></span> <span data-ttu-id="88397-116">Esto se usa ampliamente como una clave principal alternativa porque su significado atraviesa el espacio de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="88397-116">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="88397-117">(El GUID de una entidad de almacenamiento en caché es igual al GUID de objeto de Active Directory correspondiente).</span><span class="sxs-lookup"><span data-stu-id="88397-117">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88397-118">prinUri</span><span class="sxs-lookup"><span data-stu-id="88397-118">prinUri</span></span></p></td>
<td><p><span data-ttu-id="88397-119">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="88397-119">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="88397-p102">URI de la entidad de seguridad. El esquema SIP se usa para los usuarios, mientras que ma-grp se usa para prácticamente todo lo demás.</span><span class="sxs-lookup"><span data-stu-id="88397-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88397-122">prinName</span><span class="sxs-lookup"><span data-stu-id="88397-122">prinName</span></span></p></td>
<td><p><span data-ttu-id="88397-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="88397-123">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="88397-p103">Nombre común. Usado solo por los tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="88397-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88397-126">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="88397-126">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="88397-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="88397-127">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="88397-p104">Nombre para mostrar. Usado solo por los tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="88397-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88397-130">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="88397-130">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="88397-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="88397-131">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="88397-p105">Nombre de la compañía. Usado solo por los tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="88397-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88397-134">prinEmail</span><span class="sxs-lookup"><span data-stu-id="88397-134">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="88397-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="88397-135">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="88397-p106">Correo electrónico. Usado solo por los tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="88397-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88397-138">prinADPath</span><span class="sxs-lookup"><span data-stu-id="88397-138">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="88397-139">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="88397-139">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="88397-p107">Nombre de dominio del objeto de Active Directory del que la entidad de seguridad es una versión en caché. Puede tener un valor NULL en los tipos que no sean objetos de Active Directory (por ejemplo, usuarios de sistema).</span><span class="sxs-lookup"><span data-stu-id="88397-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88397-142">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="88397-142">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="88397-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="88397-143">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="88397-p108">Nombre principal de usuario (UPN) del usuario. Usado solo por los tipos de usuario normales.</span><span class="sxs-lookup"><span data-stu-id="88397-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88397-146">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="88397-146">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="88397-147">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="88397-147">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="88397-148">0: la entidad de seguridad está activa.</span><span class="sxs-lookup"><span data-stu-id="88397-148">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="88397-149">1: la entidad de seguridad está deshabilitada porque las funciones SIP del usuario están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="88397-149">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="88397-150">2: la entidad de seguridad se elimina porque el objeto de AD asociado se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="88397-150">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88397-151">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="88397-151">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="88397-152">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="88397-152">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="88397-153">Tipo de la entidad de seguridad (de la tabla tblPrincipalType).</span><span class="sxs-lookup"><span data-stu-id="88397-153">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88397-154">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="88397-154">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="88397-155">Int</span><span class="sxs-lookup"><span data-stu-id="88397-155">Int</span></span></p></td>
<td><p><span data-ttu-id="88397-156">Asignación del grupo de Lync para la entidad de identidad.</span><span class="sxs-lookup"><span data-stu-id="88397-156">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88397-157">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="88397-157">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="88397-158">Int</span><span class="sxs-lookup"><span data-stu-id="88397-158">Int</span></span></p></td>
<td><p><span data-ttu-id="88397-159">Valor de la Directiva del servidor de chat persistente para usuario, si la Directiva de tipo de etiqueta está presente.</span><span class="sxs-lookup"><span data-stu-id="88397-159">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88397-160">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="88397-160">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="88397-161">entero</span><span class="sxs-lookup"><span data-stu-id="88397-161">int</span></span></p></td>
<td><p><span data-ttu-id="88397-162">Identificador de la entidad de seguridad del creador.</span><span class="sxs-lookup"><span data-stu-id="88397-162">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88397-163">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="88397-163">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="88397-164">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="88397-164">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="88397-165">Marca de tiempo de la hora de creación.</span><span class="sxs-lookup"><span data-stu-id="88397-165">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88397-166">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="88397-166">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="88397-167">entero</span><span class="sxs-lookup"><span data-stu-id="88397-167">int</span></span></p></td>
<td><p><span data-ttu-id="88397-168">Identificador de la entidad de seguridad que actualizó esto por última vez.</span><span class="sxs-lookup"><span data-stu-id="88397-168">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88397-169">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="88397-169">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="88397-170">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="88397-170">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="88397-171">Marca de tiempo de la última actualización.</span><span class="sxs-lookup"><span data-stu-id="88397-171">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88397-172">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="88397-172">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="88397-173">datetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="88397-173">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="88397-174">Fecha y hora de la última actualización de sincronización de Active Directory para la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="88397-174">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="88397-175">Keys</span><span class="sxs-lookup"><span data-stu-id="88397-175">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88397-176">Columna</span><span class="sxs-lookup"><span data-stu-id="88397-176">Column</span></span></th>
<th><span data-ttu-id="88397-177">Descripción</span><span class="sxs-lookup"><span data-stu-id="88397-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88397-178">prinID</span><span class="sxs-lookup"><span data-stu-id="88397-178">prinID</span></span></p></td>
<td><p><span data-ttu-id="88397-179">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="88397-179">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88397-180">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="88397-180">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="88397-181">Clave externa con búsqueda en la tabla tblPrincipalType.ptypeID.</span><span class="sxs-lookup"><span data-stu-id="88397-181">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

