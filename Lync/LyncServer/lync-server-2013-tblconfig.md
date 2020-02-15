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
ms.openlocfilehash: 399d4e794b45f549aed86838463091db437b286f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="35ec1-102">tblConfig en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35ec1-102">tblConfig in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35ec1-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="35ec1-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="35ec1-104">tblConfig contiene una configuración no compatible con el servidor de chat persistente, en una fila.</span><span class="sxs-lookup"><span data-stu-id="35ec1-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="35ec1-105">Columns</span><span class="sxs-lookup"><span data-stu-id="35ec1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35ec1-106">Columna</span><span class="sxs-lookup"><span data-stu-id="35ec1-106">Column</span></span></th>
<th><span data-ttu-id="35ec1-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="35ec1-107">Type</span></span></th>
<th><span data-ttu-id="35ec1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="35ec1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35ec1-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="35ec1-109">configLabel</span></span></p></td>
<td><p><span data-ttu-id="35ec1-110">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="35ec1-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="35ec1-111">Contiene &quot;el grupo de servidores.&quot;</span><span class="sxs-lookup"><span data-stu-id="35ec1-111">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35ec1-112">configContent</span><span class="sxs-lookup"><span data-stu-id="35ec1-112">configContent</span></span></p></td>
<td><p><span data-ttu-id="35ec1-113">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="35ec1-113">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="35ec1-114">Contenido de la configuración.</span><span class="sxs-lookup"><span data-stu-id="35ec1-114">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35ec1-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="35ec1-115">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="35ec1-116">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="35ec1-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="35ec1-117">Identificador único de la instancia de base de datos.</span><span class="sxs-lookup"><span data-stu-id="35ec1-117">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="35ec1-118">Key </span><span class="sxs-lookup"><span data-stu-id="35ec1-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35ec1-119">Columna</span><span class="sxs-lookup"><span data-stu-id="35ec1-119">Column</span></span></th>
<th><span data-ttu-id="35ec1-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="35ec1-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35ec1-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="35ec1-121">configLabel</span></span></p></td>
<td><p><span data-ttu-id="35ec1-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="35ec1-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

