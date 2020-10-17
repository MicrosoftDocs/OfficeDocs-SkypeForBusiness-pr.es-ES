---
title: 'Lync Server 2013: tblComplianceParticipant'
description: 'Lync Server 2013: tblComplianceParticipant.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1385b0a635f003a72de93f10f72642314ad7ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569076"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="87b63-103">tblComplianceParticipant en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87b63-103">tblComplianceParticipant in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87b63-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="87b63-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="87b63-105">La tabla tblComplianceParticipant contiene los participantes actuales por canal y por servidor.</span><span class="sxs-lookup"><span data-stu-id="87b63-105">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="87b63-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="87b63-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87b63-107">Columna</span><span class="sxs-lookup"><span data-stu-id="87b63-107">Column</span></span></th>
<th><span data-ttu-id="87b63-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="87b63-108">Type</span></span></th>
<th><span data-ttu-id="87b63-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="87b63-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87b63-110">channelUri</span><span class="sxs-lookup"><span data-stu-id="87b63-110">channelUri</span></span></p></td>
<td><p><span data-ttu-id="87b63-111">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="87b63-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="87b63-112">Identificador uniforme de recursos (URI) del canal.</span><span class="sxs-lookup"><span data-stu-id="87b63-112">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87b63-113">userId</span><span class="sxs-lookup"><span data-stu-id="87b63-113">userId</span></span></p></td>
<td><p><span data-ttu-id="87b63-114">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="87b63-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="87b63-115">Identificador de la entidad de seguridad del participante (correspondiente a la tabla tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="87b63-115">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87b63-116">joinedAt</span><span class="sxs-lookup"><span data-stu-id="87b63-116">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="87b63-117">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="87b63-117">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="87b63-118">Marca de tiempo del evento participante.</span><span class="sxs-lookup"><span data-stu-id="87b63-118">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87b63-119">partedAt</span><span class="sxs-lookup"><span data-stu-id="87b63-119">partedAt</span></span></p></td>
<td><p><span data-ttu-id="87b63-120">BIGINT</span><span class="sxs-lookup"><span data-stu-id="87b63-120">bigint</span></span></p></td>
<td><p><span data-ttu-id="87b63-p101">Nulo si el participante aún está participando. La marca de tiempo del canal que abandona el evento si no es nulo.</span><span class="sxs-lookup"><span data-stu-id="87b63-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="87b63-123">Estas entradas se quitan finalmente cuando todos los traductores procesan el evento.</span><span class="sxs-lookup"><span data-stu-id="87b63-123">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87b63-124">userUri</span><span class="sxs-lookup"><span data-stu-id="87b63-124">userUri</span></span></p></td>
<td><p><span data-ttu-id="87b63-125">nvarchar(255), no NULL</span><span class="sxs-lookup"><span data-stu-id="87b63-125">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="87b63-126">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="87b63-126">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87b63-127">serverID</span><span class="sxs-lookup"><span data-stu-id="87b63-127">serverID</span></span></p></td>
<td><p><span data-ttu-id="87b63-128">entero</span><span class="sxs-lookup"><span data-stu-id="87b63-128">int</span></span></p></td>
<td><p><span data-ttu-id="87b63-129">Identidad del servidor (como en la tabla tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="87b63-129">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87b63-130">sessionId</span><span class="sxs-lookup"><span data-stu-id="87b63-130">sessionId</span></span></p></td>
<td><p><span data-ttu-id="87b63-131">BIGINT</span><span class="sxs-lookup"><span data-stu-id="87b63-131">bigint</span></span></p></td>
<td><p><span data-ttu-id="87b63-p102">Sesión del servidor. Es un número aleatorio que se genera cada vez que se inicia un servicio de chat. Sirve para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.</span><span class="sxs-lookup"><span data-stu-id="87b63-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="87b63-135">Key </span><span class="sxs-lookup"><span data-stu-id="87b63-135">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87b63-136">Columna</span><span class="sxs-lookup"><span data-stu-id="87b63-136">Column</span></span></th>
<th><span data-ttu-id="87b63-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="87b63-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87b63-138">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="87b63-138">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="87b63-139">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="87b63-139">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

