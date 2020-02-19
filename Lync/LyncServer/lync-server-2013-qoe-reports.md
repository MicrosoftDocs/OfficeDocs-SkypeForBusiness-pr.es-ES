---
title: 'Lync Server 2013: informes de QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b08544365cf536b791fdfffa5d1d1521a1cc966
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="a9004-102">Informes de QoE en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9004-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9004-103">_**Última modificación del tema:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="a9004-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="a9004-104">Informe de tendencias/Resumen de QoE</span><span class="sxs-lookup"><span data-stu-id="a9004-104">QoE summary/trend reports</span></span>

<span data-ttu-id="a9004-105">Los informes de Resumen/tendencias de QoE son útiles para encontrar los tiempos de uso máximo del día y para examinar la calidad de los medios en esas horas para asegurarse de que los recursos de red de la organización son suficientes.</span><span class="sxs-lookup"><span data-stu-id="a9004-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="a9004-106">La organización también puede usar los numerosos filtros disponibles en el informe para aislar los números de rendimiento de determinadas ubicaciones, tipos de dispositivos y clientes, y servidores.</span><span class="sxs-lookup"><span data-stu-id="a9004-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="a9004-107">Los informes de tendencias y de Resumen de QoE constan de:</span><span class="sxs-lookup"><span data-stu-id="a9004-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="a9004-108">Informe de tendencias/Resumen de UC a UC</span><span class="sxs-lookup"><span data-stu-id="a9004-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="a9004-109">Informe de tendencias o Resumen de RTC</span><span class="sxs-lookup"><span data-stu-id="a9004-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="a9004-110">Informe de tendencias/Resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="a9004-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="a9004-111">Informes de rendimiento de QoE</span><span class="sxs-lookup"><span data-stu-id="a9004-111">QoE performance reports</span></span>

<span data-ttu-id="a9004-112">Los informes de rendimiento de QoE proporcionan información detallada sobre los tres informes que se centran en el rendimiento de los servidores de mediación, los servidores de conferencia A/V y las ubicaciones de los extremos.</span><span class="sxs-lookup"><span data-stu-id="a9004-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="a9004-113">Informe de rendimiento del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="a9004-113">Mediation server performance report</span></span>

