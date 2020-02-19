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
ms.openlocfilehash: a63150d567b893b4d1c4445d91544b4c83659bf4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="18a88-102">Vista de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18a88-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18a88-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="18a88-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="18a88-104">La vista de usuario almacena información sobre usuarios que han participado en llamadas o sesiones con registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="18a88-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="18a88-105">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18a88-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18a88-106">Columna</span><span class="sxs-lookup"><span data-stu-id="18a88-106">Column</span></span></th>
<th><span data-ttu-id="18a88-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="18a88-107">Data Type</span></span></th>
<th><span data-ttu-id="18a88-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="18a88-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18a88-109">UserId</span><span class="sxs-lookup"><span data-stu-id="18a88-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="18a88-110">int</span><span class="sxs-lookup"><span data-stu-id="18a88-110">int</span></span></p></td>
<td><p><span data-ttu-id="18a88-111">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="18a88-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18a88-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="18a88-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="18a88-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="18a88-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="18a88-114">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="18a88-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18a88-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="18a88-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="18a88-116">identificador</span><span class="sxs-lookup"><span data-stu-id="18a88-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="18a88-117">Inquilino del usuario.</span><span class="sxs-lookup"><span data-stu-id="18a88-117">Tenant of user.</span></span> <span data-ttu-id="18a88-118">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="18a88-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18a88-119">UriType</span><span class="sxs-lookup"><span data-stu-id="18a88-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="18a88-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="18a88-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="18a88-121">Tipo de URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="18a88-121">Type of user URI.</span></span> <span data-ttu-id="18a88-122">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="18a88-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

