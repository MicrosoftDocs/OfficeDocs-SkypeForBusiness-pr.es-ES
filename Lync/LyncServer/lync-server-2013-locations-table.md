---
title: 'Lync Server 2013: tabla de ubicaciones'
description: 'Lync Server 2013: tabla de ubicaciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d07b6d3d3820f4efb3310adf0734a7e10c53e6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570586"
---
# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="a5199-103">Tabla Locations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5199-103">Locations table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5199-104">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="a5199-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="a5199-105">Cada registro representa una referencia de ubicación en una llamada de emergencia, como una llamada de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="a5199-105">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5199-106">Columna</span><span class="sxs-lookup"><span data-stu-id="a5199-106">Column</span></span></th>
<th><span data-ttu-id="a5199-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a5199-107">Data Type</span></span></th>
<th><span data-ttu-id="a5199-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="a5199-108">Key/Index</span></span></th>
<th><span data-ttu-id="a5199-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="a5199-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5199-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a5199-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a5199-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a5199-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a5199-112">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="a5199-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5199-113">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="a5199-113">Time of session request.</span></span> <span data-ttu-id="a5199-114">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="a5199-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a5199-115">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a5199-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5199-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a5199-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a5199-117">entero</span><span class="sxs-lookup"><span data-stu-id="a5199-117">int</span></span></p></td>
<td><p><span data-ttu-id="a5199-118">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="a5199-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5199-119">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="a5199-119">ID number to identify the session.</span></span> <span data-ttu-id="a5199-120">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="a5199-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a5199-121">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a5199-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5199-122"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="a5199-122"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="a5199-123">nvarchar (Max)</span><span class="sxs-lookup"><span data-stu-id="a5199-123">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5199-124">Ubicación de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="a5199-124">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

