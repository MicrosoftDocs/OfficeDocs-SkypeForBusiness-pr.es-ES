---
title: 'Lync Server 2013: tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1def19b45f09a81c1bd5a1504151bfb919f6c4f7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="71d11-102">tblLastChatId en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71d11-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71d11-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="71d11-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="71d11-104">tblLastChatId contiene el último id. de chat generado (y usado en la tabla tblChat) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="71d11-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="71d11-105">Columns</span><span class="sxs-lookup"><span data-stu-id="71d11-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71d11-106">Columna</span><span class="sxs-lookup"><span data-stu-id="71d11-106">Column</span></span></th>
<th><span data-ttu-id="71d11-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="71d11-107">Type</span></span></th>
<th><span data-ttu-id="71d11-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="71d11-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71d11-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="71d11-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="71d11-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="71d11-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="71d11-111">Identificador de nodo (tipo de salón de chat únicamente).</span><span class="sxs-lookup"><span data-stu-id="71d11-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71d11-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="71d11-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="71d11-113">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="71d11-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="71d11-114">Identificador de chat usado por última vez.</span><span class="sxs-lookup"><span data-stu-id="71d11-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="71d11-115">Keys</span><span class="sxs-lookup"><span data-stu-id="71d11-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71d11-116">Columna</span><span class="sxs-lookup"><span data-stu-id="71d11-116">Column</span></span></th>
<th><span data-ttu-id="71d11-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="71d11-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71d11-118">&lt;nodeID, lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="71d11-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="71d11-119">Clave principal (nodeID es suficiente para el procesamiento).</span><span class="sxs-lookup"><span data-stu-id="71d11-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71d11-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="71d11-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="71d11-121">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="71d11-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="71d11-122">Consulta también</span><span class="sxs-lookup"><span data-stu-id="71d11-122">See Also</span></span>


[<span data-ttu-id="71d11-123">tblChat en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71d11-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

