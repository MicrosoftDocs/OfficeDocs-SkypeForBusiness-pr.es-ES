---
title: Usar el informe de enrutamiento directo RTC de CQD
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
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
description: Use el informe de enrutamiento directo RTC de CQD para supervisar y solucionar problemas de llamadas RTC en Microsoft Teams.
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559614"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="f338d-103">Usar el informe de enrutamiento directo RTC de CQD</span><span class="sxs-lookup"><span data-stu-id="f338d-103">Using the CQD PSTN Direct Routing Report</span></span>

<span data-ttu-id="f338d-104">Novedades de marzo de 2020 hemos agregado un informe de enrutamiento directo de la RTC de CQD a nuestras [plantillas de consultas descargables de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="f338d-104">New in March 2020, we've added a CQD PSTN Direct Routing Report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="f338d-105">El informe de enrutamiento directo de la RTC de CQD ayuda a los clientes a comprender los patrones de uso y la calidad de sus servicios de RTC monitoran información sobre su SBC, el servicio de telefonía, los parámetros de red y la relación de la efectividad de la red y el uso de la Service.</span><span class="sxs-lookup"><span data-stu-id="f338d-105">The CQD PSTN Direct Routing Report helps customers to understand the usage patterns and quality of their PSTN services monitor information about your SBC, the telephony service, the network parameters, and Network Effectiveness Ratio details and usage of the service.</span></span> <span data-ttu-id="f338d-106">Esta información puede ayudarte a identificar los problemas, incluido el motivo de las llamadas interrumpidas.</span><span class="sxs-lookup"><span data-stu-id="f338d-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="f338d-107">Por ejemplo, podrá saber cuándo disminuye el volumen, cuántas llamadas se verán afectadas por el motivo.</span><span class="sxs-lookup"><span data-stu-id="f338d-107">For example, you will be able to know when volume drops, how many calls get affected by what reason.</span></span>

<span data-ttu-id="f338d-108">El informe de enrutamiento directo RTC de CQD tiene cuatro secciones:</span><span class="sxs-lookup"><span data-stu-id="f338d-108">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="f338d-109">Información general de RTC</span><span class="sxs-lookup"><span data-stu-id="f338d-109">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="f338d-110">Detalles del servicio</span><span class="sxs-lookup"><span data-stu-id="f338d-110">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="f338d-111">Relación de efectividad de la red</span><span class="sxs-lookup"><span data-stu-id="f338d-111">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="f338d-112">Parámetros de red</span><span class="sxs-lookup"><span data-stu-id="f338d-112">Network Parameters</span></span>](#network-parameters)

## <a name="pstn-overview"></a><span data-ttu-id="f338d-113">Información general de RTC</span><span class="sxs-lookup"><span data-stu-id="f338d-113">PSTN Overview</span></span>

<span data-ttu-id="f338d-114">El informe de enrutamiento directo RTC de CQD proporciona la siguiente información relacionada con el estado general del servicio durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="f338d-114">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="f338d-115">![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="f338d-115">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="f338d-116">Por ejemplo, si estás interesado en el uso general y en la salud de todas las llamadas entrantes pasando por SBC abc.bca.adatum.biz con nosotros como país interno:</span><span class="sxs-lookup"><span data-stu-id="f338d-116">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="f338d-117">**Llamar**</span><span class="sxs-lookup"><span data-stu-id="f338d-117">**Call Out**</span></span> | <span data-ttu-id="f338d-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f338d-118">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="f338d-119">1</span><span class="sxs-lookup"><span data-stu-id="f338d-119">1</span></span>            | <span data-ttu-id="f338d-120">Puede usar los filtros de la parte superior para explorar en profundidad y seleccionar ByotIn como tipo de llamada, abc.bca.contoso.com como controlador de panel de sesión y nosotros como país interno.</span><span class="sxs-lookup"><span data-stu-id="f338d-120">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="f338d-121">1</span><span class="sxs-lookup"><span data-stu-id="f338d-121">2</span></span>            | <span data-ttu-id="f338d-122">Tendencia de uso durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="f338d-122">Usage trend for the past 180 days.</span></span> <span data-ttu-id="f338d-123">Puede encontrar el informe de detalles de uso en la página Detalles del servicio.</span><span class="sxs-lookup"><span data-stu-id="f338d-123">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="f338d-124">3</span><span class="sxs-lookup"><span data-stu-id="f338d-124">3</span></span>            | <span data-ttu-id="f338d-125">Tendencia de posmarcado, latencia, vibración y pérdida de paquetes durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="f338d-125">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="f338d-126">Puede encontrar informes detallados en la página parámetros de red.</span><span class="sxs-lookup"><span data-stu-id="f338d-126">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="f338d-127">4</span><span class="sxs-lookup"><span data-stu-id="f338d-127">4</span></span>            | <span data-ttu-id="f338d-128">Llamada simultánea y tendencia de usuario activo diario durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="f338d-128">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="f338d-129">Este gráfico puede ayudarte a comprender el volumen máximo del servicio.</span><span class="sxs-lookup"><span data-stu-id="f338d-129">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="f338d-130">5</span><span class="sxs-lookup"><span data-stu-id="f338d-130">5</span></span>            | <span data-ttu-id="f338d-131">Motivo principal de finalización de la llamada la calidad de servicio afectada durante los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="f338d-131">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="f338d-132">Puede encontrar información sobre el estado del servicio en la página proporción de efectividad de red (NER).</span><span class="sxs-lookup"><span data-stu-id="f338d-132">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="f338d-133">Detalles del servicio</span><span class="sxs-lookup"><span data-stu-id="f338d-133">Service Details</span></span>

<span data-ttu-id="f338d-134">Esta página proporciona las tendencias de uso del servicio por día y el desglose de comentarios del usuario en forma geográfica.</span><span class="sxs-lookup"><span data-stu-id="f338d-134">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="f338d-135">**Llamadas totales:** Total de llamadas realizadas en ese intervalo de tiempo, incluidas las llamadas correctas y erróneas</span><span class="sxs-lookup"><span data-stu-id="f338d-135">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="f338d-136">**Total de llamadas conectadas:** Total de llamadas conectadas en ese intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="f338d-136">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="f338d-137">**Minutos totales:** Uso total de minutos en ese intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="f338d-137">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="f338d-138">**Usuarios activos diarios (DAU):** Recuento de usuarios activos diarios que hicieron al menos una llamada conectada en ese día</span><span class="sxs-lookup"><span data-stu-id="f338d-138">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="f338d-139">**Llamadas simultáneas:** Máximo de llamadas simultáneas activas en un minuto</span><span class="sxs-lookup"><span data-stu-id="f338d-139">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="f338d-140">**Comentarios del usuario:** La puntuación de "calificar la llamada" viene del usuario.</span><span class="sxs-lookup"><span data-stu-id="f338d-140">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="f338d-141">3-5 se considera una buena llamada.</span><span class="sxs-lookup"><span data-stu-id="f338d-141">3-5 is considered as a good call.</span></span> <span data-ttu-id="f338d-142">1-2 se considera una llamada incorrecta.</span><span class="sxs-lookup"><span data-stu-id="f338d-142">1-2 is considered as a bad call.</span></span>

![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report2.png)

<span data-ttu-id="f338d-144">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f338d-144">For example:</span></span>

1.  <span data-ttu-id="f338d-145">Si ve que la duración media de las llamadas desciende a 0 en 02/14/2020, primero puede comprobar si el volumen de la llamada es normal y ver si hay una gran diferencia entre las llamadas de conexión totales y las llamadas de intento total.</span><span class="sxs-lookup"><span data-stu-id="f338d-145">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="f338d-146">A continuación, vaya a la página relación de eficacia de red para invertir en las razones de error de llamada.</span><span class="sxs-lookup"><span data-stu-id="f338d-146">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="f338d-147">Si ve el aumento de los puntos rojos en el mapa de comentarios del usuario, puede ir a la página relación efectividad de red y el parámetro red para ver si hay anomalías y puede generar un vale con el servicio de asistencia al cliente de MS.</span><span class="sxs-lookup"><span data-stu-id="f338d-147">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="f338d-148">Relación de efectividad de la red</span><span class="sxs-lookup"><span data-stu-id="f338d-148">Network Effectiveness Ratio</span></span>

<span data-ttu-id="f338d-149">Esta es la misma métrica que aparece en el panel General de estado.</span><span class="sxs-lookup"><span data-stu-id="f338d-149">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="f338d-150">Puedes comprobar el número de NER por hora con detalles de llamadas afectadas para ambas direcciones de llamadas (entrante o saliente) en relación con la proporción de eficacia de la red por hora y en el gráfico de motivos de finalización de llamadas que figura a continuación.</span><span class="sxs-lookup"><span data-stu-id="f338d-150">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="f338d-151">**Ner** : la capacidad (%) de una red para hacer llamadas midiendo el número de llamadas enviadas en comparación con el número de llamadas enviadas a un destinatario.</span><span class="sxs-lookup"><span data-stu-id="f338d-151">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="f338d-152">**Código de respuesta SIP**: el código de respuesta entero de tres dígitos muestra el estado de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f338d-152">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="f338d-153">**Código de respuesta de Microsoft**: un código de respuesta enviado desde un componente de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f338d-153">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="f338d-154">**Descripción** : la fase de razón que corresponde al código de respuesta SIP y al código de respuesta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f338d-154">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="f338d-155">**Número de llamadas afectadas** : el número total de llamadas se ha visto afectado durante el intervalo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f338d-155">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="f338d-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f338d-157">For example:</span></span>

![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report4.png)

<span data-ttu-id="f338d-159">Si el NER diario tiene una DIP en 02/05/2020, puede hacer clic en la fecha y otros gráficos le aplicarán un zoom para esa fecha específica.</span><span class="sxs-lookup"><span data-stu-id="f338d-159">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report5.png)

<span data-ttu-id="f338d-161">Desde la tendencia por hora del NER en buen lugar, puede encontrar la DIP en aproximadamente 21:00.</span><span class="sxs-lookup"><span data-stu-id="f338d-161">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="f338d-162">A continuación, haga clic de nuevo para acercar la hora 21 y comprobar los detalles de la llamada para ver cuántas llamadas han fallado en esa hora y cuáles son los motivos de finalización de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f338d-162">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="f338d-163">Puede comenzar con la solución de problemas con cualquier problema de SBC o enviar un informe a un servicio de asistencia al cliente si el problema no está relacionado con SBC.</span><span class="sxs-lookup"><span data-stu-id="f338d-163">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="f338d-164">Parámetros de red</span><span class="sxs-lookup"><span data-stu-id="f338d-164">Network Parameters</span></span>

<span data-ttu-id="f338d-165">Todos los parámetros de red se miden desde la interfaz de enrutamiento directo hasta el controlador de borde de la sesión.</span><span class="sxs-lookup"><span data-stu-id="f338d-165">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="f338d-166">Para obtener más información sobre los valores recomendados, consulte [preparar la red de su organización para Microsoft Teams](prepare-network.md)y mire los valores recomendados de borde del cliente a Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="f338d-166">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="f338d-167">**Vibración** : es la medición de milisegundos de variación en el tiempo de retraso de propagación de red calculado entre dos puntos de conexión con RTCP (el protocolo de control RTP).</span><span class="sxs-lookup"><span data-stu-id="f338d-167">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="f338d-168">**Pérdida de paquetes** : es una medida de paquete que no pudo llegar. se calcula entre dos puntos finales.</span><span class="sxs-lookup"><span data-stu-id="f338d-168">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="f338d-169">**Latencia** : (también conocido como tiempo de ida y vuelta) es la cantidad de tiempo que se tarda en enviar una señal más el tiempo que tarda en recibirse el reconocimiento de esa señal.</span><span class="sxs-lookup"><span data-stu-id="f338d-169">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="f338d-170">Este tiempo de retardo consiste en los tiempos de propagación entre los dos puntos de una señal.</span><span class="sxs-lookup"><span data-stu-id="f338d-170">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report6.png)

<span data-ttu-id="f338d-172">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f338d-172">For example:</span></span>

<span data-ttu-id="f338d-173">Si ve un pico en cualquiera de los cuatro gráficos (latencia, vibración, tasa de pérdida de paquetes, retraso de la publicación de marcado) para una fecha específica, por ejemplo, latencia en 02/14/2020, haga clic en el punto de fecha.</span><span class="sxs-lookup"><span data-stu-id="f338d-173">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="f338d-174">Y el gráfico de tendencia por hora en la parte inferior se actualizará para mostrar el número por hora.</span><span class="sxs-lookup"><span data-stu-id="f338d-174">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="f338d-175">Puede comprobar el SBCs o provocar un vale con el servicio de asistencia al cliente de MS.</span><span class="sxs-lookup"><span data-stu-id="f338d-175">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Captura de pantalla: informe de CQD de RTC](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="f338d-177">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f338d-177">Related topics</span></span>

[<span data-ttu-id="f338d-178">Usar Power BI para analizar los datos del CQD para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f338d-178">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)