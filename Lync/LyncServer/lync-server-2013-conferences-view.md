---
title: 'Lync Server 2013: vista de conferencias'
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
ms.openlocfilehash: 6f01d7fb0a2cb0526d4d6954b303a7cf78bb9333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="15ff2-102">Vista de conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15ff2-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15ff2-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="15ff2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="15ff2-104">La vista Conferencias almacena información sobre las conferencias.</span><span class="sxs-lookup"><span data-stu-id="15ff2-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="15ff2-105">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15ff2-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15ff2-106">Columna</span><span class="sxs-lookup"><span data-stu-id="15ff2-106">Column</span></span></th>
<th><span data-ttu-id="15ff2-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="15ff2-107">Data Type</span></span></th>
<th><span data-ttu-id="15ff2-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="15ff2-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15ff2-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="15ff2-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="15ff2-110">datetime</span><span class="sxs-lookup"><span data-stu-id="15ff2-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="15ff2-111">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="15ff2-111">Time of session request.</span></span> <span data-ttu-id="15ff2-112">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="15ff2-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="15ff2-113">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="15ff2-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15ff2-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="15ff2-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="15ff2-115">int</span><span class="sxs-lookup"><span data-stu-id="15ff2-115">int</span></span></p></td>
<td><p><span data-ttu-id="15ff2-116">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="15ff2-116">ID number to identify the session.</span></span> <span data-ttu-id="15ff2-117">Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="15ff2-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="15ff2-118">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="15ff2-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15ff2-119"><strong>Uri</strong></span><span class="sxs-lookup"><span data-stu-id="15ff2-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="15ff2-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="15ff2-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="15ff2-121">URI de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="15ff2-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15ff2-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="15ff2-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="15ff2-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15ff2-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15ff2-124">Tipo del URI de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="15ff2-124">Type of the conference URI.</span></span> <span data-ttu-id="15ff2-125">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="15ff2-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15ff2-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="15ff2-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="15ff2-127">identificador</span><span class="sxs-lookup"><span data-stu-id="15ff2-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="15ff2-p105">Se usa en conferencias periódicas. Cada instancia de una conferencia periódica tiene el mismo ConferenceUri, pero un ConfInstance distinto.</span><span class="sxs-lookup"><span data-stu-id="15ff2-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15ff2-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="15ff2-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="15ff2-131">datetime</span><span class="sxs-lookup"><span data-stu-id="15ff2-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="15ff2-132">Hora de inicio de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="15ff2-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15ff2-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="15ff2-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="15ff2-134">datetime</span><span class="sxs-lookup"><span data-stu-id="15ff2-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="15ff2-135">Hora de finalización de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="15ff2-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15ff2-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="15ff2-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="15ff2-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="15ff2-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="15ff2-138">URI del usuario que organizó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="15ff2-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15ff2-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="15ff2-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="15ff2-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15ff2-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15ff2-141">Tipo de URI del usuario que organizó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="15ff2-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="15ff2-142">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="15ff2-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15ff2-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="15ff2-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="15ff2-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15ff2-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15ff2-145">Inquilino del usuario que organizó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="15ff2-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="15ff2-146">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="15ff2-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15ff2-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="15ff2-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="15ff2-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15ff2-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15ff2-149">Nombre de dominio completo del grupo que hospedó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="15ff2-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15ff2-150"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="15ff2-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="15ff2-151">smallint</span><span class="sxs-lookup"><span data-stu-id="15ff2-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="15ff2-p108">Máscara de bits que contiene atributos de la conferencia. Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="15ff2-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="15ff2-154">0X01: transacción sintética</span><span class="sxs-lookup"><span data-stu-id="15ff2-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

