---
title: Usar el panel de supervisión de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Resumen: Obtenga información sobre el panel de supervisión de Skype empresarial Server.'
ms.openlocfilehash: c2c86d5d5ede9581a2b41f32594118ab2605d63a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817829"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="a524d-103">Usar el panel de supervisión de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a524d-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="a524d-104">**Resumen:** Obtenga más información sobre el panel de supervisión de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a524d-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="a524d-105">El panel de supervisión proporciona a los administradores una breve descripción general del uso del sistema y el estado del sistema de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a524d-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="a524d-106">El panel está diseñado para mostrar una vista agregada de métricas del sistema clave y para hacerlo mostrando:</span><span class="sxs-lookup"><span data-stu-id="a524d-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="a524d-107">Los totales del día en curso.</span><span class="sxs-lookup"><span data-stu-id="a524d-107">Totals for the current day.</span></span> <span data-ttu-id="a524d-108">Tenga en cuenta que los valores que aparecen para el día en curso representan los datos registrados desde medianoche hasta la hora en curso (basada en la hora local del servidor de informes).</span><span class="sxs-lookup"><span data-stu-id="a524d-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="a524d-109">Esto quiere decir que normalmente verá datos de parte de un día y no de un período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="a524d-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="a524d-110">Por ejemplo, si la hora local del servidor es 8:00 A.M., verá ocho horas de datos, ya que hay ocho horas entre la medianoche y la hora actual de 8:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="a524d-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="a524d-111">Los totales de la semana y las tendencias de los totales en las últimas seis semanas.</span><span class="sxs-lookup"><span data-stu-id="a524d-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="a524d-112">Los totales del mes y las tendencias de los totales en los últimos seis meses (solo para el uso del sistema).</span><span class="sxs-lookup"><span data-stu-id="a524d-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="a524d-113">Tenga en cuenta que puede usar el cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) para devolver la dirección URL que se usa para obtener acceso a los informes de supervisión de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="a524d-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="a524d-114">Normalmente, el panel de supervisión muestra los datos de la semana de las métricas siguientes (y las tendencias de los totales de las seis semanas anteriores):</span><span class="sxs-lookup"><span data-stu-id="a524d-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="a524d-115">Métricas de uso del sistema</span><span class="sxs-lookup"><span data-stu-id="a524d-115">System Usage Metrics</span></span>

 <span data-ttu-id="a524d-116">**Registro**</span><span class="sxs-lookup"><span data-stu-id="a524d-116">**Registration**</span></span>
  
- <span data-ttu-id="a524d-117">Inicios de sesión de usuario únicos</span><span class="sxs-lookup"><span data-stu-id="a524d-117">Unique user logons</span></span>
    
  <span data-ttu-id="a524d-118">**Punto a punto**</span><span class="sxs-lookup"><span data-stu-id="a524d-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="a524d-119">Total de sesiones</span><span class="sxs-lookup"><span data-stu-id="a524d-119">Total sessions</span></span>
    
- <span data-ttu-id="a524d-120">Sesiones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="a524d-120">IM sessions</span></span>
    
- <span data-ttu-id="a524d-121">Sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="a524d-121">Audio sessions</span></span>
    
- <span data-ttu-id="a524d-122">Sesiones de vídeo</span><span class="sxs-lookup"><span data-stu-id="a524d-122">Video sessions</span></span>
    
- <span data-ttu-id="a524d-123">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a524d-123">Application sharing</span></span>
    
- <span data-ttu-id="a524d-124">Total de minutos de sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="a524d-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="a524d-125">Media de minutos de sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="a524d-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="a524d-126">**Una conferencia**</span><span class="sxs-lookup"><span data-stu-id="a524d-126">**Conference**</span></span>
  
- <span data-ttu-id="a524d-127">Total de conferencias</span><span class="sxs-lookup"><span data-stu-id="a524d-127">Total conferences</span></span>
    
