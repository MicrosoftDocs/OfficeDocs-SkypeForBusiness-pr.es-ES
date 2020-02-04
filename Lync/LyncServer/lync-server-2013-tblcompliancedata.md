---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48516f307a084d30fde06a03548119e0ada34d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="be656-102">tblComplianceData en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be656-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be656-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="be656-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="be656-104">tblComplianceData contiene los eventos de conformidad que aún no ha procesado el adaptador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="be656-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="be656-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="be656-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be656-106">Columna</span><span class="sxs-lookup"><span data-stu-id="be656-106">Column</span></span></th>
<th><span data-ttu-id="be656-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="be656-107">Type</span></span></th>
<th><span data-ttu-id="be656-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="be656-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be656-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="be656-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="be656-110">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="be656-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="be656-111">IDENTIFICADOR de evento.</span><span class="sxs-lookup"><span data-stu-id="be656-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be656-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="be656-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="be656-113">smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="be656-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="be656-114">Hora de inserción (puede ser muy próxima para cmplType = 9 porque la entrada es solo un marcador de posición en ese caso).</span><span class="sxs-lookup"><span data-stu-id="be656-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be656-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="be656-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="be656-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="be656-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="be656-117">Tipo de evento de conformidad:</span><span class="sxs-lookup"><span data-stu-id="be656-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="be656-118">1: chatear</span><span class="sxs-lookup"><span data-stu-id="be656-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="be656-119">2: chatear</span><span class="sxs-lookup"><span data-stu-id="be656-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="be656-120">3: descarga de archivos</span><span class="sxs-lookup"><span data-stu-id="be656-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="be656-121">4: carga de archivos</span><span class="sxs-lookup"><span data-stu-id="be656-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="be656-122">9: transferencia provisional de archivos</span><span class="sxs-lookup"><span data-stu-id="be656-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="be656-123">10: eliminación de chat (con Replace)</span><span class="sxs-lookup"><span data-stu-id="be656-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="be656-124">11: purgado de chat</span><span class="sxs-lookup"><span data-stu-id="be656-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be656-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="be656-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="be656-126">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="be656-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="be656-127">Marca de tiempo del evento.</span><span class="sxs-lookup"><span data-stu-id="be656-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be656-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="be656-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="be656-129">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="be656-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="be656-130">Identificador uniforme de recursos (URI) del canal.</span><span class="sxs-lookup"><span data-stu-id="be656-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be656-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="be656-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="be656-132">BIGINT</span><span class="sxs-lookup"><span data-stu-id="be656-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="be656-133">IDENTIFICADOR de chat (corresponde a la tabla tblChat. chatId).</span><span class="sxs-lookup"><span data-stu-id="be656-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be656-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="be656-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="be656-135">int, not null</span><span class="sxs-lookup"><span data-stu-id="be656-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="be656-136">IDENTIFICADOR principal del póster (correspondiente a la tabla tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="be656-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be656-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="be656-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="be656-138">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="be656-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="be656-139">URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="be656-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be656-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="be656-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="be656-141">nvarchar (Max)</span><span class="sxs-lookup"><span data-stu-id="be656-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="be656-142">Mensaje (la codificación depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="be656-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="be656-143">Clave</span><span class="sxs-lookup"><span data-stu-id="be656-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be656-144">Columna</span><span class="sxs-lookup"><span data-stu-id="be656-144">Column</span></span></th>
<th><span data-ttu-id="be656-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="be656-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be656-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="be656-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="be656-147">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="be656-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

