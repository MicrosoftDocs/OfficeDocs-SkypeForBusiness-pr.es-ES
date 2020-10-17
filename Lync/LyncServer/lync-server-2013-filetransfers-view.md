---
title: 'Lync Server 2013: vista de FileTransfers'
description: 'Lync Server 2013: vista de FileTransfers.'
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
ms.openlocfilehash: dd2b084274a4d5daa093f2269617214f703ac03e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552626"
---
# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="9215b-103">Vista FileTransfers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9215b-103">FileTransfers view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9215b-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9215b-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9215b-105">La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos punto a punto.</span><span class="sxs-lookup"><span data-stu-id="9215b-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="9215b-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9215b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9215b-107">La vista FileTransfers contiene todas las columnas de la <A href="lync-server-2013-sessiondetails-view.md">vista SessionDetails en Lync Server 2013</A> , además de las columnas que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="9215b-107">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9215b-108">Columna</span><span class="sxs-lookup"><span data-stu-id="9215b-108">Column</span></span></th>
<th><span data-ttu-id="9215b-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9215b-109">Data Type</span></span></th>
<th><span data-ttu-id="9215b-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="9215b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9215b-111"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="9215b-111"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="9215b-112">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9215b-112">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9215b-113">Nombre del archivo transferido.</span><span class="sxs-lookup"><span data-stu-id="9215b-113">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9215b-114"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="9215b-114"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="9215b-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="9215b-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9215b-116">Se usa para identificar cada mensaje de seguimiento como mensaje asociado a este.</span><span class="sxs-lookup"><span data-stu-id="9215b-116">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9215b-117"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="9215b-117"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="9215b-118">identificador</span><span class="sxs-lookup"><span data-stu-id="9215b-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9215b-119">Identificador único para distinguir entre las transferencias de archivos en las que participa el mismo nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="9215b-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9215b-120"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="9215b-120"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="9215b-121">bit</span><span class="sxs-lookup"><span data-stu-id="9215b-121">bit</span></span></p></td>
<td><p><span data-ttu-id="9215b-p102">Puede ser TRUE o NULL. Si es TRUE, Rechazar y Cancelar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="9215b-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9215b-124"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="9215b-124"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="9215b-125">bit</span><span class="sxs-lookup"><span data-stu-id="9215b-125">bit</span></span></p></td>
<td><p><span data-ttu-id="9215b-p103">Puede ser TRUE o NULL. Si es TRUE, Aceptar y Cancelar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="9215b-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9215b-128"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="9215b-128"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="9215b-129">bit</span><span class="sxs-lookup"><span data-stu-id="9215b-129">bit</span></span></p></td>
<td><p><span data-ttu-id="9215b-p104">Puede ser TRUE o NULL. Si es TRUE, Aceptar y Rechazar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="9215b-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

