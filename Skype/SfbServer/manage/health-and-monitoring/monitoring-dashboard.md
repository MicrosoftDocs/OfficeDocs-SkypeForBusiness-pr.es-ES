---
title: Uso del panel de supervisión en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Resumen: obtenga información sobre el panel de supervisión en Skype Empresarial Server.'
ms.openlocfilehash: 98a96b8a513bad485a25aff76a69d787fb3079b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827790"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="fb49f-103">Uso del panel de supervisión en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="fb49f-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="fb49f-104">**Resumen:** Obtenga información sobre el panel de supervisión en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fb49f-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="fb49f-105">El panel de supervisión proporciona a los administradores una introducción rápida al uso del sistema y el estado del sistema de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fb49f-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="fb49f-106">El panel está diseñado para mostrar una vista agregada de métricas clave del sistema y para ello, muestra cualquiera de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="fb49f-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="fb49f-107">Totales del día actual.</span><span class="sxs-lookup"><span data-stu-id="fb49f-107">Totals for the current day.</span></span> <span data-ttu-id="fb49f-108">Tenga en cuenta que los valores que se muestran para el día actual representan datos registrados desde la medianoche hasta la hora actual (según la hora local del servidor de informes).</span><span class="sxs-lookup"><span data-stu-id="fb49f-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="fb49f-109">Esto significa que normalmente se verán los datos para un día parcial y no para un período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="fb49f-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="fb49f-110">Por ejemplo, si la hora local del servidor es las 8:00 a.m., verá datos de ocho horas porque hay ocho horas entre la medianoche y la hora actual de las 8:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="fb49f-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="fb49f-111">Totales de la semana y totales de tendencias de las últimas seis semanas.</span><span class="sxs-lookup"><span data-stu-id="fb49f-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="fb49f-112">Totales del mes y totales de tendencias de los últimos seis meses (solo para uso del sistema).</span><span class="sxs-lookup"><span data-stu-id="fb49f-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="fb49f-113">Tenga en cuenta que puede usar el cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) para devolver la dirección URL usada para obtener acceso a los informes de supervisión de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="fb49f-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="fb49f-114">De forma predeterminada, el Panel de supervisión muestra los datos de las métricas siguientes de la semana actual (y los totales de tendencias de las seis semanas anteriores):</span><span class="sxs-lookup"><span data-stu-id="fb49f-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="fb49f-115">Métricas de uso del sistema</span><span class="sxs-lookup"><span data-stu-id="fb49f-115">System Usage Metrics</span></span>

 <span data-ttu-id="fb49f-116">**Registro**</span><span class="sxs-lookup"><span data-stu-id="fb49f-116">**Registration**</span></span>
  
- <span data-ttu-id="fb49f-117">Inicios de sesión de usuario únicos</span><span class="sxs-lookup"><span data-stu-id="fb49f-117">Unique user logons</span></span>
    
  <span data-ttu-id="fb49f-118">**Punto a punto**</span><span class="sxs-lookup"><span data-stu-id="fb49f-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="fb49f-119">Total de sesiones</span><span class="sxs-lookup"><span data-stu-id="fb49f-119">Total sessions</span></span>
    
- <span data-ttu-id="fb49f-120">Sesiones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="fb49f-120">IM sessions</span></span>
    
- <span data-ttu-id="fb49f-121">Sesiones de audio</span><span class="sxs-lookup"><span data-stu-id="fb49f-121">Audio sessions</span></span>
    
- <span data-ttu-id="fb49f-122">Sesiones de vídeo</span><span class="sxs-lookup"><span data-stu-id="fb49f-122">Video sessions</span></span>
    
- <span data-ttu-id="fb49f-123">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fb49f-123">Application sharing</span></span>
    
- <span data-ttu-id="fb49f-124">Total de minutos de sesión de audio</span><span class="sxs-lookup"><span data-stu-id="fb49f-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="fb49f-125">Promedio de minutos de sesión de audio</span><span class="sxs-lookup"><span data-stu-id="fb49f-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="fb49f-126">**Conferencia**</span><span class="sxs-lookup"><span data-stu-id="fb49f-126">**Conference**</span></span>
  
- <span data-ttu-id="fb49f-127">Total de conferencias</span><span class="sxs-lookup"><span data-stu-id="fb49f-127">Total conferences</span></span>
    
- <span data-ttu-id="fb49f-128">Conferencias de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="fb49f-128">IM conferences</span></span>
    
- <span data-ttu-id="fb49f-129">Conferencias A/V</span><span class="sxs-lookup"><span data-stu-id="fb49f-129">A/V conferences</span></span>
    
