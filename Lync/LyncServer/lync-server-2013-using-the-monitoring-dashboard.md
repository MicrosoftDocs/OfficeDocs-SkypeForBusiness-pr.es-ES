---
title: 'Lync Server 2013: uso del panel de supervisión'
description: 'Lync Server 2013: uso del panel de supervisión.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8a68fa1e55b7d0b8305c53802ddabaa904fa214
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556046"
---
# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="145ca-103">Uso del panel de supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="145ca-103">Using the Monitoring Dashboard in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="145ca-104">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="145ca-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="145ca-105">El panel de supervisión proporciona a los administradores una introducción rápida del uso del sistema y el estado del sistema de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="145ca-105">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="145ca-106">El panel está diseñado para mostrar una vista agregada de métricas del sistema clave y para hacerlo mostrando:</span><span class="sxs-lookup"><span data-stu-id="145ca-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="145ca-107">Totales del día actual.</span><span class="sxs-lookup"><span data-stu-id="145ca-107">Totals for the current day.</span></span> <span data-ttu-id="145ca-108">Tenga en cuenta que los valores que se muestran para el día actual representan datos que se han registrado desde medianoche hasta la hora actual (en función de la hora local del servidor de informes).</span><span class="sxs-lookup"><span data-stu-id="145ca-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="145ca-109">Esto significa que normalmente estará viendo los datos de un día parcial y no durante un período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="145ca-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="145ca-110">Por ejemplo, si la hora local del servidor es 8:00 A.M., verá ocho horas de datos porque hay ocho horas entre la medianoche y el tiempo actual de 8:00 AM.</span><span class="sxs-lookup"><span data-stu-id="145ca-110">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="145ca-111">Los totales de la semana y las tendencias de los totales de las seis últimas semanas.</span><span class="sxs-lookup"><span data-stu-id="145ca-111">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="145ca-112">Los totales del mes y los totales de tendencia para los últimos seis meses (solo para el uso del sistema).</span><span class="sxs-lookup"><span data-stu-id="145ca-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="145ca-113">Tenga en cuenta que puede usar el cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) para devolver la dirección URL usada para obtener acceso a los informes de supervisión de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="145ca-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="145ca-114">De forma predeterminada, el panel de supervisión muestra los datos de las siguientes métricas para la semana actual (y los totales de tendencia de las seis semanas anteriores):</span><span class="sxs-lookup"><span data-stu-id="145ca-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="145ca-115">Métricas de uso del sistema</span><span class="sxs-lookup"><span data-stu-id="145ca-115">System Usage Metrics</span></span>

<span data-ttu-id="145ca-116">**Registro**</span><span class="sxs-lookup"><span data-stu-id="145ca-116">**Registration**</span></span>

  - <span data-ttu-id="145ca-117">Inicios de sesión de usuario únicos</span><span class="sxs-lookup"><span data-stu-id="145ca-117">Unique user logons</span></span>

<span data-ttu-id="145ca-118">**Punto a punto**</span><span class="sxs-lookup"><span data-stu-id="145ca-118">**Peer-to-peer**</span></span>

  - <span data-ttu-id="145ca-119">Total de sesiones</span><span class="sxs-lookup"><span data-stu-id="145ca-119">Total sessions</span></span>

  - <span data-ttu-id="145ca-120">Sesiones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="145ca-120">IM sessions</span></span>

  - <span data-ttu-id="145ca-121">Sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="145ca-121">Audio sessions</span></span>

  - <span data-ttu-id="145ca-122">Sesiones de vídeo</span><span class="sxs-lookup"><span data-stu-id="145ca-122">Video sessions</span></span>

  - <span data-ttu-id="145ca-123">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="145ca-123">Application sharing</span></span>

  - <span data-ttu-id="145ca-124">Total de minutos de sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="145ca-124">Total audio session minutes</span></span>

  - <span data-ttu-id="145ca-125">Media de minutos de sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="145ca-125">Avg. audio session minutes</span></span>

