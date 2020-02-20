---
title: 'Lync Server 2013: tblConfig'
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
ms.openlocfilehash: 04138ad8e11a423fdbd3fc0cc2329ce00f9ffb39
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="faab6-102">tblConfig en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faab6-102">tblConfig in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faab6-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="faab6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="faab6-104">tblConfig contiene una configuración no compatible con el servidor de chat persistente, en una fila.</span><span class="sxs-lookup"><span data-stu-id="faab6-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="faab6-105">Columns</span><span class="sxs-lookup"><span data-stu-id="faab6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="faab6-106">Columna</span><span class="sxs-lookup"><span data-stu-id="faab6-106">Column</span></span></th>
<th><span data-ttu-id="faab6-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="faab6-107">Type</span></span></th>
<th><span data-ttu-id="faab6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="faab6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="faab6-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="faab6-109">configLabel</span></span></p></td>
<td><p><span data-ttu-id="faab6-110">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="faab6-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="faab6-111">Contiene &quot;el grupo de servidores.&quot;</span><span class="sxs-lookup"><span data-stu-id="faab6-111">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faab6-112">configContent</span><span class="sxs-lookup"><span data-stu-id="faab6-112">configContent</span></span></p></td>
<td><p><span data-ttu-id="faab6-113">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="faab6-113">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="faab6-114">Contenido de la configuración.</span><span class="sxs-lookup"><span data-stu-id="faab6-114">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faab6-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="faab6-115">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="faab6-116">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="faab6-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="faab6-117">Identificador único de la instancia de base de datos.</span><span class="sxs-lookup"><span data-stu-id="faab6-117">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="faab6-118">Key </span><span class="sxs-lookup"><span data-stu-id="faab6-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="faab6-119">Columna</span><span class="sxs-lookup"><span data-stu-id="faab6-119">Column</span></span></th>
<th><span data-ttu-id="faab6-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="faab6-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="faab6-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="faab6-121">configLabel</span></span></p></td>
<td><p><span data-ttu-id="faab6-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="faab6-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

