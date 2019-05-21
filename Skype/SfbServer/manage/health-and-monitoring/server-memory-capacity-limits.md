---
title: Supervisar los límites de capacidad de memoria del servidor en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Resumen: Aprenda a supervisar los límites de capacidad de memoria del servidor en Skype empresarial Server.'
ms.openlocfilehash: f089ab9b5be693872754691050133ad27e992896
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279826"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Supervisar los límites de capacidad de memoria del servidor en Skype empresarial Server
 
**Resumen:** Aprenda a supervisar los límites de capacidad de memoria del servidor en Skype empresarial Server.
  
> [!CAUTION]
> La información de este tema que se refiere a la planificación de capacidad solo se aplica a los clientes móviles de Lync 2010 y al servicio de movilidad (MCX). La planificación de capacidad de la API Web de comunicaciones unificadas (UCWA), usada por los clientes móviles de Lync 2013, se proporciona en Lync Server 2013, la herramienta de planeación. 

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
Dos contadores de rendimiento de movilidad pueden ayudarle a determinar su uso actual y a ayudarle a planear la capacidad del servicio de movilidad de Skype empresarial Server (MCX), así como a supervisar el uso de memoria para UCWA. Para UCWA, la categoría de contador es **LS: Web-UCWA**. En el caso de Mobility Service (Mcx), los contadores pertenecen a la categoría **LS:WEB - Mobile Communication Service**. Los contadores que se supervisan son los siguientes:
  
- **Número de sesiones actualmente activas con suscripciones de presencia activas**, que es el número actual de extremos registrados a través de UCWA o Mobility Service (Mcx) que tienen suscripciones de presencia activas (número de usuarios móviles conectados siempre)
    
- **Número de sesiones actualmente activas**, que es el número actual de extremos registrados a través de UCWA o Mobility Service
    
Si la diferencia entre **Número de sesiones actualmente activas con suscripciones de presencia activas** y **Número de sesiones actualmente activas** es pequeña con el transcurso del tiempo, significa que la mayoría de los usuarios de dispositivos móviles tiene un dispositivo conectado siempre, como un dispositivo móvil Android o Nokia (solo para Mcx). UCWA los dispositivos siempre conectados incluyen Apple y Android que ejecutan clientes móviles de Lync 2013). Si **Número de sesiones actualmente activas** es muy superior a **Número de sesiones actualmente activas con suscripciones de presencia activas**, quiere decir que hay más usuarios que usan un dispositivo de extremo en segundo plano, como un dispositivo Apple iOS o Windows Phone con Mcx. (Windows Phone es el único cliente móvil de Lync 2013 que se registrará como this).
  
Debe establecer un límite en el recuento de **sesiones activas actualmente con suscripciones de presencia activas** y contadores de rendimiento de recuento de **sesiones actualmente activos** según el uso previsto, los resultados de la planificación de capacidad y la supervisión continuada de Servicio de movilidad y otros contadores de servidor front-end. Los límites que establezca necesitan permitirle evaluar la capacidad del servidor y generar alertas cuando dicha capacidad se exceda.
  
Para determinar los límites adecuados, primero debe determinar cuánta memoria está disponible en el servidor front-end para el servicio de movilidad. Supervise los contadores para determinar cuándo hay que planear la capacidad adicional según la fórmula siguiente:
  
Memoria total usada por el servicio de movilidad de MCX (MB) = 164 + (400 + 134)/1024 * recuento **de sesiones activo en la actualidad con suscripciones de presencia activas** + 400/1024 * (recuento de sesión **actualmente** - activo recuento**de sesiones con Suscripciones de presencia activas**)
  
> [!IMPORTANT]
> La calculadora de capacidad 2010 de Microsoft Lync Server es una hoja de cálculo que se rellenó con todas las fórmulas que permiten a un planificador determinar cuáles serán los requisitos para los servidores de Skype empresarial, como la CPU, la memoria y el disco duro. Puede [descargar la hoja de cálculo y un documento asociado](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
El servidor front-end necesita suficiente memoria disponible para admitir el servicio de movilidad en situaciones de conmutación por error. Puede supervisar la memoria disponible actual en el servidor front-end con el contador de **Memory\Available Mbytes** o con la ecuación mencionada anteriormente, para planear la cantidad de memoria que espera que use el servicio de movilidad.
  
Si la cantidad de memoria disponible en el servidor front-end es inferior a 1.500 MB cuando se planea la cantidad de usuarios de movilidad esperada, necesita agregar más hardware para admitir el servicio de movilidad. Para obtener más información, consulte [supervisar la movilidad para el rendimiento en Skype empresarial Server](monitor-mobility-performance.md) en la documentación de operaciones.
  
## <a name="see-also"></a>Vea también

[Supervisar la movilidad para el rendimiento en Skype empresarial Server](monitor-mobility-performance.md)
