---
title: 'Lync Server 2013: informes de QoE'
description: 'Lync Server 2013: informes de QoE.'
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
ms.openlocfilehash: 55965d246b7f0ddd71eaeeec99d218eaf8819c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571406"
---
# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="c8c33-103">Informes de QoE en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8c33-103">QoE reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8c33-104">_**Última modificación del tema:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="c8c33-104">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="c8c33-105">Informe de tendencias/Resumen de QoE</span><span class="sxs-lookup"><span data-stu-id="c8c33-105">QoE summary/trend reports</span></span>

<span data-ttu-id="c8c33-106">Los informes de Resumen/tendencias de QoE son útiles para encontrar los tiempos de uso máximo del día y para examinar la calidad de los medios en esas horas para asegurarse de que los recursos de red de la organización son suficientes.</span><span class="sxs-lookup"><span data-stu-id="c8c33-106">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="c8c33-107">La organización también puede usar los numerosos filtros disponibles en el informe para aislar los números de rendimiento de determinadas ubicaciones, tipos de dispositivos y clientes, y servidores.</span><span class="sxs-lookup"><span data-stu-id="c8c33-107">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="c8c33-108">Los informes de tendencias y de Resumen de QoE constan de:</span><span class="sxs-lookup"><span data-stu-id="c8c33-108">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="c8c33-109">Informe de tendencias/Resumen de UC a UC</span><span class="sxs-lookup"><span data-stu-id="c8c33-109">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="c8c33-110">Informe de tendencias o Resumen de RTC</span><span class="sxs-lookup"><span data-stu-id="c8c33-110">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="c8c33-111">Informe de tendencias/Resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="c8c33-111">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="c8c33-112">Informes de rendimiento de QoE</span><span class="sxs-lookup"><span data-stu-id="c8c33-112">QoE performance reports</span></span>

<span data-ttu-id="c8c33-113">Los informes de rendimiento de QoE proporcionan información detallada sobre los tres informes que se centran en el rendimiento de los servidores de mediación, los servidores de conferencia A/V y las ubicaciones de los extremos.</span><span class="sxs-lookup"><span data-stu-id="c8c33-113">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="c8c33-114">Informe de rendimiento del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="c8c33-114">Mediation server performance report</span></span>

<span data-ttu-id="c8c33-115">El informe de rendimiento del servidor de mediación enumera las métricas logradas por una o más mediación durante el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="c8c33-115">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="c8c33-116">Las métricas de la sección del servidor de comunicaciones unificadas (UC) y la sección del servidor de mediación a la puerta de enlace de cada llamada se notifican por separado.</span><span class="sxs-lookup"><span data-stu-id="c8c33-116">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="c8c33-117">Use este informe para comparar el volumen y el rendimiento de los diversos servidores de mediación de su organización.</span><span class="sxs-lookup"><span data-stu-id="c8c33-117">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="c8c33-118">Por cada servidor de mediación (y por cada pierna de llamada), el informe muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8c33-118">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="c8c33-119">Número de llamadas</span><span class="sxs-lookup"><span data-stu-id="c8c33-119">Number of calls</span></span>

  - <span data-ttu-id="c8c33-120">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="c8c33-120">Packet Loss</span></span>

  - <span data-ttu-id="c8c33-121">Tiempo de ida y vuelta</span><span class="sxs-lookup"><span data-stu-id="c8c33-121">Round Trip Time</span></span>

  - <span data-ttu-id="c8c33-122">JIT</span><span class="sxs-lookup"><span data-stu-id="c8c33-122">Jitter</span></span>

  - <span data-ttu-id="c8c33-123">Puntuación de opinión media a la conversación (MOS)</span><span class="sxs-lookup"><span data-stu-id="c8c33-123">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="c8c33-124">Envío de MOS</span><span class="sxs-lookup"><span data-stu-id="c8c33-124">Sending MOS</span></span>

  - <span data-ttu-id="c8c33-125">Escuchar MOS</span><span class="sxs-lookup"><span data-stu-id="c8c33-125">Listening MOS</span></span>

  - <span data-ttu-id="c8c33-126">MOS de red</span><span class="sxs-lookup"><span data-stu-id="c8c33-126">Network MOS</span></span>

  - <span data-ttu-id="c8c33-127">Degradación de MOS de red</span><span class="sxs-lookup"><span data-stu-id="c8c33-127">Network MOS Degradation</span></span>

  - <span data-ttu-id="c8c33-128">Devolución de eco</span><span class="sxs-lookup"><span data-stu-id="c8c33-128">Echo Return</span></span>

  - <span data-ttu-id="c8c33-129">Nivel de señal</span><span class="sxs-lookup"><span data-stu-id="c8c33-129">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="c8c33-130">Informe de rendimiento del servidor de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="c8c33-130">A/V conferencing server performance report</span></span>

