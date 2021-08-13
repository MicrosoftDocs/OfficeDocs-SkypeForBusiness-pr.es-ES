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
ms.openlocfilehash: 3029877aa6f252ada9bbb38bca0148b8a96908ad5cf4deded7cf48e6451ec833
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298140"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurar el servicio de movilidad para un alto rendimiento en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el servicio de movilidad en Skype Empresarial Server.
  
> [!IMPORTANT]
> Este tema solo se aplica al servicio de movilidad de Skype Empresarial Server (Mcx) y no se aplica a la API web de comunicaciones unificadas (UCWA), tal como se entrega en las actualizaciones acumulativas de Lync Server 2013: febrero de 2013. 
  
Al instalar el servicio de movilidad (Mcx) en Internet Information Services (IIS) 7.5, el instalador del servicio de movilidad configura algunas opciones de rendimiento en el servidor front-end. Se recomienda usar IIS 7.5 para la movilidad. Los parámetros afectan al número máximo de solicitudes de usuario simultáneas y al número máximo de subprocesos permitidos para el servicio de movilidad.
  
Estas son las opciones de rendimiento:
  
### <a name="settings-for-mcx-on-iis-75"></a>Configuración para Mcx en IIS 7.5

1. **maxConcurrentThreadsPerCPU** está configurado en cero (0).
    
2. **maxConcurrentRequestsPerCPU** está configurado en cero (0).
    
3. El modelo del proceso ASP.NET está configurado en AutoConfig (solo para IIS 7.5).
    
4. El límite de cola HTTP.sys está configurado en 1.000 (de manera predeterminada).
    

