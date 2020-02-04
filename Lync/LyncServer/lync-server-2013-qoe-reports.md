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
ms.openlocfilehash: 9eead17e9cd08267f941d80cb25460f4d456d896
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="060e7-102">Informes de calidad de la calidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="060e7-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="060e7-103">_**Última modificación del tema:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="060e7-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="060e7-104">Resumen/informes de tendencias de QoE</span><span class="sxs-lookup"><span data-stu-id="060e7-104">QoE summary/trend reports</span></span>

<span data-ttu-id="060e7-105">Los informes de tendencias y de Resumen de la QoE son útiles para encontrar las horas de uso máxima del día y examinar la calidad de los medios para asegurarse de que los recursos de red de la organización son suficientes.</span><span class="sxs-lookup"><span data-stu-id="060e7-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="060e7-106">Su organización también puede usar los muchos filtros disponibles en el informe para aislar los números de rendimiento para determinadas ubicaciones, tipos de dispositivos y clientes, y servidores.</span><span class="sxs-lookup"><span data-stu-id="060e7-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="060e7-107">Los informes de tendencias y de Resumen de QoE constan de:</span><span class="sxs-lookup"><span data-stu-id="060e7-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="060e7-108">Resumen/Informe de tendencias de UC a UC</span><span class="sxs-lookup"><span data-stu-id="060e7-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="060e7-109">Informe de tendencias o Resumen de RTC</span><span class="sxs-lookup"><span data-stu-id="060e7-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="060e7-110">Resumen de la Conferencia/informe de tendencias</span><span class="sxs-lookup"><span data-stu-id="060e7-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="060e7-111">Informes de rendimiento de QoE</span><span class="sxs-lookup"><span data-stu-id="060e7-111">QoE performance reports</span></span>

<span data-ttu-id="060e7-112">Los informes de rendimiento de QoE proporcionan detalles sobre los tres informes que se concentran en el rendimiento de QoE de los servidores de mediación, servidores de conferencia A/V y ubicaciones de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="060e7-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="060e7-113">Informe de rendimiento del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="060e7-113">Mediation server performance report</span></span>