- <span data-ttu-id="a524d-128">Conferencias de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="a524d-128">IM conferences</span></span>
    
- <span data-ttu-id="a524d-129">Conferencias A/V</span><span class="sxs-lookup"><span data-stu-id="a524d-129">A/V conferences</span></span>
    
- <span data-ttu-id="a524d-130">Conferencias de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a524d-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="a524d-131">Conferencias web</span><span class="sxs-lookup"><span data-stu-id="a524d-131">Web conferences</span></span>
    
- <span data-ttu-id="a524d-132">Total de organizadores</span><span class="sxs-lookup"><span data-stu-id="a524d-132">Total organizers</span></span>
    
- <span data-ttu-id="a524d-133">Total de minutos de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="a524d-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="a524d-134">Media de minutos de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="a524d-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="a524d-135">Total de conferencias RTC</span><span class="sxs-lookup"><span data-stu-id="a524d-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="a524d-136">Total de participantes RTC</span><span class="sxs-lookup"><span data-stu-id="a524d-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="a524d-137">Total de minutos de participantes RTC</span><span class="sxs-lookup"><span data-stu-id="a524d-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="a524d-138">Además de las métricas de uso del sistema, las métricas siguientes muestran el total del día actual y de los seis días anteriores (si selecciona **Vista semanal**) o de la semana actual y de las seis semanas anteriores, si selecciona **Vista mensual**.</span><span class="sxs-lookup"><span data-stu-id="a524d-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="a524d-139">Diagnósticos de llamadas por usuario</span><span class="sxs-lookup"><span data-stu-id="a524d-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="a524d-140">**Usuarios con errores de llamadas**</span><span class="sxs-lookup"><span data-stu-id="a524d-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="a524d-141">Total de usuarios con errores de llamadas</span><span class="sxs-lookup"><span data-stu-id="a524d-141">Total users with call failures</span></span>
    
- <span data-ttu-id="a524d-142">Organizadores de conferencias con errores de llamadas</span><span class="sxs-lookup"><span data-stu-id="a524d-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="a524d-143">**Usuarios con llamadas de calidad deficiente**</span><span class="sxs-lookup"><span data-stu-id="a524d-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="a524d-144">Total de usuarios con llamadas de mala calidad</span><span class="sxs-lookup"><span data-stu-id="a524d-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="a524d-145">Diagnósticos de llamadas</span><span class="sxs-lookup"><span data-stu-id="a524d-145">Call Diagnostics</span></span>

<span data-ttu-id="a524d-146">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="a524d-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="a524d-147">Total de errores</span><span class="sxs-lookup"><span data-stu-id="a524d-147">Total failures</span></span>
    
- <span data-ttu-id="a524d-148">Porcentaje general de errores</span><span class="sxs-lookup"><span data-stu-id="a524d-148">Overall failure rate</span></span>
    
- <span data-ttu-id="a524d-149">Porcentaje de errores de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="a524d-149">IM failure rate</span></span>
    
- <span data-ttu-id="a524d-150">Porcentaje de errores de audio</span><span class="sxs-lookup"><span data-stu-id="a524d-150">Audio failure rate</span></span>
    
- <span data-ttu-id="a524d-151">Porcentaje de errores de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a524d-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="a524d-152">Una conferencia</span><span class="sxs-lookup"><span data-stu-id="a524d-152">Conference</span></span>
  
- <span data-ttu-id="a524d-153">Total de errores</span><span class="sxs-lookup"><span data-stu-id="a524d-153">Total failures</span></span>
    
- <span data-ttu-id="a524d-154">Porcentaje general de errores</span><span class="sxs-lookup"><span data-stu-id="a524d-154">Overall failure rate</span></span>
    
- <span data-ttu-id="a524d-155">Porcentaje de errores de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="a524d-155">IM failure rate</span></span>
    
- <span data-ttu-id="a524d-156">Porcentaje de errores de A/V</span><span class="sxs-lookup"><span data-stu-id="a524d-156">A/V failure rate</span></span>
    
