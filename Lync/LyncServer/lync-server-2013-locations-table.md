---
title: 'Lync Server 2013: Tabla Locations'
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
ms.openlocfilehash: e2d16ffd08184a650f993d175239f5aff72b8b3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="d705c-102">Tabla Locations en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d705c-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d705c-103">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="d705c-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="d705c-104">Cada registro representa una referencia de una ubicación en una llamada de emergencia, como una llamada de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d705c-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d705c-105">Columna</span><span class="sxs-lookup"><span data-stu-id="d705c-105">Column</span></span></th>
<th><span data-ttu-id="d705c-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d705c-106">Data Type</span></span></th>
<th><span data-ttu-id="d705c-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="d705c-107">Key/Index</span></span></th>
<th><span data-ttu-id="d705c-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="d705c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d705c-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d705c-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d705c-110">datetime</span><span class="sxs-lookup"><span data-stu-id="d705c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="d705c-111">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d705c-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d705c-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="d705c-112">Time of session request.</span></span> <span data-ttu-id="d705c-113">Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="d705c-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d705c-114">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d705c-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d705c-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d705c-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d705c-116">int</span><span class="sxs-lookup"><span data-stu-id="d705c-116">int</span></span></p></td>
<td><p><span data-ttu-id="d705c-117">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d705c-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d705c-118">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="d705c-118">ID number to identify the session.</span></span> <span data-ttu-id="d705c-119">Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="d705c-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d705c-120">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d705c-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d705c-121"><strong>Ubicación</strong></span><span class="sxs-lookup"><span data-stu-id="d705c-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="d705c-122">nvarchar (Max)</span><span class="sxs-lookup"><span data-stu-id="d705c-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d705c-123">Ubicación de la llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="d705c-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

