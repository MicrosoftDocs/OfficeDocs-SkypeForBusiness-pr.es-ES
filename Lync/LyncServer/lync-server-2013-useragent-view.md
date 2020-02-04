---
title: 'Lync Server 2013: vista UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 828e81d028fb476362a91c4fa0ab83c5e2c34c20
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="14d8a-102">Vista UserAgent en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14d8a-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14d8a-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="14d8a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="14d8a-104">La vista UserAgent almacena información sobre los agentes de usuario implicados en las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="14d8a-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="14d8a-105">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14d8a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14d8a-106">Columna</span><span class="sxs-lookup"><span data-stu-id="14d8a-106">Column</span></span></th>
<th><span data-ttu-id="14d8a-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="14d8a-107">Data Type</span></span></th>
<th><span data-ttu-id="14d8a-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="14d8a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14d8a-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="14d8a-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="14d8a-110">int</span><span class="sxs-lookup"><span data-stu-id="14d8a-110">int</span></span></p></td>
<td><p><span data-ttu-id="14d8a-111">Número único que identifica a este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="14d8a-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d8a-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="14d8a-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="14d8a-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="14d8a-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14d8a-114">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="14d8a-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d8a-115">UAType</span><span class="sxs-lookup"><span data-stu-id="14d8a-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="14d8a-116">smallint</span><span class="sxs-lookup"><span data-stu-id="14d8a-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="14d8a-117">Tipo de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="14d8a-117">Type of user agent.</span></span> <span data-ttu-id="14d8a-118">Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="14d8a-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d8a-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="14d8a-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="14d8a-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="14d8a-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="14d8a-121">Categoría a la que pertenece el agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="14d8a-121">Category that the user agent belongs to.</span></span> <span data-ttu-id="14d8a-122">Por ejemplo, el agente de usuario Conferencing_Attendant_1,0 pertenece a la CAA de UACategory.</span><span class="sxs-lookup"><span data-stu-id="14d8a-122">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

