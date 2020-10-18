---
title: 'Lync Server 2013: tabla FileTransfers'
description: 'Lync Server 2013: tabla FileTransfers.'
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
ms.openlocfilehash: ccde45fa3743a809499273676d567846ef292ecc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573366"
---
# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="ecbde-103">Tabla FileTransfers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecbde-103">FileTransfers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecbde-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ecbde-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ecbde-105">Cada registro representa una sesión de transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="ecbde-105">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ecbde-106">Columna</span><span class="sxs-lookup"><span data-stu-id="ecbde-106">Column</span></span></th>
<th><span data-ttu-id="ecbde-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ecbde-107">Data Type</span></span></th>
<th><span data-ttu-id="ecbde-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="ecbde-108">Key/Index</span></span></th>
<th><span data-ttu-id="ecbde-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="ecbde-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ecbde-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ecbde-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ecbde-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ecbde-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ecbde-112">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="ecbde-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecbde-113">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="ecbde-113">Time of session request.</span></span> <span data-ttu-id="ecbde-114">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="ecbde-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ecbde-115">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecbde-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecbde-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ecbde-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ecbde-117">entero</span><span class="sxs-lookup"><span data-stu-id="ecbde-117">int</span></span></p></td>
<td><p><span data-ttu-id="ecbde-118">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="ecbde-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecbde-119">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="ecbde-119">ID number to identify the session.</span></span> <span data-ttu-id="ecbde-120">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="ecbde-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ecbde-121">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecbde-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecbde-122"><strong>Nombre de archivo</strong></span><span class="sxs-lookup"><span data-stu-id="ecbde-122"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="ecbde-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ecbde-123">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecbde-124">Nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="ecbde-124">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecbde-125"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="ecbde-125"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="ecbde-126">identificador</span><span class="sxs-lookup"><span data-stu-id="ecbde-126">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecbde-127">Identificador único para distinguir entre las transferencias de archivos con el mismo nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="ecbde-127">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecbde-128"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="ecbde-128"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="ecbde-129">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ecbde-129">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ecbde-130">Principal</span><span class="sxs-lookup"><span data-stu-id="ecbde-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="ecbde-131">Se usa para identificar cada mensaje de seguimiento como mensaje asociado a este.</span><span class="sxs-lookup"><span data-stu-id="ecbde-131">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecbde-132"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="ecbde-132"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="ecbde-133">bit</span><span class="sxs-lookup"><span data-stu-id="ecbde-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecbde-p103">Puede ser TRUE o NULL. Si es TRUE, Rechazar y Cancelar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="ecbde-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecbde-136"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="ecbde-136"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="ecbde-137">bit</span><span class="sxs-lookup"><span data-stu-id="ecbde-137">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecbde-p104">Puede ser TRUE o NULL. Si es TRUE, Aceptar y Cancelar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="ecbde-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecbde-140"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="ecbde-140"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="ecbde-141">bit</span><span class="sxs-lookup"><span data-stu-id="ecbde-141">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecbde-p105">Puede ser TRUE o NULL. Si es TRUE, Aceptar y Rechazar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="ecbde-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

