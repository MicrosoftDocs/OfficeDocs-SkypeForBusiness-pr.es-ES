---
title: 'Lync Server 2013: tabla ConferenceJoinTimeThresholds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d8dcf3d8b5f74abe6e145d7ac25e43411ca085c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502317"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="cbb0c-102">Tabla ConferenceJoinTimeThresholds en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbb0c-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbb0c-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cbb0c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cbb0c-p101">La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe de resumen de hora de incorporación a la conferencia. El informe de resumen de hora de incorporación a la conferencia resume el tiempo que necesitaron los usuarios para unirse a la conferencia. Estos valores de tiempo se registran como promedio y en una de las categorías siguientes:</span><span class="sxs-lookup"><span data-stu-id="cbb0c-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="cbb0c-106">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="cbb0c-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="cbb0c-107">Entre 2 y 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="cbb0c-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="cbb0c-108">Entre 5 y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="cbb0c-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="cbb0c-109">Más de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="cbb0c-109">More than 10 seconds.</span></span>

<span data-ttu-id="cbb0c-110">La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación 2 segundos, 5 segundos y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="cbb0c-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="cbb0c-111">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbb0c-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbb0c-112">Columna</span><span class="sxs-lookup"><span data-stu-id="cbb0c-112">Column</span></span></th>
<th><span data-ttu-id="cbb0c-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cbb0c-113">Data Type</span></span></th>
<th><span data-ttu-id="cbb0c-114">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="cbb0c-114">Key/Index</span></span></th>
<th><span data-ttu-id="cbb0c-115">Detalles</span><span class="sxs-lookup"><span data-stu-id="cbb0c-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbb0c-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="cbb0c-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbb0c-117">entero</span><span class="sxs-lookup"><span data-stu-id="cbb0c-117">int</span></span></p></td>
<td><p><span data-ttu-id="cbb0c-118">Principal</span><span class="sxs-lookup"><span data-stu-id="cbb0c-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="cbb0c-119">Identificador único de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="cbb0c-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbb0c-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="cbb0c-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="cbb0c-121">entero</span><span class="sxs-lookup"><span data-stu-id="cbb0c-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbb0c-p102">Límite máximo de la clasificación. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="cbb0c-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="cbb0c-124">segundo</span><span class="sxs-lookup"><span data-stu-id="cbb0c-124">2</span></span></p></li>
<li><p><span data-ttu-id="cbb0c-125">5 </span><span class="sxs-lookup"><span data-stu-id="cbb0c-125">5</span></span></p></li>
<li><p><span data-ttu-id="cbb0c-126">10  </span><span class="sxs-lookup"><span data-stu-id="cbb0c-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

