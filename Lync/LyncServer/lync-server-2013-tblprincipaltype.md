---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="4256a-102">tblPrincipalType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4256a-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4256a-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4256a-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4256a-104">tblPrincipalType contiene tipos de principales para categorizar lo que hay en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="4256a-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="4256a-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="4256a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4256a-106">Columna</span><span class="sxs-lookup"><span data-stu-id="4256a-106">Column</span></span></th>
<th><span data-ttu-id="4256a-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="4256a-107">Type</span></span></th>
<th><span data-ttu-id="4256a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4256a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4256a-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="4256a-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="4256a-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="4256a-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="4256a-111">IDENTIFICADOR de tipo de entidad de identidad.</span><span class="sxs-lookup"><span data-stu-id="4256a-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4256a-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="4256a-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="4256a-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="4256a-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="4256a-114">Descripción del tipo.</span><span class="sxs-lookup"><span data-stu-id="4256a-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4256a-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="4256a-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="4256a-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="4256a-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4256a-117">True si el tipo corresponde a las entidades de identidad que se usan para fines internos.</span><span class="sxs-lookup"><span data-stu-id="4256a-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4256a-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="4256a-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="4256a-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="4256a-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4256a-120">True si el tipo es un tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="4256a-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="4256a-121">Clave</span><span class="sxs-lookup"><span data-stu-id="4256a-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4256a-122">Columna</span><span class="sxs-lookup"><span data-stu-id="4256a-122">Column</span></span></th>
<th><span data-ttu-id="4256a-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="4256a-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4256a-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="4256a-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="4256a-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="4256a-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="4256a-126">Valores principales</span><span class="sxs-lookup"><span data-stu-id="4256a-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4256a-127">ID</span><span class="sxs-lookup"><span data-stu-id="4256a-127">ID</span></span></th>
<th><span data-ttu-id="4256a-128">Rol</span><span class="sxs-lookup"><span data-stu-id="4256a-128">Role</span></span></th>
<th><span data-ttu-id="4256a-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="4256a-129">Description</span></span></th>
<th><span data-ttu-id="4256a-130">Usuario</span><span class="sxs-lookup"><span data-stu-id="4256a-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4256a-131">1</span><span class="sxs-lookup"><span data-stu-id="4256a-131">1</span></span></p></td>
<td><p><span data-ttu-id="4256a-132">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="4256a-132">Any</span></span></p></td>
<td><p><span data-ttu-id="4256a-133">Entidad de identidad genérica con un tipo no conocido.</span><span class="sxs-lookup"><span data-stu-id="4256a-133">Generic principal with no known type.</span></span> <span data-ttu-id="4256a-134">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="4256a-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4256a-135">2</span><span class="sxs-lookup"><span data-stu-id="4256a-135">2</span></span></p></td>
<td><p><span data-ttu-id="4256a-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="4256a-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="4256a-137">Identidad genérica del tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="4256a-137">Generic principal of user type.</span></span> <span data-ttu-id="4256a-138">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="4256a-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="4256a-139">Sí</span><span class="sxs-lookup"><span data-stu-id="4256a-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4256a-140">3</span><span class="sxs-lookup"><span data-stu-id="4256a-140">3</span></span></p></td>
<td><p><span data-ttu-id="4256a-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="4256a-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="4256a-142">Principal genérico con semántica de grupo.</span><span class="sxs-lookup"><span data-stu-id="4256a-142">Generic principal with group semantic.</span></span> <span data-ttu-id="4256a-143">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="4256a-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4256a-144">4</span><span class="sxs-lookup"><span data-stu-id="4256a-144">4</span></span></p></td>
<td><p><span data-ttu-id="4256a-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="4256a-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="4256a-146">Principal utilizado internamente por el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4256a-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4256a-147">5</span><span class="sxs-lookup"><span data-stu-id="4256a-147">5</span></span></p></td>
<td><p><span data-ttu-id="4256a-148">Usuario</span><span class="sxs-lookup"><span data-stu-id="4256a-148">User</span></span></p></td>
<td><p><span data-ttu-id="4256a-149">Usuario normal.</span><span class="sxs-lookup"><span data-stu-id="4256a-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="4256a-150">Sí</span><span class="sxs-lookup"><span data-stu-id="4256a-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4256a-151">4,8</span><span class="sxs-lookup"><span data-stu-id="4256a-151">8</span></span></p></td>
<td><p><span data-ttu-id="4256a-152">Clona</span><span class="sxs-lookup"><span data-stu-id="4256a-152">DC</span></span></p></td>
<td><p><span data-ttu-id="4256a-153">Controlador de dominio de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4256a-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4256a-154">99,999</span><span class="sxs-lookup"><span data-stu-id="4256a-154">9</span></span></p></td>
<td><p><span data-ttu-id="4256a-155">Mesa</span><span class="sxs-lookup"><span data-stu-id="4256a-155">Group</span></span></p></td>
<td><p><span data-ttu-id="4256a-156">Grupo de seguridad de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4256a-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4256a-157">base10</span><span class="sxs-lookup"><span data-stu-id="4256a-157">10</span></span></p></td>
<td><p><span data-ttu-id="4256a-158">Carpetas</span><span class="sxs-lookup"><span data-stu-id="4256a-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="4256a-159">Contenedor de Active Directory o unidad de organización.</span><span class="sxs-lookup"><span data-stu-id="4256a-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="4256a-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="4256a-160">See Also</span></span>


[<span data-ttu-id="4256a-161">tblPrincipal enn Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4256a-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

