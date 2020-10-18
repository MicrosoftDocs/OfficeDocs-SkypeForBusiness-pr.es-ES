---
title: 'Lync Server 2013: tblPrincipalMembers'
description: 'Lync Server 2013: tblPrincipalMembers.'
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
ms.openlocfilehash: 8bbb8be0b83d09b1bd54ea98655558581e6df834
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573186"
---
# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="cce92-103">tblPrincipalMembers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cce92-103">tblPrincipalMembers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cce92-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="cce92-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="cce92-105">tblPrincipalMembers contiene pertenencias de la entidad principal.</span><span class="sxs-lookup"><span data-stu-id="cce92-105">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="cce92-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="cce92-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cce92-107">Columna</span><span class="sxs-lookup"><span data-stu-id="cce92-107">Column</span></span></th>
<th><span data-ttu-id="cce92-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="cce92-108">Type</span></span></th>
<th><span data-ttu-id="cce92-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="cce92-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cce92-110">prinID</span><span class="sxs-lookup"><span data-stu-id="cce92-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="cce92-111">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="cce92-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="cce92-112">Id. de la entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="cce92-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cce92-113">memberADPath</span><span class="sxs-lookup"><span data-stu-id="cce92-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="cce92-114">nvarchar (384), no NULL</span><span class="sxs-lookup"><span data-stu-id="cce92-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="cce92-p101">Nombre distintivo de un miembro. Un miembro no tiene por qué ser una entidad principal (en la tabla tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="cce92-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="cce92-117">Keys</span><span class="sxs-lookup"><span data-stu-id="cce92-117">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cce92-118">Columna</span><span class="sxs-lookup"><span data-stu-id="cce92-118">Column</span></span></th>
<th><span data-ttu-id="cce92-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="cce92-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cce92-120">&lt;prinID, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="cce92-120">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="cce92-121">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="cce92-121">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cce92-122">prinID</span><span class="sxs-lookup"><span data-stu-id="cce92-122">prinID</span></span></p></td>
<td><p><span data-ttu-id="cce92-123">Clave externa con búsqueda en tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="cce92-123">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

