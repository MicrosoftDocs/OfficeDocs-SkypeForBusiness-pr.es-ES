---
title: 'Lync Server 2013: vista de usuario'
description: 'Lync Server 2013: vista de usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa606887e8050a51f1e5a87656bb74a7cd58bbc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558916"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="1392c-103">Vista de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1392c-103">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1392c-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1392c-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1392c-105">La vista de usuario almacena información sobre usuarios que han participado en llamadas o sesiones con registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1392c-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="1392c-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1392c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1392c-107">Columna</span><span class="sxs-lookup"><span data-stu-id="1392c-107">Column</span></span></th>
<th><span data-ttu-id="1392c-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1392c-108">Data Type</span></span></th>
<th><span data-ttu-id="1392c-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="1392c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1392c-110">UserId</span><span class="sxs-lookup"><span data-stu-id="1392c-110">UserId</span></span></p></td>
<td><p><span data-ttu-id="1392c-111">entero</span><span class="sxs-lookup"><span data-stu-id="1392c-111">int</span></span></p></td>
<td><p><span data-ttu-id="1392c-112">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="1392c-112">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1392c-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="1392c-113">UserUri</span></span></p></td>
<td><p><span data-ttu-id="1392c-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1392c-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1392c-115">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="1392c-115">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1392c-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="1392c-116">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="1392c-117">identificador</span><span class="sxs-lookup"><span data-stu-id="1392c-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1392c-118">Inquilino del usuario.</span><span class="sxs-lookup"><span data-stu-id="1392c-118">Tenant of user.</span></span> <span data-ttu-id="1392c-119">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1392c-119">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1392c-120">UriType</span><span class="sxs-lookup"><span data-stu-id="1392c-120">UriType</span></span></p></td>
<td><p><span data-ttu-id="1392c-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1392c-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1392c-122">Tipo de URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="1392c-122">Type of user URI.</span></span> <span data-ttu-id="1392c-123">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1392c-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

