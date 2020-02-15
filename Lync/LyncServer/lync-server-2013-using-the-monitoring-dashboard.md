---
title: 'Lync Server 2013: uso del panel de supervisión'
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
ms.openlocfilehash: 643cbc55730d8efb1520ed88c40977c90e35f2fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="4fd7f-102">Uso del panel de supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fd7f-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fd7f-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="4fd7f-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="4fd7f-104">El panel de supervisión proporciona a los administradores una introducción rápida del uso del sistema y el estado del sistema de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="4fd7f-105">El panel está diseñado para mostrar una vista agregada de métricas del sistema clave y para hacerlo mostrando:</span><span class="sxs-lookup"><span data-stu-id="4fd7f-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="4fd7f-106">Totales del día actual.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-106">Totals for the current day.</span></span> <span data-ttu-id="4fd7f-107">Tenga en cuenta que los valores que se muestran para el día actual representan datos que se han registrado desde medianoche hasta la hora actual (en función de la hora local del servidor de informes).</span><span class="sxs-lookup"><span data-stu-id="4fd7f-107">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="4fd7f-108">Esto significa que normalmente estará viendo los datos de un día parcial y no durante un período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-108">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="4fd7f-109">Por ejemplo, si la hora local del servidor es 8:00 A.M., verá ocho horas de datos porque hay ocho horas entre la medianoche y el tiempo actual de 8:00 AM.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-109">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="4fd7f-110">Los totales de la semana y las tendencias de los totales de las seis últimas semanas.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="4fd7f-111">Los totales del mes y los totales de tendencia para los últimos seis meses (solo para el uso del sistema).</span><span class="sxs-lookup"><span data-stu-id="4fd7f-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="4fd7f-112">Tenga en cuenta que puede usar el cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) para devolver la dirección URL usada para obtener acceso a los informes de supervisión de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="4fd7f-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="4fd7f-113">De forma predeterminada, el panel de supervisión muestra los datos de las siguientes métricas para la semana actual (y los totales de tendencia de las seis semanas anteriores):</span><span class="sxs-lookup"><span data-stu-id="4fd7f-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="4fd7f-114">Métricas de uso del sistema</span><span class="sxs-lookup"><span data-stu-id="4fd7f-114">System Usage Metrics</span></span>

<span data-ttu-id="4fd7f-115">**Registro**</span><span class="sxs-lookup"><span data-stu-id="4fd7f-115">**Registration**</span></span>

  - <span data-ttu-id="4fd7f-116">Inicios de sesión de usuario únicos</span><span class="sxs-lookup"><span data-stu-id="4fd7f-116">Unique user logons</span></span>

<span data-ttu-id="4fd7f-117">**Punto a punto**</span><span class="sxs-lookup"><span data-stu-id="4fd7f-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="4fd7f-118">Total de sesiones</span><span class="sxs-lookup"><span data-stu-id="4fd7f-118">Total sessions</span></span>

  - <span data-ttu-id="4fd7f-119">Sesiones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="4fd7f-119">IM sessions</span></span>

  - <span data-ttu-id="4fd7f-120">Sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="4fd7f-120">Audio sessions</span></span>

  - <span data-ttu-id="4fd7f-121">Sesiones de vídeo</span><span class="sxs-lookup"><span data-stu-id="4fd7f-121">Video sessions</span></span>

  - <span data-ttu-id="4fd7f-122">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="4fd7f-122">Application sharing</span></span>

  - <span data-ttu-id="4fd7f-123">Total de minutos de sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="4fd7f-123">Total audio session minutes</span></span>

  - <span data-ttu-id="4fd7f-124">Media de minutos de sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="4fd7f-124">Avg. audio session minutes</span></span>

