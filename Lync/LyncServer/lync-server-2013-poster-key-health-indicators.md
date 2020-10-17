---
title: 'Lync Server 2013: póster: indicadores de estado clave'
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
ms.openlocfilehash: d6db6a701c98a44b042d9ee36d0a749bf6363bd2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513387"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="17bc7-102">Indicadores de estado clave en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17bc7-102">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17bc7-103">_**Última modificación del tema:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="17bc7-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="17bc7-104">Este artículo es un complemento para el póster [key Health Indicators: la base para mantener un póster de los servidores de Lync en buen estado](https://go.microsoft.com/fwlink/?linkid=391838) , que puede descargar desde el centro de descarga.</span><span class="sxs-lookup"><span data-stu-id="17bc7-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="17bc7-105">![Póster que describe cómo solucionar problemas con datos de KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Póster que describe cómo solucionar problemas con datos de KHI")</span><span class="sxs-lookup"><span data-stu-id="17bc7-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="17bc7-106">Puede usar este póster para obtener información sobre los indicadores de estado clave (KHIs), los contadores de rendimiento con umbrales destinados a revelar los problemas de la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="17bc7-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="17bc7-107">La recopilación de datos de KHI suele ser el primer paso para implementar la metodología de calidad de llamadas (CQM), que se centra en garantizar una experiencia de audio de calidad para los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="17bc7-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="17bc7-108">Si tiene preguntas sobre cómo usar CQM, puede enviar sus preguntas a cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="17bc7-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="17bc7-109">En el póster se explican las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="17bc7-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="17bc7-110">¿Qué son los indicadores de estado clave?</span><span class="sxs-lookup"><span data-stu-id="17bc7-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="17bc7-111">Para recopilar datos de KHI</span><span class="sxs-lookup"><span data-stu-id="17bc7-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="17bc7-112">Flujo de corrección para todos los roles de servidor</span><span class="sxs-lookup"><span data-stu-id="17bc7-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="17bc7-113">Glosario</span><span class="sxs-lookup"><span data-stu-id="17bc7-113">Glossary</span></span>

  - <span data-ttu-id="17bc7-114">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="17bc7-114">Front-end Servers</span></span>

  - <span data-ttu-id="17bc7-115">Servidores SQL back-end</span><span class="sxs-lookup"><span data-stu-id="17bc7-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="17bc7-116">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="17bc7-116">Mediation Servers</span></span>

  - <span data-ttu-id="17bc7-117">Servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="17bc7-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="17bc7-118">¿Qué son los indicadores de estado clave?</span><span class="sxs-lookup"><span data-stu-id="17bc7-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="17bc7-119">Los indicadores de estado clave son contadores de rendimiento con umbrales destinados a revelar los problemas de la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="17bc7-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="17bc7-120">La recopilación de datos de KHI suele ser el primer paso para implementar la metodología de calidad de llamadas (CQM), que se centra en garantizar una experiencia de audio de calidad para los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="17bc7-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="17bc7-121">KHIs se usan junto con las soluciones de supervisión de Lync estándar (por ejemplo, System Center Operations Manager, transacciones sintéticas, servidor de supervisión) y no en lugar de esas soluciones.</span><span class="sxs-lookup"><span data-stu-id="17bc7-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="17bc7-122">Recopilar los contadores de rendimiento de KHI y rellenar la hoja de cálculo KHI que acompaña a la guía de redes para crear un cuadro de mandos que le ayudarán a determinar el estado del servidor de una implementación de Lync.</span><span class="sxs-lookup"><span data-stu-id="17bc7-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="17bc7-123">Una vez rellenado, le guía en la reparación del entorno y ofrece información adicional a otras partes interesadas.</span><span class="sxs-lookup"><span data-stu-id="17bc7-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="17bc7-124">Evalúe los KHIs cada mes e incorpórelo a los procesos operativos en curso de la implementación.</span><span class="sxs-lookup"><span data-stu-id="17bc7-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="17bc7-125">Descargue la [Guía de redes de Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) para ver la lista completa de KHIs y para obtener las hojas de cálculo relacionadas.</span><span class="sxs-lookup"><span data-stu-id="17bc7-125">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="17bc7-126">Para recopilar datos de KHI</span><span class="sxs-lookup"><span data-stu-id="17bc7-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="17bc7-127">Ejecute el script KHI incluido con la guía de red de Lync Server en cada Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17bc7-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="17bc7-128">Se creará un recopilador de datos dentro del monitor de rendimiento y se le asignará el nombre KHI.</span><span class="sxs-lookup"><span data-stu-id="17bc7-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="17bc7-129">De forma predeterminada, los datos se sondearán cada 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="17bc7-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="17bc7-130">Antes de iniciar el día hábil de la compañía, vaya a cada Lync Server e inicie el recopilador de datos de KHI.</span><span class="sxs-lookup"><span data-stu-id="17bc7-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="17bc7-131">Al final de ese día, detenga el recopilador de datos de KHI y copie los datos en una ubicación central.</span><span class="sxs-lookup"><span data-stu-id="17bc7-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="17bc7-132">Después de usar el monitor de rendimiento para rellenar la hoja de cálculo KHI que se incluye con la guía de redes de Lync Server, compare los resultados con los objetivos recomendados.</span><span class="sxs-lookup"><span data-stu-id="17bc7-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="17bc7-133">Flujo de corrección para todos los roles de servidor</span><span class="sxs-lookup"><span data-stu-id="17bc7-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="17bc7-134">Para cada servidor de la implementación de Lync, primero Compruebe que el estado del componente y el rendimiento del sistema del servidor se encuentra en el nivel deseado o por encima de él.</span><span class="sxs-lookup"><span data-stu-id="17bc7-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="17bc7-135">Solo después de eso, debería mirar los indicadores relacionados con el rol del servidor en la implementación general de Lync.</span><span class="sxs-lookup"><span data-stu-id="17bc7-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="17bc7-136">Empiece por recopilar datos de rendimiento de KHI para todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="17bc7-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="17bc7-137">Para cada uno de los roles del sistema (los detalles que se describen más adelante en este documento) determinan si los componentes básicos del sistema cumplen con los objetivos recomendados.</span><span class="sxs-lookup"><span data-stu-id="17bc7-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="17bc7-138">Si no es así, corrija el rendimiento del sistema y vuelva a recopilar datos de KHI y garantice el estado del sistema antes de ver las métricas específicas del rol del servidor en la implementación de Lync.</span><span class="sxs-lookup"><span data-stu-id="17bc7-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="17bc7-139">El estado del componente para todos los roles se define como:</span><span class="sxs-lookup"><span data-stu-id="17bc7-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="17bc7-140">Uso de la CPU \< 80%</span><span class="sxs-lookup"><span data-stu-id="17bc7-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="17bc7-141">Promedio de escrituras en disco \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="17bc7-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="17bc7-142">Promedio de lectura de disco \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="17bc7-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="17bc7-143">Memoria disponible \> 20% total de MB de sistema</span><span class="sxs-lookup"><span data-stu-id="17bc7-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="17bc7-144">Longitud 2 de cola de red \<</span><span class="sxs-lookup"><span data-stu-id="17bc7-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="17bc7-145">Paquetes descartados (in/out) = 0</span><span class="sxs-lookup"><span data-stu-id="17bc7-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="17bc7-146">Glosario</span><span class="sxs-lookup"><span data-stu-id="17bc7-146">Glossary</span></span>

<span data-ttu-id="17bc7-147">En este póster se usan los siguientes términos y acrónimos:</span><span class="sxs-lookup"><span data-stu-id="17bc7-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="17bc7-148">COMO MCU = unidad de control de varios puntos de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="17bc7-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="17bc7-149">MCU AV = MCU de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="17bc7-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="17bc7-150">La MCU de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="17bc7-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="17bc7-151">UCWA = API Web de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="17bc7-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="17bc7-152">Perimetral AV = recorrido de audio y vídeo a través de la periferia</span><span class="sxs-lookup"><span data-stu-id="17bc7-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="17bc7-153">Autenticación AV = autenticación de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="17bc7-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="17bc7-154">La pila SIP = contiene la implementación SIP principal de Lync</span><span class="sxs-lookup"><span data-stu-id="17bc7-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="17bc7-155">Proxy de datos = usado para las conferencias perimetrales</span><span class="sxs-lookup"><span data-stu-id="17bc7-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="17bc7-156">LySS = servicio de almacenamiento de Lync</span><span class="sxs-lookup"><span data-stu-id="17bc7-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="17bc7-157">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="17bc7-157">Front-end Servers</span></span>

<span data-ttu-id="17bc7-158">Los siguientes destinos KHI recomendados son específicos de los servidores front-end, además del estado básico del componente:</span><span class="sxs-lookup"><span data-stu-id="17bc7-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17bc7-159">Área funcional</span><span class="sxs-lookup"><span data-stu-id="17bc7-159">Functional area</span></span></th>
<th><span data-ttu-id="17bc7-160">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="17bc7-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17bc7-161">MCU AS/AV/IM</span><span class="sxs-lookup"><span data-stu-id="17bc7-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="17bc7-162">Estado de mantenimiento de MCU &lt; 2</span><span class="sxs-lookup"><span data-stu-id="17bc7-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17bc7-163">Web Components</span><span class="sxs-lookup"><span data-stu-id="17bc7-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="17bc7-164">Tiempo de espera de AD de expansión de lista de distribución &lt; 0</span><span class="sxs-lookup"><span data-stu-id="17bc7-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="17bc7-165">Errores de ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="17bc7-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="17bc7-166">Errores de LIS = 0</span><span class="sxs-lookup"><span data-stu-id="17bc7-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="17bc7-167">Errores de autenticación &lt; 1/seg.</span><span class="sxs-lookup"><span data-stu-id="17bc7-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="17bc7-168">Solicitudes ASP.NET V4 rechazadas = 0</span><span class="sxs-lookup"><span data-stu-id="17bc7-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17bc7-169">Pila SIP</span><span class="sxs-lookup"><span data-stu-id="17bc7-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="17bc7-170">Promedio de procesamiento de mensajes entrantes &lt; 1 seg.</span><span class="sxs-lookup"><span data-stu-id="17bc7-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="17bc7-171">Respuestas entrantes descartadas &lt; 1/s solicitudes entrantes descartadas &lt; 1/seg</span><span class="sxs-lookup"><span data-stu-id="17bc7-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="17bc7-172">Latencia de cola &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="17bc7-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="17bc7-173">Latencia de SPROC &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="17bc7-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="17bc7-174">Solicitudes limitadas = 0</span><span class="sxs-lookup"><span data-stu-id="17bc7-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="17bc7-175">Errores de autenticación &lt; 1/seg.</span><span class="sxs-lookup"><span data-stu-id="17bc7-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="17bc7-176">Se agotó el tiempo de espera de los mensajes entrantes &lt; 2</span><span class="sxs-lookup"><span data-stu-id="17bc7-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="17bc7-177">Tiempo medio de espera de mensajes entrantes &lt; 1 seg.</span><span class="sxs-lookup"><span data-stu-id="17bc7-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="17bc7-178">Conexiones controladas por flujo &lt; 2</span><span class="sxs-lookup"><span data-stu-id="17bc7-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="17bc7-179">Retraso de la cola de salida promedio &lt; 2 segundos</span><span class="sxs-lookup"><span data-stu-id="17bc7-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17bc7-180">LySS</span><span class="sxs-lookup"><span data-stu-id="17bc7-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="17bc7-181">% de espacio usado por la base de datos del servicio de almacenamiento &lt; 80</span><span class="sxs-lookup"><span data-stu-id="17bc7-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="17bc7-182"># de errores de replicación de réplica = 0</span><span class="sxs-lookup"><span data-stu-id="17bc7-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="17bc7-183"># de eventos de pérdida de datos = 0</span><span class="sxs-lookup"><span data-stu-id="17bc7-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17bc7-184">SQL</span><span class="sxs-lookup"><span data-stu-id="17bc7-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="17bc7-185">Esperanza de vida de la página &gt; 300 seg.</span><span class="sxs-lookup"><span data-stu-id="17bc7-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="17bc7-186">Solicitudes de lote por segundo &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="17bc7-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="17bc7-187">Servidores SQL back-end</span><span class="sxs-lookup"><span data-stu-id="17bc7-187">Backend SQL Servers</span></span>

<span data-ttu-id="17bc7-188">Los siguientes destinos KHI recomendados son específicos de los servidores SQL Server, además del estado básico del componente:</span><span class="sxs-lookup"><span data-stu-id="17bc7-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17bc7-189">Área funcional</span><span class="sxs-lookup"><span data-stu-id="17bc7-189">Functional area</span></span></th>
<th><span data-ttu-id="17bc7-190">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="17bc7-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17bc7-191">SQL</span><span class="sxs-lookup"><span data-stu-id="17bc7-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="17bc7-192">Esperanza de vida de la página &gt; 300 seg.</span><span class="sxs-lookup"><span data-stu-id="17bc7-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="17bc7-193">Solicitudes de lote por segundo &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="17bc7-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="17bc7-194">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="17bc7-194">Mediation Servers</span></span>

<span data-ttu-id="17bc7-195">Los siguientes destinos KHI recomendados son específicos de los servidores de mediación, además del estado básico del componente:</span><span class="sxs-lookup"><span data-stu-id="17bc7-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17bc7-196">Área funcional</span><span class="sxs-lookup"><span data-stu-id="17bc7-196">Functional area</span></span></th>
<th><span data-ttu-id="17bc7-197">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="17bc7-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17bc7-198">Servicio de servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="17bc7-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="17bc7-199">Índice de error de llamada de carga = 0</span><span class="sxs-lookup"><span data-stu-id="17bc7-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="17bc7-200">Llamadas con error debido al proxy &lt; 10</span><span class="sxs-lookup"><span data-stu-id="17bc7-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="17bc7-201">Llamadas con error debido a la puerta de enlace &lt; 10</span><span class="sxs-lookup"><span data-stu-id="17bc7-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="17bc7-202">Llamadas (in o out) rechazadas = 0</span><span class="sxs-lookup"><span data-stu-id="17bc7-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="17bc7-203">Candidatos con medios ausentes = 0</span><span class="sxs-lookup"><span data-stu-id="17bc7-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="17bc7-204">Errores de comprobación de conectividad de medios = 0</span><span class="sxs-lookup"><span data-stu-id="17bc7-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="17bc7-205">Servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="17bc7-205">Edge Servers</span></span>

<span data-ttu-id="17bc7-206">Los siguientes destinos KHI recomendados son específicos de los servidores perimetrales, además del estado básico del componente:</span><span class="sxs-lookup"><span data-stu-id="17bc7-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17bc7-207">Área funcional</span><span class="sxs-lookup"><span data-stu-id="17bc7-207">Functional area</span></span></th>
<th><span data-ttu-id="17bc7-208">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="17bc7-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17bc7-209">Autenticación de antivirus</span><span class="sxs-lookup"><span data-stu-id="17bc7-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="17bc7-210">Solicitudes incorrectas &lt; 20/seg</span><span class="sxs-lookup"><span data-stu-id="17bc7-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17bc7-211">Borde AV</span><span class="sxs-lookup"><span data-stu-id="17bc7-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="17bc7-212">Errores de auth. &lt; 20/seg</span><span class="sxs-lookup"><span data-stu-id="17bc7-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="17bc7-213">Errores de asignación de &lt; 20/seg.</span><span class="sxs-lookup"><span data-stu-id="17bc7-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="17bc7-214">Paquetes descartados &lt; 300/seg</span><span class="sxs-lookup"><span data-stu-id="17bc7-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17bc7-215">Proxy de datos</span><span class="sxs-lookup"><span data-stu-id="17bc7-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="17bc7-216">Conexiones de servidor limitadas &lt; 3</span><span class="sxs-lookup"><span data-stu-id="17bc7-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="17bc7-217">El sistema se está limitando a &lt; 1</span><span class="sxs-lookup"><span data-stu-id="17bc7-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17bc7-218">Pila SIP</span><span class="sxs-lookup"><span data-stu-id="17bc7-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="17bc7-219">Conexiones superadas por límite descartadas &lt; 1</span><span class="sxs-lookup"><span data-stu-id="17bc7-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="17bc7-220">Envíos agotados &lt; 10</span><span class="sxs-lookup"><span data-stu-id="17bc7-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="17bc7-221">Conexiones controladas por flujo &lt; 100</span><span class="sxs-lookup"><span data-stu-id="17bc7-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="17bc7-222">Solicitudes entrantes descartadas &lt; 1/seg.</span><span class="sxs-lookup"><span data-stu-id="17bc7-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="17bc7-223">Promedio de procesamiento de mensajes &lt; 3 seg.</span><span class="sxs-lookup"><span data-stu-id="17bc7-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17bc7-224">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17bc7-224">See Also</span></span>


[<span data-ttu-id="17bc7-225">Guía de redes de Lync Server</span><span class="sxs-lookup"><span data-stu-id="17bc7-225">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="17bc7-226">Indicadores de estado clave: la base para mantener servidores de Lync en buen estado</span><span class="sxs-lookup"><span data-stu-id="17bc7-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="17bc7-227">Metodología de calidad de llamadas de Lync</span><span class="sxs-lookup"><span data-stu-id="17bc7-227">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

