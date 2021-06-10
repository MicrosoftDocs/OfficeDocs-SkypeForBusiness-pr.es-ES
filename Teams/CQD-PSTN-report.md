---
title: Usar el informe de enrutamiento directo RTC de CQD
ms.author: serdars
author: SerdarSoysal
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
description: Use el Microsoft Teams de enrutamiento directo RTC (CQD)) para supervisar y solucionar las llamadas RTC en Microsoft Teams.
ms.openlocfilehash: f2b63f991f42aa4de9e0e4474137f7f992f95c53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094984"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="27a24-103">Usar el informe de enrutamiento directo RTC de CQD</span><span class="sxs-lookup"><span data-stu-id="27a24-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="27a24-104">Como novedad en marzo de 2020, hemos agregado un informe de enrutamiento directo RTC (CQD) del Panel de calidad de llamadas (CQD) de Microsoft Teams a nuestras plantillas de consulta de Power BI para [CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)descargables.</span><span class="sxs-lookup"><span data-stu-id="27a24-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="27a24-105">El informe de enrutamiento directo RTC CQD (CQD RTC Direct Routing Report.pbit) le ayuda a comprender los patrones de uso y la calidad de los servicios RTC.</span><span class="sxs-lookup"><span data-stu-id="27a24-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="27a24-106">Use este informe para supervisar el uso del servicio, información sobre el controlador de borde de sesión (SBC), el servicio de telefonía, los parámetros de red y los detalles de la relación de eficacia de red.</span><span class="sxs-lookup"><span data-stu-id="27a24-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="27a24-107">Esta información puede ayudarle a identificar problemas, incluido el motivo de las llamadas que se han eliminado.</span><span class="sxs-lookup"><span data-stu-id="27a24-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="27a24-108">Por ejemplo, podrá ver cuándo baja el volumen o cuántas llamadas se ven afectadas y por qué motivo.</span><span class="sxs-lookup"><span data-stu-id="27a24-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="27a24-109">El informe de enrutamiento directo RTC de CQD tiene cuatro secciones:</span><span class="sxs-lookup"><span data-stu-id="27a24-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="27a24-110">Información general sobre RTC</span><span class="sxs-lookup"><span data-stu-id="27a24-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="27a24-111">Detalles del servicio</span><span class="sxs-lookup"><span data-stu-id="27a24-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="27a24-112">Relación de eficacia de red</span><span class="sxs-lookup"><span data-stu-id="27a24-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="27a24-113">Parámetros de red</span><span class="sxs-lookup"><span data-stu-id="27a24-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="27a24-114">Momentos</span><span class="sxs-lookup"><span data-stu-id="27a24-114">Highlights</span></span>

1. <span data-ttu-id="27a24-115">Analizar por tipo de llamada, SBC, autor de la llamada y país de destinatario</span><span class="sxs-lookup"><span data-stu-id="27a24-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="27a24-116">El informe enrutamiento directo RTC CQD agrega métricas de confiabilidad y uso para todos los SBC del inquilino durante los últimos 7, 30 o 180 días (6 meses).</span><span class="sxs-lookup"><span data-stu-id="27a24-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="27a24-117">Puede analizar datos por tipo de llamada, SBC, autor de la llamada y país de destinatario.</span><span class="sxs-lookup"><span data-stu-id="27a24-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="27a24-118">Si está interesado en un determinado SBC o país, podrá identificar los cambios en las tendencias en el intervalo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="27a24-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Captura de pantalla de los filtros disponibles en el informe de enrutamiento directo RTC CQD":::
   
