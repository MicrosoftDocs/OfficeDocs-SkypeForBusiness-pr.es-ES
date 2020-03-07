---
title: Ver la utilización de Microsoft Teams en Power BI con datos del CQD
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Use los informes de uso de los equipos de Power BI para realizar un seguimiento del uso de Microsoft Teams en su organización.
ms.openlocfilehash: d22f37bb230ecbaa3cf6c33c2ba43f5ea92afaad
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559613"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="75f4a-103">Ver la utilización de Microsoft Teams en Power BI con datos del CQD</span><span class="sxs-lookup"><span data-stu-id="75f4a-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="75f4a-104">Novedades de marzo de 2020 hemos agregado un informe de uso de Teams a nuestras [plantillas de consultas descargables de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="75f4a-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="75f4a-105">Estos nuevos informes de uso de equipos le permiten ver cómo (y cuántos) usan los usuarios Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="75f4a-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams.</span></span> <span data-ttu-id="75f4a-106">Estos informes están diseñados para ser una ubicación centralizada que los administradores y los líderes de negocios pueden ir rápidamente a para esta información.</span><span class="sxs-lookup"><span data-stu-id="75f4a-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="75f4a-107">El informe de uso de Power BI para equipos consta de dos informes principales: Resumen de **[recuento de llamadas](#call-count-summary-report)** y Resumen de **[minutos de audio](#audio-minutes-summary-report)**.</span><span class="sxs-lookup"><span data-stu-id="75f4a-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="75f4a-108">Los informes de [uso diario](#daily-usage) y [detalles de audio regionales](#regional-audio-details) se reproducen cuando un usuario aprovecha los informes de análisis detallado, que se indican en las siguientes descripciones.</span><span class="sxs-lookup"><span data-stu-id="75f4a-108">The [Daily Usage](#daily-usage) and [Regional Audio Details](#regional-audio-details) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="75f4a-109">Los datos de compilación y de subred se deben rellenar para proporcionar capacidades regionales y de filtrado de red.</span><span class="sxs-lookup"><span data-stu-id="75f4a-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="75f4a-110">Informe de Resumen de la cantidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="75f4a-110">Call Count Summary Report</span></span>

<span data-ttu-id="75f4a-111">La Página principal (Resumen de recuento de llamadas) proporciona inmediatamente el número de sesiones de audio, vídeo y pantalla compartida durante los últimos 30 y 90 días, como se indica en el título de la sección.</span><span class="sxs-lookup"><span data-stu-id="75f4a-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="75f4a-112">Los datos que se muestran inicialmente son para la organización como un todo y se pueden filtrar con las opciones de lista desplegable segmentación de datos en el lado izquierdo de la página.</span><span class="sxs-lookup"><span data-stu-id="75f4a-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="75f4a-114">A la derecha de la lista desplegable segmentación, el número de llamadas por tipo de medio se divide en una vista interna o externa en los últimos treinta días.</span><span class="sxs-lookup"><span data-stu-id="75f4a-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="75f4a-115">Podemos ver a través de la captura de pantalla anterior que hay más llamadas que ocurren desde ubicaciones organizativas externas, lo cual tiene sentido considerar el entorno global actual.</span><span class="sxs-lookup"><span data-stu-id="75f4a-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="75f4a-116">![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="75f4a-116">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="75f4a-117">A la derecha del cuadro recuento de tipos de medios, tenemos el recuento mensual de llamadas por tipo de medio para los últimos 90 días.</span><span class="sxs-lookup"><span data-stu-id="75f4a-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="75f4a-118">Se puede desplazar por cada columna y tipo de medio para mostrar el recuento de un mes anterior o el mes actual hasta la fecha, proporcionando información sobre la tendencia de uso.</span><span class="sxs-lookup"><span data-stu-id="75f4a-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="75f4a-119">![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="75f4a-119">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report3.png)</span></span>

1. <span data-ttu-id="75f4a-120">El gráfico del centro funciona como el gráfico de 90, pero proporciona una vista de uso diario para los últimos 30 días y permite a un usuario hacer clic con el botón secundario y explorar en profundidad los detalles de un día específico.</span><span class="sxs-lookup"><span data-stu-id="75f4a-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="75f4a-121">![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="75f4a-121">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="75f4a-122">En la sección inferior izquierda de la página, encontrarás una tabla que proporciona valores totales para cada tipo de medio en el último año.</span><span class="sxs-lookup"><span data-stu-id="75f4a-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="75f4a-123">![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report5.png)</span><span class="sxs-lookup"><span data-stu-id="75f4a-123">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report5.png)</span></span>
  
<span data-ttu-id="75f4a-124">La tabla también tiene un desglose disponible en el que puede ver un desglose de datos regionales.</span><span class="sxs-lookup"><span data-stu-id="75f4a-124">The table also has an available drill down where you can see a regional data breakdown.</span></span>
    <span data-ttu-id="75f4a-125">![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="75f4a-125">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report6.png)</span></span>

<span data-ttu-id="75f4a-126">A la derecha de la tabla, un gráfico de barras muestra los clientes con el mayor uso (llamadas/transmisiones) en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="75f4a-126">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="75f4a-127">![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="75f4a-127">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report7.png)</span></span>


<span data-ttu-id="75f4a-128">El último conjunto de gráficos de esta página muestra cada tipo de medio individualmente, con un desglose que muestra el uso de la Conferencia y el P2P.</span><span class="sxs-lookup"><span data-stu-id="75f4a-128">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="75f4a-129">Los siguientes gráficos muestran que hay un número mucho más alto de uso de la Conferencia comparado con el P2P.</span><span class="sxs-lookup"><span data-stu-id="75f4a-129">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="75f4a-130">![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="75f4a-130">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="75f4a-131">Informe Resumen de minutos de audio</span><span class="sxs-lookup"><span data-stu-id="75f4a-131">Audio Minutes Summary Report</span></span>

<span data-ttu-id="75f4a-132">En el informe de uso de los minutos de audio, el uso total de minutos se proporciona a través de varias vistas diferentes.</span><span class="sxs-lookup"><span data-stu-id="75f4a-132">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="75f4a-133">Tenemos el Resumen de uso de treinta días que aparece al lado de las segmentaciones de forma tan fácil de usar cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="75f4a-133">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="75f4a-134">El número superior muestra el total de treinta días, con desgloses internos y externos por debajo de él.</span><span class="sxs-lookup"><span data-stu-id="75f4a-134">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="75f4a-136">El gráfico de barras superior derecha proporciona una vista yearlong del uso de audio en conferencia.</span><span class="sxs-lookup"><span data-stu-id="75f4a-136">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="75f4a-137">Desplace el puntero sobre el mes para mostrar los minutos de audio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="75f4a-137">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="75f4a-138">Para mostrar la diferencia en P2P y en el audio de las conferencias, el gráfico inferior izquierdo toma todo el audio del año pasado y lo divide entre los dos tipos.</span><span class="sxs-lookup"><span data-stu-id="75f4a-138">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

<span data-ttu-id="75f4a-139">![Captura de pantalla: informe](media/CQD-teams-utilization-report10.png) de Resumen de provincia de llamadas el último gráfico de la página de minutos de audio muestra el uso de minutos de audio en una superposición de mapa global.</span><span class="sxs-lookup"><span data-stu-id="75f4a-139">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report10.png) The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="75f4a-140">Este gráfico solo funciona si los datos de compilación y de subred se cargan en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="75f4a-140">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="75f4a-141">El gráfico circular superpuesto en el mapa se puede profundizar y, posteriormente, proporcionar el uso de audio regional.</span><span class="sxs-lookup"><span data-stu-id="75f4a-141">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report11.png)

## <a name="drill-through-capabilities"></a><span data-ttu-id="75f4a-143">Capacidades de obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="75f4a-143">Drill-through capabilities</span></span>

<span data-ttu-id="75f4a-144">Como se indicó anteriormente, los usuarios pueden profundizar en los informes de uso diarios y regionales.</span><span class="sxs-lookup"><span data-stu-id="75f4a-144">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="75f4a-145">Uso diario</span><span class="sxs-lookup"><span data-stu-id="75f4a-145">Daily Usage</span></span>

<span data-ttu-id="75f4a-146">El informe de uso diario permite que un administrador identifique los períodos de consumo máximo durante un día.</span><span class="sxs-lookup"><span data-stu-id="75f4a-146">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="75f4a-147">Además del uso, también podemos capturar los comentarios y la opinión general del usuario para ese día.</span><span class="sxs-lookup"><span data-stu-id="75f4a-147">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="75f4a-149">Estos datos se pueden usar para identificar regiones con problemas durante los tiempos de consumo máximo.</span><span class="sxs-lookup"><span data-stu-id="75f4a-149">This data can be used to identify regions having problems during peak consumption times.</span></span>

1.  <span data-ttu-id="75f4a-150">En la página de Resumen de cuenta de llamadas, profundice en una fecha específica.</span><span class="sxs-lookup"><span data-stu-id="75f4a-150">On the Call Count Summary page, drill-through on a specific date.</span></span> <span data-ttu-id="75f4a-151">Mire la tendencia por hora de ese día para averiguar el pico de uso.</span><span class="sxs-lookup"><span data-stu-id="75f4a-151">Look at the hourly trend that day to find the peak utilization.</span></span>
  <span data-ttu-id="75f4a-152">![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report13.png)</span><span class="sxs-lookup"><span data-stu-id="75f4a-152">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report13.png)</span></span>

