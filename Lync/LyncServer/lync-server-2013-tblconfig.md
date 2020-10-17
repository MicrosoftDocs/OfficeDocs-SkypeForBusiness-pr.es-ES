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
ms.openlocfilehash: 2efbed57d88e7312bc1da3a9da8f8057fd6696a5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509377"
---
# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="16e8e-102">tblConfig en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16e8e-102">tblConfig in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16e8e-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="16e8e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="16e8e-104">tblConfig contiene una configuración no compatible con el servidor de chat persistente, en una fila.</span><span class="sxs-lookup"><span data-stu-id="16e8e-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="16e8e-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="16e8e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16e8e-106">Columna</span><span class="sxs-lookup"><span data-stu-id="16e8e-106">Column</span></span></th>
<th><span data-ttu-id="16e8e-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="16e8e-107">Type</span></span></th>
<th><span data-ttu-id="16e8e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="16e8e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16e8e-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="16e8e-109">configLabel</span></span></p></td>
<td><p><span data-ttu-id="16e8e-110">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="16e8e-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="16e8e-111">Contiene el grupo de servidores &quot; .&quot;</span><span class="sxs-lookup"><span data-stu-id="16e8e-111">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16e8e-112">configContent</span><span class="sxs-lookup"><span data-stu-id="16e8e-112">configContent</span></span></p></td>
<td><p><span data-ttu-id="16e8e-113">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="16e8e-113">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="16e8e-114">Contenido de la configuración.</span><span class="sxs-lookup"><span data-stu-id="16e8e-114">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16e8e-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="16e8e-115">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="16e8e-116">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="16e8e-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="16e8e-117">Identificador único de la instancia de base de datos.</span><span class="sxs-lookup"><span data-stu-id="16e8e-117">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="16e8e-118">Key </span><span class="sxs-lookup"><span data-stu-id="16e8e-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16e8e-119">Columna</span><span class="sxs-lookup"><span data-stu-id="16e8e-119">Column</span></span></th>
<th><span data-ttu-id="16e8e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="16e8e-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16e8e-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="16e8e-121">configLabel</span></span></p></td>
<td><p><span data-ttu-id="16e8e-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="16e8e-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

