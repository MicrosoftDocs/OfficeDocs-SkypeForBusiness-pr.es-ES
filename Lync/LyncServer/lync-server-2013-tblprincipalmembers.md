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
ms.openlocfilehash: c81e9ae5b2a712e3d6bb43fc35bd8083334efc1a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="a32fa-102">tblPrincipalMembers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a32fa-102">tblPrincipalMembers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a32fa-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a32fa-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a32fa-104">tblPrincipalMembers contiene pertenencias de la entidad principal.</span><span class="sxs-lookup"><span data-stu-id="a32fa-104">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="a32fa-105">Columns</span><span class="sxs-lookup"><span data-stu-id="a32fa-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a32fa-106">Columna</span><span class="sxs-lookup"><span data-stu-id="a32fa-106">Column</span></span></th>
<th><span data-ttu-id="a32fa-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="a32fa-107">Type</span></span></th>
<th><span data-ttu-id="a32fa-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a32fa-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a32fa-109">prinID</span><span class="sxs-lookup"><span data-stu-id="a32fa-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="a32fa-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="a32fa-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a32fa-111">Id. de la entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="a32fa-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a32fa-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="a32fa-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="a32fa-113">nvarchar (384), no NULL</span><span class="sxs-lookup"><span data-stu-id="a32fa-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="a32fa-p101">Nombre distintivo de un miembro. Un miembro no tiene por qué ser una entidad principal (en la tabla tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="a32fa-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a32fa-116">Keys</span><span class="sxs-lookup"><span data-stu-id="a32fa-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a32fa-117">Columna</span><span class="sxs-lookup"><span data-stu-id="a32fa-117">Column</span></span></th>
<th><span data-ttu-id="a32fa-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="a32fa-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a32fa-119">&lt;prinID, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="a32fa-119">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="a32fa-120">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="a32fa-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a32fa-121">prinID</span><span class="sxs-lookup"><span data-stu-id="a32fa-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="a32fa-122">Clave externa con búsqueda en tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="a32fa-122">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