2.  <span data-ttu-id="75f4a-153">Haga clic en la columna de ese día para mostrar las métricas de esa hora.</span><span class="sxs-lookup"><span data-stu-id="75f4a-153">Click on the column for that day to display metrics for that hour.</span></span>
  <span data-ttu-id="75f4a-154">![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="75f4a-154">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report14.png)</span></span>
    
    1.  <span data-ttu-id="75f4a-155">La tabla que se encuentra debajo del gráfico mostrará las métricas de esa hora.</span><span class="sxs-lookup"><span data-stu-id="75f4a-155">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="75f4a-156">Se puede ordenar por cualquier encabezado de columna; sin embargo, nos interesaría encontrar áreas problemáticas.</span><span class="sxs-lookup"><span data-stu-id="75f4a-156">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
        ![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report15.png)
    
    2.  <span data-ttu-id="75f4a-158">Vemos que la región de IND está experimentando un bajo rendimiento de video en las conferencias durante este período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="75f4a-158">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="75f4a-159">Posteriormente, los informes de Microsoft QER del CQD se pueden usar para restringir la ubicación problemática a medida que se identifica la región y el intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="75f4a-159">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="regional-audio-details"></a><span data-ttu-id="75f4a-160">Detalles de audio regional</span><span class="sxs-lookup"><span data-stu-id="75f4a-160">Regional Audio Details</span></span>

