---
title: 'Lync Server 2013: usar el panel de supervisión'
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
ms.openlocfilehash: 929d0fbc650a7b067d86738e5ded176a15c511f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="96dd0-102">Usar el panel de supervisión de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96dd0-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96dd0-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="96dd0-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="96dd0-104">El panel de supervisión proporciona a los administradores una breve descripción general del uso del sistema y el estado del sistema de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96dd0-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="96dd0-105">El panel está diseñado para mostrar una vista agregada de métricas del sistema clave y para hacerlo mostrando:</span><span class="sxs-lookup"><span data-stu-id="96dd0-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="96dd0-p102">Los totales del día en curso. Tenga en cuenta que los valores que aparecen para el día en curso representan los datos registrados desde medianoche hasta la hora en curso (basada en la hora local del servidor de informes). Esto quiere decir que normalmente verá datos de parte de un día y no de un período de 24 horas. Por ejemplo, si para el servidor son las 8 de la mañana, verá datos correspondientes a ocho horas, es decir, los datos del período transcurrido entre medianoche y la hora actual (8 de la mañana).</span><span class="sxs-lookup"><span data-stu-id="96dd0-p102">Totals for the current day. Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server). That means that you will typically be viewing data for a partial day and not for a 24-hour period. For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="96dd0-110">Los totales de la semana y las tendencias de los totales en las últimas seis semanas.</span><span class="sxs-lookup"><span data-stu-id="96dd0-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="96dd0-111">Los totales del mes y las tendencias de los totales en los últimos seis meses (solo para el uso del sistema).</span><span class="sxs-lookup"><span data-stu-id="96dd0-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="96dd0-112">Tenga en cuenta que puede usar el cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) para devolver la dirección URL que se usa para acceder a los informes de supervisión de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="96dd0-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="96dd0-113">Normalmente, el panel de supervisión muestra los datos de la semana de las métricas siguientes (y las tendencias de los totales de las seis semanas anteriores):</span><span class="sxs-lookup"><span data-stu-id="96dd0-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="96dd0-114">Métricas de uso del sistema</span><span class="sxs-lookup"><span data-stu-id="96dd0-114">System Usage Metrics</span></span>

<span data-ttu-id="96dd0-115">**Registro**</span><span class="sxs-lookup"><span data-stu-id="96dd0-115">**Registration**</span></span>

  - <span data-ttu-id="96dd0-116">Inicios de sesión de usuario únicos</span><span class="sxs-lookup"><span data-stu-id="96dd0-116">Unique user logons</span></span>

<span data-ttu-id="96dd0-117">**Punto a punto**</span><span class="sxs-lookup"><span data-stu-id="96dd0-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="96dd0-118">Total de sesiones</span><span class="sxs-lookup"><span data-stu-id="96dd0-118">Total sessions</span></span>

  - <span data-ttu-id="96dd0-119">Sesiones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="96dd0-119">IM sessions</span></span>

  - <span data-ttu-id="96dd0-120">Sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="96dd0-120">Audio sessions</span></span>

  - <span data-ttu-id="96dd0-121">Sesiones de vídeo</span><span class="sxs-lookup"><span data-stu-id="96dd0-121">Video sessions</span></span>

  - <span data-ttu-id="96dd0-122">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="96dd0-122">Application sharing</span></span>

  - <span data-ttu-id="96dd0-123">Total de minutos de sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="96dd0-123">Total audio session minutes</span></span>

  - <span data-ttu-id="96dd0-124">Media de minutos de sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="96dd0-124">Avg. audio session minutes</span></span>

