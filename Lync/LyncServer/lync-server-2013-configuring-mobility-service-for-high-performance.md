---
title: 'Lync Server 2013: configuración del servicio de movilidad para alto rendimiento'
description: 'Lync Server 2013: configurar el servicio de movilidad para alto rendimiento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4732d9f6a92c383a105a6f0d7162c9b6c798de24
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556986"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="8b9e6-103">Configurar el servicio de movilidad para alto rendimiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b9e6-103">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b9e6-104">_**Última modificación del tema:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="8b9e6-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8b9e6-105">Este tema solo se aplica al servicio de movilidad de Lync Server 2013 (MCX) y no se aplica a la API Web de comunicaciones unificadas (UCWA), tal y como se proporciona en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="8b9e6-105">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="8b9e6-106">Al instalar el servicio de movilidad (MCX) en Internet Information Services (IIS) 7,5, el instalador del servicio de movilidad configura algunas opciones de rendimiento en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="8b9e6-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="8b9e6-107">Se recomienda usar IIS 7.5 para la movilidad.</span><span class="sxs-lookup"><span data-stu-id="8b9e6-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="8b9e6-108">Los parámetros afectan al número máximo de solicitudes de usuario simultáneas y al número máximo de subprocesos permitidos para el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="8b9e6-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="8b9e6-109">Estas son las opciones de configuración de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="8b9e6-109">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="8b9e6-110">Configuración de MCX en IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="8b9e6-110">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="8b9e6-111">**maxConcurrentThreadsPerCPU** está configurado en cero (0).</span><span class="sxs-lookup"><span data-stu-id="8b9e6-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="8b9e6-112">**maxConcurrentRequestsPerCPU** está configurado en cero (0).</span><span class="sxs-lookup"><span data-stu-id="8b9e6-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="8b9e6-113">El modelo del proceso ASP.NET está configurado en AutoConfig (solo para IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="8b9e6-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="8b9e6-114">El límite de cola HTTP.sys está configurado en 1.000 (de manera predeterminada).</span><span class="sxs-lookup"><span data-stu-id="8b9e6-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

