---
title: 'Lync Server 2013: tblEnumValue'
description: 'Lync Server 2013: tblEnumValue.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159f90bb96c367fcb3e11725a582a9993080d3fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571376"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="9f983-103">tblEnumValue en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f983-103">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f983-104">_**Última modificación del tema:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="9f983-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="9f983-105">tblEnumValue es una tabla codificada que contiene los valores de visibilidad y comportamiento de los atributos que se usan en la tabla node.</span><span class="sxs-lookup"><span data-stu-id="9f983-105">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="9f983-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="9f983-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f983-107">Columna</span><span class="sxs-lookup"><span data-stu-id="9f983-107">Column</span></span></th>
<th><span data-ttu-id="9f983-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="9f983-108">Type</span></span></th>
<th><span data-ttu-id="9f983-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f983-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f983-110">valueID</span><span class="sxs-lookup"><span data-stu-id="9f983-110">valueID</span></span></p></td>
<td><p><span data-ttu-id="9f983-111">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="9f983-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="9f983-112">IDENTIFICADOR del valor.</span><span class="sxs-lookup"><span data-stu-id="9f983-112">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f983-113">attributeID</span><span class="sxs-lookup"><span data-stu-id="9f983-113">attributeID</span></span></p></td>
<td><p><span data-ttu-id="9f983-114">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="9f983-114">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="9f983-115">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="9f983-115">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f983-116">attributeValue</span><span class="sxs-lookup"><span data-stu-id="9f983-116">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="9f983-117">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="9f983-117">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="9f983-118">Nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="9f983-118">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9f983-119">Keys</span><span class="sxs-lookup"><span data-stu-id="9f983-119">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f983-120">Columna</span><span class="sxs-lookup"><span data-stu-id="9f983-120">Column</span></span></th>
<th><span data-ttu-id="9f983-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f983-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f983-122">valueID</span><span class="sxs-lookup"><span data-stu-id="9f983-122">valueID</span></span></p></td>
<td><p><span data-ttu-id="9f983-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="9f983-123">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f983-124">attributeID</span><span class="sxs-lookup"><span data-stu-id="9f983-124">attributeID</span></span></p></td>
<td><p><span data-ttu-id="9f983-125">Clave externa con búsqueda en la tabla tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="9f983-125">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="9f983-126">Valores de tabla</span><span class="sxs-lookup"><span data-stu-id="9f983-126">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f983-127">valueID</span><span class="sxs-lookup"><span data-stu-id="9f983-127">valueID</span></span></th>
<th><span data-ttu-id="9f983-128">attributeID</span><span class="sxs-lookup"><span data-stu-id="9f983-128">attributeID</span></span></th>
<th><span data-ttu-id="9f983-129">attributeValue</span><span class="sxs-lookup"><span data-stu-id="9f983-129">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f983-130">segundo</span><span class="sxs-lookup"><span data-stu-id="9f983-130">2</span></span></p></td>
<td><p><span data-ttu-id="9f983-131">1</span><span class="sxs-lookup"><span data-stu-id="9f983-131">1</span></span></p></td>
<td><p><span data-ttu-id="9f983-132">empresa</span><span class="sxs-lookup"><span data-stu-id="9f983-132">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f983-133">3</span><span class="sxs-lookup"><span data-stu-id="9f983-133">3</span></span></p></td>
<td><p><span data-ttu-id="9f983-134">1</span><span class="sxs-lookup"><span data-stu-id="9f983-134">1</span></span></p></td>
<td><p><span data-ttu-id="9f983-135">ámbito</span><span class="sxs-lookup"><span data-stu-id="9f983-135">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f983-136">4 </span><span class="sxs-lookup"><span data-stu-id="9f983-136">4</span></span></p></td>
<td><p><span data-ttu-id="9f983-137">segundo</span><span class="sxs-lookup"><span data-stu-id="9f983-137">2</span></span></p></td>
<td><p><span data-ttu-id="9f983-138">normalmente</span><span class="sxs-lookup"><span data-stu-id="9f983-138">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f983-139">5 </span><span class="sxs-lookup"><span data-stu-id="9f983-139">5</span></span></p></td>
<td><p><span data-ttu-id="9f983-140">segundo</span><span class="sxs-lookup"><span data-stu-id="9f983-140">2</span></span></p></td>
<td><p><span data-ttu-id="9f983-141">Auditorio</span><span class="sxs-lookup"><span data-stu-id="9f983-141">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f983-142">6 </span><span class="sxs-lookup"><span data-stu-id="9f983-142">6</span></span></p></td>
<td><p><span data-ttu-id="9f983-143">1</span><span class="sxs-lookup"><span data-stu-id="9f983-143">1</span></span></p></td>
<td><p><span data-ttu-id="9f983-144">pendiente</span><span class="sxs-lookup"><span data-stu-id="9f983-144">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="9f983-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9f983-145">See Also</span></span>


[<span data-ttu-id="9f983-146">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f983-146">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

