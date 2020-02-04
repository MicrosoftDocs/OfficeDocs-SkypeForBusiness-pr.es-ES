---
title: 'Lync Server 2013: Tabla FileTransfers'
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
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="1169c-102">Tabla FileTransfers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1169c-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1169c-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1169c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1169c-104">Cada registro representa una sesión de transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="1169c-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1169c-105">Columna</span><span class="sxs-lookup"><span data-stu-id="1169c-105">Column</span></span></th>
<th><span data-ttu-id="1169c-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1169c-106">Data Type</span></span></th>
<th><span data-ttu-id="1169c-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="1169c-107">Key/Index</span></span></th>
<th><span data-ttu-id="1169c-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="1169c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1169c-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1169c-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1169c-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1169c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1169c-111">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="1169c-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1169c-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="1169c-112">Time of session request.</span></span> <span data-ttu-id="1169c-113">Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="1169c-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1169c-114">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1169c-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1169c-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1169c-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1169c-116">int</span><span class="sxs-lookup"><span data-stu-id="1169c-116">int</span></span></p></td>
<td><p><span data-ttu-id="1169c-117">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="1169c-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1169c-118">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="1169c-118">ID number to identify the session.</span></span> <span data-ttu-id="1169c-119">Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="1169c-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1169c-120">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1169c-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1169c-121"><strong>Nombre de archivo</strong></span><span class="sxs-lookup"><span data-stu-id="1169c-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="1169c-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1169c-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1169c-123">Nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="1169c-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1169c-124"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="1169c-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="1169c-125">identificador</span><span class="sxs-lookup"><span data-stu-id="1169c-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1169c-126">Identificador único para distinguir entre transferencias de archivos que impliquen el mismo nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="1169c-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1169c-127"><strong>Ésta</strong></span><span class="sxs-lookup"><span data-stu-id="1169c-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="1169c-128">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="1169c-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="1169c-129">Primary</span><span class="sxs-lookup"><span data-stu-id="1169c-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="1169c-130">Se usa para identificar cada mensaje de seguimiento como asociado con este.</span><span class="sxs-lookup"><span data-stu-id="1169c-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1169c-131"><strong>Aceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1169c-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="1169c-132">bit</span><span class="sxs-lookup"><span data-stu-id="1169c-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1169c-133">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="1169c-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="1169c-134">Si es verdadero, rechazar y cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="1169c-134">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1169c-135"><strong>Rechace</strong></span><span class="sxs-lookup"><span data-stu-id="1169c-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="1169c-136">bit</span><span class="sxs-lookup"><span data-stu-id="1169c-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1169c-137">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="1169c-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="1169c-138">Si es verdadero, aceptar y cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="1169c-138">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1169c-139"><strong>Cancelar.</strong></span><span class="sxs-lookup"><span data-stu-id="1169c-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="1169c-140">bit</span><span class="sxs-lookup"><span data-stu-id="1169c-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1169c-141">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="1169c-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="1169c-142">Si es verdadero, aceptar y rechazar serán NULOs.</span><span class="sxs-lookup"><span data-stu-id="1169c-142">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

