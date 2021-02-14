---
title: Uso del informe enrutamiento directo RTC del CQD
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
description: Use el informe Enrutamiento directo de llamadas (CQD) de Microsoft Teams para supervisar y solucionar problemas de llamadas RTC en Microsoft Teams.
ms.openlocfilehash: e4662d80dbba88c1049c7ef98569dae408ca9ba0
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583107"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="8ac17-103">Uso del informe enrutamiento directo RTC del CQD</span><span class="sxs-lookup"><span data-stu-id="8ac17-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="8ac17-104">Como novedad en marzo de 2020, hemos agregado un informe de enrutamiento directo de llamadas (CQD) de Microsoft Teams a nuestras plantillas de consulta descargables de Power BI para [el CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8ac17-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="8ac17-105">El informe de enrutamiento directo RTC (CQD PSTN Direct Routing Report.pbit) del CQD le ayuda a comprender los patrones de uso y la calidad de los servicios RTC.</span><span class="sxs-lookup"><span data-stu-id="8ac17-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="8ac17-106">Utilice este informe para supervisar el uso del servicio, la información sobre el controlador de borde de sesión (SBC), el servicio de telefonía, los parámetros de red y los detalles de la relación de eficacia de red.</span><span class="sxs-lookup"><span data-stu-id="8ac17-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="8ac17-107">Esta información puede ayudarle a identificar problemas, incluido el motivo por el que se descartan llamadas.</span><span class="sxs-lookup"><span data-stu-id="8ac17-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="8ac17-108">Por ejemplo, podrá ver cuándo se reduce el volumen o cuántas llamadas se ven afectadas y por qué motivo.</span><span class="sxs-lookup"><span data-stu-id="8ac17-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="8ac17-109">El informe de enrutamiento directo DE RTC del CQD tiene cuatro secciones:</span><span class="sxs-lookup"><span data-stu-id="8ac17-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="8ac17-110">Introducción a RTC</span><span class="sxs-lookup"><span data-stu-id="8ac17-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="8ac17-111">Detalles del servicio</span><span class="sxs-lookup"><span data-stu-id="8ac17-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="8ac17-112">Relación de eficacia de red</span><span class="sxs-lookup"><span data-stu-id="8ac17-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="8ac17-113">Parámetros de red</span><span class="sxs-lookup"><span data-stu-id="8ac17-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="8ac17-114">Aspectos destacados</span><span class="sxs-lookup"><span data-stu-id="8ac17-114">Highlights</span></span>

1. <span data-ttu-id="8ac17-115">Analizar por tipo de llamada, SBC, país del autor de la llamada y destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="8ac17-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="8ac17-116">El informe enrutamiento directo RTC del CQD agrega las métricas de confiabilidad y uso de todos los TDC de su inquilino durante los últimos 7, 30 o 180 días (6 meses).</span><span class="sxs-lookup"><span data-stu-id="8ac17-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="8ac17-117">Puede analizar datos por tipo de llamada, SBC, país del autor de la llamada y destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8ac17-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="8ac17-118">Si está interesado en un SBC o país en particular, podrá identificar los cambios de las tendencias en el intervalo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8ac17-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Captura de pantalla de los filtros disponibles en el informe enrutamiento directo de RTC del CQD":::
   
2. <span data-ttu-id="8ac17-120">Realizar un seguimiento de las tendencias</span><span class="sxs-lookup"><span data-stu-id="8ac17-120">Track trends</span></span>

    <span data-ttu-id="8ac17-121">El análisis de tendencias es esencial al intentar comprender el uso del servicio y la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="8ac17-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="8ac17-122">Las tendencias cada hora ofrecen un vistazo al rendimiento diario, lo que ayuda a identificar incidentes en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="8ac17-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="8ac17-123">Las tendencias diarias le permiten ver el estado del servicio desde una perspectiva a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="8ac17-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="8ac17-124">Es importante poder cambiar entre estos dos modos con la granularidad de datos adecuada.</span><span class="sxs-lookup"><span data-stu-id="8ac17-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="8ac17-125">El informe enrutamiento directo RTC del CQD proporciona información general sobre las tendencias de 6 meses, las tendencias diarias de 7 y 30 días y las tendencias cada hora, para que pueda analizar el rendimiento en cada nivel.</span><span class="sxs-lookup"><span data-stu-id="8ac17-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Captura de pantalla de los gráficos de tendencias en el informe enrutamiento directo de RTC del CQD":::

3. <span data-ttu-id="8ac17-127">Explorar en profundidad hasta SBC o nivel de usuario</span><span class="sxs-lookup"><span data-stu-id="8ac17-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="8ac17-128">Hemos mejorado la capacidad de exploración en muchas categorías de datos en el CQD, que le permite comprender rápidamente el uso o la distribución de confiabilidad en el nivel de usuario o SBC.</span><span class="sxs-lookup"><span data-stu-id="8ac17-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="8ac17-129">Al explorar en profundidad, puede ver rápidamente los problemas de poinpoint y comprender el impacto real del usuario.</span><span class="sxs-lookup"><span data-stu-id="8ac17-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="8ac17-130">Las características del informe de enrutamiento directo RTC del CQD detallan las métricas de detalle del servicio y relación de eficacia de red.</span><span class="sxs-lookup"><span data-stu-id="8ac17-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="8ac17-131">Haga clic en el punto de datos que le interesa para explorar en profundidad los detalles de nivel de usuario o SBC.</span><span class="sxs-lookup"><span data-stu-id="8ac17-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Captura de pantalla que muestra la funcionalidad de exploración en profundidad en un punto de datos":::


## <a name="pstn-overview"></a><span data-ttu-id="8ac17-133">Introducción a RTC</span><span class="sxs-lookup"><span data-stu-id="8ac17-133">PSTN Overview</span></span>

<span data-ttu-id="8ac17-134">El informe de enrutamiento directo RTC del CQD proporciona la siguiente información relacionada con el estado general del servicio durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="8ac17-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="8ac17-135">![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="8ac17-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="8ac17-136">Por ejemplo, si está interesado en el uso general y el estado de todas las llamadas entrantes que pasan a través de SBC abc.bca.adatum.biz con EE. UU. como país interno:</span><span class="sxs-lookup"><span data-stu-id="8ac17-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="8ac17-137">**Llamar**</span><span class="sxs-lookup"><span data-stu-id="8ac17-137">**Call Out**</span></span> | <span data-ttu-id="8ac17-138">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8ac17-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="8ac17-139">1</span><span class="sxs-lookup"><span data-stu-id="8ac17-139">1</span></span>            | <span data-ttu-id="8ac17-140">Puedes usar los filtros de la parte superior para explorar en profundidad y seleccionar ByotIn como tipo de llamada, abc.bca.contoso.com controlador de la sesión y EE. UU. como país interno.</span><span class="sxs-lookup"><span data-stu-id="8ac17-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="8ac17-141">2</span><span class="sxs-lookup"><span data-stu-id="8ac17-141">2</span></span>            | <span data-ttu-id="8ac17-142">Tendencia de uso de los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="8ac17-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="8ac17-143">Puede encontrar el informe de detalles de uso en la página Detalles del servicio.</span><span class="sxs-lookup"><span data-stu-id="8ac17-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="8ac17-144">3</span><span class="sxs-lookup"><span data-stu-id="8ac17-144">3</span></span>            | <span data-ttu-id="8ac17-145">Tendencia de retraso después del marcado, latencia, vibración y pérdida de paquetes de los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="8ac17-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="8ac17-146">Puede encontrar el informe detallado en la página Parámetros de red.</span><span class="sxs-lookup"><span data-stu-id="8ac17-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="8ac17-147">4</span><span class="sxs-lookup"><span data-stu-id="8ac17-147">4</span></span>            | <span data-ttu-id="8ac17-148">Tendencia de llamadas simultáneas y usuarios activos diarios en los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="8ac17-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="8ac17-149">Este gráfico puede ayudarle a comprender el volumen máximo del servicio.</span><span class="sxs-lookup"><span data-stu-id="8ac17-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="8ac17-150">5</span><span class="sxs-lookup"><span data-stu-id="8ac17-150">5</span></span>            | <span data-ttu-id="8ac17-151">El motivo principal de la finalización de la llamada ha afectado a la calidad del servicio de los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="8ac17-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="8ac17-152">Encontrará información sobre el estado del servicio en la página relación de eficacia de red (NER).</span><span class="sxs-lookup"><span data-stu-id="8ac17-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="8ac17-153">Detalles del servicio</span><span class="sxs-lookup"><span data-stu-id="8ac17-153">Service Details</span></span>

<span data-ttu-id="8ac17-154">Esta página proporciona tendencias de uso del servicio por día y un desglose de los comentarios de los usuarios por ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="8ac17-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="8ac17-155">**Llamadas de intento total:** Llamadas de intento total en ese intervalo de tiempo, incluidas las llamadas con éxito y con errores</span><span class="sxs-lookup"><span data-stu-id="8ac17-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="8ac17-156">**Total de llamadas conectadas:** Total de llamadas conectadas en ese intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="8ac17-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="8ac17-157">**Minutos totales:** Uso total de minutos en ese intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="8ac17-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="8ac17-158">**Usuarios activos diarios(DAU):** Recuento de usuarios activos diarios que realizaron al menos una llamada conectada en ese día</span><span class="sxs-lookup"><span data-stu-id="8ac17-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="8ac17-159">**Llamadas simultáneas:** Máximo de llamadas activas simultáneas en un minuto</span><span class="sxs-lookup"><span data-stu-id="8ac17-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="8ac17-160">**Comentarios del usuario:** La puntuación "Calificar mi llamada" proviene del usuario.</span><span class="sxs-lookup"><span data-stu-id="8ac17-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="8ac17-161">3-5 se considera una buena llamada.</span><span class="sxs-lookup"><span data-stu-id="8ac17-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="8ac17-162">1-2 se considera una mala llamada.</span><span class="sxs-lookup"><span data-stu-id="8ac17-162">1-2 is considered as a bad call.</span></span>

![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report2.png)

<span data-ttu-id="8ac17-164">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8ac17-164">For example:</span></span>

1.  <span data-ttu-id="8ac17-165">Si ve que la duración de llamada media se reduce a 0 a las 14/02/2020, primero puede comprobar si el volumen de la llamada tiene un aspecto normal y ver si hay una gran discrepancia entre el total de llamadas que se conectan y el total de llamadas de intento.</span><span class="sxs-lookup"><span data-stu-id="8ac17-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="8ac17-166">A continuación, vaya a la página Relación de eficacia de red para invertir en los motivos de los errores de llamada.</span><span class="sxs-lookup"><span data-stu-id="8ac17-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="8ac17-167">Si ve aumento de puntos rojos en el mapa de comentarios de los usuarios, puede ir a la página Relación de eficacia de red y parámetro de red para ver si hay alguna anómalo y podría elevar un vale con el Servicio de asistencia de MS.</span><span class="sxs-lookup"><span data-stu-id="8ac17-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="8ac17-168">Relación de eficacia de red</span><span class="sxs-lookup"><span data-stu-id="8ac17-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="8ac17-169">Esta es la misma métrica que aparece en el panel Estado general.</span><span class="sxs-lookup"><span data-stu-id="8ac17-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="8ac17-170">Puede comprobar el número NER cada hora con los detalles de las llamadas afectadas para las dos direcciones de llamada (entrantes y salientes) en el gráfico de razones de finalización de llamada y relación de eficacia de red cada hora que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="8ac17-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="8ac17-171">**NER-** La capacidad (%) de una red para entregar llamadas midiendo el número de llamadas enviadas frente al número de llamadas que se han entregado a un destinatario.</span><span class="sxs-lookup"><span data-stu-id="8ac17-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="8ac17-172">**Código de respuesta SIP:** un código de respuesta entero de tres dígitos muestra el estado de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8ac17-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="8ac17-173">**Código de respuesta de Microsoft:** un código de respuesta enviado desde el componente de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ac17-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="8ac17-174">**Descripción:** la fase del motivo que corresponde al código de respuesta SIP y al código de respuesta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ac17-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="8ac17-175">**Número de llamadas afectadas:** el número total de llamadas que se han visto afectadas durante el intervalo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8ac17-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="8ac17-177">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8ac17-177">For example:</span></span>

![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report4.png)

<span data-ttu-id="8ac17-179">Si el NER diario tiene una caída el 05/02/2020, puede hacer clic en la fecha y otros gráficos se acercarán a esa fecha específica.</span><span class="sxs-lookup"><span data-stu-id="8ac17-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report5.png)

<span data-ttu-id="8ac17-181">En la tendencia de hora de porcentaje bueno de NER, puede encontrar que la baja ocurre alrededor de las 21:00.</span><span class="sxs-lookup"><span data-stu-id="8ac17-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="8ac17-182">A continuación, haga clic de nuevo para ampliar a la hora 21 y compruebe los detalles de la llamada efectiva para ver cuántas llamadas no se realizaron en esa hora y cuáles son los motivos de la finalización de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8ac17-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="8ac17-183">Puede empezar con problemas personales en relación con los problemas de SBC o informar al Servicio de atención al cliente si el problema no está relacionado con la SBC.</span><span class="sxs-lookup"><span data-stu-id="8ac17-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="8ac17-184">Parámetros de red</span><span class="sxs-lookup"><span data-stu-id="8ac17-184">Network Parameters</span></span>

<span data-ttu-id="8ac17-185">Todos los parámetros de red se miden desde la interfaz de enrutamiento directo al controlador de borde de sesión.</span><span class="sxs-lookup"><span data-stu-id="8ac17-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="8ac17-186">Para obtener información sobre los valores recomendados, vea Preparar la red de su organización para [Microsoft Teams](prepare-network.md)y mire los valores recomendados del perímetro del cliente hasta Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="8ac17-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="8ac17-187">**Vibración: es** la medida en milisegundos de la variación del tiempo de retraso en la propagación de red que se calcula entre dos puntos de conexión mediante RTCP (el protocolo de control RTP).</span><span class="sxs-lookup"><span data-stu-id="8ac17-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="8ac17-188">**Pérdida de paquetes:** es una medida del paquete que no pudo llegar; se calcula entre dos puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="8ac17-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="8ac17-189">**Latencia:** (también conocido como tiempo de ida y vuelta) es el tiempo que tarda una señal en enviarse más el tiempo que tarda en recibirse la confirmación de dicha señal.</span><span class="sxs-lookup"><span data-stu-id="8ac17-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="8ac17-190">Este retraso en el tiempo consiste en los tiempos de propagación entre los dos puntos de una señal.</span><span class="sxs-lookup"><span data-stu-id="8ac17-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report6.png)

<span data-ttu-id="8ac17-192">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8ac17-192">For example:</span></span>

<span data-ttu-id="8ac17-193">Si ve un pico en cualquiera de los cuatro gráficos (latencia, vibración, tasa de pérdida del paquete, retraso después del marcado) para una fecha específica, por ejemplo, latencia el 14/02/2020, haga clic en el punto de fecha.</span><span class="sxs-lookup"><span data-stu-id="8ac17-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="8ac17-194">Y el gráfico de tendencia cada hora en la parte inferior se actualizará para mostrar el número cada hora.</span><span class="sxs-lookup"><span data-stu-id="8ac17-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="8ac17-195">Puede revisar los sbcs o elevar un vale con el Servicio de asistencia de MS.</span><span class="sxs-lookup"><span data-stu-id="8ac17-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="8ac17-197">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8ac17-197">Related topics</span></span>

[<span data-ttu-id="8ac17-198">Usar Power BI para analizar datos del CQD para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ac17-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="8ac17-199">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="8ac17-199">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)