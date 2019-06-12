---
title: 'Lync Server 2013: tblConfig'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745b8a1894ebca821474afdb82284fcf6bb09eb9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="37fb1-102">tblConfig en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37fb1-102">tblConfig in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37fb1-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="37fb1-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="37fb1-104">tblConfig contiene la configuración no admitida de un servidor de chat persistente, en una fila.</span><span class="sxs-lookup"><span data-stu-id="37fb1-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="37fb1-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="37fb1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37fb1-106">Columna</span><span class="sxs-lookup"><span data-stu-id="37fb1-106">Column</span></span></th>
<th><span data-ttu-id="37fb1-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="37fb1-107">Type</span></span></th>
<th><span data-ttu-id="37fb1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="37fb1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37fb1-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="37fb1-109">configLabel</span></span></p></td>
<td><p><span data-ttu-id="37fb1-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="37fb1-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="37fb1-111">Contiene &quot;el grupo.&quot;</span><span class="sxs-lookup"><span data-stu-id="37fb1-111">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37fb1-112">configContent</span><span class="sxs-lookup"><span data-stu-id="37fb1-112">configContent</span></span></p></td>
<td><p><span data-ttu-id="37fb1-113">nvarchar (Max)</span><span class="sxs-lookup"><span data-stu-id="37fb1-113">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="37fb1-114">Contenido de configuración.</span><span class="sxs-lookup"><span data-stu-id="37fb1-114">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37fb1-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="37fb1-115">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="37fb1-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="37fb1-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="37fb1-117">IDENTIFICADOR único de la instancia de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="37fb1-117">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="37fb1-118">Clave</span><span class="sxs-lookup"><span data-stu-id="37fb1-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37fb1-119">Columna</span><span class="sxs-lookup"><span data-stu-id="37fb1-119">Column</span></span></th>
<th><span data-ttu-id="37fb1-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="37fb1-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37fb1-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="37fb1-121">configLabel</span></span></p></td>
<td><p><span data-ttu-id="37fb1-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="37fb1-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

