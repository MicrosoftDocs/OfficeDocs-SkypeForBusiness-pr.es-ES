---
title: 'Lync Server 2013: tblComplianceFanout'
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
ms.openlocfilehash: c535dc860c5d1a8725d27217e8269c3d6c4902d2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="a1576-102">tblComplianceFanout en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1576-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1576-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a1576-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a1576-104">La tabla ComplianceFanout contiene todos los servidores que han procesado un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a1576-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="a1576-105">Columns</span><span class="sxs-lookup"><span data-stu-id="a1576-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1576-106">Columna</span><span class="sxs-lookup"><span data-stu-id="a1576-106">Column</span></span></th>
<th><span data-ttu-id="a1576-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="a1576-107">Type</span></span></th>
<th><span data-ttu-id="a1576-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1576-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1576-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="a1576-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="a1576-110">int</span><span class="sxs-lookup"><span data-stu-id="a1576-110">int</span></span></p></td>
<td><p><span data-ttu-id="a1576-111">Id. del evento</span><span class="sxs-lookup"><span data-stu-id="a1576-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1576-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="a1576-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="a1576-113">int</span><span class="sxs-lookup"><span data-stu-id="a1576-113">int</span></span></p></td>
<td><p><span data-ttu-id="a1576-114">Identidad del servidor (correspondiente a la tabla ServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="a1576-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="a1576-115">Key </span><span class="sxs-lookup"><span data-stu-id="a1576-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1576-116">Columna</span><span class="sxs-lookup"><span data-stu-id="a1576-116">Column</span></span></th>
<th><span data-ttu-id="a1576-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1576-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1576-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="a1576-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="a1576-119">Clave externa con búsqueda en la tabla ComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="a1576-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

