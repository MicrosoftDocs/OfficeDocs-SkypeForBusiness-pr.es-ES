---
title: 'Lync Server 2013: vista de ClientVersions'
description: 'Lync Server 2013: vista de ClientVersions.'
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
ms.openlocfilehash: 42ede7107a59db3162ac7f5344e47e81a80d57df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542806"
---
# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="41aa2-103">Vista ClientVersions en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41aa2-103">ClientVersions view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41aa2-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="41aa2-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="41aa2-105">La vista ClientVersions almacena información sobre los diversos tipos de clientes y versiones que han participado en las sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="41aa2-105">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="41aa2-106">Cada registro de la vista representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="41aa2-106">Each record in the view represents one client version.</span></span> <span data-ttu-id="41aa2-107">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41aa2-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41aa2-108">Puede haber varios registros para determinadas columnas.</span><span class="sxs-lookup"><span data-stu-id="41aa2-108">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41aa2-109">Columna</span><span class="sxs-lookup"><span data-stu-id="41aa2-109">Column</span></span></th>
<th><span data-ttu-id="41aa2-110">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="41aa2-110">Data Type</span></span></th>
<th><span data-ttu-id="41aa2-111">Detalles</span><span class="sxs-lookup"><span data-stu-id="41aa2-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41aa2-112"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="41aa2-112"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="41aa2-113">entero</span><span class="sxs-lookup"><span data-stu-id="41aa2-113">int</span></span></p></td>
<td><p><span data-ttu-id="41aa2-114">Número único de identificación de esta versión y este tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="41aa2-114">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41aa2-115"><strong>Versión</strong></span><span class="sxs-lookup"><span data-stu-id="41aa2-115"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="41aa2-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="41aa2-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="41aa2-117">Representa el agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="41aa2-117">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41aa2-118"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="41aa2-118"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="41aa2-119">entero</span><span class="sxs-lookup"><span data-stu-id="41aa2-119">int</span></span></p></td>
<td><p><span data-ttu-id="41aa2-120">Tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="41aa2-120">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41aa2-121"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="41aa2-121"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="41aa2-122">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="41aa2-122">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="41aa2-p102">Categoría a la que pertenece el cliente. Por ejemplo, el cliente Conferencing_Attendant_1.0 pertenece a ClientCategory CAA.</span><span class="sxs-lookup"><span data-stu-id="41aa2-p102">Category that the client belongs to. For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

