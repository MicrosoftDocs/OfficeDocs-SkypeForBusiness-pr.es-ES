---
title: 'Lync Server 2013: Tabla ConferenceMessageCount'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2994f02bf087ef55edff6b2153e7504f881b03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="81d4d-102">Tabla ConferenceMessageCount en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81d4d-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81d4d-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="81d4d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="81d4d-104">Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="81d4d-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="81d4d-105">Cada conferencia está representada por varios registros en esta tabla; un registro para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="81d4d-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81d4d-106">Columna</span><span class="sxs-lookup"><span data-stu-id="81d4d-106">Column</span></span></th>
<th><span data-ttu-id="81d4d-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="81d4d-107">Data Type</span></span></th>
<th><span data-ttu-id="81d4d-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="81d4d-108">Key/Index</span></span></th>
<th><span data-ttu-id="81d4d-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="81d4d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81d4d-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="81d4d-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="81d4d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="81d4d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="81d4d-112">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="81d4d-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="81d4d-113">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="81d4d-113">Time of conference instance.</span></span> <span data-ttu-id="81d4d-114">Se usa junto con <strong>SessionIdSeq</strong> para identificar de forma exclusiva una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="81d4d-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="81d4d-115">Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="81d4d-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81d4d-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="81d4d-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="81d4d-117">int</span><span class="sxs-lookup"><span data-stu-id="81d4d-117">int</span></span></p></td>
<td><p><span data-ttu-id="81d4d-118">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="81d4d-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="81d4d-119">Número de identificación para identificar la instancia de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="81d4d-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="81d4d-120">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma exclusiva una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="81d4d-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="81d4d-121">Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="81d4d-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81d4d-122"><strong>Iddeusuario</strong></span><span class="sxs-lookup"><span data-stu-id="81d4d-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="81d4d-123">int</span><span class="sxs-lookup"><span data-stu-id="81d4d-123">int</span></span></p></td>
<td><p><span data-ttu-id="81d4d-124">Extranjero</span><span class="sxs-lookup"><span data-stu-id="81d4d-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="81d4d-125">Número único que identifica a este usuario, al que se hace referencia en la <a href="lync-server-2013-users-table.md">tabla usuarios de Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="81d4d-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81d4d-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="81d4d-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="81d4d-127">smallint</span><span class="sxs-lookup"><span data-stu-id="81d4d-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="81d4d-128">El número de mensajes enviados por este usuario durante esta conferencia.</span><span class="sxs-lookup"><span data-stu-id="81d4d-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

