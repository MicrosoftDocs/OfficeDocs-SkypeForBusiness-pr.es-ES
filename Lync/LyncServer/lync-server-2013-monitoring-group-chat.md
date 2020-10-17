---
title: 'Lync Server 2013: supervisión del chat en grupo'
description: 'Lync Server 2013: supervisión del chat en grupo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625e45f455e8dba50a5fa64240b62cb010623d16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562036"
---
# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="5a949-103">Supervisión del chat en grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a949-103">Monitoring group chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a949-104">_**Última modificación del tema:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="5a949-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="5a949-105">Se recomienda ejecutar el [programa de instalación de actualización de servidor acumulativa](https://support.microsoft.com/kb/968802) más reciente disponible en el centro de descarga de Microsoft para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5a949-105">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="5a949-106">Suponiendo que ejecuta la actualización acumulativa más reciente, use la siguiente tabla de pruebas de esfuerzo para obtener información sobre las métricas para comprender si los servidores de chat en grupo se ejecutan con un estado óptimo.</span><span class="sxs-lookup"><span data-stu-id="5a949-106">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="5a949-107">Entorno de prueba y modelo de usuario</span><span class="sxs-lookup"><span data-stu-id="5a949-107">Test environment and user model</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a949-108">Tres servidores de chat en grupo en un grupo de chats en grupo, cada uno con 8 GB de memoria y 8 procesadores.</span><span class="sxs-lookup"><span data-stu-id="5a949-108">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a949-109">Dos front-ends de Lync Server 2013 en Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="5a949-109">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a949-110">60.000 usuarios simultáneos en tres servidores de chat en grupo.</span><span class="sxs-lookup"><span data-stu-id="5a949-110">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a949-111">25.000 canales hospedados por un grupo de servidores de chat.</span><span class="sxs-lookup"><span data-stu-id="5a949-111">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a949-112">Tamaño de canal:</span><span class="sxs-lookup"><span data-stu-id="5a949-112">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a949-113">Tamaño de canal pequeño: 30</span><span class="sxs-lookup"><span data-stu-id="5a949-113">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="5a949-114">Tamaño de canal medio: 150</span><span class="sxs-lookup"><span data-stu-id="5a949-114">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="5a949-115">Tamaño de canal grande: 2500</span><span class="sxs-lookup"><span data-stu-id="5a949-115">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a949-116">Número de canales:</span><span class="sxs-lookup"><span data-stu-id="5a949-116">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a949-117">Número de canales pequeños: 24.000</span><span class="sxs-lookup"><span data-stu-id="5a949-117">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="5a949-118">Número medio canales 800</span><span class="sxs-lookup"><span data-stu-id="5a949-118">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="5a949-119">Número de canales grandes 24</span><span class="sxs-lookup"><span data-stu-id="5a949-119">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="5a949-120">Número total de canales 24.824</span><span class="sxs-lookup"><span data-stu-id="5a949-120">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a949-121">Canales de invitación:</span><span class="sxs-lookup"><span data-stu-id="5a949-121">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a949-122">La mitad de los canales fueron invitaciones a canales</span><span class="sxs-lookup"><span data-stu-id="5a949-122">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a949-123">Número de canales que un usuario ha incorporado:</span><span class="sxs-lookup"><span data-stu-id="5a949-123">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a949-124">Pequeño: 12</span><span class="sxs-lookup"><span data-stu-id="5a949-124">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="5a949-125">Medio: 2</span><span class="sxs-lookup"><span data-stu-id="5a949-125">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="5a949-126">Grande: 1</span><span class="sxs-lookup"><span data-stu-id="5a949-126">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a949-127">Tasa de combinaciones:</span><span class="sxs-lookup"><span data-stu-id="5a949-127">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a949-128">10 en total/segundo, 3,33/segundo por servidor</span><span class="sxs-lookup"><span data-stu-id="5a949-128">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a949-129">Tasa de cierre de sesión:</span><span class="sxs-lookup"><span data-stu-id="5a949-129">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a949-130">10 en total/segundo, 3,33/segundo por servidor</span><span class="sxs-lookup"><span data-stu-id="5a949-130">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a949-131">Tasa de chat:</span><span class="sxs-lookup"><span data-stu-id="5a949-131">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a949-132">20 en total/segundo, 6.66/segundo por servidor</span><span class="sxs-lookup"><span data-stu-id="5a949-132">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="5a949-133">Los siguientes números de contadores de rendimiento probablemente variarán cuando se usen diferentes especificaciones de hardware o perfiles de usuario.</span><span class="sxs-lookup"><span data-stu-id="5a949-133">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="5a949-134">Contador de rendimiento que se va a supervisar</span><span class="sxs-lookup"><span data-stu-id="5a949-134">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a949-135">Contador de rendimiento</span><span class="sxs-lookup"><span data-stu-id="5a949-135">Performance Counter</span></span></th>
<th><span data-ttu-id="5a949-136">Umbrales</span><span class="sxs-lookup"><span data-stu-id="5a949-136">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a949-137">Proceso (ChannelService)- &gt; % de tiempo de procesador</span><span class="sxs-lookup"><span data-stu-id="5a949-137">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="5a949-138">Min: 0</span><span class="sxs-lookup"><span data-stu-id="5a949-138">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

