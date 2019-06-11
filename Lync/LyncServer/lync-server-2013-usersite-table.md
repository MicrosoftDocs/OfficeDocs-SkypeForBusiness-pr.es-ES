---
title: 'Lync Server 2013: Tabla UserSite'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dfb3e3d99775405ce4a09df706bec8eea59f6f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="9f1df-102">Tabla UserSite en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f1df-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f1df-103">_**Última modificación del tema:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="9f1df-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="9f1df-104">La tabla UserSite es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="9f1df-104">The UserSite table is a supporting table.</span></span> <span data-ttu-id="9f1df-105">Cada registro representa un sitio de usuario definido en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="9f1df-105">Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f1df-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="9f1df-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9f1df-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="9f1df-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9f1df-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="9f1df-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9f1df-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="9f1df-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f1df-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="9f1df-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="9f1df-111">int</span><span class="sxs-lookup"><span data-stu-id="9f1df-111">int</span></span></p></td>
<td><p><span data-ttu-id="9f1df-112">Primary</span><span class="sxs-lookup"><span data-stu-id="9f1df-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9f1df-113">Número único que identifica el sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="9f1df-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f1df-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="9f1df-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="9f1df-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="9f1df-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="9f1df-116">Solo</span><span class="sxs-lookup"><span data-stu-id="9f1df-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="9f1df-117">Nombre del sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="9f1df-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f1df-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="9f1df-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="9f1df-119">int</span><span class="sxs-lookup"><span data-stu-id="9f1df-119">int</span></span></p></td>
<td><p><span data-ttu-id="9f1df-120">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9f1df-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9f1df-121">Tabla de la tabla a la que se hace referencia <a href="lync-server-2013-region-table.md">en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9f1df-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

