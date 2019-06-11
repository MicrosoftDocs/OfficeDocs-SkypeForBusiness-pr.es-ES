---
title: 'Lync Server 2013: tblSiopWhiteList'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48183310
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fff11d98d35b288436922477025ea9cf49e924cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="c71b6-102">tblSiopWhiteList en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c71b6-102">tblSiopWhiteList in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c71b6-103">_**Última modificación del tema:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="c71b6-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="c71b6-104">tblSiopWhiteList es la lista de complementos registrados que se pueden asociar con nodos.</span><span class="sxs-lookup"><span data-stu-id="c71b6-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="c71b6-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="c71b6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c71b6-106">Columna</span><span class="sxs-lookup"><span data-stu-id="c71b6-106">Column</span></span></th>
<th><span data-ttu-id="c71b6-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="c71b6-107">Type</span></span></th>
<th><span data-ttu-id="c71b6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c71b6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c71b6-109">siopID</span><span class="sxs-lookup"><span data-stu-id="c71b6-109">siopID</span></span></p></td>
<td><p><span data-ttu-id="c71b6-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="c71b6-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="c71b6-111">GUID del complemento.</span><span class="sxs-lookup"><span data-stu-id="c71b6-111">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c71b6-112">siopName</span><span class="sxs-lookup"><span data-stu-id="c71b6-112">siopName</span></span></p></td>
<td><p><span data-ttu-id="c71b6-113">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="c71b6-113">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="c71b6-114">Display: nombre del complemento.</span><span class="sxs-lookup"><span data-stu-id="c71b6-114">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c71b6-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="c71b6-115">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="c71b6-116">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="c71b6-116">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="c71b6-117">Dirección URL del complemento.</span><span class="sxs-lookup"><span data-stu-id="c71b6-117">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="c71b6-118">Clave</span><span class="sxs-lookup"><span data-stu-id="c71b6-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c71b6-119">Columna</span><span class="sxs-lookup"><span data-stu-id="c71b6-119">Column</span></span></th>
<th><span data-ttu-id="c71b6-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c71b6-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c71b6-121">siopID</span><span class="sxs-lookup"><span data-stu-id="c71b6-121">siopID</span></span></p></td>
<td><p><span data-ttu-id="c71b6-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="c71b6-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

