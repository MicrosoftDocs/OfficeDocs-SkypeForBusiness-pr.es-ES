---
title: 'Lync Server 2013: tabla ConferenceJoinTimeThresholds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66793cc3bd545d343198d00f7fb477c1f9b88fac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="38a68-102">Tabla ConferenceJoinTimeThresholds en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38a68-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38a68-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="38a68-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="38a68-104">La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe Resumen de tiempo de combinación de conferencia.</span><span class="sxs-lookup"><span data-stu-id="38a68-104">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="38a68-105">En el informe Resumen de tiempo de combinación de conferencia se resume la cantidad de tiempo necesario para que los usuarios se unan correctamente a una conferencia; Estos valores de hora se notifican como promedio y en una de las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="38a68-105">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="38a68-106">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="38a68-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="38a68-107">Entre 2 y 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="38a68-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="38a68-108">Entre 5 segundos y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="38a68-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="38a68-109">Más de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="38a68-109">More than 10 seconds.</span></span>

<span data-ttu-id="38a68-110">La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación de 2 segundos, 5 segundos y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="38a68-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="38a68-111">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38a68-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38a68-112">Columna</span><span class="sxs-lookup"><span data-stu-id="38a68-112">Column</span></span></th>
<th><span data-ttu-id="38a68-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="38a68-113">Data Type</span></span></th>
<th><span data-ttu-id="38a68-114">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="38a68-114">Key/Index</span></span></th>
<th><span data-ttu-id="38a68-115">Detalles</span><span class="sxs-lookup"><span data-stu-id="38a68-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38a68-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="38a68-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="38a68-117">int</span><span class="sxs-lookup"><span data-stu-id="38a68-117">int</span></span></p></td>
<td><p><span data-ttu-id="38a68-118">Primary</span><span class="sxs-lookup"><span data-stu-id="38a68-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="38a68-119">Identificador único de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="38a68-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38a68-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="38a68-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="38a68-121">int</span><span class="sxs-lookup"><span data-stu-id="38a68-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38a68-122">Límite superior de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="38a68-122">Upper limit for the classification.</span></span> <span data-ttu-id="38a68-123">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="38a68-123">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="38a68-124">2</span><span class="sxs-lookup"><span data-stu-id="38a68-124">2</span></span></p></li>
<li><p><span data-ttu-id="38a68-125">5</span><span class="sxs-lookup"><span data-stu-id="38a68-125">5</span></span></p></li>
<li><p><span data-ttu-id="38a68-126">base10</span><span class="sxs-lookup"><span data-stu-id="38a68-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

