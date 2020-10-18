---
title: 'Lync Server 2013: tblADUpdates'
description: 'Lync Server 2013: tblADUpdates.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ab4418a10eac283d0f39d09b1c1fe15a32b2e68
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573686"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="ee985-103">tblADUpdates en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee985-103">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee985-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ee985-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ee985-105">tblADUpdates contiene cambios en los servicios de dominio de Active Directory que aún no se procesaron en los pasos de sincronización de Active Directory más recientes.</span><span class="sxs-lookup"><span data-stu-id="ee985-105">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="ee985-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="ee985-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee985-107">Columna</span><span class="sxs-lookup"><span data-stu-id="ee985-107">Column</span></span></th>
<th><span data-ttu-id="ee985-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee985-108">Type</span></span></th>
<th><span data-ttu-id="ee985-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee985-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee985-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="ee985-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="ee985-111">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="ee985-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="ee985-112">GUID principal del objeto que ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="ee985-112">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee985-113">prinADPath</span><span class="sxs-lookup"><span data-stu-id="ee985-113">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="ee985-114">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="ee985-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="ee985-115">Nombre distintivo del objeto.</span><span class="sxs-lookup"><span data-stu-id="ee985-115">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee985-116">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="ee985-116">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="ee985-117">bit, not null</span><span class="sxs-lookup"><span data-stu-id="ee985-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ee985-118">True si ha cambiado al menos un atributo del objeto.</span><span class="sxs-lookup"><span data-stu-id="ee985-118">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee985-119">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="ee985-119">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="ee985-120">bit, not null</span><span class="sxs-lookup"><span data-stu-id="ee985-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ee985-121">True si ha cambiado la pertenencia.</span><span class="sxs-lookup"><span data-stu-id="ee985-121">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee985-122">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="ee985-122">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="ee985-123">bit, not null</span><span class="sxs-lookup"><span data-stu-id="ee985-123">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ee985-124">No se usa.</span><span class="sxs-lookup"><span data-stu-id="ee985-124">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee985-125">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="ee985-125">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="ee985-126">bit, not null</span><span class="sxs-lookup"><span data-stu-id="ee985-126">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ee985-127">True si se ha eliminado el objeto.</span><span class="sxs-lookup"><span data-stu-id="ee985-127">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee985-128">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="ee985-128">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="ee985-129">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="ee985-129">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="ee985-130">Marca de tiempo correspondiente al momento en que se insertó la fila.</span><span class="sxs-lookup"><span data-stu-id="ee985-130">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

