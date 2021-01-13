---
title: Supervisar los límites de capacidad de memoria del servidor en Skype Empresarial Server
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
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Resumen: obtenga información sobre cómo supervisar los límites de capacidad de memoria del servidor en Skype Empresarial Server.'
ms.openlocfilehash: f1423d840fdf690332081a8083617c3a072b373c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814300"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Supervisar los límites de capacidad de memoria del servidor en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo supervisar los límites de capacidad de memoria del servidor en Skype Empresarial Server.
  
> [!CAUTION]
> La información de este tema que hace referencia a la planeación de capacidad se refiere únicamente a los clientes móviles de Lync 2010 y al servicio de movilidad (Mcx). La Herramienta de planeación de lync Server 2013 proporciona la planeación de capacidad para la API web de comunicaciones unificadas (UCWA), usada por los clientes de Lync 2013 Mobile. 

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
Dos contadores de rendimiento de movilidad pueden ayudarle a determinar su uso actual y a planear la capacidad del servicio de movilidad de Skype Empresarial Server (Mcx), así como para supervisar el uso de memoria para UCWA. Para UCWA, la categoría de contador **es LS:WEB - UCWA**. Para mobility Service (Mcx), los contadores se encuentran en la categoría **LS:WEB - Mobile Communication Service**. Los contadores que se van a supervisar son:
  
- **Recuento** de sesiones actualmente activas con suscripciones de presencia activa, que es el número actual de puntos de conexión registrados a través de UCWA o el servicio de movilidad (Mcx) que tienen suscripciones de presencia activas (número de usuarios móviles siempre conectados)
    
- **Recuento de sesiones actualmente activas,** que es el número actual de puntos de conexión registrados a través de UCWA o el servicio de movilidad
    
Si la  diferencia entre el recuento de  sesiones actualmente activas con suscripciones de presencia activa y el recuento de sesiones actualmente activas es pequeña con el tiempo, esto significa que la mayoría de los usuarios de dispositivos móviles tienen un dispositivo siempre conectado, como un dispositivo móvil Android o Nokia (solo para Mcx). Los dispositivos conectados siempre a UCWA incluyen dispositivos Apple y Android que ejecutan clientes de Lync 2013 Mobile). Si  el recuento de sesiones actualmente activas es mucho mayor que el recuento de sesiones actualmente activas con suscripciones de presencia **activa,** esto indica que hay más usuarios que usan un dispositivo de extremo en segundo plano, como un dispositivo Apple iOS o Windows Phone en Mcx. (Windows Phone es el único cliente de Lync 2013 Mobile que se registrará como este).
  
Debe establecer un límite  en el recuento de  sesiones actualmente activas con suscripciones de presencia activa y contadores de rendimiento de recuento de sesiones actualmente activos en función del uso esperado, los resultados de planeación de capacidad y la supervisión continua del servicio de movilidad y otros contadores de servidor front-end. Los límites que establezca le permitirán evaluar la capacidad del servidor y generar alertas cuando se supere la capacidad.
  
Para determinar los límites adecuados, primero debe determinar cuánta memoria está disponible en el servidor front-end para el servicio de movilidad. Supervise los contadores para determinar cuándo necesita planear la capacidad adicional, de acuerdo con la fórmula siguiente:
  
Memoria total usada por el servicio de movilidad Mcx (MB) = 164 + (400 + 134) / 1024 ***** Recuento de sesiones actualmente activas con suscripciones de presencia activa + 400 / 1024 * **(** Recuento de sesiones actualmente activas con suscripciones de presencia activa  -  )
  
> [!IMPORTANT]
> La Calculadora de capacidad de Microsoft Lync Server 2010 es una hoja de cálculo que se ha precarga con todas las fórmulas que permiten a un organizador determinar cuáles serán los requisitos para los servidores de Skype Empresarial, incluidos la CPU, la memoria y el disco duro. Puede descargar [la hoja de cálculo y un documento asociado.](https://go.microsoft.com/fwlink/p/?LinkID=212657) 
  
El servidor front-end necesita suficiente memoria disponible para admitir el servicio de movilidad en situaciones de conmutación por error. Puede supervisar la memoria disponible actualmente en el servidor front-end mediante el contador **Memory\Available Mbytes,** o mediante la ecuación mencionada anteriormente, para planear la cantidad de memoria que espera que use el servicio de movilidad.
  
Si la cantidad de memoria disponible en el servidor front-end es inferior a 1.500 MB al planear el número esperado de usuarios de movilidad, debe agregar más hardware para admitir el servicio de movilidad. Para obtener más información, consulte [Monitor mobility for performance in Skype for Business Server](monitor-mobility-performance.md) en la documentación de operaciones.
  
## <a name="see-also"></a>Vea también

[Supervisar la movilidad para el rendimiento en Skype Empresarial Server](monitor-mobility-performance.md)
