---
title: Supervisar los límites de capacidad de la memoria del servidor en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Resumen: Conozca cómo supervisar para límites de capacidad de memoria de servidor en Skype para Business Server 2015.'
ms.openlocfilehash: df05cdf43a7f09f49760f9671c900d6a9ea992b1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server-2015"></a>Supervisar los límites de capacidad de la memoria del servidor en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a supervisar para límites de capacidad de memoria de servidor en Skype para Business Server 2015.
  
> [!CAUTION]
> La información de este tema que hace referencia a la planificación de la capacidad se refiere sólo a los clientes de Lync 2010 Mobile y el servicio de movilidad (Mcx). Planificación de capacidad para el Unified Communications Web API (UCWA), utilizado por los clientes de Lync Mobile de 2013, es proporcionada por el servidor de Lync 2013, herramienta de planeación. 
  
Dos contadores de rendimiento de movilidad pueden ayudarle a determinar el uso actual y ayudarle a planear la capacidad para el Skype para servicio Business Server 2015 movilidad (Mcx), así como para supervisar el uso de memoria para UCWA. Para UCWA, la categoría de contador es **LS:WEB - UCWA**. En el caso de Mobility Service (Mcx), los contadores pertenecen a la categoría **LS:WEB - Mobile Communication Service**. Los contadores que se supervisan son los siguientes:
  
- **Número de sesiones actualmente activas con suscripciones de presencia activas**, que es el número actual de extremos registrados a través de UCWA o Mobility Service (Mcx) que tienen suscripciones de presencia activas (número de usuarios móviles conectados siempre)
    
- **Número de sesiones actualmente activas**, que es el número actual de extremos registrados a través de UCWA o Mobility Service
    
Si la diferencia entre **Número de sesiones actualmente activas con suscripciones de presencia activas** y **Número de sesiones actualmente activas** es pequeña con el transcurso del tiempo, significa que la mayoría de los usuarios de dispositivos móviles tiene un dispositivo conectado siempre, como un dispositivo móvil Android o Nokia (solo para Mcx). Dispositivos UCWA siempre conectado incluyen dispositivos de Apple y Android ejecutan Lync Mobile de 2013 clientes). Si **Número de sesiones actualmente activas** es muy superior a **Número de sesiones actualmente activas con suscripciones de presencia activas**, quiere decir que hay más usuarios que usan un dispositivo de extremo en segundo plano, como un dispositivo Apple iOS o Windows Phone con Mcx. (Windows Phone es el único cliente de Lync Mobile de 2013 que se registrará como esto).
  
Debe establecer un límite en los contadores de rendimiento **Actualmente activo recuento de sesiones con suscripciones de presencia activas** y el **Número de sesiones activas actualmente** , basados en el uso esperado, resultados de planificación de la capacidad y la supervisión continua de Servicio de movilidad y otros contadores del servidor Front-End. Los límites que establezca necesitan permitirle evaluar la capacidad del servidor y generar alertas cuando dicha capacidad se exceda.
  
Para determinar los límites adecuados, debe determinar primero cuánta memoria hay disponible en el servidor Front-End para el servicio de movilidad. Supervise los contadores para determinar cuándo hay que planear la capacidad adicional según la fórmula siguiente:
  
Total de memoria utilizada por el servicio de movilidad de Mcx (MB) = 164 + (400 + 134) 1024 * **Actualmente activo recuento de sesiones con suscripciones activas de presencia** + 400 1024 * ( **Número de sesiones activas actualmente** - **sesión activa actualmente contar con Suscripciones de presencia Active**)
  
> [!IMPORTANT]
> La calculadora de capacidad de Microsoft Lync Server 2010 es una hoja de cálculo se rellena automáticamente con todas las fórmulas que permiten un planificador determinar cuáles serán los requisitos para el Skype para servidores empresariales, incluidos CPU, memoria y disco duro. Puede [Descargar la hoja de cálculo y documento asociado](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
El servidor Front-End necesita suficiente memoria disponible para admitir el servicio de movilidad en situaciones de conmutación por error. Puede supervisar la memoria disponible actual en el servidor Front-End mediante el contador de **Mbytes disponibles** , o mediante la ecuación que se mencionó anteriormente, para planificar la cantidad de memoria que se espera que utilice el servicio de movilidad.
  
Si la cantidad de memoria disponible en el servidor Front-End es inferior a 1 500 MB al planear el número esperado de usuarios de movilidad, necesita agregar más hardware para admitir el servicio de movilidad. Para obtener más detalles, vea [movilidad del Monitor de rendimiento en Skype para Business Server 2015](monitor-mobility-performance.md) en la documentación de las operaciones.
  
## <a name="see-also"></a>Vea también

#### 

[Movilidad de Monitor de rendimiento en Skype en Business Server 2015](monitor-mobility-performance.md)

