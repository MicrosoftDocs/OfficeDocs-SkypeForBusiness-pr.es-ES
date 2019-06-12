---
title: 'Lync Server 2013: tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddc89952b544a71c469538cf11f65658e19e38d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="93f8c-102">tblLastChatId en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93f8c-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93f8c-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="93f8c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="93f8c-104">tblLastChatId contiene el último identificador de chat generado (y usado en la tabla tblChat) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="93f8c-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="93f8c-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="93f8c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93f8c-106">Columna</span><span class="sxs-lookup"><span data-stu-id="93f8c-106">Column</span></span></th>
<th><span data-ttu-id="93f8c-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="93f8c-107">Type</span></span></th>
<th><span data-ttu-id="93f8c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="93f8c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93f8c-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="93f8c-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="93f8c-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="93f8c-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="93f8c-111">IDENTIFICADOR de nodo (solo tipo salón de chat).</span><span class="sxs-lookup"><span data-stu-id="93f8c-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93f8c-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="93f8c-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="93f8c-113">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="93f8c-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="93f8c-114">Último ID de chat usado.</span><span class="sxs-lookup"><span data-stu-id="93f8c-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="93f8c-115">Sus</span><span class="sxs-lookup"><span data-stu-id="93f8c-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93f8c-116">Columna</span><span class="sxs-lookup"><span data-stu-id="93f8c-116">Column</span></span></th>
<th><span data-ttu-id="93f8c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="93f8c-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93f8c-118">&lt;nodeID, lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="93f8c-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="93f8c-119">Clave principal (solo nodeID es suficiente para procesar).</span><span class="sxs-lookup"><span data-stu-id="93f8c-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93f8c-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="93f8c-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="93f8c-121">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="93f8c-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="93f8c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="93f8c-122">See Also</span></span>


[<span data-ttu-id="93f8c-123">tblChat en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93f8c-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

