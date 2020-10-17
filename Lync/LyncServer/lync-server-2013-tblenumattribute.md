---
title: 'Lync Server 2013: tblEnumAttribute'
description: 'Lync Server 2013: tblEnumAttribute.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca979a68e758ad47b691ac704f24c68c1841938a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571396"
---
# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="cf935-103">tblEnumAttribute en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf935-103">tblEnumAttribute in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf935-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="cf935-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="cf935-105">tblEnumAttribute es una tabla codificada de forma rígida que contiene los atributos Visibility y Behavior que se utilizan en la tabla Node.</span><span class="sxs-lookup"><span data-stu-id="cf935-105">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="cf935-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="cf935-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf935-107">Columna</span><span class="sxs-lookup"><span data-stu-id="cf935-107">Column</span></span></th>
<th><span data-ttu-id="cf935-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="cf935-108">Type</span></span></th>
<th><span data-ttu-id="cf935-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf935-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf935-110">attributeID</span><span class="sxs-lookup"><span data-stu-id="cf935-110">attributeID</span></span></p></td>
<td><p><span data-ttu-id="cf935-111">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="cf935-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="cf935-112">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="cf935-112">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf935-113">attributeName</span><span class="sxs-lookup"><span data-stu-id="cf935-113">attributeName</span></span></p></td>
<td><p><span data-ttu-id="cf935-114">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="cf935-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="cf935-115">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="cf935-115">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="cf935-116">Key </span><span class="sxs-lookup"><span data-stu-id="cf935-116">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf935-117">Columna</span><span class="sxs-lookup"><span data-stu-id="cf935-117">Column</span></span></th>
<th><span data-ttu-id="cf935-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf935-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf935-119">attributeID</span><span class="sxs-lookup"><span data-stu-id="cf935-119">attributeID</span></span></p></td>
<td><p><span data-ttu-id="cf935-120">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="cf935-120">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="cf935-121">Valores de tabla</span><span class="sxs-lookup"><span data-stu-id="cf935-121">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf935-122">attributeID</span><span class="sxs-lookup"><span data-stu-id="cf935-122">attributeID</span></span></th>
<th><span data-ttu-id="cf935-123">attributeName</span><span class="sxs-lookup"><span data-stu-id="cf935-123">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf935-124">1</span><span class="sxs-lookup"><span data-stu-id="cf935-124">1</span></span></p></td>
<td><p><span data-ttu-id="cf935-125">Notoriedad.</span><span class="sxs-lookup"><span data-stu-id="cf935-125">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf935-126">segundo</span><span class="sxs-lookup"><span data-stu-id="cf935-126">2</span></span></p></td>
<td><p><span data-ttu-id="cf935-127">Comportamiento.</span><span class="sxs-lookup"><span data-stu-id="cf935-127">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="cf935-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf935-128">See Also</span></span>


[<span data-ttu-id="cf935-129">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf935-129">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