- <span data-ttu-id="fb49f-130">Conferencias de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fb49f-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="fb49f-131">Conferencias web</span><span class="sxs-lookup"><span data-stu-id="fb49f-131">Web conferences</span></span>
    
- <span data-ttu-id="fb49f-132">Organizadores totales</span><span class="sxs-lookup"><span data-stu-id="fb49f-132">Total organizers</span></span>
    
- <span data-ttu-id="fb49f-133">Total de minutos de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="fb49f-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="fb49f-134">Promedio Minutos de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="fb49f-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="fb49f-135">Total de conferencias RTC</span><span class="sxs-lookup"><span data-stu-id="fb49f-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="fb49f-136">Total de participantes RTC</span><span class="sxs-lookup"><span data-stu-id="fb49f-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="fb49f-137">Total de minutos de participantes RTC</span><span class="sxs-lookup"><span data-stu-id="fb49f-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="fb49f-138">Además de las métricas de uso del sistema, las métricas siguientes muestran el total del día actual y los seis días anteriores (si selecciona Vista **semanal)** o para la semana actual y las últimas seis semanas si selecciona Vista **mensual.**</span><span class="sxs-lookup"><span data-stu-id="fb49f-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="fb49f-139">Per-User diagnóstico de llamadas</span><span class="sxs-lookup"><span data-stu-id="fb49f-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="fb49f-140">**Usuarios con errores de llamada**</span><span class="sxs-lookup"><span data-stu-id="fb49f-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="fb49f-141">Total de usuarios con errores de llamada</span><span class="sxs-lookup"><span data-stu-id="fb49f-141">Total users with call failures</span></span>
    
- <span data-ttu-id="fb49f-142">Organizadores de conferencias con errores de llamada</span><span class="sxs-lookup"><span data-stu-id="fb49f-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="fb49f-143">**Usuarios con llamadas de mala calidad**</span><span class="sxs-lookup"><span data-stu-id="fb49f-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="fb49f-144">Total de usuarios con llamadas de calidad deficiente</span><span class="sxs-lookup"><span data-stu-id="fb49f-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="fb49f-145">Diagnóstico de llamadas</span><span class="sxs-lookup"><span data-stu-id="fb49f-145">Call Diagnostics</span></span>

<span data-ttu-id="fb49f-146">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="fb49f-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="fb49f-147">Errores totales</span><span class="sxs-lookup"><span data-stu-id="fb49f-147">Total failures</span></span>
    
- <span data-ttu-id="fb49f-148">Tasa de errores general</span><span class="sxs-lookup"><span data-stu-id="fb49f-148">Overall failure rate</span></span>
    
- <span data-ttu-id="fb49f-149">Tasa de errores de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="fb49f-149">IM failure rate</span></span>
    
- <span data-ttu-id="fb49f-150">Tasa de errores de audio</span><span class="sxs-lookup"><span data-stu-id="fb49f-150">Audio failure rate</span></span>
    
- <span data-ttu-id="fb49f-151">Tasa de errores de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fb49f-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="fb49f-152">Conferencia</span><span class="sxs-lookup"><span data-stu-id="fb49f-152">Conference</span></span>
  
- <span data-ttu-id="fb49f-153">Errores totales</span><span class="sxs-lookup"><span data-stu-id="fb49f-153">Total failures</span></span>
    
- <span data-ttu-id="fb49f-154">Tasa de errores general</span><span class="sxs-lookup"><span data-stu-id="fb49f-154">Overall failure rate</span></span>
    
- <span data-ttu-id="fb49f-155">Tasa de errores de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="fb49f-155">IM failure rate</span></span>
    
- <span data-ttu-id="fb49f-156">Tasa de errores de A/V</span><span class="sxs-lookup"><span data-stu-id="fb49f-156">A/V failure rate</span></span>
    
- <span data-ttu-id="fb49f-157">Tasa de errores de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fb49f-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="fb49f-158">Principales cinco servidores por sesiones con errores</span><span class="sxs-lookup"><span data-stu-id="fb49f-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="fb49f-159">Diagnósticos de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="fb49f-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="fb49f-160">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="fb49f-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="fb49f-161">Llamadas de calidad deficiente totales</span><span class="sxs-lookup"><span data-stu-id="fb49f-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="fb49f-162">Porcentaje de llamadas de mala calidad</span><span class="sxs-lookup"><span data-stu-id="fb49f-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="fb49f-163">Llamadas RTC con mala calidad</span><span class="sxs-lookup"><span data-stu-id="fb49f-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="fb49f-164">Conferencia</span><span class="sxs-lookup"><span data-stu-id="fb49f-164">Conference</span></span>
  
