---
title: 'Lync Server 2013: vista ClientVersions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fd25da49e8a3b6ad7838ff27a4472e711b97421
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="ef333-102">Vista ClientVersions en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef333-102">ClientVersions view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef333-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ef333-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ef333-104">La vista ClientVersions almacena información sobre los diversos tipos y versiones de los clientes que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ef333-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ef333-105">Cada registro de la vista representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="ef333-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="ef333-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef333-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef333-107">Es posible que haya varios registros para determinadas columnas.</span><span class="sxs-lookup"><span data-stu-id="ef333-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef333-108">Columna</span><span class="sxs-lookup"><span data-stu-id="ef333-108">Column</span></span></th>
<th><span data-ttu-id="ef333-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ef333-109">Data Type</span></span></th>
<th><span data-ttu-id="ef333-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="ef333-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef333-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="ef333-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="ef333-112">int</span><span class="sxs-lookup"><span data-stu-id="ef333-112">int</span></span></p></td>
<td><p><span data-ttu-id="ef333-113">Número único que identifica este tipo de cliente y versión.</span><span class="sxs-lookup"><span data-stu-id="ef333-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef333-114"><strong>Versión</strong></span><span class="sxs-lookup"><span data-stu-id="ef333-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="ef333-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ef333-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef333-116">Representa el agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="ef333-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef333-117"><strong>Tipocliente</strong></span><span class="sxs-lookup"><span data-stu-id="ef333-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ef333-118">int</span><span class="sxs-lookup"><span data-stu-id="ef333-118">int</span></span></p></td>
<td><p><span data-ttu-id="ef333-119">Tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="ef333-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef333-120"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ef333-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ef333-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ef333-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ef333-122">Categoría a la que pertenece el cliente.</span><span class="sxs-lookup"><span data-stu-id="ef333-122">Category that the client belongs to.</span></span> <span data-ttu-id="ef333-123">Por ejemplo, el cliente Conferencing_Attendant_1.0 pertenece a la CAA de ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="ef333-123">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

