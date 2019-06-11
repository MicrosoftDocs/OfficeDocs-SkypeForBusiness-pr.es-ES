---
title: 'Lync Server 2013: Tabla Dialog'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d47744cf17d3459c16e382c3551b427aa45b5ce6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="856c6-102">Tabla Dialog en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="856c6-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="856c6-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="856c6-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="856c6-104">La tabla de diálogo es una tabla de soporte técnico; cada registro representa un cuadro de diálogo protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="856c6-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="856c6-105"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="856c6-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="856c6-106"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="856c6-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="856c6-107"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="856c6-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="856c6-108"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="856c6-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="856c6-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="856c6-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="856c6-110">datetime</span><span class="sxs-lookup"><span data-stu-id="856c6-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="856c6-111">Primary</span><span class="sxs-lookup"><span data-stu-id="856c6-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="856c6-112">Hora en que el agente de calidad de excelencia (QoE) recibe el primer informe de quien llama o de quien llama.</span><span class="sxs-lookup"><span data-stu-id="856c6-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="856c6-113">Se usa en conjunción con SessionSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="856c6-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856c6-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="856c6-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="856c6-115">int</span><span class="sxs-lookup"><span data-stu-id="856c6-115">int</span></span></p></td>
<td><p><span data-ttu-id="856c6-116">Primary</span><span class="sxs-lookup"><span data-stu-id="856c6-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="856c6-117">Número de secuencia para diferenciar las sesiones cuando tienen el mismo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="856c6-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856c6-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="856c6-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="856c6-119">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="856c6-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="856c6-120">IDENTIFICADOR de cuadro de diálogo único de forma global.</span><span class="sxs-lookup"><span data-stu-id="856c6-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856c6-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="856c6-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="856c6-122">int</span><span class="sxs-lookup"><span data-stu-id="856c6-122">int</span></span></p></td>
<td><p><span data-ttu-id="856c6-123">clasificación</span><span class="sxs-lookup"><span data-stu-id="856c6-123">index</span></span></p></td>
<td><p><span data-ttu-id="856c6-124">Suma de comprobación del identificador de cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="856c6-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

