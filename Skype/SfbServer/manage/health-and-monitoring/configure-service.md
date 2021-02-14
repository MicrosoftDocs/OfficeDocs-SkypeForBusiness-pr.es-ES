---
title: Configurar el servicio de movilidad para un alto rendimiento en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumen: obtenga información sobre el servicio de movilidad en Skype Empresarial Server.'
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817040"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="b733e-103">Configurar el servicio de movilidad para un alto rendimiento en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b733e-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="b733e-104">**Resumen:** Obtenga información sobre el servicio de movilidad en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b733e-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b733e-105">Este tema solo se aplica al servicio de movilidad de Skype Empresarial Server (Mcx) y no a la API web de comunicaciones unificadas (UCWA), tal como se entrega en las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="b733e-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="b733e-106">Al instalar mobility Service (Mcx) en Internet Information Services (IIS) 7.5, el instalador del servicio de movilidad configura algunas opciones de rendimiento en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b733e-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="b733e-107">Se recomienda usar IIS 7.5 para la movilidad.</span><span class="sxs-lookup"><span data-stu-id="b733e-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="b733e-108">Los parámetros afectan al número máximo de solicitudes de usuario simultáneas y al número máximo de subprocesos permitidos para el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="b733e-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="b733e-109">Estas son las opciones de configuración de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="b733e-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="b733e-110">Configuración de Mcx en IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="b733e-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="b733e-111">**maxConcurrentThreadsPerCPU** está configurado en cero (0).</span><span class="sxs-lookup"><span data-stu-id="b733e-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="b733e-112">**maxConcurrentRequestsPerCPU** está configurado en cero (0).</span><span class="sxs-lookup"><span data-stu-id="b733e-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="b733e-113">El modelo del proceso ASP.NET está configurado en AutoConfig (solo para IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="b733e-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="b733e-114">El límite de cola HTTP.sys está configurado en 1.000 (de manera predeterminada).</span><span class="sxs-lookup"><span data-stu-id="b733e-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