<span data-ttu-id="145ca-126">**Conferencia**</span><span class="sxs-lookup"><span data-stu-id="145ca-126">**Conference**</span></span>

  - <span data-ttu-id="145ca-127">Total de conferencias</span><span class="sxs-lookup"><span data-stu-id="145ca-127">Total conferences</span></span>

  - <span data-ttu-id="145ca-128">Conferencias de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="145ca-128">IM conferences</span></span>

  - <span data-ttu-id="145ca-129">Conferencias A/V</span><span class="sxs-lookup"><span data-stu-id="145ca-129">A/V conferences</span></span>

  - <span data-ttu-id="145ca-130">Conferencias de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="145ca-130">Application sharing conferences</span></span>

  - <span data-ttu-id="145ca-131">Conferencias web</span><span class="sxs-lookup"><span data-stu-id="145ca-131">Web conferences</span></span>

  - <span data-ttu-id="145ca-132">Total de organizadores</span><span class="sxs-lookup"><span data-stu-id="145ca-132">Total organizers</span></span>

  - <span data-ttu-id="145ca-133">Total de minutos de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="145ca-133">Total A/V conference minutes</span></span>

  - <span data-ttu-id="145ca-134">Lecturas. Minutos de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="145ca-134">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="145ca-135">Total de conferencias RTC</span><span class="sxs-lookup"><span data-stu-id="145ca-135">Total PSTN conferences</span></span>

  - <span data-ttu-id="145ca-136">Total de participantes RTC</span><span class="sxs-lookup"><span data-stu-id="145ca-136">Total PSTN participants</span></span>

  - <span data-ttu-id="145ca-137">Total de minutos de participantes RTC</span><span class="sxs-lookup"><span data-stu-id="145ca-137">Total PSTN participant minutes</span></span>

<span data-ttu-id="145ca-138">Además de las métricas de uso del sistema, las métricas siguientes muestran el total del día actual y los seis días anteriores (si selecciona la **vista semanal**) o para la semana actual y las seis últimas semanas si selecciona la **vista mensual**.</span><span class="sxs-lookup"><span data-stu-id="145ca-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="145ca-139">Diagnósticos de llamadas Per-User</span><span class="sxs-lookup"><span data-stu-id="145ca-139">Per-User Call Diagnostics</span></span>

<span data-ttu-id="145ca-140">**Usuarios con errores de llamadas**</span><span class="sxs-lookup"><span data-stu-id="145ca-140">**Users with call failures**</span></span>

  - <span data-ttu-id="145ca-141">Total de usuarios con errores de llamadas</span><span class="sxs-lookup"><span data-stu-id="145ca-141">Total users with call failures</span></span>

  - <span data-ttu-id="145ca-142">Organizadores de conferencias con errores de llamadas</span><span class="sxs-lookup"><span data-stu-id="145ca-142">Conference organizers with call failures</span></span>

<span data-ttu-id="145ca-143">**Usuarios con llamadas de calidad deficiente**</span><span class="sxs-lookup"><span data-stu-id="145ca-143">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="145ca-144">Total de usuarios con llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="145ca-144">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="145ca-145">Diagnósticos de llamadas</span><span class="sxs-lookup"><span data-stu-id="145ca-145">Call Diagnostics</span></span>

<span data-ttu-id="145ca-146">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="145ca-146">Peer-to-peer</span></span>

  - <span data-ttu-id="145ca-147">Total de errores</span><span class="sxs-lookup"><span data-stu-id="145ca-147">Total failures</span></span>

  - <span data-ttu-id="145ca-148">Porcentaje de errores generales</span><span class="sxs-lookup"><span data-stu-id="145ca-148">Overall failure rate</span></span>

  - <span data-ttu-id="145ca-149">Porcentaje de errores de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="145ca-149">IM failure rate</span></span>

  - <span data-ttu-id="145ca-150">Porcentaje de errores de audio</span><span class="sxs-lookup"><span data-stu-id="145ca-150">Audio failure rate</span></span>

  - <span data-ttu-id="145ca-151">Tasa de errores de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="145ca-151">Application sharing failure rate</span></span>

<span data-ttu-id="145ca-152">Conferencia</span><span class="sxs-lookup"><span data-stu-id="145ca-152">Conference</span></span>

  - <span data-ttu-id="145ca-153">Total de errores</span><span class="sxs-lookup"><span data-stu-id="145ca-153">Total failures</span></span>

  - <span data-ttu-id="145ca-154">Porcentaje de errores generales</span><span class="sxs-lookup"><span data-stu-id="145ca-154">Overall failure rate</span></span>

  - <span data-ttu-id="145ca-155">Porcentaje de errores de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="145ca-155">IM failure rate</span></span>

  - <span data-ttu-id="145ca-156">Porcentaje de errores de A/V</span><span class="sxs-lookup"><span data-stu-id="145ca-156">A/V failure rate</span></span>

  - <span data-ttu-id="145ca-157">Tasa de errores de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="145ca-157">Application sharing failure rate</span></span>

<span data-ttu-id="145ca-158">Cinco servidores principales por sesiones con error</span><span class="sxs-lookup"><span data-stu-id="145ca-158">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="145ca-159">Diagnósticos de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="145ca-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="145ca-160">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="145ca-160">Peer-to-peer</span></span>

  - <span data-ttu-id="145ca-161">Total de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="145ca-161">Total poor quality calls</span></span>

  - <span data-ttu-id="145ca-162">Porcentaje de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="145ca-162">Poor quality call percentage</span></span>

  - <span data-ttu-id="145ca-163">Llamadas RTC con mala calidad</span><span class="sxs-lookup"><span data-stu-id="145ca-163">PSTN calls with poor quality</span></span>

