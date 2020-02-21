---
title: 'Lync Server 2013: tblPrincipalMembers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48184965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba78067f076169a808129d83c8d4202e183a3a8f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="107d4-102">tblPrincipalMembers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="107d4-102">tblPrincipalMembers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="107d4-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="107d4-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="107d4-104">tblPrincipalMembers contiene pertenencias de la entidad principal.</span><span class="sxs-lookup"><span data-stu-id="107d4-104">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="107d4-105">Columns</span><span class="sxs-lookup"><span data-stu-id="107d4-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="107d4-106">Columna</span><span class="sxs-lookup"><span data-stu-id="107d4-106">Column</span></span></th>
<th><span data-ttu-id="107d4-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="107d4-107">Type</span></span></th>
<th><span data-ttu-id="107d4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="107d4-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="107d4-109">prinID</span><span class="sxs-lookup"><span data-stu-id="107d4-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="107d4-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="107d4-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="107d4-111">Id. de la entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="107d4-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="107d4-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="107d4-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="107d4-113">nvarchar (384), no NULL</span><span class="sxs-lookup"><span data-stu-id="107d4-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="107d4-p101">Nombre distintivo de un miembro. Un miembro no tiene por qué ser una entidad principal (en la tabla tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="107d4-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="107d4-116">Keys</span><span class="sxs-lookup"><span data-stu-id="107d4-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="107d4-117">Columna</span><span class="sxs-lookup"><span data-stu-id="107d4-117">Column</span></span></th>
<th><span data-ttu-id="107d4-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="107d4-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="107d4-119">&lt;prinID, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="107d4-119">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="107d4-120">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="107d4-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="107d4-121">prinID</span><span class="sxs-lookup"><span data-stu-id="107d4-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="107d4-122">Clave externa con búsqueda en tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="107d4-122">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

