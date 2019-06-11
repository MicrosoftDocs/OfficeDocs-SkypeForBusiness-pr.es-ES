---
title: 'Lync Server 2013: Tabla DeRegisterType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97d25ded1a281df0774644cd0d69f5e12d9c85a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="602fa-102">Tabla DeRegisterType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="602fa-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="602fa-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="602fa-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="602fa-104">La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de registros de usuario, como ' cliente iniciado ', ' registro expirado ' o ' cliente ha dejado de responder '.</span><span class="sxs-lookup"><span data-stu-id="602fa-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="602fa-105">Columna</span><span class="sxs-lookup"><span data-stu-id="602fa-105">Column</span></span></th>
<th><span data-ttu-id="602fa-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="602fa-106">Data Type</span></span></th>
<th><span data-ttu-id="602fa-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="602fa-107">Key/Index</span></span></th>
<th><span data-ttu-id="602fa-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="602fa-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="602fa-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="602fa-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="602fa-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="602fa-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="602fa-111">Primary</span><span class="sxs-lookup"><span data-stu-id="602fa-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="602fa-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="602fa-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="602fa-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="602fa-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="602fa-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="602fa-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="602fa-115">0--desconocido</span><span class="sxs-lookup"><span data-stu-id="602fa-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="602fa-116">1: deregistro Iniciado por el cliente</span><span class="sxs-lookup"><span data-stu-id="602fa-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="602fa-117">2--registro expirado</span><span class="sxs-lookup"><span data-stu-id="602fa-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="602fa-118">3: cliente bloqueado</span><span class="sxs-lookup"><span data-stu-id="602fa-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="602fa-119">4: atributos de usuario modificados</span><span class="sxs-lookup"><span data-stu-id="602fa-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="602fa-120">5: se cambió la entidad de registro preferida</span><span class="sxs-lookup"><span data-stu-id="602fa-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="602fa-121">6--cliente heredado en modo de supervivencia</span><span class="sxs-lookup"><span data-stu-id="602fa-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

