---
title: 'Lync Server 2013: tblComplianceFanout'
description: 'Lync Server 2013: tblComplianceFanout.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cb94fff579c504598f027c8c68c7dde00a5a516
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568576"
---
# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="0bf78-103">tblComplianceFanout en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bf78-103">tblComplianceFanout in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bf78-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0bf78-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0bf78-105">La tabla ComplianceFanout contiene todos los servidores que han procesado un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="0bf78-105">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="0bf78-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="0bf78-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0bf78-107">Columna</span><span class="sxs-lookup"><span data-stu-id="0bf78-107">Column</span></span></th>
<th><span data-ttu-id="0bf78-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="0bf78-108">Type</span></span></th>
<th><span data-ttu-id="0bf78-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bf78-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0bf78-110">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="0bf78-110">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="0bf78-111">entero</span><span class="sxs-lookup"><span data-stu-id="0bf78-111">int</span></span></p></td>
<td><p><span data-ttu-id="0bf78-112">Id. del evento</span><span class="sxs-lookup"><span data-stu-id="0bf78-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bf78-113">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="0bf78-113">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="0bf78-114">entero</span><span class="sxs-lookup"><span data-stu-id="0bf78-114">int</span></span></p></td>
<td><p><span data-ttu-id="0bf78-115">Identidad del servidor (correspondiente a la tabla ServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="0bf78-115">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="0bf78-116">Key </span><span class="sxs-lookup"><span data-stu-id="0bf78-116">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0bf78-117">Columna</span><span class="sxs-lookup"><span data-stu-id="0bf78-117">Column</span></span></th>
<th><span data-ttu-id="0bf78-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bf78-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0bf78-119">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="0bf78-119">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="0bf78-120">Clave externa con búsqueda en la tabla ComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="0bf78-120">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

