---
title: 'Lync Server 2013: vista de conferencias'
description: 'Lync Server 2013: vista de conferencias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dee7fbb7c839c351fc9c81716a5800a678980549
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561586"
---
# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="6223b-103">Vista de conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6223b-103">Conferences view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6223b-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6223b-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6223b-105">La vista Conferencias almacena información sobre las conferencias.</span><span class="sxs-lookup"><span data-stu-id="6223b-105">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="6223b-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6223b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6223b-107">Columna</span><span class="sxs-lookup"><span data-stu-id="6223b-107">Column</span></span></th>
<th><span data-ttu-id="6223b-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6223b-108">Data Type</span></span></th>
<th><span data-ttu-id="6223b-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="6223b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6223b-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6223b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6223b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="6223b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="6223b-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="6223b-112">Time of session request.</span></span> <span data-ttu-id="6223b-113">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="6223b-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="6223b-114">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6223b-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6223b-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6223b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6223b-116">entero</span><span class="sxs-lookup"><span data-stu-id="6223b-116">int</span></span></p></td>
<td><p><span data-ttu-id="6223b-117">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="6223b-117">ID number to identify the session.</span></span> <span data-ttu-id="6223b-118">Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="6223b-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="6223b-119">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6223b-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6223b-120"><strong>Uri</strong></span><span class="sxs-lookup"><span data-stu-id="6223b-120"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6223b-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6223b-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6223b-122">URI de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="6223b-122">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6223b-123"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="6223b-123"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="6223b-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6223b-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6223b-125">Tipo del URI de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="6223b-125">Type of the conference URI.</span></span> <span data-ttu-id="6223b-126">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6223b-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6223b-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="6223b-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="6223b-128">identificador</span><span class="sxs-lookup"><span data-stu-id="6223b-128">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="6223b-p105">Se usa en conferencias periódicas. Cada instancia de una conferencia periódica tiene el mismo ConferenceUri, pero un ConfInstance distinto.</span><span class="sxs-lookup"><span data-stu-id="6223b-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6223b-131"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="6223b-131"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6223b-132">datetime</span><span class="sxs-lookup"><span data-stu-id="6223b-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="6223b-133">Hora de inicio de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="6223b-133">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6223b-134"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="6223b-134"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6223b-135">datetime</span><span class="sxs-lookup"><span data-stu-id="6223b-135">datetime</span></span></p></td>
<td><p><span data-ttu-id="6223b-136">Hora de finalización de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="6223b-136">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6223b-137"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="6223b-137"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6223b-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6223b-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6223b-139">URI del usuario que organizó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="6223b-139">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6223b-140"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="6223b-140"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="6223b-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6223b-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6223b-142">Tipo de URI del usuario que organizó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="6223b-142">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="6223b-143">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6223b-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6223b-144"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="6223b-144"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="6223b-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6223b-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6223b-146">Inquilino del usuario que organizó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="6223b-146">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="6223b-147">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6223b-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6223b-148"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="6223b-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="6223b-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6223b-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6223b-150">Nombre de dominio completo del grupo que hospedó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="6223b-150">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6223b-151"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="6223b-151"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="6223b-152">smallint</span><span class="sxs-lookup"><span data-stu-id="6223b-152">smallint</span></span></p></td>
<td><p><span data-ttu-id="6223b-p108">Máscara de bits que contiene atributos de la conferencia. Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="6223b-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="6223b-155">0X01: transacción sintética</span><span class="sxs-lookup"><span data-stu-id="6223b-155">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