2. <span data-ttu-id="27a24-120">Control de tendencias</span><span class="sxs-lookup"><span data-stu-id="27a24-120">Track trends</span></span>

    <span data-ttu-id="27a24-121">El análisis de tendencias es esencial al intentar comprender el uso y la confiabilidad del servicio.</span><span class="sxs-lookup"><span data-stu-id="27a24-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="27a24-122">Las tendencias por horas proporcionan un vistazo al rendimiento diario, lo que ayuda a identificar incidentes en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="27a24-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="27a24-123">Las tendencias diarias le permiten ver el estado del servicio desde una perspectiva a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="27a24-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="27a24-124">Es importante poder cambiar entre esos dos modos con la granularidad de datos adecuada.</span><span class="sxs-lookup"><span data-stu-id="27a24-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="27a24-125">El informe enrutamiento directo RTC de CQD proporciona información general sobre tendencias de 6 meses, tendencias diarias de 7 y 30 días y tendencias por hora para que pueda analizar el rendimiento en cada nivel.</span><span class="sxs-lookup"><span data-stu-id="27a24-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Captura de pantalla de los gráficos de tendencias en el informe de enrutamiento directo RTC CQD":::

3. <span data-ttu-id="27a24-127">Explorar en profundidad hasta SBC o nivel de usuario</span><span class="sxs-lookup"><span data-stu-id="27a24-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="27a24-128">Hemos ido creando capacidades de obtención de detalles en muchas categorías de datos en CQD, lo que le permite comprender rápidamente el uso o la distribución de confiabilidad a nivel de SBC o usuario.</span><span class="sxs-lookup"><span data-stu-id="27a24-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="27a24-129">Al usar la exploración en profundidad, puede ver rápidamente los problemas de puntos de vista y comprender el impacto real de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="27a24-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="27a24-130">El informe enrutamiento directo RTC de CQD incluye información detallada sobre las métricas Detalle del servicio y Relación de eficacia de red.</span><span class="sxs-lookup"><span data-stu-id="27a24-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="27a24-131">Haga clic en el punto de datos en el que está interesado para explorar los detalles de SBC o de nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="27a24-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Captura de pantalla que muestra la capacidad de obtención de detalles en un punto de datos":::


## <a name="pstn-overview"></a><span data-ttu-id="27a24-133">Información general sobre RTC</span><span class="sxs-lookup"><span data-stu-id="27a24-133">PSTN Overview</span></span>

<span data-ttu-id="27a24-134">El informe de enrutamiento directo RTC de CQD proporciona la siguiente información relacionada con el estado general del servicio durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="27a24-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="27a24-135">![Captura de pantalla: informe CQD RTC](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="27a24-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="27a24-136">Por ejemplo, si está interesado en el uso general y el estado de todas las llamadas entrantes que pasan por SBC abc.bca.adatum.biz ee. UU. como país interno:</span><span class="sxs-lookup"><span data-stu-id="27a24-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="27a24-137">**Llamar**</span><span class="sxs-lookup"><span data-stu-id="27a24-137">**Call Out**</span></span> | <span data-ttu-id="27a24-138">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="27a24-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="27a24-139">1</span><span class="sxs-lookup"><span data-stu-id="27a24-139">1</span></span>            | <span data-ttu-id="27a24-140">Puede usar los filtros de la parte superior para explorar en profundidad y seleccionar ByotIn como tipo de llamada, abc.bca.contoso.com como controlador de panel de sesión y EE. UU. como país interno.</span><span class="sxs-lookup"><span data-stu-id="27a24-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="27a24-141">2</span><span class="sxs-lookup"><span data-stu-id="27a24-141">2</span></span>            | <span data-ttu-id="27a24-142">Tendencia de uso de los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="27a24-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="27a24-143">Puede encontrar el informe de detalles de uso en la página Detalles del servicio.</span><span class="sxs-lookup"><span data-stu-id="27a24-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="27a24-144">3</span><span class="sxs-lookup"><span data-stu-id="27a24-144">3</span></span>            | <span data-ttu-id="27a24-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span><span class="sxs-lookup"><span data-stu-id="27a24-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="27a24-146">Puede encontrar un informe detallado en la página Parámetros de red.</span><span class="sxs-lookup"><span data-stu-id="27a24-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="27a24-147">4</span><span class="sxs-lookup"><span data-stu-id="27a24-147">4</span></span>            | <span data-ttu-id="27a24-148">Tendencia de llamadas simultáneas y usuarios activos diarios de los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="27a24-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="27a24-149">Este gráfico puede ayudarle a comprender el volumen máximo del servicio.</span><span class="sxs-lookup"><span data-stu-id="27a24-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="27a24-150">5</span><span class="sxs-lookup"><span data-stu-id="27a24-150">5</span></span>            | <span data-ttu-id="27a24-151">El motivo de finalización de la llamada superior afectó a la calidad del servicio durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="27a24-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="27a24-152">Puede encontrar detalles del estado del servicio en la página Relación eficaz de red (NER).</span><span class="sxs-lookup"><span data-stu-id="27a24-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="27a24-153">Detalles del servicio</span><span class="sxs-lookup"><span data-stu-id="27a24-153">Service Details</span></span>

