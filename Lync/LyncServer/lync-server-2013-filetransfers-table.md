---
title: 'Lync Server 2013: tabla FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aedca2ae840947aef4ccc6ec7bff4ba825090a0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="cdfb4-102">Tabla FileTransfers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdfb4-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdfb4-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cdfb4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cdfb4-104">Cada registro representa una sesión de transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdfb4-105">Columna</span><span class="sxs-lookup"><span data-stu-id="cdfb4-105">Column</span></span></th>
<th><span data-ttu-id="cdfb4-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cdfb4-106">Data Type</span></span></th>
<th><span data-ttu-id="cdfb4-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="cdfb4-107">Key/Index</span></span></th>
<th><span data-ttu-id="cdfb4-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="cdfb4-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdfb4-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="cdfb4-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cdfb4-110">datetime</span><span class="sxs-lookup"><span data-stu-id="cdfb4-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="cdfb4-111">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="cdfb4-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cdfb4-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-112">Time of session request.</span></span> <span data-ttu-id="cdfb4-113">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="cdfb4-114">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdfb4-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cdfb4-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cdfb4-116">int</span><span class="sxs-lookup"><span data-stu-id="cdfb4-116">int</span></span></p></td>
<td><p><span data-ttu-id="cdfb4-117">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="cdfb4-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cdfb4-118">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-118">ID number to identify the session.</span></span> <span data-ttu-id="cdfb4-119">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="cdfb4-120">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdfb4-121"><strong>Nombre de archivo</strong></span><span class="sxs-lookup"><span data-stu-id="cdfb4-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="cdfb4-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cdfb4-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cdfb4-123">Nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdfb4-124"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="cdfb4-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="cdfb4-125">identificador</span><span class="sxs-lookup"><span data-stu-id="cdfb4-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cdfb4-126">Identificador único para distinguir entre las transferencias de archivos con el mismo nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdfb4-127"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="cdfb4-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="cdfb4-128">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="cdfb4-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="cdfb4-129">Principal</span><span class="sxs-lookup"><span data-stu-id="cdfb4-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="cdfb4-130">Se usa para identificar cada mensaje de seguimiento como mensaje asociado a este.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdfb4-131"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="cdfb4-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="cdfb4-132">bit</span><span class="sxs-lookup"><span data-stu-id="cdfb4-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cdfb4-p103">Puede ser TRUE o NULL. Si es TRUE, Rechazar y Cancelar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdfb4-135"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="cdfb4-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="cdfb4-136">bit</span><span class="sxs-lookup"><span data-stu-id="cdfb4-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cdfb4-p104">Puede ser TRUE o NULL. Si es TRUE, Aceptar y Cancelar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdfb4-139"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="cdfb4-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="cdfb4-140">bit</span><span class="sxs-lookup"><span data-stu-id="cdfb4-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cdfb4-p105">Puede ser TRUE o NULL. Si es TRUE, Aceptar y Rechazar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="cdfb4-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