- <span data-ttu-id="a524d-157">Porcentaje de errores de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a524d-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="a524d-158">5 servidores principales por sesiones con error</span><span class="sxs-lookup"><span data-stu-id="a524d-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="a524d-159">Diagnósticos de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="a524d-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="a524d-160">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="a524d-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="a524d-161">Total de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="a524d-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="a524d-162">Porcentaje de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="a524d-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="a524d-163">Total de llamadas RTC de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="a524d-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="a524d-164">Una conferencia</span><span class="sxs-lookup"><span data-stu-id="a524d-164">Conference</span></span>
  
- <span data-ttu-id="a524d-165">Total de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="a524d-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="a524d-166">Porcentaje de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="a524d-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="a524d-167">Total de llamadas RTC de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="a524d-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="a524d-168">Los peores servidores por porcentaje de llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="a524d-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="a524d-169">Trabajar con el panel de supervisión</span><span class="sxs-lookup"><span data-stu-id="a524d-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="a524d-p103">Tal como hemos indicado, se muestran los totales predeterminados de la semana en curso y los valores de las tendencias de las seis últimas semanas. Si prefiere ver los totales del mes actual (así como los valores de las tendencias de los últimos seis meses), haga clic en el vínculo **Vista mensual** de la esquina superior derecha del panel. Si decide ver los totales mensuales, el texto del vínculo cambiará a **Vista semanal**. Puede volver a la vista semanal haciendo clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="a524d-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="a524d-p104">El panel de supervisión le limita la consulta a los totales de la semana en curso (o el mes en curso) y a los valores de las tendencias de las seis últimas semanas (o seis últimos meses). Estas fechas y horas no se pueden cambiar. Por ejemplo, con el panel no se pueden ver los totales de informe de un período que se inició nueve meses antes.</span><span class="sxs-lookup"><span data-stu-id="a524d-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="a524d-p105">Los valores que aparecen en las columnas **Esta semana**, **Este mes** u **Hoy** le vinculan a información más detallada sobre el elemento. Tenga en cuenta que el nombre de la columna y los valores que aparecen en ella cambiarán a menudo en función de la métrica elegida y en función de si ha seleccionado vista semanal o vista mensual. Por ejemplo, si hace clic en los totales que aparecen en la métrica **Inicios de sesión de usuario únicos**, verá el **Informe de registro de usuario** del período de tiempo especificado. Puede volver al panel de supervisión en cualquier momento, haciendo clic en **Panel**.</span><span class="sxs-lookup"><span data-stu-id="a524d-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="a524d-181">También puede acceder a la Página principal de informes del servidor de supervisión haciendo clic en el vínculo **informes** , en la esquina superior derecha del panel.</span><span class="sxs-lookup"><span data-stu-id="a524d-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="a524d-p106">La columna **Tendencia** muestra un gráfico de línea sencilla con los totales de las últimas seis semanas (o, en función de la métrica y del intervalo de tiempo, los últimos seis días o seis meses). Estos gráficos de línea sencilla muestran un punto de datos sin etiquetar por cada período de tiempo (por ejemplo, un punto de datos sin etiquetar por cada una de las seis últimas semanas). Ahora bien, puede recuperar los valores reales de estos gráficos manteniendo el puntero del mouse sobre el gráfico. En dicho caso, la información sobre herramientas muestra los valores máximo y mínimo del gráfico.</span><span class="sxs-lookup"><span data-stu-id="a524d-p106">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months). These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks). However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph. In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="a524d-186">Exportar datos desde el panel de supervisión</span><span class="sxs-lookup"><span data-stu-id="a524d-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="a524d-p107">El panel de supervisión proporciona varias formas de exportar la vista del panel actual. En la barra de herramientas del panel, verá un icono con el aspecto de un disquete con una flecha verde vinculada. Si hace clic en el icono, aparecerá una lista desplegable que le presentará los siguientes formatos de exportación de datos:</span><span class="sxs-lookup"><span data-stu-id="a524d-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="a524d-190">Archivo XML con datos de informe</span><span class="sxs-lookup"><span data-stu-id="a524d-190">XML file with report data</span></span>
    
