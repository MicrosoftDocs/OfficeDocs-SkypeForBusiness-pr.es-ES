---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
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
ms.openlocfilehash: baaf336013ec09b17b8e688889fdf27aa29ef644
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="95e0b-102">tblPrincipalMemberDifference en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95e0b-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95e0b-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="95e0b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="95e0b-104">tblPrincipalMemberDifference contiene cambios de pertenencia a grupos (miembros agregados y eliminados) que aún no han procesado los pasos de sincronización de servicios de dominio de Active Directory más recientes.</span><span class="sxs-lookup"><span data-stu-id="95e0b-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="95e0b-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="95e0b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95e0b-106">Columna</span><span class="sxs-lookup"><span data-stu-id="95e0b-106">Column</span></span></th>
<th><span data-ttu-id="95e0b-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="95e0b-107">Type</span></span></th>
<th><span data-ttu-id="95e0b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="95e0b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95e0b-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="95e0b-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="95e0b-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="95e0b-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="95e0b-111">GUID principal del grupo que cambió.</span><span class="sxs-lookup"><span data-stu-id="95e0b-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e0b-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="95e0b-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="95e0b-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95e0b-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="95e0b-114">Nombre distintivo del miembro.</span><span class="sxs-lookup"><span data-stu-id="95e0b-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e0b-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="95e0b-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="95e0b-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="95e0b-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="95e0b-117">False si se agregó el miembro.</span><span class="sxs-lookup"><span data-stu-id="95e0b-117">False if the member was added.</span></span> <span data-ttu-id="95e0b-118">True si se ha quitado el miembro.</span><span class="sxs-lookup"><span data-stu-id="95e0b-118">True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="95e0b-119">Clave</span><span class="sxs-lookup"><span data-stu-id="95e0b-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95e0b-120">Columna</span><span class="sxs-lookup"><span data-stu-id="95e0b-120">Column</span></span></th>
<th><span data-ttu-id="95e0b-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="95e0b-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95e0b-122">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="95e0b-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="95e0b-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="95e0b-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

