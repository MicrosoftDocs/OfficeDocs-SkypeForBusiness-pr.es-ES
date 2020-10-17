---
title: 'Lync Server 2013: tblComplianceData'
description: 'Lync Server 2013: tblComplianceData.'
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
ms.openlocfilehash: 3c597d67054303de2753182b37419f68051d3af8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568106"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="3c83b-103">tblComplianceData en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c83b-103">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c83b-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="3c83b-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="3c83b-105">La tabla tblComplianceData contiene los eventos de cumplimiento que aún no procesó el adaptador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="3c83b-105">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="3c83b-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="3c83b-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c83b-107">Columna</span><span class="sxs-lookup"><span data-stu-id="3c83b-107">Column</span></span></th>
<th><span data-ttu-id="3c83b-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="3c83b-108">Type</span></span></th>
<th><span data-ttu-id="3c83b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c83b-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c83b-110">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="3c83b-110">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="3c83b-111">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="3c83b-111">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="3c83b-112">Id. del evento.</span><span class="sxs-lookup"><span data-stu-id="3c83b-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c83b-113">entryDate</span><span class="sxs-lookup"><span data-stu-id="3c83b-113">entryDate</span></span></p></td>
<td><p><span data-ttu-id="3c83b-114">smalldatetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="3c83b-114">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="3c83b-115">Hora de inserción (puede estar lejos en el futuro para cmplType=9 porque la entrada solo es un marcador de posición en ese caso).</span><span class="sxs-lookup"><span data-stu-id="3c83b-115">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c83b-116">cmplType</span><span class="sxs-lookup"><span data-stu-id="3c83b-116">cmplType</span></span></p></td>
<td><p><span data-ttu-id="3c83b-117">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="3c83b-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3c83b-118">Tipo de evento de cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="3c83b-118">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="3c83b-119">1: Chat</span><span class="sxs-lookup"><span data-stu-id="3c83b-119">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="3c83b-120">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="3c83b-120">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="3c83b-121">3: Descarga de archivos</span><span class="sxs-lookup"><span data-stu-id="3c83b-121">3: File download</span></span></p></li>
<li><p><span data-ttu-id="3c83b-122">4: Carga de archivos</span><span class="sxs-lookup"><span data-stu-id="3c83b-122">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="3c83b-123">9: Transferencia de archivo provisional</span><span class="sxs-lookup"><span data-stu-id="3c83b-123">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="3c83b-124">10: Eliminación de chats (con reemplazo)</span><span class="sxs-lookup"><span data-stu-id="3c83b-124">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="3c83b-125">11: Depuración de chats</span><span class="sxs-lookup"><span data-stu-id="3c83b-125">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c83b-126">cmplTime</span><span class="sxs-lookup"><span data-stu-id="3c83b-126">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="3c83b-127">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="3c83b-127">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="3c83b-128">Marca de tiempo del evento.</span><span class="sxs-lookup"><span data-stu-id="3c83b-128">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c83b-129">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="3c83b-129">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="3c83b-130">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="3c83b-130">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="3c83b-131">Identificador uniforme de recursos (URI) del canal.</span><span class="sxs-lookup"><span data-stu-id="3c83b-131">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c83b-132">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="3c83b-132">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="3c83b-133">BIGINT</span><span class="sxs-lookup"><span data-stu-id="3c83b-133">bigint</span></span></p></td>
<td><p><span data-ttu-id="3c83b-134">Identificador de chat (correspondiente a la tabla tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="3c83b-134">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c83b-135">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="3c83b-135">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="3c83b-136">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="3c83b-136">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3c83b-137">Identificador de entidad de seguridad del póster (correspondiente a la tabla tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="3c83b-137">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c83b-138">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="3c83b-138">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="3c83b-139">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="3c83b-139">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="3c83b-140">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="3c83b-140">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c83b-141">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="3c83b-141">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="3c83b-142">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="3c83b-142">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="3c83b-143">Mensaje (la codificación depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="3c83b-143">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="3c83b-144">Key </span><span class="sxs-lookup"><span data-stu-id="3c83b-144">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c83b-145">Columna</span><span class="sxs-lookup"><span data-stu-id="3c83b-145">Column</span></span></th>
<th><span data-ttu-id="3c83b-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c83b-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c83b-147">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="3c83b-147">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="3c83b-148">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="3c83b-148">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

