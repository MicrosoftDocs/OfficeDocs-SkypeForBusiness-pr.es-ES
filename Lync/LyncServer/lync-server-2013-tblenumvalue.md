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
ms.openlocfilehash: 79d1b68cd10858812a1310ebbd1f2caae913da75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509327"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="88828-102">tblEnumValue en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88828-102">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88828-103">_**Última modificación del tema:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="88828-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="88828-104">tblEnumValue es una tabla codificada que contiene los valores de visibilidad y comportamiento de los atributos que se usan en la tabla node.</span><span class="sxs-lookup"><span data-stu-id="88828-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="88828-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="88828-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88828-106">Columna</span><span class="sxs-lookup"><span data-stu-id="88828-106">Column</span></span></th>
<th><span data-ttu-id="88828-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="88828-107">Type</span></span></th>
<th><span data-ttu-id="88828-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="88828-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88828-109">valueID</span><span class="sxs-lookup"><span data-stu-id="88828-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="88828-110">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="88828-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="88828-111">IDENTIFICADOR del valor.</span><span class="sxs-lookup"><span data-stu-id="88828-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88828-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="88828-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="88828-113">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="88828-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="88828-114">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="88828-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88828-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="88828-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="88828-116">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="88828-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="88828-117">Nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="88828-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="88828-118">Keys</span><span class="sxs-lookup"><span data-stu-id="88828-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88828-119">Columna</span><span class="sxs-lookup"><span data-stu-id="88828-119">Column</span></span></th>
<th><span data-ttu-id="88828-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="88828-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88828-121">valueID</span><span class="sxs-lookup"><span data-stu-id="88828-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="88828-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="88828-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88828-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="88828-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="88828-124">Clave externa con búsqueda en la tabla tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="88828-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="88828-125">Valores de tabla</span><span class="sxs-lookup"><span data-stu-id="88828-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88828-126">valueID</span><span class="sxs-lookup"><span data-stu-id="88828-126">valueID</span></span></th>
<th><span data-ttu-id="88828-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="88828-127">attributeID</span></span></th>
<th><span data-ttu-id="88828-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="88828-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88828-129">segundo</span><span class="sxs-lookup"><span data-stu-id="88828-129">2</span></span></p></td>
<td><p><span data-ttu-id="88828-130">1</span><span class="sxs-lookup"><span data-stu-id="88828-130">1</span></span></p></td>
<td><p><span data-ttu-id="88828-131">empresa</span><span class="sxs-lookup"><span data-stu-id="88828-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88828-132">3</span><span class="sxs-lookup"><span data-stu-id="88828-132">3</span></span></p></td>
<td><p><span data-ttu-id="88828-133">1</span><span class="sxs-lookup"><span data-stu-id="88828-133">1</span></span></p></td>
<td><p><span data-ttu-id="88828-134">ámbito</span><span class="sxs-lookup"><span data-stu-id="88828-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88828-135">4 </span><span class="sxs-lookup"><span data-stu-id="88828-135">4</span></span></p></td>
<td><p><span data-ttu-id="88828-136">segundo</span><span class="sxs-lookup"><span data-stu-id="88828-136">2</span></span></p></td>
<td><p><span data-ttu-id="88828-137">normalmente</span><span class="sxs-lookup"><span data-stu-id="88828-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88828-138">5 </span><span class="sxs-lookup"><span data-stu-id="88828-138">5</span></span></p></td>
<td><p><span data-ttu-id="88828-139">segundo</span><span class="sxs-lookup"><span data-stu-id="88828-139">2</span></span></p></td>
<td><p><span data-ttu-id="88828-140">Auditorio</span><span class="sxs-lookup"><span data-stu-id="88828-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88828-141">6 </span><span class="sxs-lookup"><span data-stu-id="88828-141">6</span></span></p></td>
<td><p><span data-ttu-id="88828-142">1</span><span class="sxs-lookup"><span data-stu-id="88828-142">1</span></span></p></td>
<td><p><span data-ttu-id="88828-143">pendiente</span><span class="sxs-lookup"><span data-stu-id="88828-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="88828-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88828-144">See Also</span></span>


[<span data-ttu-id="88828-145">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88828-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

