---
title: 'Lync Server 2013: tabla DeRegisterType'
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
ms.openlocfilehash: 8c9198d0551375803e0b83b2ce62d44b0d3a266c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="6adcf-102">Tabla DeRegisterType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6adcf-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6adcf-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6adcf-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6adcf-104">La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de anulación del registro de usuario, como ‘iniciado por cliente’, ‘registro expirado’ o ‘respuesta de cliente interrumpida’.</span><span class="sxs-lookup"><span data-stu-id="6adcf-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6adcf-105">Columna</span><span class="sxs-lookup"><span data-stu-id="6adcf-105">Column</span></span></th>
<th><span data-ttu-id="6adcf-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6adcf-106">Data Type</span></span></th>
<th><span data-ttu-id="6adcf-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="6adcf-107">Key/Index</span></span></th>
<th><span data-ttu-id="6adcf-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="6adcf-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6adcf-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="6adcf-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="6adcf-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="6adcf-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6adcf-111">Principal</span><span class="sxs-lookup"><span data-stu-id="6adcf-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6adcf-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="6adcf-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="6adcf-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6adcf-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6adcf-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="6adcf-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="6adcf-115">0 -- Desconocido</span><span class="sxs-lookup"><span data-stu-id="6adcf-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="6adcf-116">1 -- Anulación del registro iniciada por el cliente</span><span class="sxs-lookup"><span data-stu-id="6adcf-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="6adcf-117">2 -- Registro expirado</span><span class="sxs-lookup"><span data-stu-id="6adcf-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="6adcf-118">3 – Cliente bloqueado</span><span class="sxs-lookup"><span data-stu-id="6adcf-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="6adcf-119">4 -- Atributos de usuario modificados</span><span class="sxs-lookup"><span data-stu-id="6adcf-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="6adcf-120">5 – Registrador preferido modificado</span><span class="sxs-lookup"><span data-stu-id="6adcf-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="6adcf-121">6 -- Cliente heredado en modo de supervivencia</span><span class="sxs-lookup"><span data-stu-id="6adcf-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

