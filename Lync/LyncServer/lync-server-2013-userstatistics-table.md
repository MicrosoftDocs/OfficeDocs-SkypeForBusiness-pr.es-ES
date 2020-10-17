---
title: 'Lync Server 2013: tabla UserStatistics'
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
ms.openlocfilehash: 55df55ba8c9953a1efce25269c24b43328472d7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529997"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="607e2-102">Tabla UserStatistics en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="607e2-102">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="607e2-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="607e2-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="607e2-104">La tabla UserStatistics es una tabla auxiliar.</span><span class="sxs-lookup"><span data-stu-id="607e2-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="607e2-105">Cada registro de la tabla almacena información sobre el uso del sistema por parte de un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="607e2-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="607e2-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="607e2-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="607e2-107">Columna</span><span class="sxs-lookup"><span data-stu-id="607e2-107">Column</span></span></th>
<th><span data-ttu-id="607e2-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="607e2-108">Data Type</span></span></th>
<th><span data-ttu-id="607e2-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="607e2-109">Key/Index</span></span></th>
<th><span data-ttu-id="607e2-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="607e2-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="607e2-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="607e2-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="607e2-112">entero</span><span class="sxs-lookup"><span data-stu-id="607e2-112">int</span></span></p></td>
<td><p><span data-ttu-id="607e2-113">Principal</span><span class="sxs-lookup"><span data-stu-id="607e2-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="607e2-114">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="607e2-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="607e2-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="607e2-116">datetime</span><span class="sxs-lookup"><span data-stu-id="607e2-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="607e2-117">Hora de la última vez que el usuario inició sesión.</span><span class="sxs-lookup"><span data-stu-id="607e2-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="607e2-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="607e2-119">datetime</span><span class="sxs-lookup"><span data-stu-id="607e2-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="607e2-120">Última vez que el usuario organizó una conferencia.</span><span class="sxs-lookup"><span data-stu-id="607e2-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="607e2-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="607e2-122">datetime</span><span class="sxs-lookup"><span data-stu-id="607e2-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="607e2-123">Última vez que el usuario tuvo un error de llamada.</span><span class="sxs-lookup"><span data-stu-id="607e2-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="607e2-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="607e2-125">datetime</span><span class="sxs-lookup"><span data-stu-id="607e2-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="607e2-126">Última vez que el usuario tuvo un error de llamada como organizador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="607e2-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

