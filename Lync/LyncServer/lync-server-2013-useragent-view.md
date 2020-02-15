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
ms.openlocfilehash: 7b82d8a03f159aa1c99d53dd06a0811847f77b12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="f6e29-102">Vista UserAgent en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6e29-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6e29-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f6e29-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f6e29-104">La vista UserAgent almacena información sobre los agentes de usuario que han participado en las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f6e29-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="f6e29-105">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6e29-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6e29-106">Columna</span><span class="sxs-lookup"><span data-stu-id="f6e29-106">Column</span></span></th>
<th><span data-ttu-id="f6e29-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f6e29-107">Data Type</span></span></th>
<th><span data-ttu-id="f6e29-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="f6e29-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6e29-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="f6e29-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="f6e29-110">int</span><span class="sxs-lookup"><span data-stu-id="f6e29-110">int</span></span></p></td>
<td><p><span data-ttu-id="f6e29-111">Número único que identifica a este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="f6e29-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6e29-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="f6e29-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="f6e29-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f6e29-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6e29-114">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="f6e29-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6e29-115">UAType</span><span class="sxs-lookup"><span data-stu-id="f6e29-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="f6e29-116">smallint</span><span class="sxs-lookup"><span data-stu-id="f6e29-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="f6e29-117">Tipo de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="f6e29-117">Type of user agent.</span></span> <span data-ttu-id="f6e29-118">Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f6e29-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6e29-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="f6e29-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="f6e29-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f6e29-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f6e29-p103">Categoría a la que pertenece el agente de usuario. Por ejemplo, el agente de usuario Conferencing_Attendant_1.0 pertenece a la UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="f6e29-p103">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

