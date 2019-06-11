---
title: 'Lync Server 2013: supervisión del chat grupal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74897191cac7559237e961b7600a3ed478d11e58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="6c600-102">Supervisión de la conversación de grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c600-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c600-103">_**Última modificación del tema:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="6c600-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="6c600-104">Recomendamos encarecidamente ejecutar el [programa de instalación de actualización de servidor acumulativo](http://support.microsoft.com/kb/968802) más reciente disponible en el centro de descarga de Microsoft para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6c600-104">We highly recommend running the most recent [Cumulative Server Update Installer](http://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="6c600-105">Suponiendo que está ejecutando la actualización acumulativa más reciente, use la siguiente tabla de pruebas de estrés para ver si los servidores de chat de grupo se ejecutan con un estado óptimo.</span><span class="sxs-lookup"><span data-stu-id="6c600-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="6c600-106">Entorno de prueba y modelo de usuario</span><span class="sxs-lookup"><span data-stu-id="6c600-106">Test environment and user model</span></span>

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
<td><p><span data-ttu-id="6c600-107">Tres servidores de chat grupales en un grupo de chats grupales, cada uno con memoria de 8 GB y 8 procesadores.</span><span class="sxs-lookup"><span data-stu-id="6c600-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c600-108">Dos servidores front-end de Lync Server 2013 en Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="6c600-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c600-109">60.000 usuarios simultáneos en tres servidores de chats grupales.</span><span class="sxs-lookup"><span data-stu-id="6c600-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c600-110">25.000 canales alojados en un grupo de chats grupales.</span><span class="sxs-lookup"><span data-stu-id="6c600-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c600-111">Tamaño del canal:</span><span class="sxs-lookup"><span data-stu-id="6c600-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="6c600-112">Tamaño de canal pequeño: 30</span><span class="sxs-lookup"><span data-stu-id="6c600-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="6c600-113">Tamaño de canal medio: 150</span><span class="sxs-lookup"><span data-stu-id="6c600-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="6c600-114">Tamaño de canal grande: 2500</span><span class="sxs-lookup"><span data-stu-id="6c600-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c600-115">Recuento de canales:</span><span class="sxs-lookup"><span data-stu-id="6c600-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="6c600-116">Canales pequeños de números: 24.000</span><span class="sxs-lookup"><span data-stu-id="6c600-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="6c600-117">Número de canales media 800</span><span class="sxs-lookup"><span data-stu-id="6c600-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="6c600-118">Número de canales grandes 24</span><span class="sxs-lookup"><span data-stu-id="6c600-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="6c600-119">Número total de canales 24.824</span><span class="sxs-lookup"><span data-stu-id="6c600-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c600-120">Canales de invitación:</span><span class="sxs-lookup"><span data-stu-id="6c600-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="6c600-121">La mitad de los canales fueron invitar a canales</span><span class="sxs-lookup"><span data-stu-id="6c600-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c600-122">Número de canales que un usuario se une:</span><span class="sxs-lookup"><span data-stu-id="6c600-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="6c600-123">Pequeño: 12</span><span class="sxs-lookup"><span data-stu-id="6c600-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="6c600-124">Medio: 2</span><span class="sxs-lookup"><span data-stu-id="6c600-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="6c600-125">Grande: 1</span><span class="sxs-lookup"><span data-stu-id="6c600-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c600-126">Tasa de participación:</span><span class="sxs-lookup"><span data-stu-id="6c600-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="6c600-127">10 en total/segundo, 3,33/segundo por servidor</span><span class="sxs-lookup"><span data-stu-id="6c600-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c600-128">Tasa de cierre de sesión:</span><span class="sxs-lookup"><span data-stu-id="6c600-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="6c600-129">10 en total/segundo, 3,33/segundo por servidor</span><span class="sxs-lookup"><span data-stu-id="6c600-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c600-130">Tarifa de chat:</span><span class="sxs-lookup"><span data-stu-id="6c600-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="6c600-131">20 en total/segundo, 6.66/segundo por servidor</span><span class="sxs-lookup"><span data-stu-id="6c600-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c600-132">Los siguientes números de contador de rendimiento probablemente variarán cuando se usen especificaciones de hardware o perfiles de usuario diferentes.</span><span class="sxs-lookup"><span data-stu-id="6c600-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="6c600-133">Contador de rendimiento que se va a supervisar</span><span class="sxs-lookup"><span data-stu-id="6c600-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c600-134">Contador de rendimiento</span><span class="sxs-lookup"><span data-stu-id="6c600-134">Performance Counter</span></span></th>
<th><span data-ttu-id="6c600-135">Los</span><span class="sxs-lookup"><span data-stu-id="6c600-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c600-136">Proceso (ChannelService):&gt;% de tiempo de procesador</span><span class="sxs-lookup"><span data-stu-id="6c600-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="6c600-137">Mín: 0</span><span class="sxs-lookup"><span data-stu-id="6c600-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

