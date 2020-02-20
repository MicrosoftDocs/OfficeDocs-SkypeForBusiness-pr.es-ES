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
ms.openlocfilehash: 984dd5f161b31c40de914f363c0722657d3194ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="6d202-102">tblEnumValue en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d202-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d202-103">_**Última modificación del tema:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="6d202-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="6d202-104">tblEnumValue es una tabla codificada que contiene los valores de visibilidad y comportamiento de los atributos que se usan en la tabla node.</span><span class="sxs-lookup"><span data-stu-id="6d202-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="6d202-105">Columns</span><span class="sxs-lookup"><span data-stu-id="6d202-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d202-106">Columna</span><span class="sxs-lookup"><span data-stu-id="6d202-106">Column</span></span></th>
<th><span data-ttu-id="6d202-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="6d202-107">Type</span></span></th>
<th><span data-ttu-id="6d202-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d202-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d202-109">valueID</span><span class="sxs-lookup"><span data-stu-id="6d202-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="6d202-110">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="6d202-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="6d202-111">IDENTIFICADOR del valor.</span><span class="sxs-lookup"><span data-stu-id="6d202-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d202-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="6d202-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="6d202-113">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="6d202-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="6d202-114">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="6d202-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d202-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="6d202-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="6d202-116">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="6d202-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="6d202-117">Nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="6d202-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="6d202-118">Keys</span><span class="sxs-lookup"><span data-stu-id="6d202-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d202-119">Columna</span><span class="sxs-lookup"><span data-stu-id="6d202-119">Column</span></span></th>
<th><span data-ttu-id="6d202-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d202-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d202-121">valueID</span><span class="sxs-lookup"><span data-stu-id="6d202-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="6d202-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="6d202-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d202-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="6d202-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="6d202-124">Clave externa con búsqueda en la tabla tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="6d202-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="6d202-125">Valores de tabla</span><span class="sxs-lookup"><span data-stu-id="6d202-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d202-126">valueID</span><span class="sxs-lookup"><span data-stu-id="6d202-126">valueID</span></span></th>
<th><span data-ttu-id="6d202-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="6d202-127">attributeID</span></span></th>
<th><span data-ttu-id="6d202-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="6d202-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d202-129">segundo</span><span class="sxs-lookup"><span data-stu-id="6d202-129">2</span></span></p></td>
<td><p><span data-ttu-id="6d202-130">1</span><span class="sxs-lookup"><span data-stu-id="6d202-130">1</span></span></p></td>
<td><p><span data-ttu-id="6d202-131">empresa</span><span class="sxs-lookup"><span data-stu-id="6d202-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d202-132">3</span><span class="sxs-lookup"><span data-stu-id="6d202-132">3</span></span></p></td>
<td><p><span data-ttu-id="6d202-133">1</span><span class="sxs-lookup"><span data-stu-id="6d202-133">1</span></span></p></td>
<td><p><span data-ttu-id="6d202-134">scope</span><span class="sxs-lookup"><span data-stu-id="6d202-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d202-135">4</span><span class="sxs-lookup"><span data-stu-id="6d202-135">4</span></span></p></td>
<td><p><span data-ttu-id="6d202-136">segundo</span><span class="sxs-lookup"><span data-stu-id="6d202-136">2</span></span></p></td>
<td><p><span data-ttu-id="6d202-137">normalmente</span><span class="sxs-lookup"><span data-stu-id="6d202-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d202-138">2,5</span><span class="sxs-lookup"><span data-stu-id="6d202-138">5</span></span></p></td>
<td><p><span data-ttu-id="6d202-139">segundo</span><span class="sxs-lookup"><span data-stu-id="6d202-139">2</span></span></p></td>
<td><p><span data-ttu-id="6d202-140">Auditorio</span><span class="sxs-lookup"><span data-stu-id="6d202-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d202-141">6 </span><span class="sxs-lookup"><span data-stu-id="6d202-141">6</span></span></p></td>
<td><p><span data-ttu-id="6d202-142">1</span><span class="sxs-lookup"><span data-stu-id="6d202-142">1</span></span></p></td>
<td><p><span data-ttu-id="6d202-143">pendiente</span><span class="sxs-lookup"><span data-stu-id="6d202-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="6d202-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d202-144">See Also</span></span>


[<span data-ttu-id="6d202-145">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d202-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

