---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
description: 'Lync Server 2013: tblPrincipalMemberDifference.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce7c770a6fed02dc27d2493816fae58943d391a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573226"
---
# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="e7e84-103">tblPrincipalMemberDifference en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7e84-103">tblPrincipalMemberDifference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7e84-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e7e84-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e7e84-105">tblPrincipalMemberDifference contiene cambios de pertenencia a grupos (miembros agregados y eliminados) que aún no han sido procesados por los pasos de sincronización de servicios de dominio de Active Directory posteriores.</span><span class="sxs-lookup"><span data-stu-id="e7e84-105">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="e7e84-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="e7e84-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7e84-107">Columna</span><span class="sxs-lookup"><span data-stu-id="e7e84-107">Column</span></span></th>
<th><span data-ttu-id="e7e84-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="e7e84-108">Type</span></span></th>
<th><span data-ttu-id="e7e84-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7e84-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7e84-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e7e84-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="e7e84-111">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="e7e84-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="e7e84-112">GUID de entidad de seguridad del grupo modificado.</span><span class="sxs-lookup"><span data-stu-id="e7e84-112">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7e84-113">memberADPath</span><span class="sxs-lookup"><span data-stu-id="e7e84-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="e7e84-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e7e84-114">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="e7e84-115">Nombre distintivo del miembro.</span><span class="sxs-lookup"><span data-stu-id="e7e84-115">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7e84-116">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="e7e84-116">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="e7e84-117">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="e7e84-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e7e84-p101">False si se agregó el miembro. True si se quitó el miembro.</span><span class="sxs-lookup"><span data-stu-id="e7e84-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="e7e84-120">Key </span><span class="sxs-lookup"><span data-stu-id="e7e84-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7e84-121">Columna</span><span class="sxs-lookup"><span data-stu-id="e7e84-121">Column</span></span></th>
<th><span data-ttu-id="e7e84-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7e84-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7e84-123">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="e7e84-123">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="e7e84-124">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="e7e84-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

