---
title: Configurar el servicio de movilidad para alto rendimiento en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumen: Obtenga información sobre el servicio de movilidad en Skype para Business Server.'
ms.openlocfilehash: 3e3f0df7550a64236335108453f0c35d902a1713
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197495"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="5f071-103">Configurar el servicio de movilidad para alto rendimiento en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="5f071-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="5f071-104">**Resumen:** Obtenga información sobre el servicio de movilidad en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="5f071-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5f071-105">En este tema se aplica únicamente a la Skype para servicio de movilidad de servidor empresarial (Mcx) y no se aplica a Unified Communications Web API (UCWA), tal como se entregan en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="5f071-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="5f071-106">Al instalar el servicio de movilidad (Mcx) en Internet Information Services (IIS) 7.5, el instalador del servicio de movilidad configura algunas opciones de configuración de rendimiento en el servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="5f071-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="5f071-107">Recomendamos usar IIS 7.5 para la movilidad.</span><span class="sxs-lookup"><span data-stu-id="5f071-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="5f071-108">Los parámetros afectan al número máximo de solicitudes de usuario simultáneas y al número máximo de subprocesos permitidos para el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="5f071-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="5f071-109">Estos son los parámetros de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="5f071-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="5f071-110">Parámetros para Mcx en IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="5f071-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="5f071-111">**maxConcurrentThreadsPerCPU** está configurado en cero (0).</span><span class="sxs-lookup"><span data-stu-id="5f071-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="5f071-112">**maxConcurrentRequestsPerCPU** está configurado en cero (0).</span><span class="sxs-lookup"><span data-stu-id="5f071-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="5f071-113">El modelo del proceso ASP.NET está configurado en AutoConfig (solo para IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="5f071-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="5f071-114">El límite de cola HTTP.sys está configurado en 1.000 (de manera predeterminada).</span><span class="sxs-lookup"><span data-stu-id="5f071-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

