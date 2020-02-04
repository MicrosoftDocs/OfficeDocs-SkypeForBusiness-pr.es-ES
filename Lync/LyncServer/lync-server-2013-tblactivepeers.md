---
title: 'Lync Server 2013: tblActivePeers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29d7c5c806e7540cc742781ce364748c47c10b39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="9216a-102">tblActivePeers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9216a-102">tblActivePeers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9216a-103">_**Última modificación del tema:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="9216a-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="9216a-104">tblActivePeers contiene las conexiones de punto a punto actuales entre los servicios de chat.</span><span class="sxs-lookup"><span data-stu-id="9216a-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="9216a-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="9216a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9216a-106">Columna</span><span class="sxs-lookup"><span data-stu-id="9216a-106">Column</span></span></th>
<th><span data-ttu-id="9216a-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="9216a-107">Type</span></span></th>
<th><span data-ttu-id="9216a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9216a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9216a-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="9216a-109">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="9216a-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="9216a-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9216a-111">IDENTIFICADOR del servidor que ha publicado la entrada.</span><span class="sxs-lookup"><span data-stu-id="9216a-111">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9216a-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="9216a-112">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="9216a-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="9216a-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9216a-114">IDENTIFICADOR del elemento del mismo nivel al que está conectado el servidor de publicación.</span><span class="sxs-lookup"><span data-stu-id="9216a-114">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9216a-115">Sus</span><span class="sxs-lookup"><span data-stu-id="9216a-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9216a-116">Columna</span><span class="sxs-lookup"><span data-stu-id="9216a-116">Column</span></span></th>
<th><span data-ttu-id="9216a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="9216a-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9216a-118">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="9216a-118">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="9216a-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="9216a-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9216a-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="9216a-120">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="9216a-121">Clave externa con la búsqueda en la tabla tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="9216a-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9216a-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="9216a-122">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="9216a-123">Clave externa con la búsqueda en la tabla tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="9216a-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

