---
title: 'Lync Server 2013: tabla ConferenceJoinTimeThresholds'
description: 'Lync Server 2013: tabla ConferenceJoinTimeThresholds.'
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
ms.openlocfilehash: 5e38c8b99f444e16309882b6a8885d166fdceb9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561676"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="ca824-103">Tabla ConferenceJoinTimeThresholds en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca824-103">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca824-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ca824-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ca824-p101">La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe de resumen de hora de incorporación a la conferencia. El informe de resumen de hora de incorporación a la conferencia resume el tiempo que necesitaron los usuarios para unirse a la conferencia. Estos valores de tiempo se registran como promedio y en una de las categorías siguientes:</span><span class="sxs-lookup"><span data-stu-id="ca824-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="ca824-107">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="ca824-107">Less than 2 seconds.</span></span>

  - <span data-ttu-id="ca824-108">Entre 2 y 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="ca824-108">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="ca824-109">Entre 5 y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="ca824-109">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="ca824-110">Más de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="ca824-110">More than 10 seconds.</span></span>

<span data-ttu-id="ca824-111">La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación 2 segundos, 5 segundos y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="ca824-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="ca824-112">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca824-112">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca824-113">Columna</span><span class="sxs-lookup"><span data-stu-id="ca824-113">Column</span></span></th>
<th><span data-ttu-id="ca824-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ca824-114">Data Type</span></span></th>
<th><span data-ttu-id="ca824-115">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="ca824-115">Key/Index</span></span></th>
<th><span data-ttu-id="ca824-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="ca824-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca824-117"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="ca824-117"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca824-118">entero</span><span class="sxs-lookup"><span data-stu-id="ca824-118">int</span></span></p></td>
<td><p><span data-ttu-id="ca824-119">Principal</span><span class="sxs-lookup"><span data-stu-id="ca824-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="ca824-120">Identificador único de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="ca824-120">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca824-121"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="ca824-121"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="ca824-122">entero</span><span class="sxs-lookup"><span data-stu-id="ca824-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ca824-p102">Límite máximo de la clasificación. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="ca824-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="ca824-125">segundo</span><span class="sxs-lookup"><span data-stu-id="ca824-125">2</span></span></p></li>
<li><p><span data-ttu-id="ca824-126">5 </span><span class="sxs-lookup"><span data-stu-id="ca824-126">5</span></span></p></li>
<li><p><span data-ttu-id="ca824-127">10  </span><span class="sxs-lookup"><span data-stu-id="ca824-127">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

