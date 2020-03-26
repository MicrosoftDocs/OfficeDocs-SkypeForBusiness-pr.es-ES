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
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Use los informes de uso de los equipos de Power BI para realizar un seguimiento del uso de Microsoft Teams en su organización.
ms.openlocfilehash: efca39a89eecdf9d603a81a07d8529147f87698a
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978559"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="c81bd-103">Ver la utilización de Microsoft Teams en Power BI con datos del CQD</span><span class="sxs-lookup"><span data-stu-id="c81bd-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="c81bd-104">Novedades de marzo de 2020 hemos agregado un informe de uso de Teams a nuestras [plantillas de consultas descargables de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="c81bd-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="c81bd-105">Estos nuevos informes de uso de equipos le permiten ver cómo (y cuántos) usan los usuarios Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c81bd-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams.</span></span> <span data-ttu-id="c81bd-106">Estos informes están diseñados para ser una ubicación centralizada que los administradores y los líderes de negocios pueden ir rápidamente a para esta información.</span><span class="sxs-lookup"><span data-stu-id="c81bd-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="c81bd-107">El informe de uso de Power BI para equipos consta de dos informes principales: Resumen de **[recuento de llamadas](#call-count-summary-report)** y Resumen de **[minutos de audio](#audio-minutes-summary-report)**.</span><span class="sxs-lookup"><span data-stu-id="c81bd-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="c81bd-108">Los informes [uso diario](#daily-usage), [detalles de audio regional](#regional-audio-details), detalles de la [Conferencia](#conference-details) y lista de [usuarios](#user-list) entran en juego cuando un usuario aprovecha los informes de análisis detallado, que se indican en las descripciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="c81bd-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="c81bd-109">Los datos de compilación y de subred se deben rellenar para proporcionar capacidades regionales y de filtrado de red.</span><span class="sxs-lookup"><span data-stu-id="c81bd-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="c81bd-110">Informe de Resumen de la cantidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="c81bd-110">Call Count Summary Report</span></span>

<span data-ttu-id="c81bd-111">La Página principal (Resumen de recuento de llamadas) proporciona inmediatamente el número de sesiones de audio, vídeo y pantalla compartida durante los últimos 30 y 90 días, como se indica en el título de la sección.</span><span class="sxs-lookup"><span data-stu-id="c81bd-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="c81bd-112">Los datos que se muestran inicialmente son para la organización como un todo y se pueden filtrar con las opciones de lista desplegable segmentación de datos en el lado izquierdo de la página.</span><span class="sxs-lookup"><span data-stu-id="c81bd-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="c81bd-114">A la derecha de la lista desplegable segmentación, el número de llamadas por tipo de medio se divide en una vista interna o externa en los últimos treinta días.</span><span class="sxs-lookup"><span data-stu-id="c81bd-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="c81bd-115">Podemos ver a través de la captura de pantalla anterior que hay más llamadas que ocurren desde ubicaciones organizativas externas, lo cual tiene sentido considerar el entorno global actual.</span><span class="sxs-lookup"><span data-stu-id="c81bd-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="c81bd-116">![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="c81bd-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="c81bd-117">A la derecha del cuadro recuento de tipos de medios, tenemos el recuento mensual de llamadas por tipo de medio para los últimos 90 días.</span><span class="sxs-lookup"><span data-stu-id="c81bd-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="c81bd-118">Se puede desplazar por cada columna y tipo de medio para mostrar el recuento de un mes anterior o el mes actual hasta la fecha, proporcionando información sobre la tendencia de uso.</span><span class="sxs-lookup"><span data-stu-id="c81bd-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="c81bd-119">![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="c81bd-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="c81bd-120">El gráfico del centro funciona como el gráfico de 90, pero proporciona una vista de uso diario para los últimos 30 días y permite a un usuario hacer clic con el botón secundario y explorar en profundidad los detalles de un día específico.</span><span class="sxs-lookup"><span data-stu-id="c81bd-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="c81bd-121">![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="c81bd-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="c81bd-122">En la sección inferior izquierda de la página, encontrarás una tabla que proporciona valores totales para cada tipo de medio en el último año.</span><span class="sxs-lookup"><span data-stu-id="c81bd-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="c81bd-123">![Captura de pantalla: informes](media/CQD-teams-utilization-report5.png) ![de uso de equipos captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="c81bd-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="c81bd-124">A la derecha de la tabla, un gráfico de barras muestra los clientes con el mayor uso (llamadas/transmisiones) en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="c81bd-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="c81bd-125">![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="c81bd-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="c81bd-126">El último conjunto de gráficos de esta página muestra cada tipo de medio individualmente, con un desglose que muestra el uso de la Conferencia y el P2P.</span><span class="sxs-lookup"><span data-stu-id="c81bd-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="c81bd-127">Los siguientes gráficos muestran que hay un número mucho más alto de uso de la Conferencia comparado con el P2P.</span><span class="sxs-lookup"><span data-stu-id="c81bd-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="c81bd-128">![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="c81bd-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="c81bd-129">Informe Resumen de minutos de audio</span><span class="sxs-lookup"><span data-stu-id="c81bd-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="c81bd-130">En el informe de uso de los minutos de audio, el uso total de minutos se proporciona a través de varias vistas diferentes.</span><span class="sxs-lookup"><span data-stu-id="c81bd-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="c81bd-131">Tenemos el Resumen de uso de treinta días que aparece al lado de las segmentaciones de forma tan fácil de usar cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="c81bd-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="c81bd-132">El número superior muestra el total de treinta días, con desgloses internos y externos por debajo de él.</span><span class="sxs-lookup"><span data-stu-id="c81bd-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="c81bd-134">El gráfico de barras superior derecha proporciona una vista yearlong del uso de audio en conferencia.</span><span class="sxs-lookup"><span data-stu-id="c81bd-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="c81bd-135">Desplace el puntero sobre el mes para mostrar los minutos de audio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="c81bd-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="c81bd-136">Para mostrar la diferencia en P2P y en el audio de las conferencias, el gráfico inferior izquierdo toma todo el audio del año pasado y lo divide entre los dos tipos.</span><span class="sxs-lookup"><span data-stu-id="c81bd-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="c81bd-138">El último gráfico de la página de minutos de audio muestra el uso de minutos de audio en una superposición de mapa global.</span><span class="sxs-lookup"><span data-stu-id="c81bd-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="c81bd-139">Este gráfico solo funciona si los datos de compilación y de subred se cargan en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="c81bd-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="c81bd-140">El gráfico circular superpuesto en el mapa se puede profundizar y, posteriormente, proporcionar el uso de audio regional.</span><span class="sxs-lookup"><span data-stu-id="c81bd-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="c81bd-142">Capacidades de obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="c81bd-142">Drill-through capabilities</span></span>

<span data-ttu-id="c81bd-143">Como se indicó anteriormente, los usuarios pueden profundizar en los informes de uso diarios y regionales.</span><span class="sxs-lookup"><span data-stu-id="c81bd-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="c81bd-144">Uso diario</span><span class="sxs-lookup"><span data-stu-id="c81bd-144">Daily Usage</span></span>

<span data-ttu-id="c81bd-145">El informe de uso diario permite que un administrador identifique los períodos de consumo máximo durante un día.</span><span class="sxs-lookup"><span data-stu-id="c81bd-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="c81bd-146">Además del uso, también podemos capturar los comentarios y la opinión general del usuario para ese día.</span><span class="sxs-lookup"><span data-stu-id="c81bd-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="c81bd-148">El informe de uso diario muestra el número de recursos compartidos de audio, vídeo y pantalla para el día seleccionado con la capacidad añadida de diferenciar entre conectividad interna y externa.</span><span class="sxs-lookup"><span data-stu-id="c81bd-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="c81bd-149">Un desglose de conferencia y de punto a punto es el derecho inmediato del total de moda.</span><span class="sxs-lookup"><span data-stu-id="c81bd-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="c81bd-150">La parte superior derecha del informe proporciona una lista de conferencias con el identificador y los participantes asociados para el día.</span><span class="sxs-lookup"><span data-stu-id="c81bd-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="c81bd-151">En la lista de conferencias se ofrece un desglose adicional del informe detalles de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="c81bd-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="c81bd-152">REEMPLAZAR GRÁFICO</span><span class="sxs-lookup"><span data-stu-id="c81bd-152">REPLACE GRAPHIC</span></span>

![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="c81bd-154">El gráfico de barras del área del centro permite que el usuario identifique los períodos de consumo máximo en el curso de un día.</span><span class="sxs-lookup"><span data-stu-id="c81bd-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="c81bd-155">Los usuarios pueden profundizar en la hora representada en el gráfico, que presentará el informe de la lista de usuarios para la hora.</span><span class="sxs-lookup"><span data-stu-id="c81bd-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="c81bd-156">A la derecha del gráfico de barras, los comentarios del usuario se presentan en un formato visual.</span><span class="sxs-lookup"><span data-stu-id="c81bd-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="c81bd-157">Si bien la opinión del usuario puede ser subjetiva, ofrece información que puede usarse para identificar posibles problemas.</span><span class="sxs-lookup"><span data-stu-id="c81bd-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="c81bd-158">La tabla inferior proporciona una variedad de métricas para el día.</span><span class="sxs-lookup"><span data-stu-id="c81bd-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="c81bd-159">Los porcentajes deficientes, junto con las tarifas de error, pueden proporcionar a un administrador las posibles áreas de mejora.</span><span class="sxs-lookup"><span data-stu-id="c81bd-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="c81bd-160">Cada hora también se puede seleccionar individualmente, tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="c81bd-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="c81bd-161">Estos datos se pueden usar para identificar regiones con problemas durante los tiempos de consumo máximo.</span><span class="sxs-lookup"><span data-stu-id="c81bd-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="c81bd-162">Haga clic en la columna de ese día para mostrar las métricas de esa hora.</span><span class="sxs-lookup"><span data-stu-id="c81bd-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="c81bd-163">![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="c81bd-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="c81bd-164">La tabla que se encuentra debajo del gráfico mostrará las métricas de esa hora.</span><span class="sxs-lookup"><span data-stu-id="c81bd-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="c81bd-165">Se puede ordenar por cualquier encabezado de columna; sin embargo, nos interesaría encontrar áreas problemáticas.</span><span class="sxs-lookup"><span data-stu-id="c81bd-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="c81bd-167">Vemos que la región de IND está experimentando un bajo rendimiento de video en las conferencias durante este período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="c81bd-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="c81bd-168">Posteriormente, los informes de Microsoft QER del CQD se pueden usar para restringir la ubicación problemática a medida que se identifica la región y el intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="c81bd-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="c81bd-169">Detalles de la Conferencia</span><span class="sxs-lookup"><span data-stu-id="c81bd-169">Conference Details</span></span>

<span data-ttu-id="c81bd-170">El informe detalles de la Conferencia proporciona información adicional sobre las reuniones, desde una lista de asistentes, a los tipos de medios utilizados durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="c81bd-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="c81bd-171">Haga clic con el botón derecho en una conferencia la barra de participantes en el gráfico de identificación de la Conferencia en la página uso diario para desglosar los detalles de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="c81bd-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report24.png)

![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="c81bd-174">Podemos ver a los participantes en la Conferencia, así como toda la información pertinente, a fin de perder el paquete y la vibración para ayudarle en los esfuerzos potenciales de solución de problemas en la tabla inferior.</span><span class="sxs-lookup"><span data-stu-id="c81bd-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="c81bd-176">Detalles de audio regional</span><span class="sxs-lookup"><span data-stu-id="c81bd-176">Regional Audio Details</span></span>

<span data-ttu-id="c81bd-177">Los detalles de audio regionales detallan específicamente el uso de minutos de audio en la región seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c81bd-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="c81bd-178">Los usuarios con acceso al CQD pueden ver las tendencias de uso para el audio P2P y de conferencia dentro de la región seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c81bd-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="c81bd-179">En la página Resumen de cuenta de llamadas, profundice en la tabla como región específica.</span><span class="sxs-lookup"><span data-stu-id="c81bd-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="c81bd-180">![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="c81bd-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="c81bd-181">Seleccione la fila con la región que necesita la información adicional.</span><span class="sxs-lookup"><span data-stu-id="c81bd-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="c81bd-182">![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="c81bd-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="c81bd-183">Las tendencias de datos muestran un número significativo de minutos que se usan en la red interna, con conferencias que superan mucho el uso de P2P.</span><span class="sxs-lookup"><span data-stu-id="c81bd-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="c81bd-184">![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="c81bd-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="c81bd-185">La tendencia regional de audio puede usarse para mostrar cómo afectan los usuarios a las influencias externas del mundo.</span><span class="sxs-lookup"><span data-stu-id="c81bd-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="c81bd-186">En concreto, en este momento, esperamos que el uso externo de las regiones EMEA y APAC aumente con personas a las que se les pidió que trabajaran de forma remota.</span><span class="sxs-lookup"><span data-stu-id="c81bd-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="c81bd-187">Lista de usuarios</span><span class="sxs-lookup"><span data-stu-id="c81bd-187">User List</span></span>

<span data-ttu-id="c81bd-188">La lista desplegable lista de usuarios proporciona, como puede esperar, información específica de usuario para una hora específica seleccionada por la persona que visualiza el informe.</span><span class="sxs-lookup"><span data-stu-id="c81bd-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="c81bd-189">El informe de la lista de usuarios es accesible a través de un desglose en el gráfico tendencias por hora en el informe de uso diario.</span><span class="sxs-lookup"><span data-stu-id="c81bd-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="c81bd-190">Haga clic con el botón secundario en la hora en la que se necesita información adicional y seleccione obtención de detalles y lista de usuarios, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="c81bd-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="c81bd-192">El informe lista de usuarios muestra la conectividad interna o externa a través del gráfico de anillos en la parte central superior de la página.</span><span class="sxs-lookup"><span data-stu-id="c81bd-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="c81bd-193">Podemos ver que hay una gran participación desde fuera de la red corporativa en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="c81bd-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="c81bd-194">En la parte superior derecha del gráfico se muestra el número de llamadas realizadas por cada usuario dentro de esa hora.</span><span class="sxs-lookup"><span data-stu-id="c81bd-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Captura de pantalla: informes de uso de Teams](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="c81bd-196">La tabla inferior proporciona información detallada sobre las sesiones en las que participó cada usuario durante esa hora.</span><span class="sxs-lookup"><span data-stu-id="c81bd-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="c81bd-197">La columna tipo de error es útil para determinar qué ha provocado la llamada.</span><span class="sxs-lookup"><span data-stu-id="c81bd-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="c81bd-198">Las columnas de los dispositivos de captura y representación son útiles para identificar por qué se notificó una llamada con una calidad deficiente.</span><span class="sxs-lookup"><span data-stu-id="c81bd-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c81bd-199">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c81bd-199">Related topics</span></span>

[<span data-ttu-id="c81bd-200">Dimensiones y medidas disponibles en el Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="c81bd-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="c81bd-201">Clasificación de la secuencia en el Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="c81bd-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="c81bd-202">Configurar el análisis de llamadas de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c81bd-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="c81bd-203">Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas</span><span class="sxs-lookup"><span data-stu-id="c81bd-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="c81bd-204">Análisis de llamadas y Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="c81bd-204">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 