- <span data-ttu-id="a524d-191">Archivo CSV (delimitado por comas)</span><span class="sxs-lookup"><span data-stu-id="a524d-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="a524d-192">PDF</span><span class="sxs-lookup"><span data-stu-id="a524d-192">PDF</span></span>
    
- <span data-ttu-id="a524d-193">Archivo MHTML (archivo web)</span><span class="sxs-lookup"><span data-stu-id="a524d-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="a524d-194">Archivo de Excel</span><span class="sxs-lookup"><span data-stu-id="a524d-194">Excel</span></span>
    
- <span data-ttu-id="a524d-195">Archivo TIFF</span><span class="sxs-lookup"><span data-stu-id="a524d-195">TIFF file</span></span>
    
- <span data-ttu-id="a524d-196">Archivo de Word</span><span class="sxs-lookup"><span data-stu-id="a524d-196">Word</span></span>
    
<span data-ttu-id="a524d-197">Para exportar la vista de panel actual (y sus valores), haga clic en la opción de exportación deseada.</span><span class="sxs-lookup"><span data-stu-id="a524d-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="a524d-198">Skype empresarial Server genera un informe en el formato especificado y, a continuación, le ofrece la opción de abrir ese informe o guardarlo.</span><span class="sxs-lookup"><span data-stu-id="a524d-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="a524d-199">Tenga en cuenta que, de forma predeterminada, los títulos de Skype empresarial Server son el **Panel de supervisión** de informes y los guarda en la carpeta descargas.</span><span class="sxs-lookup"><span data-stu-id="a524d-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="a524d-200">Para darle al informe otro nombre o guardarlo en otra carpeta, haga clic en la flecha situada al lado del botón **Guardar** y después haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="a524d-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="a524d-201">Si le parece bien el nombre **Panel de supervisión** y está de acuerdo en guardar el informe en la carpeta Descargas, solo tiene que hacer clic en el botón **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a524d-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="a524d-p109">Es posible que, cuando intente exportar datos del panel, aparezca el cuadro de diálogo **Alerta de seguridad** junto con el mensaje "La configuración actual no permite descargar este archivo". Si ocurre esto, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a524d-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>
  
- <span data-ttu-id="a524d-204">En Internet Explorer, seleccione **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="a524d-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="a524d-205">En el cuadro de diálogo **Opciones de Internet**, en la pestaña **Seguridad**, haga clic en **Sitios de confianza** y después en **Sitios**.</span><span class="sxs-lookup"><span data-stu-id="a524d-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="a524d-206">En el cuadro de diálogo **sitios de confianza** , haga clic en **Agregar** para agregar el servidor de Skype empresarial que ejecuta los informes de Skype empresarial Server a las colecciones de sitios web de confianza.</span><span class="sxs-lookup"><span data-stu-id="a524d-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="a524d-207">Haga clic en **Cerrar** y, luego, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a524d-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="a524d-p110">Necesitará actualizar el panel de supervisión antes de que entren en vigor los cambios. Para ello, presione F5 o haga clic en el icono **Actualizar** de la barra de herramientas del panel (el icono **Actualizar** es un círculo que contiene un par de flechas verdes).</span><span class="sxs-lookup"><span data-stu-id="a524d-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="a524d-p111">También puede crear una hoja de cálculo de Excel que contenga fuentes de datos activos, lo que incluye vínculos con los últimos datos del panel de supervisión. Para crear un archivo de fuentes de datos activos, haga clic en el icono naranja **Exportar a fuente de datos** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="a524d-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="a524d-213">Si prefiere imprimir el panel actual, haga clic en el icono de la impresora de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="a524d-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

