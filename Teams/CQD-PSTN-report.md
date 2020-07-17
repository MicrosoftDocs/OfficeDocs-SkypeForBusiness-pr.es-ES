---
title: Usar el informe de enrutamiento directo RTC de CQD
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies, fan.fan
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
description: Use el panel de calidad de llamadas de Microsoft Teams (CQD)) informe de enrutamiento directo de RTC para supervisar y solucionar problemas de llamadas RTC en Microsoft Teams.
ms.openlocfilehash: 0987ae30c9bb0b428a4d46bf036c2de938c555f0
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085346"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="1debf-103">Usar el informe de enrutamiento directo RTC de CQD</span><span class="sxs-lookup"><span data-stu-id="1debf-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="1debf-104">Novedades de marzo de 2020 hemos agregado un informe de enrutamiento directo de la RTC del panel de calidad de llamadas de Microsoft Teams (CQD) a [las plantillas de consultas descargables de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="1debf-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="1debf-105">El informe de enrutamiento directo de CQD de CQD (informe de enrutamiento directo de RTC de CQD. PBit) le ayuda a comprender los patrones de uso y la calidad de sus servicios RTC.</span><span class="sxs-lookup"><span data-stu-id="1debf-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="1debf-106">Use este informe para supervisar el uso del servicio, información sobre el controlador de borde de sesión (SBC), el servicio de telefonía, los parámetros de red y los detalles de la relación de la efectividad de la red.</span><span class="sxs-lookup"><span data-stu-id="1debf-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="1debf-107">Esta información puede ayudarte a identificar los problemas, incluido el motivo de las llamadas interrumpidas.</span><span class="sxs-lookup"><span data-stu-id="1debf-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="1debf-108">Por ejemplo, podrás ver cuándo disminuye el volumen o cuántas llamadas se ven afectadas y por qué motivos.</span><span class="sxs-lookup"><span data-stu-id="1debf-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="1debf-109">El informe de enrutamiento directo RTC de CQD tiene cuatro secciones:</span><span class="sxs-lookup"><span data-stu-id="1debf-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="1debf-110">Información general de RTC</span><span class="sxs-lookup"><span data-stu-id="1debf-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="1debf-111">Detalles del servicio</span><span class="sxs-lookup"><span data-stu-id="1debf-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="1debf-112">Relación de efectividad de la red</span><span class="sxs-lookup"><span data-stu-id="1debf-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="1debf-113">Parámetros de red</span><span class="sxs-lookup"><span data-stu-id="1debf-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="1debf-114">Saltar</span><span class="sxs-lookup"><span data-stu-id="1debf-114">Highlights</span></span>

1. <span data-ttu-id="1debf-115">Analizar por tipo de llamada, SBC, autor de la llamada y país de la llamada</span><span class="sxs-lookup"><span data-stu-id="1debf-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="1debf-116">El informe de enrutamiento directo del CQD de CQD agrega métricas de confiabilidad y uso para todos los SBCs de su inquilino para los últimos 7, 30 o 180 días (6 meses).</span><span class="sxs-lookup"><span data-stu-id="1debf-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="1debf-117">Puede analizar datos por tipo de llamada, SBC, autor de la llamada y país de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1debf-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="1debf-118">Si está interesado en un determinado país o SBC, podrá identificar los cambios en las tendencias durante el intervalo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1debf-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Captura de pantalla de filtros disponibles en el informe de enrutamiento directo de CQD de CQD":::
   
2. <span data-ttu-id="1debf-120">Rastrear tendencias</span><span class="sxs-lookup"><span data-stu-id="1debf-120">Track trends</span></span>

    <span data-ttu-id="1debf-121">El análisis de tendencias es esencial al intentar comprender la confiabilidad y el uso del servicio.</span><span class="sxs-lookup"><span data-stu-id="1debf-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="1debf-122">Las tendencias por hora proporcionan un estrecho aspecto del rendimiento diario, lo que ayuda a identificar incidentes en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="1debf-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="1debf-123">Las tendencias diarias le permiten ver su estado del servicio desde una perspectiva a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="1debf-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="1debf-124">Es importante poder alternar entre los dos modos con la granularidad de datos adecuada.</span><span class="sxs-lookup"><span data-stu-id="1debf-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="1debf-125">El informe de enrutamiento directo RTC de CQD proporciona información general de las tendencias de seis meses, tendencias diarias de 7 y 30 días y tendencias por hora para que pueda analizar el rendimiento de cada nivel.</span><span class="sxs-lookup"><span data-stu-id="1debf-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Captura de pantalla de gráficos de tendencias en el informe de enrutamiento directo RTC de CQD":::

3. <span data-ttu-id="1debf-127">Obtención de detalles de SBC o nivel de usuario</span><span class="sxs-lookup"><span data-stu-id="1debf-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="1debf-128">Hemos creado una capacidad de obtención de detalles en muchas categorías de datos de CQD, lo que le permite comprender rápidamente el uso o la distribución de confiabilidad en el nivel de usuario o de SBC.</span><span class="sxs-lookup"><span data-stu-id="1debf-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="1debf-129">Al usar la obtención de detalles, puede poinpoint problemas rápidamente y comprender el impacto real de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1debf-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="1debf-130">El informe de enrutamiento directo de CQD RTC ofrece obtención de detalles de las métricas de relación de detalles de servicio y eficacia de red.</span><span class="sxs-lookup"><span data-stu-id="1debf-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="1debf-131">Haga clic en el punto de datos en el que está interesado para obtener detalles sobre la información de SBC o de nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="1debf-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Captura de pantalla que muestra la capacidad de obtención de detalles en un punto de datos":::


## <a name="pstn-overview"></a><span data-ttu-id="1debf-133">Información general de RTC</span><span class="sxs-lookup"><span data-stu-id="1debf-133">PSTN Overview</span></span>

<span data-ttu-id="1debf-134">El informe de enrutamiento directo RTC de CQD proporciona la siguiente información relacionada con el estado general del servicio durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="1debf-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="1debf-135">![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="1debf-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="1debf-136">Por ejemplo, si estás interesado en el uso general y en la salud de todas las llamadas entrantes pasando por SBC abc.bca.adatum.biz con nosotros como país interno:</span><span class="sxs-lookup"><span data-stu-id="1debf-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="1debf-137">**Llamar**</span><span class="sxs-lookup"><span data-stu-id="1debf-137">**Call Out**</span></span> | <span data-ttu-id="1debf-138">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1debf-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1debf-139">1</span><span class="sxs-lookup"><span data-stu-id="1debf-139">1</span></span>            | <span data-ttu-id="1debf-140">Puede usar los filtros de la parte superior para explorar en profundidad y seleccionar ByotIn como tipo de llamada, abc.bca.contoso.com como controlador de panel de sesión y nosotros como país interno.</span><span class="sxs-lookup"><span data-stu-id="1debf-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="1debf-141">2</span><span class="sxs-lookup"><span data-stu-id="1debf-141">2</span></span>            | <span data-ttu-id="1debf-142">Tendencia de uso durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="1debf-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="1debf-143">Puede encontrar el informe de detalles de uso en la página Detalles del servicio.</span><span class="sxs-lookup"><span data-stu-id="1debf-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="1debf-144">3</span><span class="sxs-lookup"><span data-stu-id="1debf-144">3</span></span>            | <span data-ttu-id="1debf-145">Tendencia de posmarcado, latencia, vibración y pérdida de paquetes durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="1debf-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="1debf-146">Puede encontrar informes detallados en la página parámetros de red.</span><span class="sxs-lookup"><span data-stu-id="1debf-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="1debf-147">4</span><span class="sxs-lookup"><span data-stu-id="1debf-147">4</span></span>            | <span data-ttu-id="1debf-148">Llamada simultánea y tendencia de usuario activo diario durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="1debf-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="1debf-149">Este gráfico puede ayudarte a comprender el volumen máximo del servicio.</span><span class="sxs-lookup"><span data-stu-id="1debf-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="1debf-150">5</span><span class="sxs-lookup"><span data-stu-id="1debf-150">5</span></span>            | <span data-ttu-id="1debf-151">Motivo principal de finalización de la llamada la calidad de servicio afectada durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="1debf-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="1debf-152">Puede encontrar información sobre el estado del servicio en la página proporción de efectividad de red (NER).</span><span class="sxs-lookup"><span data-stu-id="1debf-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="1debf-153">Detalles del servicio</span><span class="sxs-lookup"><span data-stu-id="1debf-153">Service Details</span></span>

<span data-ttu-id="1debf-154">Esta página proporciona las tendencias de uso del servicio por día y el desglose de comentarios del usuario en forma geográfica.</span><span class="sxs-lookup"><span data-stu-id="1debf-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="1debf-155">**Llamadas totales:** Total de llamadas realizadas en ese intervalo de tiempo, incluidas las llamadas correctas y erróneas</span><span class="sxs-lookup"><span data-stu-id="1debf-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="1debf-156">**Total de llamadas conectadas:** Total de llamadas conectadas en ese intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="1debf-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="1debf-157">**Minutos totales:** Uso total de minutos en ese intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="1debf-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="1debf-158">**Usuarios activos diarios (DAU):** Recuento de usuarios activos diarios que hicieron al menos una llamada conectada en ese día</span><span class="sxs-lookup"><span data-stu-id="1debf-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="1debf-159">**Llamadas simultáneas:** Máximo de llamadas simultáneas activas en un minuto</span><span class="sxs-lookup"><span data-stu-id="1debf-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="1debf-160">**Comentarios del usuario:** La puntuación de "calificar la llamada" viene del usuario.</span><span class="sxs-lookup"><span data-stu-id="1debf-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="1debf-161">3-5 se considera una buena llamada.</span><span class="sxs-lookup"><span data-stu-id="1debf-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="1debf-162">1-2 se considera una llamada incorrecta.</span><span class="sxs-lookup"><span data-stu-id="1debf-162">1-2 is considered as a bad call.</span></span>

![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report2.png)

<span data-ttu-id="1debf-164">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1debf-164">For example:</span></span>

1.  <span data-ttu-id="1debf-165">Si ve que la duración media de las llamadas desciende a 0 en 02/14/2020, primero puede comprobar si el volumen de la llamada es normal y ver si hay una gran diferencia entre las llamadas de conexión totales y las llamadas de intento total.</span><span class="sxs-lookup"><span data-stu-id="1debf-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="1debf-166">A continuación, vaya a la página relación de eficacia de red para invertir en las razones de error de llamada.</span><span class="sxs-lookup"><span data-stu-id="1debf-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="1debf-167">Si ve el aumento de los puntos rojos en el mapa de comentarios del usuario, puede ir a la página relación efectividad de red y el parámetro red para ver si hay anomalías y puede generar un vale con el servicio de asistencia al cliente de MS.</span><span class="sxs-lookup"><span data-stu-id="1debf-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="1debf-168">Relación de efectividad de la red</span><span class="sxs-lookup"><span data-stu-id="1debf-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="1debf-169">Esta es la misma métrica que aparece en el panel General de estado.</span><span class="sxs-lookup"><span data-stu-id="1debf-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="1debf-170">Puedes comprobar el número de NER por hora con detalles de llamadas afectadas para ambas direcciones de llamadas (entrante o saliente) en relación con la proporción de eficacia de la red por hora y en el gráfico de motivos de finalización de llamadas que figura a continuación.</span><span class="sxs-lookup"><span data-stu-id="1debf-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="1debf-171">**Ner** : la capacidad (%) de una red para hacer llamadas midiendo el número de llamadas enviadas en comparación con el número de llamadas enviadas a un destinatario.</span><span class="sxs-lookup"><span data-stu-id="1debf-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="1debf-172">**Código de respuesta SIP**: el código de respuesta entero de tres dígitos muestra el estado de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1debf-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="1debf-173">**Código de respuesta de Microsoft**: un código de respuesta enviado desde un componente de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1debf-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="1debf-174">**Descripción** : la fase de razón que corresponde al código de respuesta SIP y al código de respuesta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1debf-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="1debf-175">**Número de llamadas afectadas** : el número total de llamadas se ha visto afectado durante el intervalo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1debf-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="1debf-177">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1debf-177">For example:</span></span>

![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report4.png)

<span data-ttu-id="1debf-179">Si el NER diario tiene una DIP en 02/05/2020, puede hacer clic en la fecha y otros gráficos le aplicarán un zoom para esa fecha específica.</span><span class="sxs-lookup"><span data-stu-id="1debf-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report5.png)

<span data-ttu-id="1debf-181">Desde la tendencia por hora del NER en buen lugar, puede encontrar la DIP en aproximadamente 21:00.</span><span class="sxs-lookup"><span data-stu-id="1debf-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="1debf-182">A continuación, haga clic de nuevo para acercar la hora 21 y comprobar los detalles de la llamada para ver cuántas llamadas han fallado en esa hora y cuáles son los motivos de finalización de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1debf-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="1debf-183">Puede comenzar con la solución de problemas con cualquier problema de SBC o enviar un informe a un servicio de asistencia al cliente si el problema no está relacionado con SBC.</span><span class="sxs-lookup"><span data-stu-id="1debf-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="1debf-184">Parámetros de red</span><span class="sxs-lookup"><span data-stu-id="1debf-184">Network Parameters</span></span>

<span data-ttu-id="1debf-185">Todos los parámetros de red se miden desde la interfaz de enrutamiento directo hasta el controlador de borde de la sesión.</span><span class="sxs-lookup"><span data-stu-id="1debf-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="1debf-186">Para obtener más información sobre los valores recomendados, consulte [preparar la red de su organización para Microsoft Teams](prepare-network.md)y mire los valores recomendados de borde del cliente a Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="1debf-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="1debf-187">**Vibración** : es la medición de milisegundos de variación en el tiempo de retraso de propagación de red calculado entre dos puntos de conexión con RTCP (el protocolo de control RTP).</span><span class="sxs-lookup"><span data-stu-id="1debf-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="1debf-188">**Pérdida de paquetes** : es una medida de paquete que no pudo llegar. se calcula entre dos puntos finales.</span><span class="sxs-lookup"><span data-stu-id="1debf-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="1debf-189">**Latencia** : (también conocido como tiempo de ida y vuelta) es la cantidad de tiempo que se tarda en enviar una señal más el tiempo que tarda en recibirse el reconocimiento de esa señal.</span><span class="sxs-lookup"><span data-stu-id="1debf-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="1debf-190">Este tiempo de retardo consiste en los tiempos de propagación entre los dos puntos de una señal.</span><span class="sxs-lookup"><span data-stu-id="1debf-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report6.png)

<span data-ttu-id="1debf-192">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1debf-192">For example:</span></span>

<span data-ttu-id="1debf-193">Si ve un pico en cualquiera de los cuatro gráficos (latencia, vibración, tasa de pérdida de paquetes, retraso de la publicación de marcado) para una fecha específica, por ejemplo, latencia en 02/14/2020, haga clic en el punto de fecha.</span><span class="sxs-lookup"><span data-stu-id="1debf-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="1debf-194">Y el gráfico de tendencia por hora en la parte inferior se actualizará para mostrar el número por hora.</span><span class="sxs-lookup"><span data-stu-id="1debf-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="1debf-195">Puede comprobar el SBCs o provocar un vale con el servicio de asistencia al cliente de MS.</span><span class="sxs-lookup"><span data-stu-id="1debf-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="1debf-197">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1debf-197">Related topics</span></span>

[<span data-ttu-id="1debf-198">Usar Power BI para analizar los datos del CQD para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1debf-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="1debf-199">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="1debf-199">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)