<span data-ttu-id="96dd0-125">**Una conferencia**</span><span class="sxs-lookup"><span data-stu-id="96dd0-125">**Conference**</span></span>

  - <span data-ttu-id="96dd0-126">Total de conferencias</span><span class="sxs-lookup"><span data-stu-id="96dd0-126">Total conferences</span></span>

  - <span data-ttu-id="96dd0-127">Conferencias de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="96dd0-127">IM conferences</span></span>

  - <span data-ttu-id="96dd0-128">Conferencias A/V</span><span class="sxs-lookup"><span data-stu-id="96dd0-128">A/V conferences</span></span>

  - <span data-ttu-id="96dd0-129">Conferencias de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="96dd0-129">Application sharing conferences</span></span>

  - <span data-ttu-id="96dd0-130">Conferencias web</span><span class="sxs-lookup"><span data-stu-id="96dd0-130">Web conferences</span></span>

  - <span data-ttu-id="96dd0-131">Total de organizadores</span><span class="sxs-lookup"><span data-stu-id="96dd0-131">Total organizers</span></span>

  - <span data-ttu-id="96dd0-132">Total de minutos de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="96dd0-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="96dd0-133">Media de minutos de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="96dd0-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="96dd0-134">Total de conferencias RTC</span><span class="sxs-lookup"><span data-stu-id="96dd0-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="96dd0-135">Total de participantes RTC</span><span class="sxs-lookup"><span data-stu-id="96dd0-135">Total PSTN participants</span></span>

  - <span data-ttu-id="96dd0-136">Total de minutos de participantes RTC</span><span class="sxs-lookup"><span data-stu-id="96dd0-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="96dd0-137">Además de las métricas de uso del sistema, las métricas siguientes muestran el total del día actual y de los seis días anteriores (si selecciona **Vista semanal**) o de la semana actual y de las seis semanas anteriores, si selecciona **Vista mensual**.</span><span class="sxs-lookup"><span data-stu-id="96dd0-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="96dd0-138">Diagnósticos de llamadas por usuario</span><span class="sxs-lookup"><span data-stu-id="96dd0-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="96dd0-139">**Usuarios con errores de llamadas**</span><span class="sxs-lookup"><span data-stu-id="96dd0-139">**Users with call failures**</span></span>

  - <span data-ttu-id="96dd0-140">Total de usuarios con errores de llamadas</span><span class="sxs-lookup"><span data-stu-id="96dd0-140">Total users with call failures</span></span>

  - <span data-ttu-id="96dd0-141">Organizadores de conferencias con errores de llamadas</span><span class="sxs-lookup"><span data-stu-id="96dd0-141">Conference organizers with call failures</span></span>

<span data-ttu-id="96dd0-142">**Usuarios con llamadas de calidad deficiente**</span><span class="sxs-lookup"><span data-stu-id="96dd0-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="96dd0-143">Total de usuarios con llamadas de mala calidad</span><span class="sxs-lookup"><span data-stu-id="96dd0-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="96dd0-144">Diagnósticos de llamadas</span><span class="sxs-lookup"><span data-stu-id="96dd0-144">Call Diagnostics</span></span>

<span data-ttu-id="96dd0-145">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="96dd0-145">Peer-to-peer</span></span>

  - <span data-ttu-id="96dd0-146">Total de errores</span><span class="sxs-lookup"><span data-stu-id="96dd0-146">Total failures</span></span>

  - <span data-ttu-id="96dd0-147">Porcentaje general de errores</span><span class="sxs-lookup"><span data-stu-id="96dd0-147">Overall failure rate</span></span>

  - <span data-ttu-id="96dd0-148">Porcentaje de errores de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="96dd0-148">IM failure rate</span></span>

  - <span data-ttu-id="96dd0-149">Porcentaje de errores de audio</span><span class="sxs-lookup"><span data-stu-id="96dd0-149">Audio failure rate</span></span>

  - <span data-ttu-id="96dd0-150">Porcentaje de errores de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="96dd0-150">Application sharing failure rate</span></span>

<span data-ttu-id="96dd0-151">Una conferencia</span><span class="sxs-lookup"><span data-stu-id="96dd0-151">Conference</span></span>

  - <span data-ttu-id="96dd0-152">Total de errores</span><span class="sxs-lookup"><span data-stu-id="96dd0-152">Total failures</span></span>

  - <span data-ttu-id="96dd0-153">Porcentaje general de errores</span><span class="sxs-lookup"><span data-stu-id="96dd0-153">Overall failure rate</span></span>

  - <span data-ttu-id="96dd0-154">Porcentaje de errores de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="96dd0-154">IM failure rate</span></span>

  - <span data-ttu-id="96dd0-155">Porcentaje de errores de A/V</span><span class="sxs-lookup"><span data-stu-id="96dd0-155">A/V failure rate</span></span>

  - <span data-ttu-id="96dd0-156">Porcentaje de errores de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="96dd0-156">Application sharing failure rate</span></span>

