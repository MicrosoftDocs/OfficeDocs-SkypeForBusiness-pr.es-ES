---
title: Supervisar el uso de UCWA y del servicio de movilidad en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumen: Administrar el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server 2015.'
ms.openlocfilehash: e71d18fe90eb9a7f2fd7b6563e6d6930f2473e74
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server-2015"></a>Supervisar el uso de UCWA y del servicio de movilidad en Skype Empresarial Server 2015
 
**Resumen:** Administrar el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server 2015.
  
Debe supervisar de forma continua, la CPU y la memoria utilizada por el Skype para servicio de movilidad Business Server (Mcx) y la API de Web de comunicaciones unificadas (UCWA). Para supervisar el uso, haga lo siguiente:
  
 **Para la API web de comunicaciones unificadas (UCWA):**
  
- El proceso de trabajo de **LyncUcwa** en el Administrador de servicios de Internet Information Server (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).
    
- Los contadores de rendimiento **CPU** y **Procesador**.
    
Para la mayoría de las implementaciones, el uso de la CPU de UCWA tendría que estar por debajo del 15 % como promedio. Uso de la memoria debe caer dentro de los límites descritos en el [Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server 2015](server-memory-capacity-limits.md).
  
Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento para determinar cuándo un servidor está sobrecargado de solicitudes:
  
- **LS:WEB - límite y Authentication\WEB - Nº Total de peticiones en el procesamiento de**, lo que indica el número de peticiones de web en el servidor pendientes. Cuando este contador alcanza las 10.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.
    
- **ASP.NET\Requests en cola** (debe ser siempre cero).
    
> [!NOTE]
> Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web. 
  
 **Para el servicio de movilidad (Mcx):**
  
- Los procesos de trabajo de **CSIntMcxAppPool** y **CSExtMcxAppPool** en el Administrador de servicios de Internet Information Server (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).
    
- Los contadores de rendimiento **CPU** y **Procesador**.
    
En la mayoría de las implementaciones, el uso de la CPU por parte del servicio Movilidad tendría que estar por debajo del 15 por ciento de media. Uso de la memoria debe caer dentro de los límites descritos en el [Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server 2015](server-memory-capacity-limits.md).
  
Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:
  
- **V2.0.50727\Requests ASP.NET actual**, lo que indica el número de peticiones de web en el servidor pendientes. Cuando este contador alcanza las 5.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.
    
- **ASP.NET\Requests en cola** (debe ser siempre cero).
    
> [!NOTE]
> Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web. 
  
## <a name="see-also"></a>Vea también

#### 

[Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server 2015](server-memory-capacity-limits.md)