- <span data-ttu-id="fb49f-165">Llamadas de calidad deficiente totales</span><span class="sxs-lookup"><span data-stu-id="fb49f-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="fb49f-166">Porcentaje de llamadas de mala calidad</span><span class="sxs-lookup"><span data-stu-id="fb49f-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="fb49f-167">Llamadas RTC con mala calidad</span><span class="sxs-lookup"><span data-stu-id="fb49f-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="fb49f-168">Principales servidores por porcentaje de llamadas de mala calidad</span><span class="sxs-lookup"><span data-stu-id="fb49f-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="fb49f-169">Trabajar con el panel de supervisión</span><span class="sxs-lookup"><span data-stu-id="fb49f-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="fb49f-170">Como se ha indicado, los totales predeterminados se muestran para la semana actual y los valores de tendencia se muestran en las últimas seis semanas.</span><span class="sxs-lookup"><span data-stu-id="fb49f-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="fb49f-171">Si prefiere ver los totales del mes actual (así como los valores  de tendencia de los últimos seis meses), haga clic en el vínculo Vista mensual en la esquina superior derecha del panel.</span><span class="sxs-lookup"><span data-stu-id="fb49f-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="fb49f-172">Si decide ver los totales mensuales, el texto del vínculo cambiará a **Vista semanal.**</span><span class="sxs-lookup"><span data-stu-id="fb49f-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="fb49f-173">Puede volver a la vista semanal haciendo clic en ese vínculo.</span><span class="sxs-lookup"><span data-stu-id="fb49f-173">You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="fb49f-174">El Panel de supervisión le limita a ver los totales de la semana actual (o mes) y los valores de tendencia de las últimas seis semanas (o meses).</span><span class="sxs-lookup"><span data-stu-id="fb49f-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="fb49f-175">No puede cambiar estas fechas y horas.</span><span class="sxs-lookup"><span data-stu-id="fb49f-175">You cannot change these dates and times.</span></span> <span data-ttu-id="fb49f-176">Por ejemplo, no puede usar el panel para ver los totales del informe del período de tiempo que comenzó hace nueve meses.</span><span class="sxs-lookup"><span data-stu-id="fb49f-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="fb49f-177">Los valores que se muestran en **las columnas Esta semana**, Este **mes** o **Hoy** le vinculan a información más detallada sobre el elemento.</span><span class="sxs-lookup"><span data-stu-id="fb49f-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="fb49f-178">Tenga en cuenta que el nombre de columna y los valores que se muestran en esa columna a menudo serán diferentes en función de la métrica elegida y en función de si ha seleccionado la vista semanal o la vista mensual.</span><span class="sxs-lookup"><span data-stu-id="fb49f-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="fb49f-179">Por ejemplo, si hace clic en los totales que se  muestran para la métrica **Inicios** de sesión de usuario único, verá el Informe de registro de usuarios para el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="fb49f-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="fb49f-180">Puede volver al Panel de supervisión en cualquier momento haciendo clic en **Panel.**</span><span class="sxs-lookup"><span data-stu-id="fb49f-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="fb49f-181">También puede obtener acceso a la página  principal de informes del servidor de supervisión haciendo clic en el vínculo Informes de la esquina superior derecha del panel.</span><span class="sxs-lookup"><span data-stu-id="fb49f-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="fb49f-182">La **columna Tendencia** muestra un gráfico de líneas sencillo que muestra los totales de las últimas seis semanas (o, según la métrica y el intervalo de tiempo, los últimos seis días o los últimos seis meses).</span><span class="sxs-lookup"><span data-stu-id="fb49f-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="fb49f-183">Estos gráficos de líneas simples muestran un punto de datos sin etiquetar para cada período de tiempo (por ejemplo, un punto de datos sin etiquetar para cada una de las últimas seis semanas).</span><span class="sxs-lookup"><span data-stu-id="fb49f-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="fb49f-184">Sin embargo, puede recuperar los valores reales de estos gráficos manteniendo el puntero del mouse sobre el gráfico.</span><span class="sxs-lookup"><span data-stu-id="fb49f-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="fb49f-185">En ese caso, una información sobre herramientas muestra los valores máximos y mínimos del gráfico.</span><span class="sxs-lookup"><span data-stu-id="fb49f-185">In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="fb49f-186">Exportación de datos desde el panel de supervisión</span><span class="sxs-lookup"><span data-stu-id="fb49f-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="fb49f-187">El Panel de supervisión proporciona varias formas de exportar la vista de panel actual.</span><span class="sxs-lookup"><span data-stu-id="fb49f-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="fb49f-188">En la barra de herramientas panel, verá un icono que tiene el aspecto de un disquete con una flecha verde adjunta.</span><span class="sxs-lookup"><span data-stu-id="fb49f-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="fb49f-189">Si hace clic en este icono, aparecerá una lista desplegable con los siguientes formatos de exportación de datos:</span><span class="sxs-lookup"><span data-stu-id="fb49f-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="fb49f-190">Archivo XML con datos de informe</span><span class="sxs-lookup"><span data-stu-id="fb49f-190">XML file with report data</span></span>
    
