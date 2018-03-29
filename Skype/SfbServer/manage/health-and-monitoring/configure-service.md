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
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server-2015"></a>Configurar el servicio de movilidad para alto rendimiento en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información acerca del servicio de movilidad en Skype para Business Server 2015.
  
> [!IMPORTANT]
> Este tema sólo se aplica a la Skype para servicio de movilidad Business Server 2015 (Mcx) y no se aplica a Unified Communications Web API (UCWA), según se explicó en las actualizaciones acumulativas de Lync Server 2013: febrero de 2013. 
  
Al instalar el servicio de movilidad (Mcx) en servicios de Internet Information Server (IIS) 7.5, el instalador del servicio de movilidad configura algunas opciones de rendimiento en el servidor Front-End. Recomendamos usar IIS 7.5 para la movilidad. Los parámetros afectan al número máximo de solicitudes de usuario simultáneas y al número máximo de subprocesos permitidos para el servicio de movilidad.
  
Estos son los parámetros de rendimiento:
  
### <a name="settings-for-mcx-on-iis-75"></a>Parámetros para Mcx en IIS 7.5

1. **maxConcurrentThreadsPerCPU** se establece en cero (0).
    
2. **maxConcurrentRequestsPerCPU** se establece en cero (0).
    
3. El modelo del proceso ASP.NET está configurado en AutoConfig (solo para IIS 7.5).
    
4. El límite de cola HTTP.sys está configurado en 1.000 (de manera predeterminada).
    

