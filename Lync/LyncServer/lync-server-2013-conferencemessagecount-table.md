---
title: 'Lync Server 2013: tabla ConferenceMessageCount'
description: 'Lync Server 2013: tabla ConferenceMessageCount.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 271b654c09ab1aef194eb613e660de208aea1534
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561626"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="f2a1e-103">Tabla ConferenceMessageCount en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2a1e-103">ConferenceMessageCount table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2a1e-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f2a1e-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f2a1e-105">Cada registro de esta tabla representa un usuario en una conferencia de mi y incluye el número de mensajes enviados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f2a1e-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="f2a1e-106">Cada conferencia se representa mediante varios registros en esta tabla; un registro para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="f2a1e-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2a1e-107">Columna</span><span class="sxs-lookup"><span data-stu-id="f2a1e-107">Column</span></span></th>
<th><span data-ttu-id="f2a1e-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f2a1e-108">Data Type</span></span></th>
<th><span data-ttu-id="f2a1e-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="f2a1e-109">Key/Index</span></span></th>
<th><span data-ttu-id="f2a1e-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="f2a1e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2a1e-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f2a1e-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f2a1e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f2a1e-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f2a1e-113">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="f2a1e-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2a1e-114">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="f2a1e-114">Time of conference instance.</span></span> <span data-ttu-id="f2a1e-115">Se usa junto con <strong>SessionIdSeq</strong> para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="f2a1e-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="f2a1e-116">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f2a1e-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2a1e-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f2a1e-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f2a1e-118">entero</span><span class="sxs-lookup"><span data-stu-id="f2a1e-118">int</span></span></p></td>
<td><p><span data-ttu-id="f2a1e-119">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="f2a1e-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2a1e-120">Número de identificación de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="f2a1e-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="f2a1e-121">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="f2a1e-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="f2a1e-122">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f2a1e-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2a1e-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="f2a1e-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2a1e-124">entero</span><span class="sxs-lookup"><span data-stu-id="f2a1e-124">int</span></span></p></td>
<td><p><span data-ttu-id="f2a1e-125">Externa</span><span class="sxs-lookup"><span data-stu-id="f2a1e-125">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2a1e-126">Número único que identifica a este usuario, al que se hace referencia en la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f2a1e-126">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2a1e-127"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="f2a1e-127"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f2a1e-128">smallint</span><span class="sxs-lookup"><span data-stu-id="f2a1e-128">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f2a1e-129">El número de mensajes enviados por este usuario durante esta conferencia.</span><span class="sxs-lookup"><span data-stu-id="f2a1e-129">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

