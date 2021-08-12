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
ms.openlocfilehash: d62ae4a7e9eaed4fd866107de276990c3d883d946b2d44035fcac4fa47b69e61
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314466"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Supervisar los límites de capacidad de memoria del servidor en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo supervisar los límites de capacidad de memoria del servidor en Skype Empresarial Server.
  
> [!CAUTION]
> La información de este tema que hace referencia a la planeación de capacidad se refiere únicamente a los clientes de Lync 2010 Mobile y el Servicio de movilidad (Mcx). Lync Server 2013, Planning Tool, proporciona la planeación de capacidad para la API web de comunicaciones unificadas (UCWA), que usan los clientes de Lync 2013 Mobile. 

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes Skype Empresarial móviles ya usan la API web de comunicaciones unificadas (UCWA) para admitir mensajería instantánea (MI), presencia y contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
Dos contadores de rendimiento de movilidad pueden ayudarle a determinar el uso actual y ayudarle a planear la capacidad del servicio de movilidad de Skype Empresarial Server (Mcx), así como a supervisar el uso de memoria para UCWA. Para UCWA, la categoría de contador es **LS:WEB - UCWA**. Para el Servicio de movilidad (Mcx), los contadores están en la categoría **LS:WEB - Mobile Communication Service**. Los contadores que se van a supervisar son:
  
- **Recuento de sesiones** activas con suscripciones de presencia activa, que es el número actual de puntos de conexión registrados a través de UCWA o el Servicio de movilidad (Mcx) que tienen suscripciones de presencia activa (número de usuarios móviles siempre conectados)
    
- **Recuento de sesiones activas** actualmente, que es el número actual de puntos de conexión registrados a través de UCWA o el servicio de movilidad
    
Si la diferencia entre **recuento** de sesiones  activas con suscripciones de presencia activa y recuento de sesiones activas es pequeña con el tiempo, esto significa que la mayoría de los usuarios de dispositivos móviles tienen un dispositivo siempre conectado, como un dispositivo móvil Android o Nokia (solo para Mcx). Los dispositivos ucwa siempre conectados incluyen dispositivos Apple y Android que ejecutan clientes móviles de Lync 2013). Si **el** número de sesiones activas actualmente es mucho mayor que el recuento de sesiones activas actualmente con suscripciones de presencia **activa,** esto indica que más usuarios usan un dispositivo de punto de conexión en segundo plano, como un dispositivo iOS de Apple o Windows Phone en Mcx. (Windows Phone es el único cliente de Lync 2013 Mobile que se registrará como este).
  
Debe establecer un límite  en el recuento de  sesiones actualmente activas con suscripciones de presencia activa y contadores de rendimiento de recuento de sesiones actualmente activos en función del uso esperado, los resultados de planeación de capacidad y la supervisión continua del servicio de movilidad y otros contadores de servidor front-end. Los límites que establezca deben permitirle evaluar la capacidad del servidor y generar alertas cuando se supere la capacidad.
  
Para determinar los límites adecuados, primero debe determinar cuánta memoria está disponible en el servidor front-end para el servicio de movilidad. Supervise los contadores para determinar cuándo necesita planear la capacidad adicional, de acuerdo con la siguiente fórmula:
  
Memoria total usada por mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 * **Recuento** de sesiones activas con suscripciones de presencia activa + 400 / 1024 * **(** Recuento de sesiones activas actualmente con suscripciones de presencia  -  **activa**)
  
> [!IMPORTANT]
> La Calculadora de capacidad de Microsoft Lync Server 2010 es una hoja de cálculo que está prepoblada con todas las fórmulas que permiten a un organizador determinar cuáles serán los requisitos para los servidores de Skype Empresarial, incluida la CPU, la memoria y el disco duro. Puede descargar [la hoja de cálculo y un documento asociado.](https://go.microsoft.com/fwlink/p/?LinkID=212657) 
  
El servidor front-end necesita suficiente memoria disponible para admitir el servicio de movilidad en situaciones de conmutación por error. Puede supervisar la memoria disponible actual en el servidor front-end mediante el contador **Memory\Available Mbytes,** o mediante la ecuación mencionada anteriormente, para planear la cantidad de memoria que espera que use el servicio de movilidad.
  
Si la cantidad de memoria disponible en el servidor front-end es inferior a 1.500 MB al planear el número esperado de usuarios de movilidad, debe agregar más hardware para admitir el servicio de movilidad. Para obtener más información, consulte [Monitor mobility for performance in Skype Empresarial Server](monitor-mobility-performance.md) en la documentación sobre operaciones.
  
## <a name="see-also"></a>Consulte también

[Supervisar la movilidad para obtener rendimiento en Skype Empresarial Server](monitor-mobility-performance.md)
