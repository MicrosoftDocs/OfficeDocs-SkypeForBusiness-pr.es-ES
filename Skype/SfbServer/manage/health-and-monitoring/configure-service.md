---
title: Configurar el servicio de movilidad para un alto rendimiento en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumen: Obtenga información sobre el servicio de movilidad de Skype empresarial Server.'
ms.openlocfilehash: d50aab5ced14753a7665c6560220d1dfdca1061d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818060"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurar el servicio de movilidad para un alto rendimiento en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre el servicio de movilidad de Skype empresarial Server.
  
> [!IMPORTANT]
> Este tema se aplica solo al servicio de movilidad de Skype empresarial Server (MCX) y no se aplica a la API Web de comunicaciones unificadas (UCWA), tal como se proporciona en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013. 
  
Al instalar el servicio de movilidad (MCX) en servicios de Internet Information Server (IIS) 7,5, el instalador del servicio de movilidad configura algunos valores de rendimiento en el servidor front-end. Recomendamos usar IIS 7.5 para la movilidad. Los parámetros afectan al número máximo de solicitudes de usuario simultáneas y al número máximo de subprocesos permitidos para el servicio de movilidad.
  
Estos son los parámetros de rendimiento:
  
### <a name="settings-for-mcx-on-iis-75"></a>Parámetros para Mcx en IIS 7.5

1. **maxConcurrentThreadsPerCPU** está configurado en cero (0).
    
2. **maxConcurrentRequestsPerCPU** está configurado en cero (0).
    
3. El modelo del proceso ASP.NET está configurado en AutoConfig (solo para IIS 7.5).
    
4. El límite de cola HTTP.sys está configurado en 1.000 (de manera predeterminada).
    

