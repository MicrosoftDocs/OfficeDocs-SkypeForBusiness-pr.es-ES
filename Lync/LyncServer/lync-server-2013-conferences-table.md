---
title: 'Lync Server 2013: tabla de conferencias'
description: 'Lync Server 2013: tabla de conferencias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e0d8c61e795dc0c8f9843b871d7e4efd1bec571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561606"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="4af12-103">Tabla conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4af12-103">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4af12-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4af12-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4af12-105">Cada registro de esta tabla contiene detalles de llamadas sobre una conferencia.</span><span class="sxs-lookup"><span data-stu-id="4af12-105">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4af12-106">Columna</span><span class="sxs-lookup"><span data-stu-id="4af12-106">Column</span></span></th>
<th><span data-ttu-id="4af12-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4af12-107">Data Type</span></span></th>
<th><span data-ttu-id="4af12-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="4af12-108">Key/Index</span></span></th>
<th><span data-ttu-id="4af12-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="4af12-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4af12-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4af12-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4af12-111">datetime</span><span class="sxs-lookup"><span data-stu-id="4af12-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="4af12-112">Principal</span><span class="sxs-lookup"><span data-stu-id="4af12-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4af12-113">Hora en que el agente CDR capturó la solicitud de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4af12-113">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="4af12-114">Solo se usa como clave principal para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4af12-114">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4af12-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4af12-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4af12-116">entero</span><span class="sxs-lookup"><span data-stu-id="4af12-116">int</span></span></p></td>
<td><p><span data-ttu-id="4af12-117">Principal</span><span class="sxs-lookup"><span data-stu-id="4af12-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="4af12-118">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="4af12-118">ID number to identify the session.</span></span> <span data-ttu-id="4af12-119">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4af12-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4af12-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="4af12-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="4af12-121">entero</span><span class="sxs-lookup"><span data-stu-id="4af12-121">int</span></span></p></td>
<td><p><span data-ttu-id="4af12-122">Externa</span><span class="sxs-lookup"><span data-stu-id="4af12-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4af12-123">URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4af12-123">Conference URI.</span></span> <span data-ttu-id="4af12-124">Consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4af12-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4af12-125"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="4af12-125"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="4af12-126">identificador</span><span class="sxs-lookup"><span data-stu-id="4af12-126">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4af12-127">Útil para las conferencias recurrentes; cada instancia de una conferencia periódica tiene la misma <strong>URI</strong>, pero tendrá un <strong>ConfInstance</strong>diferente.</span><span class="sxs-lookup"><span data-stu-id="4af12-127">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4af12-128"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="4af12-128"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4af12-129">datetime</span><span class="sxs-lookup"><span data-stu-id="4af12-129">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4af12-130">Hora de inicio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="4af12-130">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4af12-131"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="4af12-131"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4af12-132">datetime</span><span class="sxs-lookup"><span data-stu-id="4af12-132">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4af12-133">Hora de inicio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="4af12-133">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4af12-134"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="4af12-134"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="4af12-135">entero</span><span class="sxs-lookup"><span data-stu-id="4af12-135">int</span></span></p></td>
<td><p><span data-ttu-id="4af12-136">Externa</span><span class="sxs-lookup"><span data-stu-id="4af12-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4af12-137">Número de identificador para identificar el grupo de servidores en el que se capturó la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="4af12-137">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="4af12-138">Consulte la <a href="lync-server-2013-pools-table.md">tabla grupos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4af12-138">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4af12-139"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="4af12-139"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4af12-140">Int</span><span class="sxs-lookup"><span data-stu-id="4af12-140">Int</span></span></p></td>
<td><p><span data-ttu-id="4af12-141">Externa</span><span class="sxs-lookup"><span data-stu-id="4af12-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4af12-142">Número de identificador para identificar el URI del organizador de esta conferencia.</span><span class="sxs-lookup"><span data-stu-id="4af12-142">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="4af12-143">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4af12-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4af12-144"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="4af12-144"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4af12-145">smallint</span><span class="sxs-lookup"><span data-stu-id="4af12-145">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4af12-146">Máscara de bits que contiene los atributos de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="4af12-146">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="4af12-147">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="4af12-147">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="4af12-148">0X01</span><span class="sxs-lookup"><span data-stu-id="4af12-148">0X01</span></span></p></li>
<li><p><span data-ttu-id="4af12-149">Vitaminas</span><span class="sxs-lookup"><span data-stu-id="4af12-149">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="4af12-150">Transacción</span><span class="sxs-lookup"><span data-stu-id="4af12-150">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4af12-151"><strong>Procesan</strong></span><span class="sxs-lookup"><span data-stu-id="4af12-151"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="4af12-152">bit</span><span class="sxs-lookup"><span data-stu-id="4af12-152">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4af12-153">Campo interno usado por el servicio de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4af12-153">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="4af12-154">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4af12-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4af12-155">\* Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1.</span><span class="sxs-lookup"><span data-stu-id="4af12-155">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="4af12-156">Si dos sesiones comienzan exactamente al mismo tiempo, el SessionIdSeq para uno será 1, y el otro será 2, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="4af12-156">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

