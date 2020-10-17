---
title: 'Lync Server 2013: tblPrincipalType'
description: 'Lync Server 2013: tblPrincipalType.'
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
ms.openlocfilehash: ba0f607d4499b54b16d7ecf8a4e7de603e874788
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549866"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="a8baf-103">tblPrincipalType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8baf-103">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8baf-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a8baf-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a8baf-105">tblPrincipalType contiene los tipos de entidades de seguridad que se utilizan para clasificar lo que aparece en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="a8baf-105">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="a8baf-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="a8baf-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8baf-107">Columna</span><span class="sxs-lookup"><span data-stu-id="a8baf-107">Column</span></span></th>
<th><span data-ttu-id="a8baf-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="a8baf-108">Type</span></span></th>
<th><span data-ttu-id="a8baf-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8baf-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8baf-110">ptypeID</span><span class="sxs-lookup"><span data-stu-id="a8baf-110">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="a8baf-111">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="a8baf-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="a8baf-112">Id. del tipo de entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="a8baf-112">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8baf-113">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="a8baf-113">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="a8baf-114">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="a8baf-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="a8baf-115">Descripción del tipo.</span><span class="sxs-lookup"><span data-stu-id="a8baf-115">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8baf-116">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="a8baf-116">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="a8baf-117">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="a8baf-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="a8baf-118">Verdadero si el tipo corresponde a las entidades de seguridad utilizadas para fines internos.</span><span class="sxs-lookup"><span data-stu-id="a8baf-118">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8baf-119">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="a8baf-119">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="a8baf-120">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="a8baf-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="a8baf-121">Verdadero si el tipo es un tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="a8baf-121">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="a8baf-122">Key </span><span class="sxs-lookup"><span data-stu-id="a8baf-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8baf-123">Columna</span><span class="sxs-lookup"><span data-stu-id="a8baf-123">Column</span></span></th>
<th><span data-ttu-id="a8baf-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8baf-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8baf-125">ptypeID</span><span class="sxs-lookup"><span data-stu-id="a8baf-125">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="a8baf-126">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="a8baf-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="a8baf-127">Valores de las entidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="a8baf-127">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8baf-128">ID</span><span class="sxs-lookup"><span data-stu-id="a8baf-128">ID</span></span></th>
<th><span data-ttu-id="a8baf-129">Role</span><span class="sxs-lookup"><span data-stu-id="a8baf-129">Role</span></span></th>
<th><span data-ttu-id="a8baf-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8baf-130">Description</span></span></th>
<th><span data-ttu-id="a8baf-131">Usuario</span><span class="sxs-lookup"><span data-stu-id="a8baf-131">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8baf-132">1</span><span class="sxs-lookup"><span data-stu-id="a8baf-132">1</span></span></p></td>
<td><p><span data-ttu-id="a8baf-133">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="a8baf-133">Any</span></span></p></td>
<td><p><span data-ttu-id="a8baf-p101">Entidad de seguridad genérica sin tipo conocido. No se utiliza en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="a8baf-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8baf-136">segundo</span><span class="sxs-lookup"><span data-stu-id="a8baf-136">2</span></span></p></td>
<td><p><span data-ttu-id="a8baf-137">AnyUser</span><span class="sxs-lookup"><span data-stu-id="a8baf-137">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="a8baf-p102">Entidad de seguridad genérica de tipo de usuario. No se utiliza en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="a8baf-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="a8baf-140">Sí</span><span class="sxs-lookup"><span data-stu-id="a8baf-140">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8baf-141">3</span><span class="sxs-lookup"><span data-stu-id="a8baf-141">3</span></span></p></td>
<td><p><span data-ttu-id="a8baf-142">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="a8baf-142">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="a8baf-p103">Entidad de seguridad genérica con semántica de grupo. No se utiliza en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="a8baf-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8baf-145">4 </span><span class="sxs-lookup"><span data-stu-id="a8baf-145">4</span></span></p></td>
<td><p><span data-ttu-id="a8baf-146">SystemUser</span><span class="sxs-lookup"><span data-stu-id="a8baf-146">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="a8baf-147">Entidad de identidad usada internamente por el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a8baf-147">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8baf-148">5 </span><span class="sxs-lookup"><span data-stu-id="a8baf-148">5</span></span></p></td>
<td><p><span data-ttu-id="a8baf-149">Usuario</span><span class="sxs-lookup"><span data-stu-id="a8baf-149">User</span></span></p></td>
<td><p><span data-ttu-id="a8baf-150">Usuario habitual.</span><span class="sxs-lookup"><span data-stu-id="a8baf-150">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="a8baf-151">Sí</span><span class="sxs-lookup"><span data-stu-id="a8baf-151">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8baf-152">8 </span><span class="sxs-lookup"><span data-stu-id="a8baf-152">8</span></span></p></td>
<td><p><span data-ttu-id="a8baf-153">DC</span><span class="sxs-lookup"><span data-stu-id="a8baf-153">DC</span></span></p></td>
<td><p><span data-ttu-id="a8baf-154">Controlador de dominio de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a8baf-154">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8baf-155">9 </span><span class="sxs-lookup"><span data-stu-id="a8baf-155">9</span></span></p></td>
<td><p><span data-ttu-id="a8baf-156">Grupo</span><span class="sxs-lookup"><span data-stu-id="a8baf-156">Group</span></span></p></td>
<td><p><span data-ttu-id="a8baf-157">Grupo de seguridad de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a8baf-157">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8baf-158">10  </span><span class="sxs-lookup"><span data-stu-id="a8baf-158">10</span></span></p></td>
<td><p><span data-ttu-id="a8baf-159">Folder</span><span class="sxs-lookup"><span data-stu-id="a8baf-159">Folder</span></span></p></td>
<td><p><span data-ttu-id="a8baf-160">Unidad organizativa o contenedor de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a8baf-160">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="a8baf-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8baf-161">See Also</span></span>


[<span data-ttu-id="a8baf-162">tblPrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8baf-162">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

