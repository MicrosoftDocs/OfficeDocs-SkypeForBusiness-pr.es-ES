---
title: 'Lync Server 2013: tblComplianceParticipant'
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
ms.openlocfilehash: 484948a01c82dc8ca256e3e50e484c94a9b81de4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="7e3e8-102">tblComplianceParticipant en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e3e8-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e3e8-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7e3e8-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7e3e8-104">tblComplianceParticipant contiene los participantes actuales por canal y por servidor.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="7e3e8-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="7e3e8-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e3e8-106">Columna</span><span class="sxs-lookup"><span data-stu-id="7e3e8-106">Column</span></span></th>
<th><span data-ttu-id="7e3e8-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="7e3e8-107">Type</span></span></th>
<th><span data-ttu-id="7e3e8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e3e8-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e3e8-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="7e3e8-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="7e3e8-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-111">Identificador uniforme de recursos (URI) del canal.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3e8-112">Iddeusuario</span><span class="sxs-lookup"><span data-stu-id="7e3e8-112">userId</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="7e3e8-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-114">IDENTIFICADOR principal del participante (correspondiente a la tabla tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="7e3e8-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3e8-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="7e3e8-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-116">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="7e3e8-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-117">Marca de tiempo del evento de Unión.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3e8-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="7e3e8-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-119">BIGINT</span><span class="sxs-lookup"><span data-stu-id="7e3e8-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-120">NULL si el participante aún se ha unido.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-120">Null if participant is still joined.</span></span> <span data-ttu-id="7e3e8-121">Marca de tiempo del canal dejando el evento si no es NULL.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-121">The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="7e3e8-122">Estas entradas se eliminan en algún momento cuando todos los traductores procesan el evento.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3e8-123">userUri</span><span class="sxs-lookup"><span data-stu-id="7e3e8-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-124">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="7e3e8-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-125">URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3e8-126">serverID</span><span class="sxs-lookup"><span data-stu-id="7e3e8-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-127">int</span><span class="sxs-lookup"><span data-stu-id="7e3e8-127">int</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-128">Identidad del servidor (como en la tabla tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="7e3e8-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3e8-129">Identificador</span><span class="sxs-lookup"><span data-stu-id="7e3e8-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-130">BIGINT</span><span class="sxs-lookup"><span data-stu-id="7e3e8-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-131">Sesión de servidor.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-131">Server session.</span></span> <span data-ttu-id="7e3e8-132">Este es un número aleatorio generado cada vez que se inicia un servicio de chat.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="7e3e8-133">Se usa para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="7e3e8-134">Clave</span><span class="sxs-lookup"><span data-stu-id="7e3e8-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e3e8-135">Columna</span><span class="sxs-lookup"><span data-stu-id="7e3e8-135">Column</span></span></th>
<th><span data-ttu-id="7e3e8-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e3e8-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e3e8-137">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="7e3e8-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="7e3e8-138">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="7e3e8-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