<span data-ttu-id="27a24-154">Esta página proporciona tendencias de uso del servicio por día y un desglose de los comentarios de los usuarios por geográfica.</span><span class="sxs-lookup"><span data-stu-id="27a24-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="27a24-155">**Total de llamadas de intento :** Total de llamadas tentativa en ese intervalo de tiempo, incluidas las llamadas correctas y las fallidas</span><span class="sxs-lookup"><span data-stu-id="27a24-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="27a24-156">**Total de llamadas conectadas:** Total de llamadas conectadas en ese intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="27a24-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="27a24-157">**Minutos totales:** Uso total de minutos en ese intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="27a24-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="27a24-158">**Usuarios activos diarios(DAU) –** Recuento de usuarios activos diarios que realizaron al menos una llamada conectada ese día</span><span class="sxs-lookup"><span data-stu-id="27a24-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="27a24-159">**Llamadas simultáneas:** Máximo de llamadas activas simultáneas en un minuto</span><span class="sxs-lookup"><span data-stu-id="27a24-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="27a24-160">**Comentarios de los usuarios:** La puntuación "Calificar mi llamada" proviene del usuario.</span><span class="sxs-lookup"><span data-stu-id="27a24-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="27a24-161">3-5 se considera una buena llamada.</span><span class="sxs-lookup"><span data-stu-id="27a24-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="27a24-162">1-2 se considera una mala llamada.</span><span class="sxs-lookup"><span data-stu-id="27a24-162">1-2 is considered as a bad call.</span></span>

![Captura de pantalla: informe CQD RTC](media/CQD-PSTN-report2.png)

<span data-ttu-id="27a24-164">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27a24-164">For example:</span></span>

1.  <span data-ttu-id="27a24-165">Si ve que la duración media de la llamada disminuye a 0 a las 02/14/2020, primero puede comprobar si el volumen de llamada tiene un aspecto normal y ver si hay una gran discrepancia entre las llamadas totales de conexión y las llamadas de intento total.</span><span class="sxs-lookup"><span data-stu-id="27a24-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="27a24-166">A continuación, vaya a la página Relación de eficacia de red para invertir en los motivos de error de llamada.</span><span class="sxs-lookup"><span data-stu-id="27a24-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="27a24-167">Si ve un aumento de puntos rojos en el mapa de comentarios de los usuarios, puede ir a la página Relación de eficacia de red y a Parámetro de red para ver si hay alguna anomalía y podría aumentar un vale con MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="27a24-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="27a24-168">Relación de eficacia de red</span><span class="sxs-lookup"><span data-stu-id="27a24-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="27a24-169">Esta es la misma métrica que aparece en el panel Estado general.</span><span class="sxs-lookup"><span data-stu-id="27a24-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="27a24-170">Puede comprobar el número NER por hora con el detalle de las llamadas afectadas para las dos direcciones de llamada (entrantes y salientes) en la relación de efectividad de la red por hora y en el gráfico de motivos de finalización de llamadas que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="27a24-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="27a24-171">**NER:** la capacidad (%) de una red para entregar llamadas midiendo el número de llamadas enviadas frente al número de llamadas entregadas a un destinatario.</span><span class="sxs-lookup"><span data-stu-id="27a24-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="27a24-172">**Código de respuesta SIP:** un código de respuesta entero de tres dígitos muestra el estado de la llamada.</span><span class="sxs-lookup"><span data-stu-id="27a24-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="27a24-173">**Código de respuesta de Microsoft:** un código de respuesta enviado desde el componente de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="27a24-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="27a24-174">**Descripción:** la fase de motivo que corresponde al código de respuesta SIP y al código de respuesta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="27a24-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="27a24-175">**Número de llamadas afectadas:** el número total de llamadas se ha visto afectada durante el intervalo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="27a24-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Captura de pantalla: informe CQD RTC](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="27a24-177">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27a24-177">For example:</span></span>