- <span data-ttu-id="fb49f-191">Archivo CSV (delimitado por comas)</span><span class="sxs-lookup"><span data-stu-id="fb49f-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="fb49f-192">PDF</span><span class="sxs-lookup"><span data-stu-id="fb49f-192">PDF</span></span>
    
- <span data-ttu-id="fb49f-193">Archivo MHTML (archivo web)</span><span class="sxs-lookup"><span data-stu-id="fb49f-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="fb49f-194">Excel</span><span class="sxs-lookup"><span data-stu-id="fb49f-194">Excel</span></span>
    
- <span data-ttu-id="fb49f-195">Archivo TIFF</span><span class="sxs-lookup"><span data-stu-id="fb49f-195">TIFF file</span></span>
    
- <span data-ttu-id="fb49f-196">Word</span><span class="sxs-lookup"><span data-stu-id="fb49f-196">Word</span></span>
    
<span data-ttu-id="fb49f-197">Para exportar la vista de panel actual (y sus valores), haga clic en la opción de exportación deseada.</span><span class="sxs-lookup"><span data-stu-id="fb49f-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="fb49f-198">Skype Empresarial Server genera un informe en el formato especificado y, a continuación, le ofrece la opción de abrir ese informe o guardarlo.</span><span class="sxs-lookup"><span data-stu-id="fb49f-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="fb49f-199">Tenga en cuenta que, de forma predeterminada, Skype Empresarial Server títulos del panel de supervisión de informes y lo guarda en la carpeta descargas. </span><span class="sxs-lookup"><span data-stu-id="fb49f-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="fb49f-200">Para dar un nombre diferente al informe o almacenarlo en una  carpeta diferente, haga clic en la flecha situada junto al botón Guardar y, a continuación, haga clic **en Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="fb49f-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="fb49f-201">Si está bien con el panel de **supervisión** de nombres y con el informe guardado en la carpeta Descargas, solo tiene que hacer clic en **el botón** Guardar.</span><span class="sxs-lookup"><span data-stu-id="fb49f-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="fb49f-202">Es posible que, al intentar exportar datos  del panel, aparezca un cuadro de diálogo Alerta de seguridad junto con el mensaje "La configuración actual no permite que se descargue este archivo".</span><span class="sxs-lookup"><span data-stu-id="fb49f-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="fb49f-203">Si esto ocurre, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb49f-203">If that occurs, do the following:</span></span>
  
- <span data-ttu-id="fb49f-204">En Internet Explorer, seleccione **Opciones de Internet.**</span><span class="sxs-lookup"><span data-stu-id="fb49f-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="fb49f-205">En el cuadro de diálogo Opciones de **Internet,** en la **ficha** Seguridad, haga clic en Sitios de **confianza** y, a continuación, en **Sitios.**</span><span class="sxs-lookup"><span data-stu-id="fb49f-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="fb49f-206">En el cuadro de  **diálogo Sitios** de confianza, haga clic en Agregar para agregar el Skype Empresarial Server que ejecuta informes de Skype Empresarial Server a las colecciones de sitios web de confianza.</span><span class="sxs-lookup"><span data-stu-id="fb49f-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="fb49f-207">Haga **clic en Cerrar** y, a continuación, en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="fb49f-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="fb49f-208">A continuación, deberá actualizar el Panel de supervisión antes de que los cambios sumen efecto.</span><span class="sxs-lookup"><span data-stu-id="fb49f-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="fb49f-209">Para ello, presione F5 o  haga clic en el icono Actualizar de la barra de herramientas del panel.</span><span class="sxs-lookup"><span data-stu-id="fb49f-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="fb49f-210">(El **icono** Actualizar es un círculo con un par de flechas verdes).</span><span class="sxs-lookup"><span data-stu-id="fb49f-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="fb49f-211">También puede crear una hoja de cálculo de Excel que incluya fuentes de datos dinámicas, que incluya vínculos a los últimos datos del Panel de supervisión.</span><span class="sxs-lookup"><span data-stu-id="fb49f-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="fb49f-212">Para crear un archivo de fuente de datos en directo, haga clic en el icono **naranja** Exportar a fuente de datos de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="fb49f-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="fb49f-213">Si prefiere imprimir el panel actual, haga clic en el icono de impresora de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="fb49f-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

