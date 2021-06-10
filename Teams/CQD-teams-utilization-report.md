---
title: Ver Microsoft Teams uso en Power BI con datos CQD
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Use los Teams de uso Power BI para obtener acceso Microsoft Teams datos del Panel de calidad de llamadas (CQD) para realizar un seguimiento Microsoft Teams uso en su organización.
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095044"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="4de1b-103">Ver Microsoft Teams uso en Power BI con datos CQD</span><span class="sxs-lookup"><span data-stu-id="4de1b-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="4de1b-104">Como novedad en marzo de 2020, hemos agregado un informe de uso Teams a nuestras plantillas de consulta de Power BI descarga para [CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="4de1b-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="4de1b-105">Este nuevo Teams de uso de llamadas le permite ver cómo (y cuánto) usan los usuarios Microsoft Teams mediante el acceso Teams datos del Panel de calidad de llamadas (CQD).</span><span class="sxs-lookup"><span data-stu-id="4de1b-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="4de1b-106">Estos informes están diseñados para ser una ubicación centralizada a la que los administradores y los líderes empresariales pueden ir rápidamente para obtener estos datos.</span><span class="sxs-lookup"><span data-stu-id="4de1b-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="4de1b-107">El Teams de uso Power BI consta de dos informes **[principales:](#call-count-summary-report)** Resumen del recuento de llamadas y **[Resumen de minutos de audio.](#audio-minutes-summary-report)**</span><span class="sxs-lookup"><span data-stu-id="4de1b-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="4de1b-108">Los [informes Uso](#daily-usage)diario, [](#conference-details) Detalles [](#user-list) regionales de [audio,](#regional-audio-details)Detalles de conferencia e Lista de usuarios se reproducen cuando un usuario aprovecha los informes detallados, que se indican en las descripciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="4de1b-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="4de1b-109">Los datos de creación y subred deben rellenarse para proporcionar funcionalidades de filtrado de red y regionales.</span><span class="sxs-lookup"><span data-stu-id="4de1b-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="4de1b-110">Informe de resumen del recuento de llamadas</span><span class="sxs-lookup"><span data-stu-id="4de1b-110">Call Count Summary Report</span></span>

<span data-ttu-id="4de1b-111">La página principal (Resumen del recuento de llamadas) proporciona inmediatamente el número de sesiones de audio, vídeo y uso compartido de pantalla durante los últimos 30 y 90 días, como se indica en el título de la sección.</span><span class="sxs-lookup"><span data-stu-id="4de1b-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="4de1b-112">Los datos mostrados inicialmente son para toda la organización y se pueden filtrar con las opciones desplegables de segmentación de datos en el lado izquierdo de la página.</span><span class="sxs-lookup"><span data-stu-id="4de1b-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="4de1b-114">A la derecha de los menús desplegables de segmentación de datos, el número de llamadas por tipo de medios se desglosa a una vista interna o externa en los últimos treinta días.</span><span class="sxs-lookup"><span data-stu-id="4de1b-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="4de1b-115">A través de la captura de pantalla anterior, podemos ver que hay más llamadas desde ubicaciones externas a la organización, lo que tiene sentido teniendo en cuenta el entorno global actual.</span><span class="sxs-lookup"><span data-stu-id="4de1b-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="4de1b-116">![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="4de1b-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="4de1b-117">A la derecha del cuadro de recuento de tipo multimedia, tenemos el recuento de llamadas mensuales por tipo de medio durante los últimos 90 días.</span><span class="sxs-lookup"><span data-stu-id="4de1b-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="4de1b-118">Se puede mantener el puntero sobre cada columna y tipo de elemento multimedia para mostrar el recuento de un mes anterior o del mes actual hasta la fecha, proporcionando información de tendencia de uso.</span><span class="sxs-lookup"><span data-stu-id="4de1b-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="4de1b-119">![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="4de1b-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="4de1b-120">El gráfico central funciona como lo hace el gráfico de 90 días, pero proporciona una vista de uso diario durante los últimos 30 días y permite al usuario hacer clic con el botón derecho y explorar detalles para un día específico.</span><span class="sxs-lookup"><span data-stu-id="4de1b-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="4de1b-121">![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="4de1b-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="4de1b-122">En la sección inferior izquierda de la página, encontrará una tabla que proporciona valores totales para cada tipo de elemento multimedia durante el año pasado.</span><span class="sxs-lookup"><span data-stu-id="4de1b-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="4de1b-123">![Captura de pantalla: Teams de informes de ](media/CQD-teams-utilization-report5.png) ![ uso: Teams de uso](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="4de1b-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="4de1b-124">A la derecha de la tabla, un gráfico de barras muestra los clientes con más uso (llamadas/transmisiones) durante los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="4de1b-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="4de1b-125">![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="4de1b-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="4de1b-126">El último conjunto de gráficos de esta página muestra cada tipo de elemento multimedia individualmente, con un desglose que muestra el uso de conferencias y P2P.</span><span class="sxs-lookup"><span data-stu-id="4de1b-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="4de1b-127">Los gráficos siguientes muestran que hay un número significativamente mayor de uso de conferencias en comparación con P2P.</span><span class="sxs-lookup"><span data-stu-id="4de1b-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="4de1b-128">![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="4de1b-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="4de1b-129">Informe de resumen de minutos de audio</span><span class="sxs-lookup"><span data-stu-id="4de1b-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="4de1b-130">En el informe de uso minutos de audio, el uso total de minutos se proporciona a través de varias vistas diferentes.</span><span class="sxs-lookup"><span data-stu-id="4de1b-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="4de1b-131">Tenemos el resumen de uso de treinta días que se muestra junto a las segmentaciones de datos como fácil de usar en los cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="4de1b-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="4de1b-132">El número superior muestra el total de treinta días, con desgloses internos y externos por debajo.</span><span class="sxs-lookup"><span data-stu-id="4de1b-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="4de1b-134">El gráfico de barras superior derecha proporciona una vista de todo el año del uso de audio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4de1b-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="4de1b-135">Mantenga el puntero sobre el mes para mostrar los minutos de audio de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="4de1b-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="4de1b-136">Para mostrar la diferencia en el audio de conferencia y P2P, el gráfico inferior izquierdo toma todo el audio del año pasado y lo divide entre los dos tipos.</span><span class="sxs-lookup"><span data-stu-id="4de1b-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="4de1b-138">El último gráfico de la página Minutos de audio muestra el uso de minutos de audio en una superposición de mapa global.</span><span class="sxs-lookup"><span data-stu-id="4de1b-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="4de1b-139">Este gráfico solo funcionará si los datos de creación y subred se cargan en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="4de1b-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="4de1b-140">El gráfico circular superpuesto en el mapa se puede explorar en profundidad y, posteriormente, proporcionar el uso de audio regional.</span><span class="sxs-lookup"><span data-stu-id="4de1b-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="4de1b-142">Capacidades de obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="4de1b-142">Drill-through capabilities</span></span>

<span data-ttu-id="4de1b-143">Como se ha indicado anteriormente, los usuarios pueden explorar en profundidad los informes de uso diarios y regionales.</span><span class="sxs-lookup"><span data-stu-id="4de1b-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="4de1b-144">Uso diario</span><span class="sxs-lookup"><span data-stu-id="4de1b-144">Daily Usage</span></span>

<span data-ttu-id="4de1b-145">El informe Uso diario permite a un administrador identificar los períodos de consumo máximo durante el transcurso de un día.</span><span class="sxs-lookup"><span data-stu-id="4de1b-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="4de1b-146">Además del uso, también podemos capturar el sentimiento general del usuario y los comentarios de ese día.</span><span class="sxs-lookup"><span data-stu-id="4de1b-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="4de1b-148">El informe Uso diario muestra el número de recursos compartidos de audio, vídeo y pantalla del día seleccionado con la capacidad adicional de diferenciar entre conectividad interna y externa.</span><span class="sxs-lookup"><span data-stu-id="4de1b-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="4de1b-149">Un desglose de conferencia y punto a punto está a la derecha inmediata del cuadro total de la modalidad.</span><span class="sxs-lookup"><span data-stu-id="4de1b-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="4de1b-150">La parte superior derecha del informe proporciona una lista de conferencias con su id. asociado y los participantes del día.</span><span class="sxs-lookup"><span data-stu-id="4de1b-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="4de1b-151">La lista de conferencias también proporciona un detalle adicional al informe Detalles de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="4de1b-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="4de1b-152">REEMPLAZAR GRÁFICO</span><span class="sxs-lookup"><span data-stu-id="4de1b-152">REPLACE GRAPHIC</span></span>

![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="4de1b-154">El gráfico de barras del área central permite al usuario identificar períodos de consumo máximo durante el transcurso de un día.</span><span class="sxs-lookup"><span data-stu-id="4de1b-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="4de1b-155">Los usuarios pueden explorar en profundidad la hora representada en el gráfico que presentará el informe lista de usuarios para la hora.</span><span class="sxs-lookup"><span data-stu-id="4de1b-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="4de1b-156">A la derecha del gráfico de barras, los comentarios de los usuarios se presentan en un formato visual.</span><span class="sxs-lookup"><span data-stu-id="4de1b-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="4de1b-157">Aunque el sentimiento del usuario puede ser subjetivo, proporciona información que se puede usar para identificar posibles problemas.</span><span class="sxs-lookup"><span data-stu-id="4de1b-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="4de1b-158">La tabla inferior proporciona un rango de métricas para el día.</span><span class="sxs-lookup"><span data-stu-id="4de1b-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="4de1b-159">Los porcentajes bajos junto con las tasas de errores pueden proporcionar a un administrador áreas potenciales de mejora.</span><span class="sxs-lookup"><span data-stu-id="4de1b-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="4de1b-160">Cada hora también se puede seleccionar individualmente, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="4de1b-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="4de1b-161">Estos datos se pueden usar para identificar las regiones que tienen problemas durante las horas de máximo consumo.</span><span class="sxs-lookup"><span data-stu-id="4de1b-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="4de1b-162">Haga clic en la columna de ese día para mostrar las métricas de esa hora.</span><span class="sxs-lookup"><span data-stu-id="4de1b-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="4de1b-163">![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="4de1b-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="4de1b-164">La tabla debajo del gráfico mostrará las métricas de esa hora.</span><span class="sxs-lookup"><span data-stu-id="4de1b-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="4de1b-165">Esto se puede ordenar por cualquier encabezado de columna; sin embargo, nos interesaría encontrar áreas problemáticas.</span><span class="sxs-lookup"><span data-stu-id="4de1b-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="4de1b-167">Vemos que la región IND está experimentando un rendimiento de vídeo deficiente en las conferencias durante este período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="4de1b-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="4de1b-168">Posteriormente, los informes de QER de CQD de Microsoft se pueden usar para restringir la ubicación problemática a medida que se ha identificado la región y el período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="4de1b-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="4de1b-169">Detalles de la conferencia</span><span class="sxs-lookup"><span data-stu-id="4de1b-169">Conference Details</span></span>

<span data-ttu-id="4de1b-170">El informe Detalles de conferencia proporciona información adicional para las reuniones, desde una lista de asistentes, hasta los tipos de medios usados durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="4de1b-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="4de1b-171">Haga clic con el botón derecho en la barra del participante en el gráfico id. de conferencia de la página Uso diario para explorar los detalles de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="4de1b-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report24.png)

![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="4de1b-174">Podemos ver a los participantes en la conferencia, así como toda la información pertinente hasta la pérdida de paquetes y la vibración para ayudar con los posibles esfuerzos de solución de problemas en la tabla inferior.</span><span class="sxs-lookup"><span data-stu-id="4de1b-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="4de1b-176">Detalles del audio regional</span><span class="sxs-lookup"><span data-stu-id="4de1b-176">Regional Audio Details</span></span>

<span data-ttu-id="4de1b-177">En detalles de audio regionales se muestra específicamente el uso de minutos de audio para la región seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4de1b-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="4de1b-178">Los usuarios con acceso a CQD pueden ver las tendencias de uso de P2P y audio de conferencia en la región seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4de1b-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="4de1b-179">En la página Resumen del recuento de llamadas, puede explorar en profundidad como región específica a través de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4de1b-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="4de1b-180">![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="4de1b-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="4de1b-181">Seleccione la fila con la región para la que se necesita información adicional.</span><span class="sxs-lookup"><span data-stu-id="4de1b-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="4de1b-182">![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="4de1b-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="4de1b-183">Las tendencias de datos muestran un número significativo de minutos que se usan en la red interna, con conferencias que superan ampliamente el uso de P2P.</span><span class="sxs-lookup"><span data-stu-id="4de1b-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="4de1b-184">![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="4de1b-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="4de1b-185">La tendencia de audio regional se puede usar para mostrar cómo los usuarios se verán afectados por las influencias externas en el mundo.</span><span class="sxs-lookup"><span data-stu-id="4de1b-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="4de1b-186">En concreto, en este momento, esperamos que el uso externo de las regiones EMEA y APAC aumente con la razón de que se pida a las personas que trabajen de forma remota.</span><span class="sxs-lookup"><span data-stu-id="4de1b-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="4de1b-187">Lista de usuarios</span><span class="sxs-lookup"><span data-stu-id="4de1b-187">User List</span></span>

<span data-ttu-id="4de1b-188">La lista de usuarios proporciona, como es de esperar, información específica del usuario para una hora específica seleccionada por la persona que ve el informe.</span><span class="sxs-lookup"><span data-stu-id="4de1b-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="4de1b-189">El informe de lista de usuarios es accesible mediante una exploración en profundidad en el gráfico Tendencias por horas en el informe Uso diario.</span><span class="sxs-lookup"><span data-stu-id="4de1b-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="4de1b-190">Haga clic con el botón derecho en la hora en la que se necesita información adicional y seleccione Explorar y Lista de usuarios, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="4de1b-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="4de1b-192">El informe Lista de usuarios muestra la conectividad interna y externa a través del gráfico de anillos en el centro superior de la página.</span><span class="sxs-lookup"><span data-stu-id="4de1b-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="4de1b-193">Podemos ver que hay una gran cantidad de participación de Fuera de la red corporativa en la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="4de1b-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="4de1b-194">En la parte superior derecha del gráfico se muestra el número de llamadas realizadas por cada usuario en esa hora.</span><span class="sxs-lookup"><span data-stu-id="4de1b-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Captura de pantalla: Teams de uso de datos](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="4de1b-196">La tabla inferior proporciona información detallada para las sesiones en las que participó cada usuario durante esa hora.</span><span class="sxs-lookup"><span data-stu-id="4de1b-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="4de1b-197">La columna Tipo de error es útil para determinar qué provocó la colocación de una llamada.</span><span class="sxs-lookup"><span data-stu-id="4de1b-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="4de1b-198">Las columnas Capturar y Representar dispositivo son útiles para identificar por qué se ha notificado que una llamada tiene mala calidad.</span><span class="sxs-lookup"><span data-stu-id="4de1b-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="4de1b-199">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4de1b-199">Related topics</span></span>

[<span data-ttu-id="4de1b-200">Dimensiones y medidas disponibles en el Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="4de1b-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="4de1b-201">Clasificación de la secuencia en el Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="4de1b-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="4de1b-202">Configurar el análisis de llamadas de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="4de1b-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="4de1b-203">Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas</span><span class="sxs-lookup"><span data-stu-id="4de1b-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="4de1b-204">Análisis de llamadas y Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="4de1b-204">Call Analytics and Call Quality Dashboard</span></span>](./monitor-call-quality-qos.md)

[<span data-ttu-id="4de1b-205">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="4de1b-205">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