![Captura de pantalla: informe CQD RTC](media/CQD-PSTN-report4.png)

<span data-ttu-id="27a24-179">Si el 02/05/2020 del 02/05/2020, puede hacer clic en la fecha y otros gráficos se acercarán a esa fecha específica.</span><span class="sxs-lookup"><span data-stu-id="27a24-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Captura de pantalla: informe CQD RTC](media/CQD-PSTN-report5.png)

<span data-ttu-id="27a24-181">En la Tendencia buena por hora porcentual de NER, puede encontrar que la caída se produce alrededor de las 21:00.</span><span class="sxs-lookup"><span data-stu-id="27a24-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="27a24-182">A continuación, haga clic de nuevo para acercar a la hora 21 y compruebe Detalles de la llamada efectiva para ver cuántas llamadas fallaron en esa hora y cuáles son los motivos de finalización de la llamada.</span><span class="sxs-lookup"><span data-stu-id="27a24-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="27a24-183">Puede empezar con la grabación con problemas personales en cualquier problema de SBC o informar a Service Desk si el problema no está relacionado con SBC.</span><span class="sxs-lookup"><span data-stu-id="27a24-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="27a24-184">Parámetros de red</span><span class="sxs-lookup"><span data-stu-id="27a24-184">Network Parameters</span></span>

<span data-ttu-id="27a24-185">Todos los parámetros de red se miden desde la interfaz de enrutamiento directo al controlador de borde de sesión.</span><span class="sxs-lookup"><span data-stu-id="27a24-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="27a24-186">Para obtener información sobre los valores recomendados, vea Preparar la red de su organización para Microsoft Teams [y](prepare-network.md)consulte el Perímetro del cliente para Microsoft Edge valores recomendados.</span><span class="sxs-lookup"><span data-stu-id="27a24-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="27a24-187">**Vibración:** es la medida de milisegundos de variación en el tiempo de retraso de propagación de red que se calcula entre dos puntos de conexión mediante RTCP (el protocolo de control RTP).</span><span class="sxs-lookup"><span data-stu-id="27a24-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="27a24-188">**Pérdida de paquetes:** es una medida de paquete que no ha podido llegar; se calcula entre dos puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="27a24-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="27a24-189">**Latencia:** (también conocido como tiempo de ida y vuelta) es el tiempo que se tarda en enviar una señal más el tiempo que tarda en recibirse la confirmación de esa señal.</span><span class="sxs-lookup"><span data-stu-id="27a24-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="27a24-190">Este retraso de tiempo consiste en los tiempos de propagación entre los dos puntos de una señal.</span><span class="sxs-lookup"><span data-stu-id="27a24-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Captura de pantalla: informe CQD RTC](media/CQD-PSTN-report6.png)

<span data-ttu-id="27a24-192">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27a24-192">For example:</span></span>

<span data-ttu-id="27a24-193">Si ve un pico en cualquiera de los cuatro gráficos (Latencia, Vibración, Tasa de pérdida de paquetes, Retraso de marcado posterior) para una fecha específica, por ejemplo, Latencia el 14/02/2020, haga clic en el punto de fecha.</span><span class="sxs-lookup"><span data-stu-id="27a24-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="27a24-194">Y el gráfico de tendencia por hora en la parte inferior se actualizará para mostrar el número por hora.</span><span class="sxs-lookup"><span data-stu-id="27a24-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="27a24-195">Puede comprobar los SBC o aumentar un vale con MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="27a24-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Captura de pantalla: informe CQD RTC](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="27a24-197">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="27a24-197">Related topics</span></span>

[<span data-ttu-id="27a24-198">Use Power BI datos CQD para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="27a24-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="27a24-199">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="27a24-199">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)