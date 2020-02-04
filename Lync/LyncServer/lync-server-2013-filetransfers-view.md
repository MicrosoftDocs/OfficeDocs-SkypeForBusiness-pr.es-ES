---
title: 'Lync Server 2013: vista FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4469140f7f92c563a594c883d02f3add1e65c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="fb216-102">Vista FileTransfers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb216-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb216-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fb216-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fb216-104">La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="fb216-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="fb216-105">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb216-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fb216-106">La vista FileTransfers contiene todas las columnas de la <A href="lync-server-2013-sessiondetails-view.md">vista SessionDetails de Lync Server 2013</A> , además de las columnas que figuran a continuación.</span><span class="sxs-lookup"><span data-stu-id="fb216-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb216-107">Columna</span><span class="sxs-lookup"><span data-stu-id="fb216-107">Column</span></span></th>
<th><span data-ttu-id="fb216-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="fb216-108">Data Type</span></span></th>
<th><span data-ttu-id="fb216-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="fb216-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb216-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="fb216-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="fb216-111">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fb216-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb216-112">Nombre del archivo transferido.</span><span class="sxs-lookup"><span data-stu-id="fb216-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb216-113"><strong>Ésta</strong></span><span class="sxs-lookup"><span data-stu-id="fb216-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="fb216-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="fb216-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="fb216-115">Se usa para identificar cada mensaje de seguimiento como asociado con este.</span><span class="sxs-lookup"><span data-stu-id="fb216-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb216-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="fb216-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="fb216-117">identificador</span><span class="sxs-lookup"><span data-stu-id="fb216-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fb216-118">Identificador único para distinguir entre transferencias de archivos que impliquen el mismo nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="fb216-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb216-119"><strong>Aceptable</strong></span><span class="sxs-lookup"><span data-stu-id="fb216-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="fb216-120">bit</span><span class="sxs-lookup"><span data-stu-id="fb216-120">bit</span></span></p></td>
<td><p><span data-ttu-id="fb216-121">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="fb216-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="fb216-122">Si es verdadero, rechazar y cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="fb216-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb216-123"><strong>Rechace</strong></span><span class="sxs-lookup"><span data-stu-id="fb216-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="fb216-124">bit</span><span class="sxs-lookup"><span data-stu-id="fb216-124">bit</span></span></p></td>
<td><p><span data-ttu-id="fb216-125">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="fb216-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="fb216-126">Si es verdadero, aceptar y cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="fb216-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb216-127"><strong>Cancelar.</strong></span><span class="sxs-lookup"><span data-stu-id="fb216-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="fb216-128">bit</span><span class="sxs-lookup"><span data-stu-id="fb216-128">bit</span></span></p></td>
<td><p><span data-ttu-id="fb216-129">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="fb216-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="fb216-130">Si es verdadero, aceptar y rechazar serán NULOs.</span><span class="sxs-lookup"><span data-stu-id="fb216-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