<span data-ttu-id="060e7-114">El informe de rendimiento del servidor de mediación enumera las métricas logradas por una o más mediación durante el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="060e7-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="060e7-115">Se informa por separado de las métricas de la pierna de las comunicaciones unificadas (UC) y la pierna del servidor a la puerta de enlace de cada llamada.</span><span class="sxs-lookup"><span data-stu-id="060e7-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="060e7-116">Use este informe para comparar el volumen y el rendimiento de los diversos servidores de mediación de su organización.</span><span class="sxs-lookup"><span data-stu-id="060e7-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="060e7-117">Para cada servidor de mediación (y para cada una de las llamadas), el informe muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="060e7-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="060e7-118">Número de llamadas</span><span class="sxs-lookup"><span data-stu-id="060e7-118">Number of calls</span></span>

  - <span data-ttu-id="060e7-119">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="060e7-119">Packet Loss</span></span>

  - <span data-ttu-id="060e7-120">Tiempo de ida y vuelta</span><span class="sxs-lookup"><span data-stu-id="060e7-120">Round Trip Time</span></span>

  - <span data-ttu-id="060e7-121">Vibración</span><span class="sxs-lookup"><span data-stu-id="060e7-121">Jitter</span></span>

  - <span data-ttu-id="060e7-122">Puntuación de la media de conversación (MOS)</span><span class="sxs-lookup"><span data-stu-id="060e7-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="060e7-123">Envío de MOS</span><span class="sxs-lookup"><span data-stu-id="060e7-123">Sending MOS</span></span>

  - <span data-ttu-id="060e7-124">Escuchando MOS</span><span class="sxs-lookup"><span data-stu-id="060e7-124">Listening MOS</span></span>

  - <span data-ttu-id="060e7-125">MOS de red</span><span class="sxs-lookup"><span data-stu-id="060e7-125">Network MOS</span></span>

  - <span data-ttu-id="060e7-126">Degradación de MOS de red</span><span class="sxs-lookup"><span data-stu-id="060e7-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="060e7-127">Retorno de eco</span><span class="sxs-lookup"><span data-stu-id="060e7-127">Echo Return</span></span>

  - <span data-ttu-id="060e7-128">Nivel de señal</span><span class="sxs-lookup"><span data-stu-id="060e7-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="060e7-129">Informe de rendimiento del servidor de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="060e7-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="060e7-130">El informe de rendimiento del servidor de conferencia A/V proporciona listas de métricas realizadas por uno o varios servidores de conferencia A/V durante el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="060e7-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="060e7-131">Este informe se puede usar para comparar el volumen y el rendimiento de varios servidores de conferencia A/V de su organización.</span><span class="sxs-lookup"><span data-stu-id="060e7-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="060e7-132">Su organización también puede aislar el informe para que muestre solo la experiencia de tipos de clientes específicos, como clientes de Lync o clientes RTC.</span><span class="sxs-lookup"><span data-stu-id="060e7-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="060e7-133">Para cada servidor de conferencia A/V, el informe muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="060e7-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="060e7-134">Número de conferencias</span><span class="sxs-lookup"><span data-stu-id="060e7-134">Number of conferences</span></span>

  - <span data-ttu-id="060e7-135">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="060e7-135">Packet Loss</span></span>

  - <span data-ttu-id="060e7-136">Tiempo de ida y vuelta</span><span class="sxs-lookup"><span data-stu-id="060e7-136">Round Trip Time</span></span>

  - <span data-ttu-id="060e7-137">Vibración</span><span class="sxs-lookup"><span data-stu-id="060e7-137">Jitter</span></span>

  - <span data-ttu-id="060e7-138">Puntuación de la media de conversación (MOS)</span><span class="sxs-lookup"><span data-stu-id="060e7-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="060e7-139">Envío de MOS</span><span class="sxs-lookup"><span data-stu-id="060e7-139">Sending MOS</span></span>

  - <span data-ttu-id="060e7-140">Escuchando MOS</span><span class="sxs-lookup"><span data-stu-id="060e7-140">Listening MOS</span></span>

  - <span data-ttu-id="060e7-141">MOS de red</span><span class="sxs-lookup"><span data-stu-id="060e7-141">Network MOS</span></span>

  - <span data-ttu-id="060e7-142">Degradación de MOS de red</span><span class="sxs-lookup"><span data-stu-id="060e7-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="060e7-143">Retorno de eco</span><span class="sxs-lookup"><span data-stu-id="060e7-143">Echo Return</span></span>

  - <span data-ttu-id="060e7-144">Nivel de señal</span><span class="sxs-lookup"><span data-stu-id="060e7-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="060e7-145">Informe de rendimiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="060e7-145">Location-based performance report</span></span>

<span data-ttu-id="060e7-146">El informe de rendimiento basado en la ubicación proporciona una lista de ubicaciones de red y de cada ubicación muestra el número de llamadas en cada rango predeterminado de calidad.</span><span class="sxs-lookup"><span data-stu-id="060e7-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="060e7-147">El objetivo de este informe es proporcionar una perspectiva de la calidad de los medios de la mayor parte de las llamadas telefónicas de la organización para las diversas ubicaciones, de modo que pueda identificar las ubicaciones con un bajo rendimiento y ver los diferentes grados de calidad de los medios de su organización ubicaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="060e7-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="060e7-148">Al mostrar el informe, aparecen tablas de métricas diferentes: una tabla por cada métrica en la que la organización decide informar.</span><span class="sxs-lookup"><span data-stu-id="060e7-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="060e7-149">Puede elegir entre las siguientes métricas para este informe:</span><span class="sxs-lookup"><span data-stu-id="060e7-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="060e7-150">Puntuación de la media de conversación (MOS)</span><span class="sxs-lookup"><span data-stu-id="060e7-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="060e7-151">MOS de red</span><span class="sxs-lookup"><span data-stu-id="060e7-151">Network MOS</span></span>

  - <span data-ttu-id="060e7-152">Degradación de MOS de red</span><span class="sxs-lookup"><span data-stu-id="060e7-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="060e7-153">Envío de MOS</span><span class="sxs-lookup"><span data-stu-id="060e7-153">Sending MOS</span></span>

  - <span data-ttu-id="060e7-154">Escuchando MOS</span><span class="sxs-lookup"><span data-stu-id="060e7-154">Listening MOS</span></span>

  - <span data-ttu-id="060e7-155">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="060e7-155">Packet Loss</span></span>

  - <span data-ttu-id="060e7-156">Vibración</span><span class="sxs-lookup"><span data-stu-id="060e7-156">Jitter</span></span>

  - <span data-ttu-id="060e7-157">Latencia</span><span class="sxs-lookup"><span data-stu-id="060e7-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

