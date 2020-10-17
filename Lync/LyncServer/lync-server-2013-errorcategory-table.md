---
title: 'Lync Server 2013: tabla categoría'
description: 'Lync Server 2013: tabla categoría.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8154c73f33b5dad62a338335a960553cfc06ec13
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546436"
---
# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="435f3-103">Tabla categoría en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="435f3-103">ErrorCategory table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="435f3-104">_**Última modificación del tema:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="435f3-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="435f3-105">La tabla categoría contiene el nombre descriptivo para cada clasificación de diagnóstico de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="435f3-105">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="435f3-106">De forma predeterminada, Lync Server 2013 usa las siguientes clasificaciones:</span><span class="sxs-lookup"><span data-stu-id="435f3-106">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="435f3-107">0 -- Éxito</span><span class="sxs-lookup"><span data-stu-id="435f3-107">0 -- Success</span></span>

  - <span data-ttu-id="435f3-108">1--error esperado</span><span class="sxs-lookup"><span data-stu-id="435f3-108">1 -- Expected failure</span></span>

  - <span data-ttu-id="435f3-109">2 – Error inesperado</span><span class="sxs-lookup"><span data-stu-id="435f3-109">2 – Unexpected failure</span></span>

<span data-ttu-id="435f3-110">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="435f3-110">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="435f3-111">Columna</span><span class="sxs-lookup"><span data-stu-id="435f3-111">Column</span></span></th>
<th><span data-ttu-id="435f3-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="435f3-112">Data Type</span></span></th>
<th><span data-ttu-id="435f3-113">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="435f3-113">Key/Index</span></span></th>
<th><span data-ttu-id="435f3-114">Detalles</span><span class="sxs-lookup"><span data-stu-id="435f3-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="435f3-115"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="435f3-115"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="435f3-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="435f3-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="435f3-117">Principal</span><span class="sxs-lookup"><span data-stu-id="435f3-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="435f3-118">Identificador único de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="435f3-118">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="435f3-119"><strong>Nombre</strong></span><span class="sxs-lookup"><span data-stu-id="435f3-119"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="435f3-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="435f3-120">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="435f3-p102">Valor y nombre descriptivo asignados a la clasificación. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="435f3-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="435f3-123">0 -- Éxito</span><span class="sxs-lookup"><span data-stu-id="435f3-123">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="435f3-124">1--error esperado</span><span class="sxs-lookup"><span data-stu-id="435f3-124">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="435f3-125">2 – Error inesperado</span><span class="sxs-lookup"><span data-stu-id="435f3-125">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

