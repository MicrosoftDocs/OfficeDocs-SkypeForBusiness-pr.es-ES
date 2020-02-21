---
title: 'Lync Server 2013: tabla de conferencias'
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
ms.openlocfilehash: d3dbaf1a721433cc04aa681dad56d753de8bc9a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="1b243-102">Tabla conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b243-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b243-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1b243-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1b243-104">Cada registro de esta tabla contiene detalles de llamadas sobre una conferencia.</span><span class="sxs-lookup"><span data-stu-id="1b243-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b243-105">Columna</span><span class="sxs-lookup"><span data-stu-id="1b243-105">Column</span></span></th>
<th><span data-ttu-id="1b243-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1b243-106">Data Type</span></span></th>
<th><span data-ttu-id="1b243-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="1b243-107">Key/Index</span></span></th>
<th><span data-ttu-id="1b243-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="1b243-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b243-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1b243-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1b243-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1b243-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1b243-111">Principal</span><span class="sxs-lookup"><span data-stu-id="1b243-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="1b243-112">Hora en que el agente CDR capturó la solicitud de conferencia.</span><span class="sxs-lookup"><span data-stu-id="1b243-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="1b243-113">Solo se usa como clave principal para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="1b243-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b243-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1b243-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1b243-115">int</span><span class="sxs-lookup"><span data-stu-id="1b243-115">int</span></span></p></td>
<td><p><span data-ttu-id="1b243-116">Principal</span><span class="sxs-lookup"><span data-stu-id="1b243-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="1b243-117">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="1b243-117">ID number to identify the session.</span></span> <span data-ttu-id="1b243-118">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="1b243-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b243-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="1b243-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b243-120">int</span><span class="sxs-lookup"><span data-stu-id="1b243-120">int</span></span></p></td>
<td><p><span data-ttu-id="1b243-121">Externa</span><span class="sxs-lookup"><span data-stu-id="1b243-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b243-122">URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="1b243-122">Conference URI.</span></span> <span data-ttu-id="1b243-123">Consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1b243-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b243-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="1b243-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="1b243-125">identificador</span><span class="sxs-lookup"><span data-stu-id="1b243-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1b243-126">Útil para las conferencias recurrentes; cada instancia de una conferencia periódica tiene la misma <strong>URI</strong>, pero tendrá un <strong>ConfInstance</strong>diferente.</span><span class="sxs-lookup"><span data-stu-id="1b243-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b243-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="1b243-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1b243-128">datetime</span><span class="sxs-lookup"><span data-stu-id="1b243-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1b243-129">Hora de inicio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="1b243-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b243-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="1b243-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1b243-131">datetime</span><span class="sxs-lookup"><span data-stu-id="1b243-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1b243-132">Hora de inicio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="1b243-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b243-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="1b243-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b243-134">int</span><span class="sxs-lookup"><span data-stu-id="1b243-134">int</span></span></p></td>
<td><p><span data-ttu-id="1b243-135">Externa</span><span class="sxs-lookup"><span data-stu-id="1b243-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b243-136">Número de identificador para identificar el grupo de servidores en el que se capturó la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="1b243-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="1b243-137">Consulte la <a href="lync-server-2013-pools-table.md">tabla grupos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1b243-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b243-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="1b243-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b243-139">Int</span><span class="sxs-lookup"><span data-stu-id="1b243-139">Int</span></span></p></td>
<td><p><span data-ttu-id="1b243-140">Externa</span><span class="sxs-lookup"><span data-stu-id="1b243-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b243-141">Número de identificador para identificar el URI del organizador de esta conferencia.</span><span class="sxs-lookup"><span data-stu-id="1b243-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="1b243-142">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1b243-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b243-143"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="1b243-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="1b243-144">smallint</span><span class="sxs-lookup"><span data-stu-id="1b243-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b243-145">Máscara de bits que contiene los atributos de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="1b243-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="1b243-146">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="1b243-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b243-147">0X01</span><span class="sxs-lookup"><span data-stu-id="1b243-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="1b243-148">Vitaminas</span><span class="sxs-lookup"><span data-stu-id="1b243-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="1b243-149">Transacción</span><span class="sxs-lookup"><span data-stu-id="1b243-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b243-150"><strong>Procesan</strong></span><span class="sxs-lookup"><span data-stu-id="1b243-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="1b243-151">bit</span><span class="sxs-lookup"><span data-stu-id="1b243-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b243-152">Campo interno usado por el servicio de supervisión.</span><span class="sxs-lookup"><span data-stu-id="1b243-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="1b243-153">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b243-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1b243-154">\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1.</span><span class="sxs-lookup"><span data-stu-id="1b243-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="1b243-155">Si dos sesiones comienzan exactamente al mismo tiempo, el SessionIdSeq para uno será 1, y el otro será 2, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="1b243-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

