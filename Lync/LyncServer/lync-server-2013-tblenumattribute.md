---
title: 'Lync Server 2013: tblEnumAttribute'
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
ms.openlocfilehash: fbb970d217ff24396fa72c76ba4b88c3d38be6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="0605e-102">tblEnumAttribute en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0605e-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0605e-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0605e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0605e-104">tblEnumAttribute es una tabla codificada de forma rígida que contiene los atributos Visibility y Behavior que se utilizan en la tabla Node.</span><span class="sxs-lookup"><span data-stu-id="0605e-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="0605e-105">Columns</span><span class="sxs-lookup"><span data-stu-id="0605e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0605e-106">Columna</span><span class="sxs-lookup"><span data-stu-id="0605e-106">Column</span></span></th>
<th><span data-ttu-id="0605e-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="0605e-107">Type</span></span></th>
<th><span data-ttu-id="0605e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0605e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0605e-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="0605e-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="0605e-110">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="0605e-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="0605e-111">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="0605e-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0605e-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="0605e-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="0605e-113">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="0605e-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="0605e-114">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="0605e-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="0605e-115">Key </span><span class="sxs-lookup"><span data-stu-id="0605e-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0605e-116">Columna</span><span class="sxs-lookup"><span data-stu-id="0605e-116">Column</span></span></th>
<th><span data-ttu-id="0605e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="0605e-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0605e-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="0605e-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="0605e-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="0605e-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="0605e-120">Valores de tabla</span><span class="sxs-lookup"><span data-stu-id="0605e-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0605e-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="0605e-121">attributeID</span></span></th>
<th><span data-ttu-id="0605e-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="0605e-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0605e-123">1</span><span class="sxs-lookup"><span data-stu-id="0605e-123">1</span></span></p></td>
<td><p><span data-ttu-id="0605e-124">Notoriedad.</span><span class="sxs-lookup"><span data-stu-id="0605e-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0605e-125">segundo</span><span class="sxs-lookup"><span data-stu-id="0605e-125">2</span></span></p></td>
<td><p><span data-ttu-id="0605e-126">Comportamiento.</span><span class="sxs-lookup"><span data-stu-id="0605e-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="0605e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="0605e-127">See Also</span></span>


[<span data-ttu-id="0605e-128">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0605e-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