<span data-ttu-id="145ca-164">Conferencia</span><span class="sxs-lookup"><span data-stu-id="145ca-164">Conference</span></span>

  - <span data-ttu-id="145ca-165">Total de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="145ca-165">Total poor quality calls</span></span>

  - <span data-ttu-id="145ca-166">Porcentaje de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="145ca-166">Poor quality call percentage</span></span>

  - <span data-ttu-id="145ca-167">Llamadas RTC con mala calidad</span><span class="sxs-lookup"><span data-stu-id="145ca-167">PSTN calls with poor quality</span></span>

<span data-ttu-id="145ca-168">Principales servidores con un porcentaje de llamadas de mala calidad</span><span class="sxs-lookup"><span data-stu-id="145ca-168">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="145ca-169">Trabajar con el panel de supervisión</span><span class="sxs-lookup"><span data-stu-id="145ca-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="145ca-170">Como se indicó, de forma predeterminada, se muestran los totales de la semana actual y se muestran los valores de tendencia de las seis últimas semanas.</span><span class="sxs-lookup"><span data-stu-id="145ca-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="145ca-171">Si prefiere ver los totales del mes actual (así como los valores de tendencia de los últimos seis meses), haga clic en el vínculo **vista mensual** en la esquina superior derecha del panel.</span><span class="sxs-lookup"><span data-stu-id="145ca-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="145ca-172">Si decide ver los totales mensuales, el texto del vínculo cambiará a la **vista semanal**.</span><span class="sxs-lookup"><span data-stu-id="145ca-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="145ca-173">Puede volver a la vista semanal haciendo clic en ese vínculo.</span><span class="sxs-lookup"><span data-stu-id="145ca-173">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="145ca-174">El panel de supervisión le limita a mirar los totales de la semana en curso (o mes) y los valores de tendencia de las seis últimas semanas (o meses).</span><span class="sxs-lookup"><span data-stu-id="145ca-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="145ca-175">No puede cambiar estas fechas y horas.</span><span class="sxs-lookup"><span data-stu-id="145ca-175">You cannot change these dates and times.</span></span> <span data-ttu-id="145ca-176">Por ejemplo, no puede usar el panel para ver totales de informes para el período de tiempo que comienza nueve meses.</span><span class="sxs-lookup"><span data-stu-id="145ca-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="145ca-177">Los valores que se muestran en las columnas **esta semana**, **este mes**o **hoy** le vinculan a información más detallada sobre el elemento.</span><span class="sxs-lookup"><span data-stu-id="145ca-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="145ca-178">Tenga en cuenta que el nombre de columna y los valores que se muestran en la columna con frecuencia serán distintos en función de la métrica elegida y dependiendo de si ha seleccionado la vista semanal o mensual.</span><span class="sxs-lookup"><span data-stu-id="145ca-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="145ca-179">Por ejemplo, si hace clic en los totales que se muestran para la métrica de **inicios de sesión de usuario únicos** , verá el **Informe de registro de usuario** para el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="145ca-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="145ca-180">Puede volver al panel de supervisión en cualquier momento haciendo clic en **Panel**.</span><span class="sxs-lookup"><span data-stu-id="145ca-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="145ca-181">También puede acceder a la Página principal de informes del servidor de supervisión haciendo clic en el vínculo <STRONG>informes</STRONG> de la esquina superior derecha del panel.</span><span class="sxs-lookup"><span data-stu-id="145ca-181">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="145ca-182">La columna **tendencia** muestra un gráfico de líneas simple que muestra los totales de las seis últimas semanas (o en función de la métrica y el intervalo de tiempo, los últimos seis días o los últimos seis meses).</span><span class="sxs-lookup"><span data-stu-id="145ca-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="145ca-183">Estos gráficos de líneas simples muestran un punto de datos sin etiquetar para cada período de tiempo (por ejemplo, un punto de datos sin etiquetar para cada una de las seis últimas semanas).</span><span class="sxs-lookup"><span data-stu-id="145ca-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="145ca-184">Sin embargo, puede recuperar los valores reales de estos gráficos manteniendo el puntero del mouse sobre el gráfico.</span><span class="sxs-lookup"><span data-stu-id="145ca-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="145ca-185">En ese caso, una información sobre herramientas muestra los valores máximos y mínimos en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="145ca-185">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="145ca-186">Exportar datos desde el panel de supervisión</span><span class="sxs-lookup"><span data-stu-id="145ca-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="145ca-187">El panel de supervisión ofrece varias formas de exportar la vista del panel actual.</span><span class="sxs-lookup"><span data-stu-id="145ca-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="145ca-188">En la barra de herramientas del panel, verá un icono similar a un disquete con una flecha verde adjunta.</span><span class="sxs-lookup"><span data-stu-id="145ca-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="145ca-189">Si hace clic en este icono, aparecerá una lista desplegable que proporciona los siguientes formatos de exportación de datos:</span><span class="sxs-lookup"><span data-stu-id="145ca-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="145ca-190">Archivo XML con datos de informe</span><span class="sxs-lookup"><span data-stu-id="145ca-190">XML file with report data</span></span>

  - <span data-ttu-id="145ca-191">Archivo CSV (delimitado por comas)</span><span class="sxs-lookup"><span data-stu-id="145ca-191">CSV (comma delimited)</span></span>

  - <span data-ttu-id="145ca-192">PDF</span><span class="sxs-lookup"><span data-stu-id="145ca-192">PDF</span></span>

  - <span data-ttu-id="145ca-193">Archivo MHTML (archivo web)</span><span class="sxs-lookup"><span data-stu-id="145ca-193">MHTML (web archive)</span></span>

  - <span data-ttu-id="145ca-194">Excel</span><span class="sxs-lookup"><span data-stu-id="145ca-194">Excel</span></span>

  - <span data-ttu-id="145ca-195">Archivo TIFF</span><span class="sxs-lookup"><span data-stu-id="145ca-195">TIFF file</span></span>

  - <span data-ttu-id="145ca-196">Word</span><span class="sxs-lookup"><span data-stu-id="145ca-196">Word</span></span>

