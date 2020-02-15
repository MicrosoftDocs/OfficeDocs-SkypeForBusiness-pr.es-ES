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
ms.openlocfilehash: 98c24093f332f568daadfb0cd336f0d5fde3eb35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="90366-102">Tabla UserStatistics en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90366-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90366-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="90366-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="90366-104">La tabla UserStatistics es una tabla auxiliar.</span><span class="sxs-lookup"><span data-stu-id="90366-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="90366-105">Cada registro de la tabla almacena información sobre el uso del sistema por parte de un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="90366-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="90366-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="90366-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90366-107">Columna</span><span class="sxs-lookup"><span data-stu-id="90366-107">Column</span></span></th>
<th><span data-ttu-id="90366-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="90366-108">Data Type</span></span></th>
<th><span data-ttu-id="90366-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="90366-109">Key/Index</span></span></th>
<th><span data-ttu-id="90366-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="90366-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90366-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="90366-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="90366-112">int</span><span class="sxs-lookup"><span data-stu-id="90366-112">int</span></span></p></td>
<td><p><span data-ttu-id="90366-113">Principal</span><span class="sxs-lookup"><span data-stu-id="90366-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="90366-114">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="90366-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90366-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="90366-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="90366-116">datetime</span><span class="sxs-lookup"><span data-stu-id="90366-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="90366-117">Hora de la última vez que el usuario inició sesión.</span><span class="sxs-lookup"><span data-stu-id="90366-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90366-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="90366-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="90366-119">datetime</span><span class="sxs-lookup"><span data-stu-id="90366-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="90366-120">Última vez que el usuario organizó una conferencia.</span><span class="sxs-lookup"><span data-stu-id="90366-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90366-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="90366-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="90366-122">datetime</span><span class="sxs-lookup"><span data-stu-id="90366-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="90366-123">Última vez que el usuario tuvo un error de llamada.</span><span class="sxs-lookup"><span data-stu-id="90366-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90366-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="90366-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="90366-125">datetime</span><span class="sxs-lookup"><span data-stu-id="90366-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="90366-126">Última vez que el usuario tuvo un error de llamada como organizador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="90366-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

