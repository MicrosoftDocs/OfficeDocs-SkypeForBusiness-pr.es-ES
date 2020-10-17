---
title: 'Lync Server 2013: tblConfig'
description: 'Lync Server 2013: tblConfig.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8990e0b2c8724a5e90c36e706b92f9985f288772
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550436"
---
# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="0508f-103">tblConfig en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0508f-103">tblConfig in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0508f-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0508f-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0508f-105">tblConfig contiene una configuración no compatible con el servidor de chat persistente, en una fila.</span><span class="sxs-lookup"><span data-stu-id="0508f-105">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="0508f-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="0508f-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0508f-107">Columna</span><span class="sxs-lookup"><span data-stu-id="0508f-107">Column</span></span></th>
<th><span data-ttu-id="0508f-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="0508f-108">Type</span></span></th>
<th><span data-ttu-id="0508f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0508f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0508f-110">configLabel</span><span class="sxs-lookup"><span data-stu-id="0508f-110">configLabel</span></span></p></td>
<td><p><span data-ttu-id="0508f-111">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="0508f-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="0508f-112">Contiene el grupo de servidores &quot; .&quot;</span><span class="sxs-lookup"><span data-stu-id="0508f-112">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0508f-113">configContent</span><span class="sxs-lookup"><span data-stu-id="0508f-113">configContent</span></span></p></td>
<td><p><span data-ttu-id="0508f-114">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="0508f-114">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="0508f-115">Contenido de la configuración.</span><span class="sxs-lookup"><span data-stu-id="0508f-115">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0508f-116">configPoolID</span><span class="sxs-lookup"><span data-stu-id="0508f-116">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="0508f-117">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="0508f-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="0508f-118">Identificador único de la instancia de base de datos.</span><span class="sxs-lookup"><span data-stu-id="0508f-118">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="0508f-119">Key </span><span class="sxs-lookup"><span data-stu-id="0508f-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0508f-120">Columna</span><span class="sxs-lookup"><span data-stu-id="0508f-120">Column</span></span></th>
<th><span data-ttu-id="0508f-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="0508f-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0508f-122">configLabel</span><span class="sxs-lookup"><span data-stu-id="0508f-122">configLabel</span></span></p></td>
<td><p><span data-ttu-id="0508f-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="0508f-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