<span data-ttu-id="96dd0-157">5 servidores principales por sesiones con error</span><span class="sxs-lookup"><span data-stu-id="96dd0-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="96dd0-158">Diagnósticos de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="96dd0-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="96dd0-159">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="96dd0-159">Peer-to-peer</span></span>

  - <span data-ttu-id="96dd0-160">Total de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="96dd0-160">Total poor quality calls</span></span>

  - <span data-ttu-id="96dd0-161">Porcentaje de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="96dd0-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="96dd0-162">Total de llamadas RTC de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="96dd0-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="96dd0-163">Una conferencia</span><span class="sxs-lookup"><span data-stu-id="96dd0-163">Conference</span></span>

  - <span data-ttu-id="96dd0-164">Total de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="96dd0-164">Total poor quality calls</span></span>

  - <span data-ttu-id="96dd0-165">Porcentaje de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="96dd0-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="96dd0-166">Total de llamadas RTC de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="96dd0-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="96dd0-167">Los peores servidores por porcentaje de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="96dd0-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="96dd0-168">Trabajar con el panel de supervisión</span><span class="sxs-lookup"><span data-stu-id="96dd0-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="96dd0-p103">Tal como hemos indicado, se muestran los totales predeterminados de la semana en curso y los valores de las tendencias de las seis últimas semanas. Si prefiere ver los totales del mes actual (así como los valores de las tendencias de los últimos seis meses), haga clic en el vínculo **Vista mensual** de la esquina superior derecha del panel. Si decide ver los totales mensuales, el texto del vínculo cambiará a **Vista semanal**. Puede volver a la vista semanal haciendo clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="96dd0-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="96dd0-p104">El panel de supervisión le limita la consulta a los totales de la semana en curso (o el mes en curso) y a los valores de las tendencias de las seis últimas semanas (o seis últimos meses). Estas fechas y horas no se pueden cambiar. Por ejemplo, con el panel no se pueden ver los totales de informe de un período que se inició nueve meses antes.</span><span class="sxs-lookup"><span data-stu-id="96dd0-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="96dd0-p105">Los valores que aparecen en las columnas **Esta semana**, **Este mes** u **Hoy** le vinculan a información más detallada sobre el elemento. Tenga en cuenta que el nombre de la columna y los valores que aparecen en ella cambiarán a menudo en función de la métrica elegida y en función de si ha seleccionado vista semanal o vista mensual. Por ejemplo, si hace clic en los totales que aparecen en la métrica **Inicios de sesión de usuario únicos**, verá el **Informe de registro de usuario** del período de tiempo especificado. Puede volver al panel de supervisión en cualquier momento, haciendo clic en **Panel**.</span><span class="sxs-lookup"><span data-stu-id="96dd0-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="96dd0-180">También puede acceder a la Página principal de informes del servidor de supervisión haciendo clic en el vínculo <STRONG>informes</STRONG> , en la esquina superior derecha del panel.</span><span class="sxs-lookup"><span data-stu-id="96dd0-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="96dd0-181">La columna **Tendencia** muestra un gráfico de línea sencilla con los totales de las últimas seis semanas (o, en función de la métrica y del intervalo de tiempo, los últimos seis días o seis meses).</span><span class="sxs-lookup"><span data-stu-id="96dd0-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="96dd0-182">Estos gráficos de línea sencilla muestran un punto de datos sin etiquetar por cada período de tiempo (por ejemplo, un punto de datos sin etiquetar por cada una de las seis últimas semanas).</span><span class="sxs-lookup"><span data-stu-id="96dd0-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="96dd0-183">Ahora bien, puede recuperar los valores reales de estos gráficos manteniendo el puntero del mouse sobre el gráfico.</span><span class="sxs-lookup"><span data-stu-id="96dd0-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="96dd0-184">En ese caso, la información sobre herramientas muestra los valores máximos y mínimos en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="96dd0-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="96dd0-185">Exportar datos desde el panel de supervisión</span><span class="sxs-lookup"><span data-stu-id="96dd0-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="96dd0-p107">El panel de supervisión proporciona varias formas de exportar la vista del panel actual. En la barra de herramientas del panel, verá un icono con el aspecto de un disquete con una flecha verde vinculada. Si hace clic en el icono, aparecerá una lista desplegable que le presentará los siguientes formatos de exportación de datos:</span><span class="sxs-lookup"><span data-stu-id="96dd0-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="96dd0-189">Archivo XML con datos de informe</span><span class="sxs-lookup"><span data-stu-id="96dd0-189">XML file with report data</span></span>

  - <span data-ttu-id="96dd0-190">Archivo CSV (delimitado por comas)</span><span class="sxs-lookup"><span data-stu-id="96dd0-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="96dd0-191">PDF</span><span class="sxs-lookup"><span data-stu-id="96dd0-191">PDF</span></span>

  - <span data-ttu-id="96dd0-192">Archivo MHTML (archivo web)</span><span class="sxs-lookup"><span data-stu-id="96dd0-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="96dd0-193">Archivo de Excel</span><span class="sxs-lookup"><span data-stu-id="96dd0-193">Excel</span></span>

  - <span data-ttu-id="96dd0-194">Archivo TIFF</span><span class="sxs-lookup"><span data-stu-id="96dd0-194">TIFF file</span></span>

  - <span data-ttu-id="96dd0-195">Archivo de Word</span><span class="sxs-lookup"><span data-stu-id="96dd0-195">Word</span></span>