<span data-ttu-id="4fd7f-125">**Conversación**</span><span class="sxs-lookup"><span data-stu-id="4fd7f-125">**Conference**</span></span>

  - <span data-ttu-id="4fd7f-126">Total de conferencias</span><span class="sxs-lookup"><span data-stu-id="4fd7f-126">Total conferences</span></span>

  - <span data-ttu-id="4fd7f-127">Conferencias de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="4fd7f-127">IM conferences</span></span>

  - <span data-ttu-id="4fd7f-128">Conferencias A/V</span><span class="sxs-lookup"><span data-stu-id="4fd7f-128">A/V conferences</span></span>

  - <span data-ttu-id="4fd7f-129">Conferencias de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="4fd7f-129">Application sharing conferences</span></span>

  - <span data-ttu-id="4fd7f-130">Conferencias web</span><span class="sxs-lookup"><span data-stu-id="4fd7f-130">Web conferences</span></span>

  - <span data-ttu-id="4fd7f-131">Total de organizadores</span><span class="sxs-lookup"><span data-stu-id="4fd7f-131">Total organizers</span></span>

  - <span data-ttu-id="4fd7f-132">Total de minutos de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="4fd7f-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="4fd7f-133">Lecturas. Minutos de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="4fd7f-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="4fd7f-134">Total de conferencias RTC</span><span class="sxs-lookup"><span data-stu-id="4fd7f-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="4fd7f-135">Total de participantes RTC</span><span class="sxs-lookup"><span data-stu-id="4fd7f-135">Total PSTN participants</span></span>

  - <span data-ttu-id="4fd7f-136">Total de minutos de participantes RTC</span><span class="sxs-lookup"><span data-stu-id="4fd7f-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="4fd7f-137">Además de las métricas de uso del sistema, las métricas siguientes muestran el total del día actual y los seis días anteriores (si selecciona la **vista semanal**) o para la semana actual y las seis últimas semanas si selecciona la **vista mensual**.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="4fd7f-138">Diagnósticos de llamadas por usuario</span><span class="sxs-lookup"><span data-stu-id="4fd7f-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="4fd7f-139">**Usuarios con errores de llamadas**</span><span class="sxs-lookup"><span data-stu-id="4fd7f-139">**Users with call failures**</span></span>

  - <span data-ttu-id="4fd7f-140">Total de usuarios con errores de llamadas</span><span class="sxs-lookup"><span data-stu-id="4fd7f-140">Total users with call failures</span></span>

  - <span data-ttu-id="4fd7f-141">Organizadores de conferencias con errores de llamadas</span><span class="sxs-lookup"><span data-stu-id="4fd7f-141">Conference organizers with call failures</span></span>

<span data-ttu-id="4fd7f-142">**Usuarios con llamadas de calidad deficiente**</span><span class="sxs-lookup"><span data-stu-id="4fd7f-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="4fd7f-143">Total de usuarios con llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="4fd7f-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="4fd7f-144">Diagnósticos de llamadas</span><span class="sxs-lookup"><span data-stu-id="4fd7f-144">Call Diagnostics</span></span>

<span data-ttu-id="4fd7f-145">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="4fd7f-145">Peer-to-peer</span></span>

  - <span data-ttu-id="4fd7f-146">Total de errores</span><span class="sxs-lookup"><span data-stu-id="4fd7f-146">Total failures</span></span>

  - <span data-ttu-id="4fd7f-147">Porcentaje de errores generales</span><span class="sxs-lookup"><span data-stu-id="4fd7f-147">Overall failure rate</span></span>

  - <span data-ttu-id="4fd7f-148">Porcentaje de errores de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="4fd7f-148">IM failure rate</span></span>

  - <span data-ttu-id="4fd7f-149">Porcentaje de errores de audio</span><span class="sxs-lookup"><span data-stu-id="4fd7f-149">Audio failure rate</span></span>

  - <span data-ttu-id="4fd7f-150">Tasa de errores de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="4fd7f-150">Application sharing failure rate</span></span>

<span data-ttu-id="4fd7f-151">Conversación</span><span class="sxs-lookup"><span data-stu-id="4fd7f-151">Conference</span></span>

  - <span data-ttu-id="4fd7f-152">Total de errores</span><span class="sxs-lookup"><span data-stu-id="4fd7f-152">Total failures</span></span>

  - <span data-ttu-id="4fd7f-153">Porcentaje de errores generales</span><span class="sxs-lookup"><span data-stu-id="4fd7f-153">Overall failure rate</span></span>

  - <span data-ttu-id="4fd7f-154">Porcentaje de errores de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="4fd7f-154">IM failure rate</span></span>

  - <span data-ttu-id="4fd7f-155">Porcentaje de errores de A/V</span><span class="sxs-lookup"><span data-stu-id="4fd7f-155">A/V failure rate</span></span>

  - <span data-ttu-id="4fd7f-156">Tasa de errores de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="4fd7f-156">Application sharing failure rate</span></span>

