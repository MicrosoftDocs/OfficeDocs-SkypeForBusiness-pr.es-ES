---
title: 'Lync Server 2013: tabla UserStatistics'
description: 'Lync Server 2013: tabla UserStatistics.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75b34fa3c34af4cc9cf2cacc6ae7feb4d217114c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548536"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="945d8-103">Tabla UserStatistics en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="945d8-103">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="945d8-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="945d8-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="945d8-105">La tabla UserStatistics es una tabla auxiliar.</span><span class="sxs-lookup"><span data-stu-id="945d8-105">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="945d8-106">Cada registro de la tabla almacena información sobre el uso del sistema por parte de un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="945d8-106">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="945d8-107">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="945d8-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="945d8-108">Columna</span><span class="sxs-lookup"><span data-stu-id="945d8-108">Column</span></span></th>
<th><span data-ttu-id="945d8-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="945d8-109">Data Type</span></span></th>
<th><span data-ttu-id="945d8-110">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="945d8-110">Key/Index</span></span></th>
<th><span data-ttu-id="945d8-111">Detalles</span><span class="sxs-lookup"><span data-stu-id="945d8-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="945d8-112"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="945d8-112"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="945d8-113">entero</span><span class="sxs-lookup"><span data-stu-id="945d8-113">int</span></span></p></td>
<td><p><span data-ttu-id="945d8-114">Principal</span><span class="sxs-lookup"><span data-stu-id="945d8-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="945d8-115">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="945d8-115">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="945d8-116"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="945d8-116"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="945d8-117">datetime</span><span class="sxs-lookup"><span data-stu-id="945d8-117">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="945d8-118">Hora de la última vez que el usuario inició sesión.</span><span class="sxs-lookup"><span data-stu-id="945d8-118">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="945d8-119"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="945d8-119"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="945d8-120">datetime</span><span class="sxs-lookup"><span data-stu-id="945d8-120">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="945d8-121">Última vez que el usuario organizó una conferencia.</span><span class="sxs-lookup"><span data-stu-id="945d8-121">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="945d8-122"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="945d8-122"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="945d8-123">datetime</span><span class="sxs-lookup"><span data-stu-id="945d8-123">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="945d8-124">Última vez que el usuario tuvo un error de llamada.</span><span class="sxs-lookup"><span data-stu-id="945d8-124">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="945d8-125"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="945d8-125"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="945d8-126">datetime</span><span class="sxs-lookup"><span data-stu-id="945d8-126">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="945d8-127">Última vez que el usuario tuvo un error de llamada como organizador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="945d8-127">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

