---
title: 'Lync Server 2013: tabla de cuadros de diálogo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 578b27a61e6af7114da19eb0d6d21dea38dba551
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="fcc02-102">Tabla de cuadro de diálogo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcc02-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcc02-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fcc02-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fcc02-104">La tabla Diálogo es una tabla de apoyo, en la que cada registro representa un cuadro de diálogo de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="fcc02-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcc02-105"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="fcc02-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fcc02-106"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="fcc02-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fcc02-107"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="fcc02-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fcc02-108"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="fcc02-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcc02-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="fcc02-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fcc02-110">datetime</span><span class="sxs-lookup"><span data-stu-id="fcc02-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="fcc02-111">Principal</span><span class="sxs-lookup"><span data-stu-id="fcc02-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="fcc02-p101">Momento en el que el agente de calidad de la experiencia (QoE) recibe el primer informe del autor o del destinatario de la llamada. Se usa junto con SessionSeq para identificar una sesión de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="fcc02-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc02-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fcc02-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fcc02-115">int</span><span class="sxs-lookup"><span data-stu-id="fcc02-115">int</span></span></p></td>
<td><p><span data-ttu-id="fcc02-116">Principal</span><span class="sxs-lookup"><span data-stu-id="fcc02-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="fcc02-117">Número de secuencia que se usa para diferenciar sesiones cuando tienen el mismo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="fcc02-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc02-118"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="fcc02-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="fcc02-119">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="fcc02-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fcc02-120">Id. de diálogo, exclusivo a nivel global.</span><span class="sxs-lookup"><span data-stu-id="fcc02-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc02-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="fcc02-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="fcc02-122">int</span><span class="sxs-lookup"><span data-stu-id="fcc02-122">int</span></span></p></td>
<td><p><span data-ttu-id="fcc02-123">index</span><span class="sxs-lookup"><span data-stu-id="fcc02-123">index</span></span></p></td>
<td><p><span data-ttu-id="fcc02-124">Suma de comprobación del Id. de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fcc02-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