<span data-ttu-id="4fd7f-157">Cinco servidores principales por sesiones con error</span><span class="sxs-lookup"><span data-stu-id="4fd7f-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="4fd7f-158">Diagnósticos de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="4fd7f-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="4fd7f-159">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="4fd7f-159">Peer-to-peer</span></span>

  - <span data-ttu-id="4fd7f-160">Total de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="4fd7f-160">Total poor quality calls</span></span>

  - <span data-ttu-id="4fd7f-161">Porcentaje de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="4fd7f-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="4fd7f-162">Llamadas RTC con mala calidad</span><span class="sxs-lookup"><span data-stu-id="4fd7f-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="4fd7f-163">Conversación</span><span class="sxs-lookup"><span data-stu-id="4fd7f-163">Conference</span></span>

  - <span data-ttu-id="4fd7f-164">Total de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="4fd7f-164">Total poor quality calls</span></span>

  - <span data-ttu-id="4fd7f-165">Porcentaje de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="4fd7f-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="4fd7f-166">Llamadas RTC con mala calidad</span><span class="sxs-lookup"><span data-stu-id="4fd7f-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="4fd7f-167">Principales servidores con un porcentaje de llamadas de mala calidad</span><span class="sxs-lookup"><span data-stu-id="4fd7f-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="4fd7f-168">Trabajar con el panel de supervisión</span><span class="sxs-lookup"><span data-stu-id="4fd7f-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="4fd7f-169">Como se indicó, de forma predeterminada, se muestran los totales de la semana actual y se muestran los valores de tendencia de las seis últimas semanas.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-169">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="4fd7f-170">Si prefiere ver los totales del mes actual (así como los valores de tendencia de los últimos seis meses), haga clic en el vínculo **vista mensual** en la esquina superior derecha del panel.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-170">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="4fd7f-171">Si decide ver los totales mensuales, el texto del vínculo cambiará a la **vista semanal**.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-171">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="4fd7f-172">Puede volver a la vista semanal haciendo clic en ese vínculo.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-172">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4fd7f-173">El panel de supervisión le limita a mirar los totales de la semana en curso (o mes) y los valores de tendencia de las seis últimas semanas (o meses).</span><span class="sxs-lookup"><span data-stu-id="4fd7f-173">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="4fd7f-174">No puede cambiar estas fechas y horas.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-174">You cannot change these dates and times.</span></span> <span data-ttu-id="4fd7f-175">Por ejemplo, no puede usar el panel para ver totales de informes para el período de tiempo que comienza nueve meses.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-175">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="4fd7f-176">Los valores que se muestran en las columnas **esta semana**, **este mes**o **hoy** le vinculan a información más detallada sobre el elemento.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-176">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="4fd7f-177">Tenga en cuenta que el nombre de columna y los valores que se muestran en la columna con frecuencia serán distintos en función de la métrica elegida y dependiendo de si ha seleccionado la vista semanal o mensual.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-177">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="4fd7f-178">Por ejemplo, si hace clic en los totales que se muestran para la métrica de **inicios de sesión de usuario únicos** , verá el **Informe de registro de usuario** para el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-178">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="4fd7f-179">Puede volver al panel de supervisión en cualquier momento haciendo clic en **Panel**.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-179">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4fd7f-180">También puede acceder a la Página principal de informes del servidor de supervisión haciendo clic en el vínculo <STRONG>informes</STRONG> de la esquina superior derecha del panel.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="4fd7f-181">La columna **tendencia** muestra un gráfico de líneas simple que muestra los totales de las seis últimas semanas (o en función de la métrica y el intervalo de tiempo, los últimos seis días o los últimos seis meses).</span><span class="sxs-lookup"><span data-stu-id="4fd7f-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="4fd7f-182">Estos gráficos de líneas simples muestran un punto de datos sin etiquetar para cada período de tiempo (por ejemplo, un punto de datos sin etiquetar para cada una de las seis últimas semanas).</span><span class="sxs-lookup"><span data-stu-id="4fd7f-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="4fd7f-183">Sin embargo, puede recuperar los valores reales de estos gráficos manteniendo el puntero del mouse sobre el gráfico.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="4fd7f-184">En ese caso, una información sobre herramientas muestra los valores máximos y mínimos en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="4fd7f-185">Exportar datos desde el panel de supervisión</span><span class="sxs-lookup"><span data-stu-id="4fd7f-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="4fd7f-186">El panel de supervisión ofrece varias formas de exportar la vista del panel actual.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-186">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="4fd7f-187">En la barra de herramientas del panel, verá un icono similar a un disquete con una flecha verde adjunta.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-187">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="4fd7f-188">Si hace clic en este icono, aparecerá una lista desplegable que proporciona los siguientes formatos de exportación de datos:</span><span class="sxs-lookup"><span data-stu-id="4fd7f-188">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="4fd7f-189">Archivo XML con datos de informe</span><span class="sxs-lookup"><span data-stu-id="4fd7f-189">XML file with report data</span></span>

  - <span data-ttu-id="4fd7f-190">Archivo CSV (delimitado por comas)</span><span class="sxs-lookup"><span data-stu-id="4fd7f-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="4fd7f-191">PDF</span><span class="sxs-lookup"><span data-stu-id="4fd7f-191">PDF</span></span>

  - <span data-ttu-id="4fd7f-192">Archivo MHTML (archivo web)</span><span class="sxs-lookup"><span data-stu-id="4fd7f-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="4fd7f-193">Excel</span><span class="sxs-lookup"><span data-stu-id="4fd7f-193">Excel</span></span>

  - <span data-ttu-id="4fd7f-194">Archivo TIFF</span><span class="sxs-lookup"><span data-stu-id="4fd7f-194">TIFF file</span></span>

  - <span data-ttu-id="4fd7f-195">Word</span><span class="sxs-lookup"><span data-stu-id="4fd7f-195">Word</span></span>

