---
title: 'Lync Server 2013: informes de diagnóstico de calidad multimedia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05836ea853c89b132d39eaaba1b66056fa958072
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="51d40-102">Informes de diagnóstico de calidad multimedia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51d40-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51d40-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="51d40-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="51d40-104">Los Informes de diagnósticos de calidad de medios proporcionan información sobre la calidad de las llamadas, e información de diagnóstico y solución de problemas para las llamadas en las que se produjeron errores.</span><span class="sxs-lookup"><span data-stu-id="51d40-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="51d40-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="51d40-105">In This Section</span></span>

  - <span data-ttu-id="51d40-106">[Informe de Resumen de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   proporciona datos de calidad general para diferentes tipos de extremos, entre los que se incluyen llamadas de voz de punto a punto de empresa, llamadas de conferencia de voz de empresa y llamadas que se basan, al menos en parte, en el público red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="51d40-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="51d40-107">[El informe de comparación de calidad multimedia de Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   ofrece una comparación de los valores de calidad de las llamadas para diferentes tipos de llamadas de audio (por ejemplo, llamadas hechas a través de una red inalámbrica, y llamadas hechas a través de una conexión por cable).</span><span class="sxs-lookup"><span data-stu-id="51d40-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="51d40-108">[Informe rendimiento del servidor de Lync Server 2013](lync-server-2013-server-performance-report.md)   enumera los servidores que han experimentado la mayoría de los problemas, basados en medidas de esta métrica de calidad clave como degradación, pérdida de paquetes y vibración.</span><span class="sxs-lookup"><span data-stu-id="51d40-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="51d40-109">[Informe de ubicación en Lync Server 2013](lync-server-2013-location-report.md)   proporciona una lista de ubicaciones de red y un resumen de la calidad de los medios de las llamadas que se producen en cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="51d40-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="51d40-110">Para este informe, las ubicaciones se basan en subredes IP.</span><span class="sxs-lookup"><span data-stu-id="51d40-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="51d40-111">[Informe de dispositivos en Lync Server 2013](lync-server-2013-device-report.md)   ofrece un resumen de los dispositivos que se usan para las llamadas de telefonía IP e incluye la calidad media de los medios de las llamadas por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="51d40-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="51d40-112">[Informe de la lista de llamadas de Lync Server 2013](lync-server-2013-call-list-report.md)   proporciona información detallada sobre las llamadas realizadas o recibidas en su organización.</span><span class="sxs-lookup"><span data-stu-id="51d40-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="51d40-113">[Informe de detalles de llamadas en Lync Server 2013](lync-server-2013-call-detail-report.md)   proporciona información detallada sobre las llamadas telefónicas hechas desde su organización o recibidas en ella.</span><span class="sxs-lookup"><span data-stu-id="51d40-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="51d40-114">[Informe de tendencias de calidad de Media Server en Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   le permite comparar de forma gráfica hasta 5 servidores en métricas de la calidad de la experiencia, como el volumen de las llamadas, el porcentaje de llamadas deficientes, la pérdida de paquetes y la vibración.</span><span class="sxs-lookup"><span data-stu-id="51d40-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="51d40-115">[El informe de distribución de métricas de calidad media de Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   proporciona un gráfico que muestra los valores de distribución para una métrica de calidad de experiencia, como la vibración o la pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="51d40-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="51d40-116">[Informe de tendencias de ubicación en Lync Server 2013](lync-server-2013-location-trend-report.md)   proporciona información sobre la tendencia de la calidad de las llamadas para ubicaciones de red.</span><span class="sxs-lookup"><span data-stu-id="51d40-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

