---
title: Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Resumen: Obtenga información sobre cómo supervisar los límites de capacidad de memoria de servidor en Skype para Business Server.'
ms.openlocfilehash: 249145e0e76377c356082965a76ce8bf3d11af42
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225359"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo supervisar los límites de capacidad de memoria de servidor en Skype para Business Server.
  
> [!CAUTION]
> La información de este tema que hace referencia a la planeación de capacidad pertenece únicamente a los clientes móviles de Lync 2010 y el servicio de movilidad (Mcx). Planeación de la capacidad para el Unified Communications Web API (UCWA), usado por los clientes móviles de Lync 2013, es proporcionada por la herramienta de planeación de Lync Server 2013. 

> [!NOTE]
> Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos. Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.
  
Dos contadores de rendimiento de movilidad pueden ayudarle a determinar su uso actual y le ayudará a planear la capacidad para el Skype para servicio de movilidad de servidor empresarial (Mcx), así como para supervisar el uso de memoria para UCWA. Para UCWA, la categoría de contador es **LS:WEB - UCWA**. En el caso de Mobility Service (Mcx), los contadores pertenecen a la categoría **LS:WEB - Mobile Communication Service**. Los contadores que se supervisan son los siguientes:
  
- **Número de sesiones actualmente activas con suscripciones de presencia activas**, que es el número actual de extremos registrados a través de UCWA o Mobility Service (Mcx) que tienen suscripciones de presencia activas (número de usuarios móviles conectados siempre)
    
- **Número de sesiones actualmente activas**, que es el número actual de extremos registrados a través de UCWA o Mobility Service
    
Si la diferencia entre **Número de sesiones actualmente activas con suscripciones de presencia activas** y **Número de sesiones actualmente activas** es pequeña con el transcurso del tiempo, significa que la mayoría de los usuarios de dispositivos móviles tiene un dispositivo conectado siempre, como un dispositivo móvil Android o Nokia (solo para Mcx). Dispositivos UCWA siempre conectados incluyen dispositivos de Apple y Android que ejecutan clientes de Lync 2013 Mobile). Si **Número de sesiones actualmente activas** es muy superior a **Número de sesiones actualmente activas con suscripciones de presencia activas**, quiere decir que hay más usuarios que usan un dispositivo de extremo en segundo plano, como un dispositivo Apple iOS o Windows Phone con Mcx. (Windows Phone es el cliente de Lync 2013 Mobile sólo que va a registrar como esto).
  
Debe establecer un límite en los contadores de rendimiento **Actualmente recuento de sesiones de activas con suscripciones de presencia activa** y **Recuento de sesiones actualmente activas** en función de su uso previsto, resultados de planificación de capacidad y la supervisión continua de Servicio de movilidad y otros contadores de servidor Front-End. Los límites que establezca necesitan permitirle evaluar la capacidad del servidor y generar alertas cuando dicha capacidad se exceda.
  
Para determinar los límites adecuados, debe primero determinar cuánta memoria está disponible en el servidor Front-End para el servicio de movilidad. Supervise los contadores para determinar cuándo hay que planear la capacidad adicional según la fórmula siguiente:
  
Número total de memoria usada por el servicio de movilidad de Mcx (MB) = 164 + (400 + 134) 1024 * **Actualmente recuento de sesiones de activas con suscripciones de presencia activa** + 400 / 1024 * ( **Recuento de sesiones activas actualmente** - **sesión actualmente activa contar con Suscripciones de presencia activa**)
  
> [!IMPORTANT]
> La calculadora de capacidad de Microsoft Lync Server 2010 es una hoja de cálculo que se rellena automáticamente con todas las fórmulas que les permiten a un organizador determinar cuáles serán los requisitos para la Skype para servidores empresariales, incluidos CPU, memoria y unidad de disco duro. Puede [Descargar la hoja de cálculo y un documento asociado](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
El servidor Front-End necesita suficiente memoria disponible para admitir el servicio de movilidad en situaciones de conmutación por error. Puede supervisar la memoria disponible actual en el servidor Front-End mediante el contador **Memory\Available Mbytes** , o mediante el uso de la ecuación mencionada anteriormente, para planear para la cantidad de memoria que se espera que use el servicio de movilidad.
  
Si la cantidad de memoria disponible en el servidor Front-End es inferior a 1 500 MB al planear el número esperado de usuarios de movilidad, necesita agregar más hardware para admitir el servicio de movilidad. Para obtener más detalles, vea [movilidad de Monitor de rendimiento en Skype para Business Server](monitor-mobility-performance.md) en la documentación sobre operaciones.
  
## <a name="see-also"></a>Vea también

[Movilidad de Monitor de rendimiento en Skype para Business Server](monitor-mobility-performance.md)
