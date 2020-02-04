---
title: 'Lync Server 2013: tblPrincipal'
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
ms.openlocfilehash: 25de9273fb6e153bb154bf0062edd96cb67bbac2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="04881-102">tblPrincipal enn Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04881-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04881-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="04881-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="04881-104">tblPrincipal contiene todos los principales, incluidos los usuarios, las carpetas y los grupos.</span><span class="sxs-lookup"><span data-stu-id="04881-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="04881-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="04881-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04881-106">Columna</span><span class="sxs-lookup"><span data-stu-id="04881-106">Column</span></span></th>
<th><span data-ttu-id="04881-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="04881-107">Type</span></span></th>
<th><span data-ttu-id="04881-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="04881-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04881-109">prinID</span><span class="sxs-lookup"><span data-stu-id="04881-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="04881-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="04881-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="04881-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="04881-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04881-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="04881-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="04881-113">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="04881-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="04881-114">GUID principal.</span><span class="sxs-lookup"><span data-stu-id="04881-114">Principal GUID.</span></span> <span data-ttu-id="04881-115">Esto se usa ampliamente como una clave principal alternativa porque su significado pasa a ser el espacio de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="04881-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="04881-116">(El GUID de un principal en caché es igual al GUID de objeto de Active Directory correspondiente).</span><span class="sxs-lookup"><span data-stu-id="04881-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04881-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="04881-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="04881-118">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="04881-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="04881-119">URI principal.</span><span class="sxs-lookup"><span data-stu-id="04881-119">Principal URI.</span></span> <span data-ttu-id="04881-120">El esquema SIP se usa para los usuarios y el mA-GRP se usa para casi todos los demás.</span><span class="sxs-lookup"><span data-stu-id="04881-120">The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04881-121">prinName</span><span class="sxs-lookup"><span data-stu-id="04881-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="04881-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="04881-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="04881-123">Nombre común.</span><span class="sxs-lookup"><span data-stu-id="04881-123">Common name.</span></span> <span data-ttu-id="04881-124">Solo se usan los tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="04881-124">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04881-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="04881-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="04881-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="04881-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="04881-127">Nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="04881-127">Display name.</span></span> <span data-ttu-id="04881-128">Solo se usan los tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="04881-128">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04881-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="04881-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="04881-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="04881-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="04881-131">Nombre de la empresa.</span><span class="sxs-lookup"><span data-stu-id="04881-131">Company name.</span></span> <span data-ttu-id="04881-132">Solo se usan los tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="04881-132">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04881-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="04881-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="04881-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="04881-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="04881-135">Correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="04881-135">Email.</span></span> <span data-ttu-id="04881-136">Solo se usan los tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="04881-136">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04881-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="04881-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="04881-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="04881-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="04881-139">Nombre de dominio del objeto de Active Directory del que el principal es una versión almacenada en caché.</span><span class="sxs-lookup"><span data-stu-id="04881-139">Domain name of the Active Directory object that the principal is a cached version of.</span></span> <span data-ttu-id="04881-140">Puede ser null para los tipos que no son objetos de Active Directory (como usuarios del sistema).</span><span class="sxs-lookup"><span data-stu-id="04881-140">Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04881-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="04881-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="04881-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="04881-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="04881-143">Nombre principal de usuario (UPN) del usuario.</span><span class="sxs-lookup"><span data-stu-id="04881-143">User’s user principal name (UPN).</span></span> <span data-ttu-id="04881-144">Solo lo usan los tipos de usuario normales.</span><span class="sxs-lookup"><span data-stu-id="04881-144">Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04881-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="04881-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="04881-146">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="04881-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="04881-147">0: la principal está activa.</span><span class="sxs-lookup"><span data-stu-id="04881-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="04881-148">1: la entidad de la identidad está deshabilitada porque las funciones SIP del usuario están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="04881-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="04881-149">2: se eliminó el capital porque el objeto de AD asociado se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="04881-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04881-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="04881-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="04881-151">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="04881-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="04881-152">Tipo principal (de la tabla tblPrincipalType).</span><span class="sxs-lookup"><span data-stu-id="04881-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04881-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="04881-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="04881-154">ENT</span><span class="sxs-lookup"><span data-stu-id="04881-154">Int</span></span></p></td>
<td><p><span data-ttu-id="04881-155">Asignación de grupo de Lync para la entidad de identidad.</span><span class="sxs-lookup"><span data-stu-id="04881-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04881-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="04881-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="04881-157">ENT</span><span class="sxs-lookup"><span data-stu-id="04881-157">Int</span></span></p></td>
<td><p><span data-ttu-id="04881-158">Valor de la Directiva del servidor de chat persistente para usuario, si la Directiva de tipo de etiqueta está presente.</span><span class="sxs-lookup"><span data-stu-id="04881-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04881-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="04881-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="04881-160">int</span><span class="sxs-lookup"><span data-stu-id="04881-160">int</span></span></p></td>
<td><p><span data-ttu-id="04881-161">IDENTIFICADOR principal del creador.</span><span class="sxs-lookup"><span data-stu-id="04881-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04881-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="04881-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="04881-163">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="04881-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="04881-164">Marca de tiempo de la hora de creación.</span><span class="sxs-lookup"><span data-stu-id="04881-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04881-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="04881-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="04881-166">int</span><span class="sxs-lookup"><span data-stu-id="04881-166">int</span></span></p></td>
<td><p><span data-ttu-id="04881-167">IDENTIFICADOR de la entidad de identidad que la actualizó por última vez.</span><span class="sxs-lookup"><span data-stu-id="04881-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04881-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="04881-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="04881-169">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="04881-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="04881-170">Marca de tiempo de la última actualización.</span><span class="sxs-lookup"><span data-stu-id="04881-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04881-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="04881-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="04881-172">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="04881-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="04881-173">Fecha y hora de la última actualización de sincronización de Active Directory para la entidad de identidad.</span><span class="sxs-lookup"><span data-stu-id="04881-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="04881-174">Sus</span><span class="sxs-lookup"><span data-stu-id="04881-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04881-175">Columna</span><span class="sxs-lookup"><span data-stu-id="04881-175">Column</span></span></th>
<th><span data-ttu-id="04881-176">Descripción</span><span class="sxs-lookup"><span data-stu-id="04881-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04881-177">prinID</span><span class="sxs-lookup"><span data-stu-id="04881-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="04881-178">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="04881-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04881-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="04881-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="04881-180">Clave externa con la búsqueda en la tabla tblPrincipalType. ptypeID.</span><span class="sxs-lookup"><span data-stu-id="04881-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

