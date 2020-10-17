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
ms.openlocfilehash: 5e4b0c8154429fa68bc05e757130e0b92a47e65c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523767"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="845ad-102">tblPrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="845ad-102">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="845ad-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="845ad-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="845ad-104">La tabla tblPrincipal contiene todas las entidades de seguridad, incluidos usuarios, carpetas y grupos.</span><span class="sxs-lookup"><span data-stu-id="845ad-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="845ad-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="845ad-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="845ad-106">Columna</span><span class="sxs-lookup"><span data-stu-id="845ad-106">Column</span></span></th>
<th><span data-ttu-id="845ad-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="845ad-107">Type</span></span></th>
<th><span data-ttu-id="845ad-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="845ad-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="845ad-109">prinID</span><span class="sxs-lookup"><span data-stu-id="845ad-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="845ad-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="845ad-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="845ad-111">Identificador de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="845ad-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845ad-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="845ad-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="845ad-113">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="845ad-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="845ad-114">GUID de entidad de identidad.</span><span class="sxs-lookup"><span data-stu-id="845ad-114">Principal GUID.</span></span> <span data-ttu-id="845ad-115">Esto se usa ampliamente como una clave principal alternativa porque su significado atraviesa el espacio de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="845ad-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="845ad-116">(El GUID de una entidad de almacenamiento en caché es igual al GUID de objeto de Active Directory correspondiente).</span><span class="sxs-lookup"><span data-stu-id="845ad-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="845ad-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="845ad-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="845ad-118">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="845ad-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="845ad-p102">URI de la entidad de seguridad. El esquema SIP se usa para los usuarios, mientras que ma-grp se usa para prácticamente todo lo demás.</span><span class="sxs-lookup"><span data-stu-id="845ad-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845ad-121">prinName</span><span class="sxs-lookup"><span data-stu-id="845ad-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="845ad-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="845ad-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="845ad-p103">Nombre común. Usado solo por los tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="845ad-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="845ad-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="845ad-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="845ad-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="845ad-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="845ad-p104">Nombre para mostrar. Usado solo por los tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="845ad-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845ad-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="845ad-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="845ad-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="845ad-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="845ad-p105">Nombre de la compañía. Usado solo por los tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="845ad-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="845ad-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="845ad-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="845ad-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="845ad-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="845ad-p106">Correo electrónico. Usado solo por los tipos de usuario.</span><span class="sxs-lookup"><span data-stu-id="845ad-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845ad-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="845ad-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="845ad-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="845ad-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="845ad-p107">Nombre de dominio del objeto de Active Directory del que la entidad de seguridad es una versión en caché. Puede tener un valor NULL en los tipos que no sean objetos de Active Directory (por ejemplo, usuarios de sistema).</span><span class="sxs-lookup"><span data-stu-id="845ad-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="845ad-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="845ad-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="845ad-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="845ad-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="845ad-p108">Nombre principal de usuario (UPN) del usuario. Usado solo por los tipos de usuario normales.</span><span class="sxs-lookup"><span data-stu-id="845ad-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845ad-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="845ad-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="845ad-146">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="845ad-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="845ad-147">0: la entidad de seguridad está activa.</span><span class="sxs-lookup"><span data-stu-id="845ad-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="845ad-148">1: la entidad de seguridad está deshabilitada porque las funciones SIP del usuario están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="845ad-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="845ad-149">2: la entidad de seguridad se elimina porque el objeto de AD asociado se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="845ad-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="845ad-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="845ad-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="845ad-151">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="845ad-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="845ad-152">Tipo de la entidad de seguridad (de la tabla tblPrincipalType).</span><span class="sxs-lookup"><span data-stu-id="845ad-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845ad-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="845ad-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="845ad-154">Int</span><span class="sxs-lookup"><span data-stu-id="845ad-154">Int</span></span></p></td>
<td><p><span data-ttu-id="845ad-155">Asignación del grupo de Lync para la entidad de identidad.</span><span class="sxs-lookup"><span data-stu-id="845ad-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="845ad-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="845ad-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="845ad-157">Int</span><span class="sxs-lookup"><span data-stu-id="845ad-157">Int</span></span></p></td>
<td><p><span data-ttu-id="845ad-158">Valor de la Directiva del servidor de chat persistente para usuario, si la Directiva de tipo de etiqueta está presente.</span><span class="sxs-lookup"><span data-stu-id="845ad-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845ad-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="845ad-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="845ad-160">entero</span><span class="sxs-lookup"><span data-stu-id="845ad-160">int</span></span></p></td>
<td><p><span data-ttu-id="845ad-161">Identificador de la entidad de seguridad del creador.</span><span class="sxs-lookup"><span data-stu-id="845ad-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="845ad-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="845ad-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="845ad-163">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="845ad-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="845ad-164">Marca de tiempo de la hora de creación.</span><span class="sxs-lookup"><span data-stu-id="845ad-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845ad-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="845ad-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="845ad-166">entero</span><span class="sxs-lookup"><span data-stu-id="845ad-166">int</span></span></p></td>
<td><p><span data-ttu-id="845ad-167">Identificador de la entidad de seguridad que actualizó esto por última vez.</span><span class="sxs-lookup"><span data-stu-id="845ad-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="845ad-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="845ad-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="845ad-169">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="845ad-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="845ad-170">Marca de tiempo de la última actualización.</span><span class="sxs-lookup"><span data-stu-id="845ad-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845ad-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="845ad-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="845ad-172">datetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="845ad-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="845ad-173">Fecha y hora de la última actualización de sincronización de Active Directory para la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="845ad-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="845ad-174">Keys</span><span class="sxs-lookup"><span data-stu-id="845ad-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="845ad-175">Columna</span><span class="sxs-lookup"><span data-stu-id="845ad-175">Column</span></span></th>
<th><span data-ttu-id="845ad-176">Descripción</span><span class="sxs-lookup"><span data-stu-id="845ad-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="845ad-177">prinID</span><span class="sxs-lookup"><span data-stu-id="845ad-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="845ad-178">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="845ad-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845ad-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="845ad-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="845ad-180">Clave externa con búsqueda en la tabla tblPrincipalType.ptypeID.</span><span class="sxs-lookup"><span data-stu-id="845ad-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