<span data-ttu-id="96dd0-196">Para exportar la vista de panel actual (y sus valores), haga clic en la opción de exportación deseada.</span><span class="sxs-lookup"><span data-stu-id="96dd0-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="96dd0-197">Lync Server 2013 genera un informe en el formato especificado y, a continuación, le ofrece la opción de abrir ese informe o guardarlo.</span><span class="sxs-lookup"><span data-stu-id="96dd0-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="96dd0-198">Tenga en cuenta que, de forma predeterminada, Lync Server títulos el **Panel de supervisión** de informes y lo guarda en la carpeta descargas.</span><span class="sxs-lookup"><span data-stu-id="96dd0-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="96dd0-199">Para darle al informe otro nombre o guardarlo en otra carpeta, haga clic en la flecha situada al lado del botón **Guardar** y después haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="96dd0-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="96dd0-200">Si le parece bien el nombre **Panel de supervisión** y está de acuerdo en guardar el informe en la carpeta Descargas, solo tiene que hacer clic en el botón **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="96dd0-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="96dd0-p109">Es posible que, cuando intente exportar datos del panel, aparezca el cuadro de diálogo **Alerta de seguridad** junto con el mensaje "La configuración actual no permite descargar este archivo". Si ocurre esto, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96dd0-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>

  - <span data-ttu-id="96dd0-203">En Internet Explorer, seleccione **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="96dd0-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="96dd0-204">En el cuadro de diálogo **Opciones de Internet**, en la pestaña **Seguridad**, haga clic en **Sitios de confianza** y después en **Sitios**.</span><span class="sxs-lookup"><span data-stu-id="96dd0-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="96dd0-205">En el cuadro de diálogo **sitios de confianza** , haga clic en **Agregar** para agregar el Lync Server 2013 que ejecuta los informes de Lync Server 2013 a las colecciones de sitios web de confianza.</span><span class="sxs-lookup"><span data-stu-id="96dd0-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="96dd0-206">Haga clic en **Cerrar** y, luego, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="96dd0-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="96dd0-p110">Necesitará actualizar el panel de supervisión antes de que entren en vigor los cambios. Para ello, presione F5 o haga clic en el icono **Actualizar** de la barra de herramientas del panel (el icono **Actualizar** es un círculo que contiene un par de flechas verdes).</span><span class="sxs-lookup"><span data-stu-id="96dd0-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="96dd0-p111">También puede crear una hoja de cálculo de Excel que contenga fuentes de datos activos, lo que incluye vínculos con los últimos datos del panel de supervisión. Para crear un archivo de fuentes de datos activos, haga clic en el icono naranja **Exportar a fuente de datos** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="96dd0-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="96dd0-212">Si prefiere imprimir el panel actual, haga clic en el icono de la impresora de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="96dd0-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

