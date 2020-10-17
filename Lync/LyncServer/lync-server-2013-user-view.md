---
title: 'Lync Server 2013: vista de usuario'
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
ms.openlocfilehash: f978b6acaa1cdfdf6abf2d768c1fb679af260a63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530157"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="c9f14-102">Vista de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9f14-102">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9f14-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c9f14-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c9f14-104">La vista de usuario almacena información sobre usuarios que han participado en llamadas o sesiones con registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c9f14-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="c9f14-105">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9f14-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9f14-106">Columna</span><span class="sxs-lookup"><span data-stu-id="c9f14-106">Column</span></span></th>
<th><span data-ttu-id="c9f14-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c9f14-107">Data Type</span></span></th>
<th><span data-ttu-id="c9f14-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="c9f14-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9f14-109">UserId</span><span class="sxs-lookup"><span data-stu-id="c9f14-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="c9f14-110">entero</span><span class="sxs-lookup"><span data-stu-id="c9f14-110">int</span></span></p></td>
<td><p><span data-ttu-id="c9f14-111">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="c9f14-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9f14-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="c9f14-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="c9f14-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c9f14-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c9f14-114">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="c9f14-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9f14-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="c9f14-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="c9f14-116">identificador</span><span class="sxs-lookup"><span data-stu-id="c9f14-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c9f14-117">Inquilino del usuario.</span><span class="sxs-lookup"><span data-stu-id="c9f14-117">Tenant of user.</span></span> <span data-ttu-id="c9f14-118">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c9f14-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9f14-119">UriType</span><span class="sxs-lookup"><span data-stu-id="c9f14-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="c9f14-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c9f14-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c9f14-121">Tipo de URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="c9f14-121">Type of user URI.</span></span> <span data-ttu-id="c9f14-122">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c9f14-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