<span data-ttu-id="4fd7f-196">Para exportar la vista del panel actual (y sus valores), haga clic en la opción de exportación que desee.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="4fd7f-197">Lync Server 2013 genera un informe en el formato especificado y, a continuación, ofrece la opción de abrir el informe o guardarlo.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="4fd7f-198">Tenga en cuenta que, de forma predeterminada, Lync Server títulos el **Panel de supervisión** de informes y lo guarda en la carpeta descargas.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="4fd7f-199">Para dar al informe un nombre diferente o para almacenarlo en una carpeta diferente, haga clic en la flecha situada junto al botón **Guardar** y, a continuación, haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="4fd7f-200">Si está bien con el **Panel de supervisión** de nombres y si tiene el informe guardado en la carpeta descargas, solo tiene que hacer clic en el botón **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="4fd7f-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="4fd7f-201">Es posible que, al intentar exportar datos de panel, aparezca un cuadro de diálogo de **alerta de seguridad** junto con el mensaje "la configuración actual no permite la descarga de este archivo".</span><span class="sxs-lookup"><span data-stu-id="4fd7f-201">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="4fd7f-202">Si esto ocurre, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4fd7f-202">If that occurs, do the following:</span></span>

  - <span data-ttu-id="4fd7f-203">En Internet Explorer, seleccione **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="4fd7f-204">En el cuadro de diálogo **Opciones de Internet** , en la ficha **seguridad** , haga clic en **sitios de confianza** y, a continuación, en **sitios**.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="4fd7f-205">En el cuadro de diálogo **sitios de confianza** , haga clic en **Agregar** para agregar los informes de Lync Server 2013 que ejecutan Lync Server 2013 a las colecciones de sitios web de confianza.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="4fd7f-206">Haga clic en **cerrar** y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="4fd7f-207">Tendrá que actualizar el panel de supervisión antes de que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-207">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="4fd7f-208">Para ello, presione F5 o haga clic en el icono **Actualizar** de la barra de herramientas del panel.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-208">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="4fd7f-209">(El icono de **actualización** es un círculo con un par de flechas verdes en él.)</span><span class="sxs-lookup"><span data-stu-id="4fd7f-209">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="4fd7f-210">También puede crear una hoja de cálculo de Excel que incluya fuentes de datos activos, que incluye vínculos a los últimos datos del panel de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-210">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="4fd7f-211">Para crear un archivo de fuente de datos activo, haga clic en el icono naranja **exportar a la fuente de datos** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-211">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="4fd7f-212">Si prefiere imprimir el panel actual, haga clic en el icono de la impresora en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="4fd7f-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