<span data-ttu-id="75f4a-161">Los detalles de audio regionales detallan específicamente el uso de minutos de audio en la región seleccionada.</span><span class="sxs-lookup"><span data-stu-id="75f4a-161">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="75f4a-162">Los usuarios con acceso al CQD pueden ver las tendencias de uso para el audio P2P y de conferencia dentro de la región seleccionada.</span><span class="sxs-lookup"><span data-stu-id="75f4a-162">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="75f4a-163">En la página Resumen de cuenta de llamadas, profundice en la tabla como región específica.</span><span class="sxs-lookup"><span data-stu-id="75f4a-163">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="75f4a-164">![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="75f4a-164">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="75f4a-165">Seleccione la fila con la región que necesita la información adicional.</span><span class="sxs-lookup"><span data-stu-id="75f4a-165">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="75f4a-166">![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="75f4a-166">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="75f4a-167">Las tendencias de datos muestran un número significativo de minutos que se usan en la red interna, con conferencias que superan mucho el uso de P2P.</span><span class="sxs-lookup"><span data-stu-id="75f4a-167">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="75f4a-168">![Captura de pantalla: informe Resumen de provincia de llamada](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="75f4a-168">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="75f4a-169">La tendencia regional de audio puede usarse para mostrar cómo afectan los usuarios a las influencias externas del mundo.</span><span class="sxs-lookup"><span data-stu-id="75f4a-169">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="75f4a-170">En concreto, en este momento, esperamos que el uso externo de las regiones EMEA y APAC aumente con personas a las que se les pidió que trabajaran de forma remota.</span><span class="sxs-lookup"><span data-stu-id="75f4a-170">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>



## <a name="related-topics"></a><span data-ttu-id="75f4a-171">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="75f4a-171">Related topics</span></span>

[<span data-ttu-id="75f4a-172">Dimensiones y medidas disponibles en el Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="75f4a-172">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="75f4a-173">Clasificación de la secuencia en el Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="75f4a-173">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="75f4a-174">Configurar el análisis de llamadas de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="75f4a-174">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="75f4a-175">Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas</span><span class="sxs-lookup"><span data-stu-id="75f4a-175">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="75f4a-176">Análisis de llamadas y Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="75f4a-176">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 