---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60fa841f7f88e0da2c428ae68c5007fb79e6c69d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536327"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="cb958-102">tblPrincipalType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb958-102">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb958-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="cb958-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="cb958-104">tblPrincipalType contiene los tipos de entidades de seguridad que se utilizan para clasificar lo que aparece en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="cb958-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="cb958-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="cb958-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb958-106">Columna</span><span class="sxs-lookup"><span data-stu-id="cb958-106">Column</span></span></th>
<th><span data-ttu-id="cb958-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="cb958-107">Type</span></span></th>
<th><span data-ttu-id="cb958-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb958-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb958-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="cb958-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="cb958-110">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="cb958-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="cb958-111">Id. del tipo de entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="cb958-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb958-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="cb958-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="cb958-113">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="cb958-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="cb958-114">Descripción del tipo.</span><span class="sxs-lookup"><span data-stu-id="cb958-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb958-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="cb958-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="cb958-116">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="cb958-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="cb958-117">Verdadero si el tipo corresponde a las entidades de seguridad utilizadas para fines internos.</span><span class="sxs-lookup"><span data-stu-id="cb958-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb958-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="cb958-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="cb958-119">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="cb958-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="cb958-120">Verdadero si el tipo es un tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="cb958-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="cb958-121">Key </span><span class="sxs-lookup"><span data-stu-id="cb958-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb958-122">Columna</span><span class="sxs-lookup"><span data-stu-id="cb958-122">Column</span></span></th>
<th><span data-ttu-id="cb958-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb958-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb958-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="cb958-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="cb958-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="cb958-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="cb958-126">Valores de las entidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="cb958-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb958-127">ID</span><span class="sxs-lookup"><span data-stu-id="cb958-127">ID</span></span></th>
<th><span data-ttu-id="cb958-128">Role</span><span class="sxs-lookup"><span data-stu-id="cb958-128">Role</span></span></th>
<th><span data-ttu-id="cb958-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb958-129">Description</span></span></th>
<th><span data-ttu-id="cb958-130">Usuario</span><span class="sxs-lookup"><span data-stu-id="cb958-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb958-131">1</span><span class="sxs-lookup"><span data-stu-id="cb958-131">1</span></span></p></td>
<td><p><span data-ttu-id="cb958-132">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cb958-132">Any</span></span></p></td>
<td><p><span data-ttu-id="cb958-p101">Entidad de seguridad genérica sin tipo conocido. No se utiliza en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="cb958-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb958-135">segundo</span><span class="sxs-lookup"><span data-stu-id="cb958-135">2</span></span></p></td>
<td><p><span data-ttu-id="cb958-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="cb958-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="cb958-p102">Entidad de seguridad genérica de tipo de usuario. No se utiliza en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="cb958-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="cb958-139">Sí</span><span class="sxs-lookup"><span data-stu-id="cb958-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb958-140">3</span><span class="sxs-lookup"><span data-stu-id="cb958-140">3</span></span></p></td>
<td><p><span data-ttu-id="cb958-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="cb958-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="cb958-p103">Entidad de seguridad genérica con semántica de grupo. No se utiliza en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="cb958-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb958-144">4 </span><span class="sxs-lookup"><span data-stu-id="cb958-144">4</span></span></p></td>
<td><p><span data-ttu-id="cb958-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="cb958-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="cb958-146">Entidad de identidad usada internamente por el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="cb958-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb958-147">5 </span><span class="sxs-lookup"><span data-stu-id="cb958-147">5</span></span></p></td>
<td><p><span data-ttu-id="cb958-148">Usuario</span><span class="sxs-lookup"><span data-stu-id="cb958-148">User</span></span></p></td>
<td><p><span data-ttu-id="cb958-149">Usuario habitual.</span><span class="sxs-lookup"><span data-stu-id="cb958-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="cb958-150">Sí</span><span class="sxs-lookup"><span data-stu-id="cb958-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb958-151">8 </span><span class="sxs-lookup"><span data-stu-id="cb958-151">8</span></span></p></td>
<td><p><span data-ttu-id="cb958-152">DC</span><span class="sxs-lookup"><span data-stu-id="cb958-152">DC</span></span></p></td>
<td><p><span data-ttu-id="cb958-153">Controlador de dominio de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cb958-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb958-154">9 </span><span class="sxs-lookup"><span data-stu-id="cb958-154">9</span></span></p></td>
<td><p><span data-ttu-id="cb958-155">Grupo</span><span class="sxs-lookup"><span data-stu-id="cb958-155">Group</span></span></p></td>
<td><p><span data-ttu-id="cb958-156">Grupo de seguridad de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cb958-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb958-157">10  </span><span class="sxs-lookup"><span data-stu-id="cb958-157">10</span></span></p></td>
<td><p><span data-ttu-id="cb958-158">Folder</span><span class="sxs-lookup"><span data-stu-id="cb958-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="cb958-159">Unidad organizativa o contenedor de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cb958-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="cb958-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb958-160">See Also</span></span>


[<span data-ttu-id="cb958-161">tblPrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb958-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

