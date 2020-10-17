---
title: 'Lync Server 2013: informes de diagnósticos de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Reports
ms:assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615013(v=OCS.15)
ms:contentKeyID: 48184794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46073c5540b0b4cd48f6c5a13c17d4a4d3f12a46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526337"
---
# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="73eba-102">Informes de diagnósticos de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73eba-102">Call Diagnostic Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73eba-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="73eba-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="73eba-104">Los informes de diagnósticos de llamadas contienen información resumida y datos de diagnóstico sobre las sesiones punto a punto y de conferencia en las que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="73eba-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="73eba-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="73eba-105">In This Section</span></span>

  - <span data-ttu-id="73eba-106">[Informe de Resumen de diagnósticos de llamadas en Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)     Proporciona un resumen general de sesiones punto a punto y sesiones de conferencia en las que se han producido errores.</span><span class="sxs-lookup"><span data-stu-id="73eba-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="73eba-107">Las sesiones punto a punto son sesiones que implican solo dos participantes.</span><span class="sxs-lookup"><span data-stu-id="73eba-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="73eba-108">Las sesiones de conferencia implican tres o más participantes.</span><span class="sxs-lookup"><span data-stu-id="73eba-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="73eba-109">[Informe de diagnósticos de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)     Proporciona una vista de tendencia general de las sesiones punto a punto con errores.</span><span class="sxs-lookup"><span data-stu-id="73eba-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="73eba-110">Una sesión punto a punto implica tan solo dos participantes.</span><span class="sxs-lookup"><span data-stu-id="73eba-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="73eba-111">[Informe de diagnósticos de conferencia en Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)     Proporciona una vista de tendencia general de las sesiones de conferencia con errores y vistas de tendencia para cada modalidad de conferencia.</span><span class="sxs-lookup"><span data-stu-id="73eba-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="73eba-112">Las sesiones de conferencia implican al menos tres participantes.</span><span class="sxs-lookup"><span data-stu-id="73eba-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="73eba-113">[Informe de errores principales en Lync Server 2013](lync-server-2013-top-failures-report.md)     Proporciona una lista de los errores más frecuentes y sus tendencias a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="73eba-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="73eba-114">[Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md)     Proporciona un análisis de las sesiones con errores.</span><span class="sxs-lookup"><span data-stu-id="73eba-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="73eba-115">[Informe de lista de errores en Lync Server 2013](lync-server-2013-failure-list-report.md)     Proporciona información detallada sobre los participantes individuales implicados en una conferencia con errores.</span><span class="sxs-lookup"><span data-stu-id="73eba-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="73eba-116">[Informe de diagnósticos en Lync Server 2013](lync-server-2013-diagnostic-report.md)     Proporciona información de diagnóstico y solución de problemas (incluidos los códigos de respuesta SIP y los identificadores y encabezados de diagnóstico) para las sesiones con errores.</span><span class="sxs-lookup"><span data-stu-id="73eba-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

