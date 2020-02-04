---
title: 'Lync Server 2013: póster: indicadores clave de estado'
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
ms.openlocfilehash: 812ce68c84f86250fd25cc646bbcd5faddf0e566
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="c5bea-102">Indicadores clave de estado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5bea-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5bea-103">_**Última modificación del tema:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="c5bea-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="c5bea-104">Este artículo es un complemento de los [indicadores clave de estado: la base para mantener el póster de los servidores de Lync en buen estado](http://go.microsoft.com/fwlink/?linkid=391838) , que puede descargar desde el centro de descarga.</span><span class="sxs-lookup"><span data-stu-id="c5bea-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="c5bea-105">![Póster que describe la solución de problemas con datos de KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Póster que describe la solución de problemas con datos de KHI")</span><span class="sxs-lookup"><span data-stu-id="c5bea-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="c5bea-106">Puede usar este póster para obtener información sobre los indicadores clave de estado (KHIs), los contadores de rendimiento con umbrales destinados a revelar problemas de experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="c5bea-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="c5bea-107">La recopilación de datos de KHI suele ser el primer paso para implementar la metodología de calidad de las llamadas (CQM), que se centra en garantizar una experiencia de audio de calidad para los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="c5bea-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="c5bea-108">Si tienes preguntas sobre cómo usar CQM, puedes enviar tus preguntas a cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c5bea-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="c5bea-109">En el póster se explican las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="c5bea-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="c5bea-110">¿Qué son los indicadores de estado clave?</span><span class="sxs-lookup"><span data-stu-id="c5bea-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="c5bea-111">Para recopilar datos de KHI</span><span class="sxs-lookup"><span data-stu-id="c5bea-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="c5bea-112">Flujo de corrección para todos los roles de servidor</span><span class="sxs-lookup"><span data-stu-id="c5bea-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="c5bea-113">Glosario</span><span class="sxs-lookup"><span data-stu-id="c5bea-113">Glossary</span></span>

  - <span data-ttu-id="c5bea-114">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="c5bea-114">Front-end Servers</span></span>

  - <span data-ttu-id="c5bea-115">Servidores SQL back-end</span><span class="sxs-lookup"><span data-stu-id="c5bea-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="c5bea-116">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="c5bea-116">Mediation Servers</span></span>

  - <span data-ttu-id="c5bea-117">Servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="c5bea-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="c5bea-118">¿Qué son los indicadores de estado clave?</span><span class="sxs-lookup"><span data-stu-id="c5bea-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="c5bea-119">Los indicadores de estado de clave son contadores de rendimiento con umbrales destinados a revelar problemas de experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="c5bea-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="c5bea-120">La recopilación de datos de KHI suele ser el primer paso para implementar la metodología de calidad de las llamadas (CQM), que se centra en garantizar una experiencia de audio de calidad para los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="c5bea-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="c5bea-121">KHIs se usan además de las soluciones de supervisión estándar de Lync (por ejemplo, System Center Operations Manager, transacciones sintéticas, servidor de supervisión) y no en lugar de esas soluciones.</span><span class="sxs-lookup"><span data-stu-id="c5bea-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="c5bea-122">Recopilar los contadores de rendimiento de KHI y rellenar la hoja de cálculo KHI que acompaña a la guía de redes para crear un cuadro de mandos que le ayudará a determinar el estado del servidor de una implementación de Lync.</span><span class="sxs-lookup"><span data-stu-id="c5bea-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="c5bea-123">Una vez que se haya rellenado, le guiará para reparar el entorno y le dará información adicional a otros participantes.</span><span class="sxs-lookup"><span data-stu-id="c5bea-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="c5bea-124">Evalúe KHIs cada mes e incorpórelo a cualquier proceso operativo en curso de implementación.</span><span class="sxs-lookup"><span data-stu-id="c5bea-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="c5bea-125">Descargue la [Guía de redes de Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677) para ver la lista completa de KHIs y para obtener las hojas de cálculo relacionadas.</span><span class="sxs-lookup"><span data-stu-id="c5bea-125">Download the [Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="c5bea-126">Para recopilar datos de KHI</span><span class="sxs-lookup"><span data-stu-id="c5bea-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="c5bea-127">Ejecute el script KHI que se incluye con la guía de redes de Lync Server en cada servidor de Lync.</span><span class="sxs-lookup"><span data-stu-id="c5bea-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="c5bea-128">Esto creará un recopilador de datos dentro del monitor de rendimiento y le dará el nombre KHI.</span><span class="sxs-lookup"><span data-stu-id="c5bea-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="c5bea-129">De forma predeterminada, los datos se sondearán cada 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="c5bea-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="c5bea-130">Antes de iniciar el día hábil de la empresa, vaya a cada servidor de Lync e inicie el recopilador de datos de KHI.</span><span class="sxs-lookup"><span data-stu-id="c5bea-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="c5bea-131">Al final de ese día, detenga el recopilador de datos de KHI y copie los datos en una ubicación central.</span><span class="sxs-lookup"><span data-stu-id="c5bea-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="c5bea-132">Después de usar Monitor de rendimiento para rellenar la hoja de cálculo KHI incluida en la descarga de la guía de redes de Lync Server, compare los resultados con los destinos recomendados.</span><span class="sxs-lookup"><span data-stu-id="c5bea-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="c5bea-133">Flujo de corrección para todos los roles de servidor</span><span class="sxs-lookup"><span data-stu-id="c5bea-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="c5bea-134">Para cada servidor de la implementación de Lync, primero Compruebe que el estado del componente y el rendimiento del sistema del servidor están en el nivel deseado o por encima de él.</span><span class="sxs-lookup"><span data-stu-id="c5bea-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="c5bea-135">Solo después de eso debería consultar los indicadores relacionados con el rol del servidor en la implementación general de Lync.</span><span class="sxs-lookup"><span data-stu-id="c5bea-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="c5bea-136">Comienza con la recopilación de datos de rendimiento de KHI para todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="c5bea-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="c5bea-137">Para cada uno de los roles del sistema (los detalles tratados más adelante en este documento) determine si los componentes básicos del sistema cumplen los objetivos recomendados.</span><span class="sxs-lookup"><span data-stu-id="c5bea-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="c5bea-138">Si no es así, corrija el rendimiento del sistema y vuelva a recopilar datos de KHI y asegúrese de que el estado del sistema antes de ver las métricas específicas de la función del servidor en la implementación de Lync.</span><span class="sxs-lookup"><span data-stu-id="c5bea-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="c5bea-139">El estado del componente para todos los roles se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="c5bea-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="c5bea-140">Uso de \< la CPU 80%</span><span class="sxs-lookup"><span data-stu-id="c5bea-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="c5bea-141">Promedio de escrituras \< en disco: 10 ms</span><span class="sxs-lookup"><span data-stu-id="c5bea-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="c5bea-142">Disco de lectura \< promedio: 10 ms</span><span class="sxs-lookup"><span data-stu-id="c5bea-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="c5bea-143">Memoria \>disponible 20% de sistema total MB</span><span class="sxs-lookup"><span data-stu-id="c5bea-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="c5bea-144">Longitud \< de cola de red 2</span><span class="sxs-lookup"><span data-stu-id="c5bea-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="c5bea-145">Paquetes descartados (o fuera) = 0</span><span class="sxs-lookup"><span data-stu-id="c5bea-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="c5bea-146">Glosario</span><span class="sxs-lookup"><span data-stu-id="c5bea-146">Glossary</span></span>

<span data-ttu-id="c5bea-147">Los siguientes términos y acrónimos se usan en este póster:</span><span class="sxs-lookup"><span data-stu-id="c5bea-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="c5bea-148">Como la unidad de control de varios puntos de la MCU = uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c5bea-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="c5bea-149">CABLE MCU = audio/video MCU</span><span class="sxs-lookup"><span data-stu-id="c5bea-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="c5bea-150">MI MCU = mensajería instantánea MCU</span><span class="sxs-lookup"><span data-stu-id="c5bea-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="c5bea-151">UCWA = API Web de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="c5bea-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="c5bea-152">Borde AV = recorrido de audio o vídeo vía borde</span><span class="sxs-lookup"><span data-stu-id="c5bea-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="c5bea-153">Autenticación AV = autenticación de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="c5bea-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="c5bea-154">SIP Stack = contiene la implementación de SIP principal de Lync</span><span class="sxs-lookup"><span data-stu-id="c5bea-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="c5bea-155">Proxy de datos = usado para conferencias perimetrales</span><span class="sxs-lookup"><span data-stu-id="c5bea-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="c5bea-156">LySS = servicio de almacenamiento de Lync</span><span class="sxs-lookup"><span data-stu-id="c5bea-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="c5bea-157">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="c5bea-157">Front-end Servers</span></span>

<span data-ttu-id="c5bea-158">Los siguientes destinos KHI recomendados son específicos de los servidores front-end, además del estado básico de los componentes:</span><span class="sxs-lookup"><span data-stu-id="c5bea-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5bea-159">Área funcional</span><span class="sxs-lookup"><span data-stu-id="c5bea-159">Functional area</span></span></th>
<th><span data-ttu-id="c5bea-160">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="c5bea-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5bea-161">AS/AV/MENSAJERÍA INSTANTÁNEA MCU</span><span class="sxs-lookup"><span data-stu-id="c5bea-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="c5bea-162">Estado &lt;de mantenimiento MCU 2</span><span class="sxs-lookup"><span data-stu-id="c5bea-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5bea-163">Componentes Web</span><span class="sxs-lookup"><span data-stu-id="c5bea-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="c5bea-164">Tiempo de espera de anuncio de &lt;expansión de lista de distribución 0</span><span class="sxs-lookup"><span data-stu-id="c5bea-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="c5bea-165">Errores de ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="c5bea-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="c5bea-166">Errores de LIS = 0</span><span class="sxs-lookup"><span data-stu-id="c5bea-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="c5bea-167">Errores &lt; de autenticación 1/s</span><span class="sxs-lookup"><span data-stu-id="c5bea-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c5bea-168">Solicitudes ASP.NET V4 rechazadas = 0</span><span class="sxs-lookup"><span data-stu-id="c5bea-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5bea-169">Pila SIP</span><span class="sxs-lookup"><span data-stu-id="c5bea-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="c5bea-170">Promedio de procesamiento &lt; de mensajes entrantes de 1 s</span><span class="sxs-lookup"><span data-stu-id="c5bea-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="c5bea-171">Respuestas entrantes &lt; quitadas 1/s solicitudes &lt; entrantes descartadas 1/s</span><span class="sxs-lookup"><span data-stu-id="c5bea-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c5bea-172">Latencia &lt; de cola 100 ms</span><span class="sxs-lookup"><span data-stu-id="c5bea-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="c5bea-173">Latencia &lt; del procedimiento almacenado 100 ms</span><span class="sxs-lookup"><span data-stu-id="c5bea-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="c5bea-174">Solicitudes limitadas = 0</span><span class="sxs-lookup"><span data-stu-id="c5bea-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="c5bea-175">Errores &lt; de autenticación 1/s</span><span class="sxs-lookup"><span data-stu-id="c5bea-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c5bea-176">Se agotó el tiempo de &lt; espera de los mensajes entrantes 2</span><span class="sxs-lookup"><span data-stu-id="c5bea-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="c5bea-177">Promedio de mensajes entrantes &lt; en espera 1 s</span><span class="sxs-lookup"><span data-stu-id="c5bea-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="c5bea-178">Conexiones &lt; controladas por flujo 2</span><span class="sxs-lookup"><span data-stu-id="c5bea-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="c5bea-179">Retraso &lt; de cola de salida promedio 2 s</span><span class="sxs-lookup"><span data-stu-id="c5bea-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5bea-180">LySS</span><span class="sxs-lookup"><span data-stu-id="c5bea-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="c5bea-181">% de espacio usado por la base de &lt; BD de servicio de almacenamiento 80</span><span class="sxs-lookup"><span data-stu-id="c5bea-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="c5bea-182">#de errores de replicación de réplica = 0</span><span class="sxs-lookup"><span data-stu-id="c5bea-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="c5bea-183">#eventos de pérdida de datos = 0</span><span class="sxs-lookup"><span data-stu-id="c5bea-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5bea-184">SQL</span><span class="sxs-lookup"><span data-stu-id="c5bea-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="c5bea-185">Esperanza &gt; de vida de la página 300 s</span><span class="sxs-lookup"><span data-stu-id="c5bea-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="c5bea-186">Solicitudes de lotes/ &lt; s 2500</span><span class="sxs-lookup"><span data-stu-id="c5bea-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="c5bea-187">Servidores SQL back-end</span><span class="sxs-lookup"><span data-stu-id="c5bea-187">Backend SQL Servers</span></span>

<span data-ttu-id="c5bea-188">Los siguientes destinos KHI recomendados son específicos de los servidores SQL Server además del estado básico de los componentes:</span><span class="sxs-lookup"><span data-stu-id="c5bea-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5bea-189">Área funcional</span><span class="sxs-lookup"><span data-stu-id="c5bea-189">Functional area</span></span></th>
<th><span data-ttu-id="c5bea-190">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="c5bea-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5bea-191">SQL</span><span class="sxs-lookup"><span data-stu-id="c5bea-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="c5bea-192">Esperanza &gt; de vida de la página 300 s</span><span class="sxs-lookup"><span data-stu-id="c5bea-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="c5bea-193">Solicitudes de lotes/ &lt; s 2500</span><span class="sxs-lookup"><span data-stu-id="c5bea-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="c5bea-194">Servidores de mediación</span><span class="sxs-lookup"><span data-stu-id="c5bea-194">Mediation Servers</span></span>

<span data-ttu-id="c5bea-195">Los siguientes destinos KHI recomendados son específicos de los servidores de mediación, además del estado básico de los componentes:</span><span class="sxs-lookup"><span data-stu-id="c5bea-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5bea-196">Área funcional</span><span class="sxs-lookup"><span data-stu-id="c5bea-196">Functional area</span></span></th>
<th><span data-ttu-id="c5bea-197">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="c5bea-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5bea-198">Servicio servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="c5bea-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="c5bea-199">Índice de error de llamada de carga = 0</span><span class="sxs-lookup"><span data-stu-id="c5bea-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="c5bea-200">Llamadas fallidas debido al &lt;proxy 10</span><span class="sxs-lookup"><span data-stu-id="c5bea-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="c5bea-201">Llamadas fallidas debido a &lt;la puerta de enlace 10</span><span class="sxs-lookup"><span data-stu-id="c5bea-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="c5bea-202">Llamadas (dentro o salida) rechazadas = 0</span><span class="sxs-lookup"><span data-stu-id="c5bea-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="c5bea-203">Candidatos a medios ausentes = 0</span><span class="sxs-lookup"><span data-stu-id="c5bea-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="c5bea-204">Errores de comprobación de conectividad de medios = 0</span><span class="sxs-lookup"><span data-stu-id="c5bea-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="c5bea-205">Servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="c5bea-205">Edge Servers</span></span>

<span data-ttu-id="c5bea-206">Los siguientes destinos KHI recomendados son específicos de los servidores perimetrales además del estado básico de los componentes:</span><span class="sxs-lookup"><span data-stu-id="c5bea-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5bea-207">Área funcional</span><span class="sxs-lookup"><span data-stu-id="c5bea-207">Functional area</span></span></th>
<th><span data-ttu-id="c5bea-208">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="c5bea-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5bea-209">Autenticación de AV</span><span class="sxs-lookup"><span data-stu-id="c5bea-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="c5bea-210">Solicitudes &lt; erróneas 20/s</span><span class="sxs-lookup"><span data-stu-id="c5bea-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5bea-211">Borde AV</span><span class="sxs-lookup"><span data-stu-id="c5bea-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="c5bea-212">Errores &lt;de auth. 20/s</span><span class="sxs-lookup"><span data-stu-id="c5bea-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="c5bea-213">Errores &lt;de asignación de 20/s</span><span class="sxs-lookup"><span data-stu-id="c5bea-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="c5bea-214">Paquetes descartados &lt;300/s</span><span class="sxs-lookup"><span data-stu-id="c5bea-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5bea-215">Proxy de datos</span><span class="sxs-lookup"><span data-stu-id="c5bea-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="c5bea-216">Conexiones &lt; de servidor limitado 3</span><span class="sxs-lookup"><span data-stu-id="c5bea-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="c5bea-217">El sistema está limitando &lt;1</span><span class="sxs-lookup"><span data-stu-id="c5bea-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5bea-218">Pila SIP</span><span class="sxs-lookup"><span data-stu-id="c5bea-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="c5bea-219">Descartar &lt; conexiones por límite 1</span><span class="sxs-lookup"><span data-stu-id="c5bea-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="c5bea-220">Se agotó el tiempo &lt;de espera de envíos 10</span><span class="sxs-lookup"><span data-stu-id="c5bea-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="c5bea-221">Conexiones &lt;controladas por flujo 100</span><span class="sxs-lookup"><span data-stu-id="c5bea-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="c5bea-222">Solicitudes entrantes &lt; descartadas 1/s</span><span class="sxs-lookup"><span data-stu-id="c5bea-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c5bea-223">Promedio de procesamiento &lt; de mensajes 3 por segundo</span><span class="sxs-lookup"><span data-stu-id="c5bea-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5bea-224">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5bea-224">See Also</span></span>


[<span data-ttu-id="c5bea-225">Guía de redes de Lync Server</span><span class="sxs-lookup"><span data-stu-id="c5bea-225">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="c5bea-226">Indicadores clave de estado: la base para mantener los servidores de Lync en buen estado</span><span class="sxs-lookup"><span data-stu-id="c5bea-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="c5bea-227">Metodología de calidad de llamadas de Lync</span><span class="sxs-lookup"><span data-stu-id="c5bea-227">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