<span data-ttu-id="a9004-114">El informe de rendimiento del servidor de mediación enumera las métricas logradas por una o más mediación durante el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="a9004-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="a9004-115">Las métricas de la sección del servidor de comunicaciones unificadas (UC) y la sección del servidor de mediación a la puerta de enlace de cada llamada se notifican por separado.</span><span class="sxs-lookup"><span data-stu-id="a9004-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="a9004-116">Use este informe para comparar el volumen y el rendimiento de los diversos servidores de mediación de su organización.</span><span class="sxs-lookup"><span data-stu-id="a9004-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="a9004-117">Por cada servidor de mediación (y por cada pierna de llamada), el informe muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9004-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="a9004-118">Número de llamadas</span><span class="sxs-lookup"><span data-stu-id="a9004-118">Number of calls</span></span>

  - <span data-ttu-id="a9004-119">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="a9004-119">Packet Loss</span></span>

  - <span data-ttu-id="a9004-120">Tiempo de ida y vuelta</span><span class="sxs-lookup"><span data-stu-id="a9004-120">Round Trip Time</span></span>

  - <span data-ttu-id="a9004-121">JIT</span><span class="sxs-lookup"><span data-stu-id="a9004-121">Jitter</span></span>

  - <span data-ttu-id="a9004-122">Puntuación de opinión media a la conversación (MOS)</span><span class="sxs-lookup"><span data-stu-id="a9004-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="a9004-123">Envío de MOS</span><span class="sxs-lookup"><span data-stu-id="a9004-123">Sending MOS</span></span>

  - <span data-ttu-id="a9004-124">Escuchar MOS</span><span class="sxs-lookup"><span data-stu-id="a9004-124">Listening MOS</span></span>

  - <span data-ttu-id="a9004-125">MOS de red</span><span class="sxs-lookup"><span data-stu-id="a9004-125">Network MOS</span></span>

  - <span data-ttu-id="a9004-126">Degradación de MOS de red</span><span class="sxs-lookup"><span data-stu-id="a9004-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="a9004-127">Devolución de eco</span><span class="sxs-lookup"><span data-stu-id="a9004-127">Echo Return</span></span>

  - <span data-ttu-id="a9004-128">Nivel de señal</span><span class="sxs-lookup"><span data-stu-id="a9004-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="a9004-129">Informe de rendimiento del servidor de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="a9004-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="a9004-130">El informe de rendimiento del servidor de conferencia A/V proporciona listas de métricas realizadas por uno o varios servidores de conferencia A/V durante el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="a9004-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="a9004-131">Este informe se puede usar para comparar el volumen y el rendimiento de los diversos servidores de conferencia A/V de la organización.</span><span class="sxs-lookup"><span data-stu-id="a9004-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="a9004-132">La organización también puede aislar el informe para mostrar solo la experiencia de determinados tipos de clientes, como clientes de Lync o RTC.</span><span class="sxs-lookup"><span data-stu-id="a9004-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="a9004-133">Para cada servidor de conferencia A/V, el informe muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9004-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="a9004-134">Número de conferencias</span><span class="sxs-lookup"><span data-stu-id="a9004-134">Number of conferences</span></span>

  - <span data-ttu-id="a9004-135">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="a9004-135">Packet Loss</span></span>

  - <span data-ttu-id="a9004-136">Tiempo de ida y vuelta</span><span class="sxs-lookup"><span data-stu-id="a9004-136">Round Trip Time</span></span>

  - <span data-ttu-id="a9004-137">JIT</span><span class="sxs-lookup"><span data-stu-id="a9004-137">Jitter</span></span>

  - <span data-ttu-id="a9004-138">Puntuación de opinión media a la conversación (MOS)</span><span class="sxs-lookup"><span data-stu-id="a9004-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="a9004-139">Envío de MOS</span><span class="sxs-lookup"><span data-stu-id="a9004-139">Sending MOS</span></span>

  - <span data-ttu-id="a9004-140">Escuchar MOS</span><span class="sxs-lookup"><span data-stu-id="a9004-140">Listening MOS</span></span>

  - <span data-ttu-id="a9004-141">MOS de red</span><span class="sxs-lookup"><span data-stu-id="a9004-141">Network MOS</span></span>

  - <span data-ttu-id="a9004-142">Degradación de MOS de red</span><span class="sxs-lookup"><span data-stu-id="a9004-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="a9004-143">Devolución de eco</span><span class="sxs-lookup"><span data-stu-id="a9004-143">Echo Return</span></span>

  - <span data-ttu-id="a9004-144">Nivel de señal</span><span class="sxs-lookup"><span data-stu-id="a9004-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="a9004-145">Informe de rendimiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="a9004-145">Location-based performance report</span></span>

<span data-ttu-id="a9004-146">El informe de rendimiento basado en ubicación proporciona una lista de ubicaciones de red y para cada ubicación muestra el número de llamadas en cada rango de calidad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a9004-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="a9004-147">El objetivo de este informe es proporcionar información sobre la calidad de los medios de la mayor parte de las llamadas telefónicas de la organización en varias ubicaciones, de modo que pueda identificar las ubicaciones con un rendimiento deficiente y ver los diferentes grados de calidad de los medios en la organización. distintas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="a9004-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="a9004-148">Cuando se muestra el informe, aparecen diferentes tablas de métricas: una tabla para cada métrica a la que la organización decide informar.</span><span class="sxs-lookup"><span data-stu-id="a9004-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="a9004-149">Puede elegir entre las siguientes métricas para este informe:</span><span class="sxs-lookup"><span data-stu-id="a9004-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="a9004-150">Puntuación de opinión media a la conversación (MOS)</span><span class="sxs-lookup"><span data-stu-id="a9004-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="a9004-151">MOS de red</span><span class="sxs-lookup"><span data-stu-id="a9004-151">Network MOS</span></span>

  - <span data-ttu-id="a9004-152">Degradación de MOS de red</span><span class="sxs-lookup"><span data-stu-id="a9004-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="a9004-153">Envío de MOS</span><span class="sxs-lookup"><span data-stu-id="a9004-153">Sending MOS</span></span>

  - <span data-ttu-id="a9004-154">Escuchar MOS</span><span class="sxs-lookup"><span data-stu-id="a9004-154">Listening MOS</span></span>

  - <span data-ttu-id="a9004-155">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="a9004-155">Packet Loss</span></span>

  - <span data-ttu-id="a9004-156">JIT</span><span class="sxs-lookup"><span data-stu-id="a9004-156">Jitter</span></span>

  - <span data-ttu-id="a9004-157">Latencia</span><span class="sxs-lookup"><span data-stu-id="a9004-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

