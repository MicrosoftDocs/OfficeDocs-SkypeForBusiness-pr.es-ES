---
title: 'Lync Server 2013: Tabla DeRegisterType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65c94513a3578f8608da555cdd0b3e2273b8a7da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="7e193-102">Tabla DeRegisterType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e193-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e193-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7e193-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7e193-104">La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de registros de usuario, como ' cliente iniciado ', ' registro expirado ' o ' cliente ha dejado de responder '.</span><span class="sxs-lookup"><span data-stu-id="7e193-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e193-105">Columna</span><span class="sxs-lookup"><span data-stu-id="7e193-105">Column</span></span></th>
<th><span data-ttu-id="7e193-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7e193-106">Data Type</span></span></th>
<th><span data-ttu-id="7e193-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="7e193-107">Key/Index</span></span></th>
<th><span data-ttu-id="7e193-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="7e193-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e193-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="7e193-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e193-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="7e193-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7e193-111">Primary</span><span class="sxs-lookup"><span data-stu-id="7e193-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e193-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="7e193-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="7e193-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e193-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7e193-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="7e193-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="7e193-115">0--desconocido</span><span class="sxs-lookup"><span data-stu-id="7e193-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="7e193-116">1: deregistro Iniciado por el cliente</span><span class="sxs-lookup"><span data-stu-id="7e193-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="7e193-117">2--registro expirado</span><span class="sxs-lookup"><span data-stu-id="7e193-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="7e193-118">3: cliente bloqueado</span><span class="sxs-lookup"><span data-stu-id="7e193-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="7e193-119">4: atributos de usuario modificados</span><span class="sxs-lookup"><span data-stu-id="7e193-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="7e193-120">5: se cambió la entidad de registro preferida</span><span class="sxs-lookup"><span data-stu-id="7e193-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="7e193-121">6--cliente heredado en modo de supervivencia</span><span class="sxs-lookup"><span data-stu-id="7e193-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