<span data-ttu-id="c8c33-131">El informe de rendimiento del servidor de conferencia A/V proporciona listas de métricas realizadas por uno o varios servidores de conferencia A/V durante el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="c8c33-131">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="c8c33-132">Este informe se puede usar para comparar el volumen y el rendimiento de los diversos servidores de conferencia A/V de la organización.</span><span class="sxs-lookup"><span data-stu-id="c8c33-132">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="c8c33-133">La organización también puede aislar el informe para mostrar solo la experiencia de determinados tipos de clientes, como clientes de Lync o RTC.</span><span class="sxs-lookup"><span data-stu-id="c8c33-133">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="c8c33-134">Para cada servidor de conferencia A/V, el informe muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8c33-134">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="c8c33-135">Número de conferencias</span><span class="sxs-lookup"><span data-stu-id="c8c33-135">Number of conferences</span></span>

  - <span data-ttu-id="c8c33-136">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="c8c33-136">Packet Loss</span></span>

  - <span data-ttu-id="c8c33-137">Tiempo de ida y vuelta</span><span class="sxs-lookup"><span data-stu-id="c8c33-137">Round Trip Time</span></span>

  - <span data-ttu-id="c8c33-138">JIT</span><span class="sxs-lookup"><span data-stu-id="c8c33-138">Jitter</span></span>

  - <span data-ttu-id="c8c33-139">Puntuación de opinión media a la conversación (MOS)</span><span class="sxs-lookup"><span data-stu-id="c8c33-139">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="c8c33-140">Envío de MOS</span><span class="sxs-lookup"><span data-stu-id="c8c33-140">Sending MOS</span></span>

  - <span data-ttu-id="c8c33-141">Escuchar MOS</span><span class="sxs-lookup"><span data-stu-id="c8c33-141">Listening MOS</span></span>

  - <span data-ttu-id="c8c33-142">MOS de red</span><span class="sxs-lookup"><span data-stu-id="c8c33-142">Network MOS</span></span>

  - <span data-ttu-id="c8c33-143">Degradación de MOS de red</span><span class="sxs-lookup"><span data-stu-id="c8c33-143">Network MOS Degradation</span></span>

  - <span data-ttu-id="c8c33-144">Devolución de eco</span><span class="sxs-lookup"><span data-stu-id="c8c33-144">Echo Return</span></span>

  - <span data-ttu-id="c8c33-145">Nivel de señal</span><span class="sxs-lookup"><span data-stu-id="c8c33-145">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="c8c33-146">Informe de rendimiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="c8c33-146">Location-based performance report</span></span>

<span data-ttu-id="c8c33-147">El Location-Based informe de rendimiento proporciona una lista de ubicaciones de red y para cada ubicación muestra el número de llamadas en cada rango de calidad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c8c33-147">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="c8c33-148">El objetivo de este informe es proporcionar información sobre la calidad de los medios de la mayor parte de las llamadas telefónicas de la organización en varias ubicaciones, de modo que pueda identificar las ubicaciones de bajo rendimiento y ver los distintos grados de calidad de los medios en las distintas ubicaciones de la organización.</span><span class="sxs-lookup"><span data-stu-id="c8c33-148">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="c8c33-149">Cuando se muestra el informe, aparecen diferentes tablas de métricas: una tabla para cada métrica a la que la organización decide informar.</span><span class="sxs-lookup"><span data-stu-id="c8c33-149">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="c8c33-150">Puede elegir entre las siguientes métricas para este informe:</span><span class="sxs-lookup"><span data-stu-id="c8c33-150">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="c8c33-151">Puntuación de opinión media a la conversación (MOS)</span><span class="sxs-lookup"><span data-stu-id="c8c33-151">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="c8c33-152">MOS de red</span><span class="sxs-lookup"><span data-stu-id="c8c33-152">Network MOS</span></span>

  - <span data-ttu-id="c8c33-153">Degradación de MOS de red</span><span class="sxs-lookup"><span data-stu-id="c8c33-153">Network MOS Degradation</span></span>

  - <span data-ttu-id="c8c33-154">Envío de MOS</span><span class="sxs-lookup"><span data-stu-id="c8c33-154">Sending MOS</span></span>

  - <span data-ttu-id="c8c33-155">Escuchar MOS</span><span class="sxs-lookup"><span data-stu-id="c8c33-155">Listening MOS</span></span>

  - <span data-ttu-id="c8c33-156">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="c8c33-156">Packet Loss</span></span>

  - <span data-ttu-id="c8c33-157">JIT</span><span class="sxs-lookup"><span data-stu-id="c8c33-157">Jitter</span></span>

  - <span data-ttu-id="c8c33-158">Latencia</span><span class="sxs-lookup"><span data-stu-id="c8c33-158">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

