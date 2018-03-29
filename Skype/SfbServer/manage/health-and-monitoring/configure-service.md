---
title: Configurar el servicio de movilidad para alto rendimiento en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumen: Conozca el servicio de movilidad en Skype para Business Server 2015.'
ms.openlocfilehash: 12f64ed75195bb94365686d76cdfca841e6c9c8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server-2015"></a><span data-ttu-id="aeedc-103">Configurar el servicio de movilidad para alto rendimiento en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="aeedc-103">Configure Mobility Service for high performance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="aeedc-104">**Resumen:** Obtenga información acerca del servicio de movilidad en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="aeedc-104">**Summary:** Learn about the Mobility Service in Skype for Business Server 2015.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="aeedc-105">Este tema sólo se aplica a la Skype para servicio de movilidad Business Server 2015 (Mcx) y no se aplica a Unified Communications Web API (UCWA), según se explicó en las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="aeedc-105">This topic applies only to the Skype for Business Server 2015 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="aeedc-106">Al instalar el servicio de movilidad (Mcx) en servicios de Internet Information Server (IIS) 7.5, el instalador del servicio de movilidad configura algunas opciones de rendimiento en el servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="aeedc-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="aeedc-107">Recomendamos usar IIS 7.5 para la movilidad.</span><span class="sxs-lookup"><span data-stu-id="aeedc-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="aeedc-108">Los parámetros afectan al número máximo de solicitudes de usuario simultáneas y al número máximo de subprocesos permitidos para el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="aeedc-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="aeedc-109">Estos son los parámetros de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="aeedc-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="aeedc-110">Parámetros para Mcx en IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="aeedc-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="aeedc-111">**maxConcurrentThreadsPerCPU** se establece en cero (0).</span><span class="sxs-lookup"><span data-stu-id="aeedc-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="aeedc-112">**maxConcurrentRequestsPerCPU** se establece en cero (0).</span><span class="sxs-lookup"><span data-stu-id="aeedc-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="aeedc-113">El modelo del proceso ASP.NET está configurado en AutoConfig (solo para IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="aeedc-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="aeedc-114">El límite de cola HTTP.sys está configurado en 1.000 (de manera predeterminada).</span><span class="sxs-lookup"><span data-stu-id="aeedc-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