<span data-ttu-id="145ca-197">Para exportar la vista del panel actual (y sus valores), haga clic en la opción de exportación que desee.</span><span class="sxs-lookup"><span data-stu-id="145ca-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="145ca-198">Lync Server 2013 genera un informe en el formato especificado y, a continuación, ofrece la opción de abrir el informe o guardarlo.</span><span class="sxs-lookup"><span data-stu-id="145ca-198">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="145ca-199">Tenga en cuenta que, de forma predeterminada, Lync Server títulos el **Panel de supervisión** de informes y lo guarda en la carpeta descargas.</span><span class="sxs-lookup"><span data-stu-id="145ca-199">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="145ca-200">Para dar al informe un nombre diferente o para almacenarlo en una carpeta diferente, haga clic en la flecha situada junto al botón **Guardar** y, a continuación, haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="145ca-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="145ca-201">Si está bien con el **Panel de supervisión** de nombres y si tiene el informe guardado en la carpeta descargas, solo tiene que hacer clic en el botón **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="145ca-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="145ca-202">Es posible que, al intentar exportar datos de panel, aparezca un cuadro de diálogo de **alerta de seguridad** junto con el mensaje "la configuración actual no permite la descarga de este archivo".</span><span class="sxs-lookup"><span data-stu-id="145ca-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="145ca-203">Si esto ocurre, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="145ca-203">If that occurs, do the following:</span></span>

  - <span data-ttu-id="145ca-204">En Internet Explorer, seleccione **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="145ca-204">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="145ca-205">En el cuadro de diálogo **Opciones de Internet** , en la ficha **seguridad** , haga clic en **sitios de confianza** y, a continuación, en **sitios**.</span><span class="sxs-lookup"><span data-stu-id="145ca-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="145ca-206">En el cuadro de diálogo **sitios de confianza** , haga clic en **Agregar** para agregar los informes de Lync Server 2013 que ejecutan Lync Server 2013 a las colecciones de sitios web de confianza.</span><span class="sxs-lookup"><span data-stu-id="145ca-206">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="145ca-207">Haga clic en **cerrar** y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="145ca-207">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="145ca-208">Tendrá que actualizar el panel de supervisión antes de que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="145ca-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="145ca-209">Para ello, presione F5 o haga clic en el icono **Actualizar** de la barra de herramientas del panel.</span><span class="sxs-lookup"><span data-stu-id="145ca-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="145ca-210">(El icono de **actualización** es un círculo con un par de flechas verdes en él.)</span><span class="sxs-lookup"><span data-stu-id="145ca-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="145ca-211">También puede crear una hoja de cálculo de Excel que incluya fuentes de datos activos, que incluye vínculos a los últimos datos del panel de supervisión.</span><span class="sxs-lookup"><span data-stu-id="145ca-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="145ca-212">Para crear un archivo de fuente de datos activo, haga clic en el icono naranja **exportar a la fuente de datos** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="145ca-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="145ca-213">Si prefiere imprimir el panel actual, haga clic en el icono de la impresora en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="145ca-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

