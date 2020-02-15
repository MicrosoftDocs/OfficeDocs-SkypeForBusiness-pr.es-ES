---
title: 'Lync Server 2013: vista de FileTransfers'
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
ms.openlocfilehash: 95cc6790766d68ee478cf1b80326c974f7c15f1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="8254f-102">Vista FileTransfers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8254f-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8254f-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8254f-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8254f-104">La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos punto a punto.</span><span class="sxs-lookup"><span data-stu-id="8254f-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="8254f-105">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8254f-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8254f-106">La vista FileTransfers contiene todas las columnas de la <A href="lync-server-2013-sessiondetails-view.md">vista SessionDetails en Lync Server 2013</A> , además de las columnas que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="8254f-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8254f-107">Columna</span><span class="sxs-lookup"><span data-stu-id="8254f-107">Column</span></span></th>
<th><span data-ttu-id="8254f-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8254f-108">Data Type</span></span></th>
<th><span data-ttu-id="8254f-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="8254f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8254f-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="8254f-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="8254f-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8254f-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8254f-112">Nombre del archivo transferido.</span><span class="sxs-lookup"><span data-stu-id="8254f-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8254f-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="8254f-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="8254f-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8254f-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8254f-115">Se usa para identificar cada mensaje de seguimiento como mensaje asociado a este.</span><span class="sxs-lookup"><span data-stu-id="8254f-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8254f-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="8254f-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="8254f-117">identificador</span><span class="sxs-lookup"><span data-stu-id="8254f-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="8254f-118">Identificador único para distinguir entre las transferencias de archivos en las que participa el mismo nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="8254f-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8254f-119"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="8254f-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="8254f-120">bit</span><span class="sxs-lookup"><span data-stu-id="8254f-120">bit</span></span></p></td>
<td><p><span data-ttu-id="8254f-p102">Puede ser TRUE o NULL. Si es TRUE, Rechazar y Cancelar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="8254f-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8254f-123"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="8254f-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="8254f-124">bit</span><span class="sxs-lookup"><span data-stu-id="8254f-124">bit</span></span></p></td>
<td><p><span data-ttu-id="8254f-p103">Puede ser TRUE o NULL. Si es TRUE, Aceptar y Cancelar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="8254f-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8254f-127"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="8254f-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="8254f-128">bit</span><span class="sxs-lookup"><span data-stu-id="8254f-128">bit</span></span></p></td>
<td><p><span data-ttu-id="8254f-p104">Puede ser TRUE o NULL. Si es TRUE, Aceptar y Rechazar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="8254f-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

