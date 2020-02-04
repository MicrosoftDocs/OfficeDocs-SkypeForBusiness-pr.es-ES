---
title: 'Lync Server 2013: tblEnumValue'
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
ms.openlocfilehash: 2c09c5e911dcd63f50d8b15343075c5b3e05e631
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="7470e-102">tblEnumValue en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7470e-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7470e-103">_**Última modificación del tema:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="7470e-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="7470e-104">tblEnumValue es una tabla codificada que contiene los valores de visibilidad y comportamiento de los atributos que se usan en la tabla de nodos.</span><span class="sxs-lookup"><span data-stu-id="7470e-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="7470e-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="7470e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7470e-106">Columna</span><span class="sxs-lookup"><span data-stu-id="7470e-106">Column</span></span></th>
<th><span data-ttu-id="7470e-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="7470e-107">Type</span></span></th>
<th><span data-ttu-id="7470e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7470e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7470e-109">valueID</span><span class="sxs-lookup"><span data-stu-id="7470e-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="7470e-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="7470e-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="7470e-111">IDENTIFICADOR del valor.</span><span class="sxs-lookup"><span data-stu-id="7470e-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7470e-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="7470e-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="7470e-113">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="7470e-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="7470e-114">IDENTIFICADOR del atributo.</span><span class="sxs-lookup"><span data-stu-id="7470e-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7470e-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="7470e-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="7470e-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="7470e-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="7470e-117">Nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="7470e-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7470e-118">Sus</span><span class="sxs-lookup"><span data-stu-id="7470e-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7470e-119">Columna</span><span class="sxs-lookup"><span data-stu-id="7470e-119">Column</span></span></th>
<th><span data-ttu-id="7470e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="7470e-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7470e-121">valueID</span><span class="sxs-lookup"><span data-stu-id="7470e-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="7470e-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="7470e-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7470e-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="7470e-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="7470e-124">Clave externa con la búsqueda en la tabla tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="7470e-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="7470e-125">Valores de tabla</span><span class="sxs-lookup"><span data-stu-id="7470e-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7470e-126">valueID</span><span class="sxs-lookup"><span data-stu-id="7470e-126">valueID</span></span></th>
<th><span data-ttu-id="7470e-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="7470e-127">attributeID</span></span></th>
<th><span data-ttu-id="7470e-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="7470e-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7470e-129">1</span><span class="sxs-lookup"><span data-stu-id="7470e-129">2</span></span></p></td>
<td><p><span data-ttu-id="7470e-130">1</span><span class="sxs-lookup"><span data-stu-id="7470e-130">1</span></span></p></td>
<td><p><span data-ttu-id="7470e-131">private</span><span class="sxs-lookup"><span data-stu-id="7470e-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7470e-132">3</span><span class="sxs-lookup"><span data-stu-id="7470e-132">3</span></span></p></td>
<td><p><span data-ttu-id="7470e-133">1</span><span class="sxs-lookup"><span data-stu-id="7470e-133">1</span></span></p></td>
<td><p><span data-ttu-id="7470e-134">ID</span><span class="sxs-lookup"><span data-stu-id="7470e-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7470e-135">4</span><span class="sxs-lookup"><span data-stu-id="7470e-135">4</span></span></p></td>
<td><p><span data-ttu-id="7470e-136">1</span><span class="sxs-lookup"><span data-stu-id="7470e-136">2</span></span></p></td>
<td><p><span data-ttu-id="7470e-137">normal</span><span class="sxs-lookup"><span data-stu-id="7470e-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7470e-138">5</span><span class="sxs-lookup"><span data-stu-id="7470e-138">5</span></span></p></td>
<td><p><span data-ttu-id="7470e-139">1</span><span class="sxs-lookup"><span data-stu-id="7470e-139">2</span></span></p></td>
<td><p><span data-ttu-id="7470e-140">Audi</span><span class="sxs-lookup"><span data-stu-id="7470e-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7470e-141">6</span><span class="sxs-lookup"><span data-stu-id="7470e-141">6</span></span></p></td>
<td><p><span data-ttu-id="7470e-142">1</span><span class="sxs-lookup"><span data-stu-id="7470e-142">1</span></span></p></td>
<td><p><span data-ttu-id="7470e-143">volver</span><span class="sxs-lookup"><span data-stu-id="7470e-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="7470e-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="7470e-144">See Also</span></span>


[<span data-ttu-id="7470e-145">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7470e-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

