---
title: 'Lync Server 2013: póster: indicadores de estado clave'
description: 'Lync Server 2013: póster: indicadores de estado clave.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9962d1764d5d2c664bb8415261344d9b48c81149
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566346"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="e3a0e-103">Indicadores de estado clave en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3a0e-103">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3a0e-104">_**Última modificación del tema:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="e3a0e-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="e3a0e-105">Este artículo es un complemento para el póster [key Health Indicators: la base para mantener un póster de los servidores de Lync en buen estado](https://go.microsoft.com/fwlink/?linkid=391838) , que puede descargar desde el centro de descarga.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-105">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="e3a0e-106">![Póster que describe cómo solucionar problemas con datos de KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Póster que describe cómo solucionar problemas con datos de KHI")</span><span class="sxs-lookup"><span data-stu-id="e3a0e-106">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="e3a0e-107">Puede usar este póster para obtener información sobre los indicadores de estado clave (KHIs), los contadores de rendimiento con umbrales destinados a revelar los problemas de la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-107">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="e3a0e-108">La recopilación de datos de KHI suele ser el primer paso para implementar la metodología de calidad de llamadas (CQM), que se centra en garantizar una experiencia de audio de calidad para los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-108">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="e3a0e-109">Si tiene preguntas sobre cómo usar CQM, puede enviar sus preguntas a cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="e3a0e-110">En el póster se explican las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="e3a0e-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="e3a0e-111">¿Qué son los indicadores de estado clave?</span><span class="sxs-lookup"><span data-stu-id="e3a0e-111">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="e3a0e-112">Para recopilar datos de KHI</span><span class="sxs-lookup"><span data-stu-id="e3a0e-112">To Collect KHI Data</span></span>

  - <span data-ttu-id="e3a0e-113">Flujo de corrección para todos los roles de servidor</span><span class="sxs-lookup"><span data-stu-id="e3a0e-113">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="e3a0e-114">Glosario</span><span class="sxs-lookup"><span data-stu-id="e3a0e-114">Glossary</span></span>

  - <span data-ttu-id="e3a0e-115">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e3a0e-115">Front-end Servers</span></span>

  - <span data-ttu-id="e3a0e-116">Servidores SQL back-end</span><span class="sxs-lookup"><span data-stu-id="e3a0e-116">Backend SQL Servers</span></span>

  - <span data-ttu-id="e3a0e-117">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="e3a0e-117">Mediation Servers</span></span>

  - <span data-ttu-id="e3a0e-118">Servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="e3a0e-118">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="e3a0e-119">¿Qué son los indicadores de estado clave?</span><span class="sxs-lookup"><span data-stu-id="e3a0e-119">What are Key Health Indicators?</span></span>

<span data-ttu-id="e3a0e-120">Los indicadores de estado clave son contadores de rendimiento con umbrales destinados a revelar los problemas de la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-120">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="e3a0e-121">La recopilación de datos de KHI suele ser el primer paso para implementar la metodología de calidad de llamadas (CQM), que se centra en garantizar una experiencia de audio de calidad para los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-121">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="e3a0e-122">KHIs se usan junto con las soluciones de supervisión de Lync estándar (por ejemplo, System Center Operations Manager, transacciones sintéticas, servidor de supervisión) y no en lugar de esas soluciones.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-122">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="e3a0e-123">Recopilar los contadores de rendimiento de KHI y rellenar la hoja de cálculo KHI que acompaña a la guía de redes para crear un cuadro de mandos que le ayudarán a determinar el estado del servidor de una implementación de Lync.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-123">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="e3a0e-124">Una vez rellenado, le guía en la reparación del entorno y ofrece información adicional a otras partes interesadas.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-124">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="e3a0e-125">Evalúe los KHIs cada mes e incorpórelo a los procesos operativos en curso de la implementación.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-125">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="e3a0e-126">Descargue la [Guía de redes de Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) para ver la lista completa de KHIs y para obtener las hojas de cálculo relacionadas.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-126">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="e3a0e-127">Para recopilar datos de KHI</span><span class="sxs-lookup"><span data-stu-id="e3a0e-127">To Collect KHI Data</span></span>

1.  <span data-ttu-id="e3a0e-128">Ejecute el script KHI incluido con la guía de red de Lync Server en cada Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-128">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="e3a0e-129">Se creará un recopilador de datos dentro del monitor de rendimiento y se le asignará el nombre KHI.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-129">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="e3a0e-130">De forma predeterminada, los datos se sondearán cada 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-130">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="e3a0e-131">Antes de iniciar el día hábil de la compañía, vaya a cada Lync Server e inicie el recopilador de datos de KHI.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-131">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="e3a0e-132">Al final de ese día, detenga el recopilador de datos de KHI y copie los datos en una ubicación central.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-132">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="e3a0e-133">Después de usar el monitor de rendimiento para rellenar la hoja de cálculo KHI que se incluye con la guía de redes de Lync Server, compare los resultados con los objetivos recomendados.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-133">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="e3a0e-134">Flujo de corrección para todos los roles de servidor</span><span class="sxs-lookup"><span data-stu-id="e3a0e-134">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="e3a0e-135">Para cada servidor de la implementación de Lync, primero Compruebe que el estado del componente y el rendimiento del sistema del servidor se encuentra en el nivel deseado o por encima de él.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-135">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="e3a0e-136">Solo después de eso, debería mirar los indicadores relacionados con el rol del servidor en la implementación general de Lync.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-136">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="e3a0e-137">Empiece por recopilar datos de rendimiento de KHI para todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-137">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="e3a0e-138">Para cada uno de los roles del sistema (los detalles que se describen más adelante en este documento) determinan si los componentes básicos del sistema cumplen con los objetivos recomendados.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-138">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="e3a0e-139">Si no es así, corrija el rendimiento del sistema y vuelva a recopilar datos de KHI y garantice el estado del sistema antes de ver las métricas específicas del rol del servidor en la implementación de Lync.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-139">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="e3a0e-140">El estado del componente para todos los roles se define como:</span><span class="sxs-lookup"><span data-stu-id="e3a0e-140">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="e3a0e-141">Uso de la CPU \< 80%</span><span class="sxs-lookup"><span data-stu-id="e3a0e-141">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="e3a0e-142">Promedio de escrituras en disco \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="e3a0e-142">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="e3a0e-143">Promedio de lectura de disco \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="e3a0e-143">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="e3a0e-144">Memoria disponible \> 20% total de MB de sistema</span><span class="sxs-lookup"><span data-stu-id="e3a0e-144">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="e3a0e-145">Longitud 2 de cola de red \<</span><span class="sxs-lookup"><span data-stu-id="e3a0e-145">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="e3a0e-146">Paquetes descartados (in/out) = 0</span><span class="sxs-lookup"><span data-stu-id="e3a0e-146">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="e3a0e-147">Glosario</span><span class="sxs-lookup"><span data-stu-id="e3a0e-147">Glossary</span></span>

<span data-ttu-id="e3a0e-148">En este póster se usan los siguientes términos y acrónimos:</span><span class="sxs-lookup"><span data-stu-id="e3a0e-148">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="e3a0e-149">COMO MCU = unidad de control de varios puntos de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e3a0e-149">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="e3a0e-150">MCU AV = MCU de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="e3a0e-150">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="e3a0e-151">La MCU de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="e3a0e-151">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="e3a0e-152">UCWA = API Web de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="e3a0e-152">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="e3a0e-153">Perimetral AV = recorrido de audio y vídeo a través de la periferia</span><span class="sxs-lookup"><span data-stu-id="e3a0e-153">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="e3a0e-154">Autenticación AV = autenticación de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="e3a0e-154">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="e3a0e-155">La pila SIP = contiene la implementación SIP principal de Lync</span><span class="sxs-lookup"><span data-stu-id="e3a0e-155">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="e3a0e-156">Proxy de datos = usado para las conferencias perimetrales</span><span class="sxs-lookup"><span data-stu-id="e3a0e-156">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="e3a0e-157">LySS = servicio de almacenamiento de Lync</span><span class="sxs-lookup"><span data-stu-id="e3a0e-157">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="e3a0e-158">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e3a0e-158">Front-end Servers</span></span>

<span data-ttu-id="e3a0e-159">Los siguientes destinos KHI recomendados son específicos de los servidores front-end, además del estado básico del componente:</span><span class="sxs-lookup"><span data-stu-id="e3a0e-159">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3a0e-160">Área funcional</span><span class="sxs-lookup"><span data-stu-id="e3a0e-160">Functional area</span></span></th>
<th><span data-ttu-id="e3a0e-161">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="e3a0e-161">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3a0e-162">MCU AS/AV/IM</span><span class="sxs-lookup"><span data-stu-id="e3a0e-162">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="e3a0e-163">Estado de mantenimiento de MCU &lt; 2</span><span class="sxs-lookup"><span data-stu-id="e3a0e-163">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3a0e-164">Web Components</span><span class="sxs-lookup"><span data-stu-id="e3a0e-164">Web Components</span></span></p></td>
<td><p><span data-ttu-id="e3a0e-165">Tiempo de espera de AD de expansión de lista de distribución &lt; 0</span><span class="sxs-lookup"><span data-stu-id="e3a0e-165">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="e3a0e-166">Errores de ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="e3a0e-166">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="e3a0e-167">Errores de LIS = 0</span><span class="sxs-lookup"><span data-stu-id="e3a0e-167">LIS failures = 0</span></span></p>
<p><span data-ttu-id="e3a0e-168">Errores de autenticación &lt; 1/seg.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-168">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="e3a0e-169">Solicitudes ASP.NET V4 rechazadas = 0</span><span class="sxs-lookup"><span data-stu-id="e3a0e-169">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3a0e-170">Pila SIP</span><span class="sxs-lookup"><span data-stu-id="e3a0e-170">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="e3a0e-171">Promedio de procesamiento de mensajes entrantes &lt; 1 seg.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-171">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="e3a0e-172">Respuestas entrantes descartadas &lt; 1/s solicitudes entrantes descartadas &lt; 1/seg</span><span class="sxs-lookup"><span data-stu-id="e3a0e-172">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="e3a0e-173">Latencia de cola &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="e3a0e-173">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="e3a0e-174">Latencia de SPROC &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="e3a0e-174">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="e3a0e-175">Solicitudes limitadas = 0</span><span class="sxs-lookup"><span data-stu-id="e3a0e-175">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="e3a0e-176">Errores de autenticación &lt; 1/seg.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-176">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="e3a0e-177">Se agotó el tiempo de espera de los mensajes entrantes &lt; 2</span><span class="sxs-lookup"><span data-stu-id="e3a0e-177">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="e3a0e-178">Tiempo medio de espera de mensajes entrantes &lt; 1 seg.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-178">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="e3a0e-179">Conexiones controladas por flujo &lt; 2</span><span class="sxs-lookup"><span data-stu-id="e3a0e-179">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="e3a0e-180">Retraso de la cola de salida promedio &lt; 2 segundos</span><span class="sxs-lookup"><span data-stu-id="e3a0e-180">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3a0e-181">LySS</span><span class="sxs-lookup"><span data-stu-id="e3a0e-181">LySS</span></span></p></td>
<td><p><span data-ttu-id="e3a0e-182">% de espacio usado por la base de datos del servicio de almacenamiento &lt; 80</span><span class="sxs-lookup"><span data-stu-id="e3a0e-182">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="e3a0e-183"># de errores de replicación de réplica = 0</span><span class="sxs-lookup"><span data-stu-id="e3a0e-183"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="e3a0e-184"># de eventos de pérdida de datos = 0</span><span class="sxs-lookup"><span data-stu-id="e3a0e-184"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3a0e-185">SQL</span><span class="sxs-lookup"><span data-stu-id="e3a0e-185">SQL</span></span></p></td>
<td><p><span data-ttu-id="e3a0e-186">Esperanza de vida de la página &gt; 300 seg.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-186">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="e3a0e-187">Solicitudes de lote por segundo &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="e3a0e-187">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="e3a0e-188">Servidores SQL back-end</span><span class="sxs-lookup"><span data-stu-id="e3a0e-188">Backend SQL Servers</span></span>

<span data-ttu-id="e3a0e-189">Los siguientes destinos KHI recomendados son específicos de los servidores SQL Server, además del estado básico del componente:</span><span class="sxs-lookup"><span data-stu-id="e3a0e-189">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3a0e-190">Área funcional</span><span class="sxs-lookup"><span data-stu-id="e3a0e-190">Functional area</span></span></th>
<th><span data-ttu-id="e3a0e-191">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="e3a0e-191">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3a0e-192">SQL</span><span class="sxs-lookup"><span data-stu-id="e3a0e-192">SQL</span></span></p></td>
<td><p><span data-ttu-id="e3a0e-193">Esperanza de vida de la página &gt; 300 seg.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-193">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="e3a0e-194">Solicitudes de lote por segundo &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="e3a0e-194">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="e3a0e-195">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="e3a0e-195">Mediation Servers</span></span>

<span data-ttu-id="e3a0e-196">Los siguientes destinos KHI recomendados son específicos de los servidores de mediación, además del estado básico del componente:</span><span class="sxs-lookup"><span data-stu-id="e3a0e-196">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3a0e-197">Área funcional</span><span class="sxs-lookup"><span data-stu-id="e3a0e-197">Functional area</span></span></th>
<th><span data-ttu-id="e3a0e-198">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="e3a0e-198">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3a0e-199">Servicio de servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="e3a0e-199">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="e3a0e-200">Índice de error de llamada de carga = 0</span><span class="sxs-lookup"><span data-stu-id="e3a0e-200">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="e3a0e-201">Llamadas con error debido al proxy &lt; 10</span><span class="sxs-lookup"><span data-stu-id="e3a0e-201">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="e3a0e-202">Llamadas con error debido a la puerta de enlace &lt; 10</span><span class="sxs-lookup"><span data-stu-id="e3a0e-202">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="e3a0e-203">Llamadas (in o out) rechazadas = 0</span><span class="sxs-lookup"><span data-stu-id="e3a0e-203">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="e3a0e-204">Candidatos con medios ausentes = 0</span><span class="sxs-lookup"><span data-stu-id="e3a0e-204">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="e3a0e-205">Errores de comprobación de conectividad de medios = 0</span><span class="sxs-lookup"><span data-stu-id="e3a0e-205">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="e3a0e-206">Servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="e3a0e-206">Edge Servers</span></span>

<span data-ttu-id="e3a0e-207">Los siguientes destinos KHI recomendados son específicos de los servidores perimetrales, además del estado básico del componente:</span><span class="sxs-lookup"><span data-stu-id="e3a0e-207">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3a0e-208">Área funcional</span><span class="sxs-lookup"><span data-stu-id="e3a0e-208">Functional area</span></span></th>
<th><span data-ttu-id="e3a0e-209">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="e3a0e-209">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3a0e-210">Autenticación de antivirus</span><span class="sxs-lookup"><span data-stu-id="e3a0e-210">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="e3a0e-211">Solicitudes incorrectas &lt; 20/seg</span><span class="sxs-lookup"><span data-stu-id="e3a0e-211">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3a0e-212">Borde AV</span><span class="sxs-lookup"><span data-stu-id="e3a0e-212">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="e3a0e-213">Errores de auth. &lt; 20/seg</span><span class="sxs-lookup"><span data-stu-id="e3a0e-213">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="e3a0e-214">Errores de asignación de &lt; 20/seg.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-214">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="e3a0e-215">Paquetes descartados &lt; 300/seg</span><span class="sxs-lookup"><span data-stu-id="e3a0e-215">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3a0e-216">Proxy de datos</span><span class="sxs-lookup"><span data-stu-id="e3a0e-216">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="e3a0e-217">Conexiones de servidor limitadas &lt; 3</span><span class="sxs-lookup"><span data-stu-id="e3a0e-217">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="e3a0e-218">El sistema se está limitando a &lt; 1</span><span class="sxs-lookup"><span data-stu-id="e3a0e-218">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3a0e-219">Pila SIP</span><span class="sxs-lookup"><span data-stu-id="e3a0e-219">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="e3a0e-220">Conexiones superadas por límite descartadas &lt; 1</span><span class="sxs-lookup"><span data-stu-id="e3a0e-220">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="e3a0e-221">Envíos agotados &lt; 10</span><span class="sxs-lookup"><span data-stu-id="e3a0e-221">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="e3a0e-222">Conexiones controladas por flujo &lt; 100</span><span class="sxs-lookup"><span data-stu-id="e3a0e-222">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="e3a0e-223">Solicitudes entrantes descartadas &lt; 1/seg.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-223">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="e3a0e-224">Promedio de procesamiento de mensajes &lt; 3 seg.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-224">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3a0e-225">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3a0e-225">See Also</span></span>


[<span data-ttu-id="e3a0e-226">Guía de redes de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e3a0e-226">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="e3a0e-227">Indicadores de estado clave: la base para mantener servidores de Lync en buen estado</span><span class="sxs-lookup"><span data-stu-id="e3a0e-227">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="e3a0e-228">Metodología de calidad de llamadas de Lync</span><span class="sxs-lookup"><span data-stu-id="e3a0e-228">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

