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
ms.openlocfilehash: 41100a6cc41c38b3d32870d530f99d8c919a2e83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="860cb-102">Informes de diagnósticos de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="860cb-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="860cb-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="860cb-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="860cb-104">Los informes de diagnósticos de llamadas contienen información resumida y datos de diagnóstico sobre las sesiones punto a punto y de conferencia en las que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="860cb-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="860cb-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="860cb-105">In This Section</span></span>

  - <span data-ttu-id="860cb-106">[El informe Resumen de diagnóstico de llamadas en Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   proporciona un resumen general de sesiones de punto a punto con errores y sesiones de conferencia.</span><span class="sxs-lookup"><span data-stu-id="860cb-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="860cb-107">Las sesiones de punto a punto son sesiones que implican solo dos participantes.</span><span class="sxs-lookup"><span data-stu-id="860cb-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="860cb-108">Las sesiones de conferencia implican a tres o más participantes.</span><span class="sxs-lookup"><span data-stu-id="860cb-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="860cb-109">[El informe de diagnóstico de actividad de punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   proporciona una vista de tendencia general de sesiones de punto a punto con errores.</span><span class="sxs-lookup"><span data-stu-id="860cb-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="860cb-110">En una sesión punto a punto solo participan dos personas.</span><span class="sxs-lookup"><span data-stu-id="860cb-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="860cb-111">[El informe de diagnóstico de conferencia de Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   proporciona una vista de tendencia general de las sesiones de conferencia con errores y las vistas de tendencias para cada modalidad de conferencia.</span><span class="sxs-lookup"><span data-stu-id="860cb-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="860cb-112">En las sesiones de conferencia participan como mínimo tres personas.</span><span class="sxs-lookup"><span data-stu-id="860cb-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="860cb-113">[El informe de errores principales de Lync Server 2013](lync-server-2013-top-failures-report.md)   proporciona una lista de los errores más frecuentes y sus tendencias a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="860cb-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="860cb-114">[Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md)   ofrece un análisis de las sesiones fallidas.</span><span class="sxs-lookup"><span data-stu-id="860cb-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="860cb-115">[Informe lista de errores en Lync Server 2013](lync-server-2013-failure-list-report.md)   proporciona información detallada sobre los participantes individuales implicados en una conferencia con errores.</span><span class="sxs-lookup"><span data-stu-id="860cb-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="860cb-116">[El informe de diagnóstico de Lync Server 2013](lync-server-2013-diagnostic-report.md)   proporciona información de diagnóstico y solución de problemas (incluidos los códigos de respuesta SIP y los encabezados e identificadores de diagnóstico) para las sesiones con error.</span><span class="sxs-lookup"><span data-stu-id="860cb-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

