---
title: Configurar el servicio de movilidad para alto rendimiento en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumen: Obtenga información sobre el servicio de movilidad en Skype para Business Server.'
ms.openlocfilehash: bd787e78ebd3228faa1c47f1f54e688551c3e67d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926595"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurar el servicio de movilidad para alto rendimiento en Skype para Business Server
 
**Resumen:** Obtenga información sobre el servicio de movilidad en Skype para Business Server.
  
> [!IMPORTANT]
> En este tema se aplica únicamente a la Skype para servicio de movilidad de servidor empresarial (Mcx) y no se aplica a Unified Communications Web API (UCWA), tal como se entregan en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013. 
  
Al instalar el servicio de movilidad (Mcx) en Internet Information Services (IIS) 7.5, el instalador del servicio de movilidad configura algunas opciones de configuración de rendimiento en el servidor Front-End. Recomendamos usar IIS 7.5 para la movilidad. Los parámetros afectan al número máximo de solicitudes de usuario simultáneas y al número máximo de subprocesos permitidos para el servicio de movilidad.
  
Estos son los parámetros de rendimiento:
  
### <a name="settings-for-mcx-on-iis-75"></a>Parámetros para Mcx en IIS 7.5

1. **maxConcurrentThreadsPerCPU** está configurado en cero (0).
    
2. **maxConcurrentRequestsPerCPU** está configurado en cero (0).
    
3. El modelo del proceso ASP.NET está configurado en AutoConfig (solo para IIS 7.5).
    
4. El límite de cola HTTP.sys está configurado en 1.000 (de manera predeterminada).
    

