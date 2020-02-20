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
ms.openlocfilehash: dc2858ede3d1d3ccd1cc9af44c564fcac3424f35
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="902be-102">tblComplianceData en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="902be-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="902be-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="902be-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="902be-104">La tabla tblComplianceData contiene los eventos de cumplimiento que aún no procesó el adaptador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="902be-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="902be-105">Columns</span><span class="sxs-lookup"><span data-stu-id="902be-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="902be-106">Columna</span><span class="sxs-lookup"><span data-stu-id="902be-106">Column</span></span></th>
<th><span data-ttu-id="902be-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="902be-107">Type</span></span></th>
<th><span data-ttu-id="902be-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="902be-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="902be-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="902be-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="902be-110">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="902be-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="902be-111">Id. del evento.</span><span class="sxs-lookup"><span data-stu-id="902be-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="902be-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="902be-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="902be-113">smalldatetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="902be-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="902be-114">Hora de inserción (puede estar lejos en el futuro para cmplType=9 porque la entrada solo es un marcador de posición en ese caso).</span><span class="sxs-lookup"><span data-stu-id="902be-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="902be-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="902be-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="902be-116">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="902be-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="902be-117">Tipo de evento de cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="902be-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="902be-118">1: Chat</span><span class="sxs-lookup"><span data-stu-id="902be-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="902be-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="902be-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="902be-120">3: Descarga de archivos</span><span class="sxs-lookup"><span data-stu-id="902be-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="902be-121">4: Carga de archivos</span><span class="sxs-lookup"><span data-stu-id="902be-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="902be-122">9: Transferencia de archivo provisional</span><span class="sxs-lookup"><span data-stu-id="902be-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="902be-123">10: Eliminación de chats (con reemplazo)</span><span class="sxs-lookup"><span data-stu-id="902be-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="902be-124">11: Depuración de chats</span><span class="sxs-lookup"><span data-stu-id="902be-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="902be-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="902be-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="902be-126">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="902be-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="902be-127">Marca de tiempo del evento.</span><span class="sxs-lookup"><span data-stu-id="902be-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="902be-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="902be-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="902be-129">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="902be-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="902be-130">Identificador uniforme de recursos (URI) del canal.</span><span class="sxs-lookup"><span data-stu-id="902be-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="902be-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="902be-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="902be-132">BIGINT</span><span class="sxs-lookup"><span data-stu-id="902be-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="902be-133">Identificador de chat (correspondiente a la tabla tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="902be-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="902be-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="902be-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="902be-135">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="902be-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="902be-136">Identificador de entidad de seguridad del póster (correspondiente a la tabla tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="902be-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="902be-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="902be-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="902be-138">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="902be-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="902be-139">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="902be-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="902be-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="902be-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="902be-141">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="902be-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="902be-142">Mensaje (la codificación depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="902be-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="902be-143">Key </span><span class="sxs-lookup"><span data-stu-id="902be-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="902be-144">Columna</span><span class="sxs-lookup"><span data-stu-id="902be-144">Column</span></span></th>
<th><span data-ttu-id="902be-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="902be-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="902be-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="902be-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="902be-147">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="902be-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

