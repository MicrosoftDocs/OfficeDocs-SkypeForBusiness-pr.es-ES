---
title: Contadores de rendimiento de movilidad en Skype Empresarial Server
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
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Resumen: obtenga información sobre los contadores de rendimiento que puede usar para supervisar los servidores que ejecutan la API web de comunicaciones unificadas (UCWA) y el servicio de movilidad Mcx de Skype Empresarial Server.'
ms.openlocfilehash: d711ada11cee9cb12a5cde25cab583f8b174ac50
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814410"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Contadores de rendimiento de movilidad en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre los contadores de rendimiento que puede usar para supervisar los servidores que ejecutan la API web de comunicaciones unificadas (UCWA) y el servicio de movilidad Mcx de Skype Empresarial Server.
  
En las tablas siguientes se muestran los nombres y descripciones de los contadores de rendimiento que puede usar para supervisar los servidores que ejecutan la API web de comunicaciones unificadas (UCWA) y el servicio de movilidad Mcx de Skype Empresarial Server. 
  
El nombre de categoría de los contadores de la tabla UCWA es **LS:WEB - UCWA**.
  
El nombre de categoría de los contadores de la tabla Servicio de movilidad de Mcx es **LS:WEB - Mobile Communication Service**.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
## <a name="performance-counters-for-ucwa"></a>Contadores de rendimiento para UCWA

|Counter|Descripción|
|:-----|:-----|
|Recuento de aplicaciones activas  <br/> |El número actual de aplicaciones  <br/> |
|Recuento de modalidades de uso compartido de aplicaciones activas  <br/> |Número actual de modalidad de uso compartido de aplicaciones  <br/> |
|Recuento de modalidad de audio activo  <br/> |El número actual de modalidad de audio  <br/> |
|Recuento de modalidades de colaboración de datos activos  <br/> |El número actual de modalidad de colaboración de datos  <br/> |
|Latencia de obtener fotos de Active Directory (ms)  <br/> |Este contador muestra el tiempo promedio (en milisegundos) para recuperar una foto de Active Directory  <br/> |
|Recuento de modalidades de mensajería activa  <br/> |Número actual de modalidad de mensajería  <br/> |
|Recuento de modalidades de vídeo panorámico activo  <br/> |El número actual de modalidad de vídeo panorámico  <br/> |
|Recuento de obtener pendientes activos  <br/> |El número de pendientes actualmente activos obtiene; conexiones de larga duración al servidor  <br/> |
|Recuento de sesiones activas  <br/> |Número actual de extremos registrados en UCWA por aplicación y total  <br/> |
|Recuento de instancias de usuario activas  <br/> |El número actual de instancias de usuario  <br/> |
|Instancias de usuario activas sin aplicación  <br/> |El número actual de instancias de usuario sin aplicación  <br/> |
|Recuento de modalidad de vídeo activo  <br/> |El número actual de modalidad de vídeo  <br/> |
|Solicitudes de creación de aplicaciones recibidas/segundo  <br/> |Tasa por segundo de solicitudes de creación de aplicaciones recibidas  <br/> |
|Errores de unión a MCU de AS  <br/> |El número de errores de unión a MCU de AS  <br/> |
|Errores de unión a MCU av  <br/> |El número de errores de unión a MCU av  <br/> |
|Tiempo medio de inicio de la aplicación (ms)  <br/> |Tiempo medio de inicio de la aplicación en milisegundos  <br/> |
|Duración media de la sesión (ms)  <br/> |Duración media de una sesión en milisegundos  <br/> |
|Errores de unión a MCU de datos  <br/> |Número de errores de unión a MCU de datos  <br/> |
|Latencia de búsqueda de contactos de Exchange (ms)  <br/> |Este contador muestra el tiempo promedio (en milisegundos) para buscar contacto en Exchange  <br/> |
|Latencia de exchange HD Photo Get (ms)  <br/> |Este contador muestra el tiempo promedio (en milisegundos) para recuperar una foto de Exchange  <br/> |
|Respuestas HTTP 4xx/segundo  <br/> |Tasa por segundo de respuestas con código HTTP 4xx  <br/> |
|Respuestas HTTP 5xx/segundo  <br/> |Tasa por segundo de respuestas con código HTTP 5xx  <br/> |
|Errores de unión a MCU de MI  <br/> |Número de errores de unión a MCU de MENSAJERÍA instantánea  <br/> |
|Número de errores de obtener fotos de Active Directory  <br/> |El número total de errores para recuperar fotos de Active Directory  <br/> |
|Número de errores de búsqueda de contactos  <br/> |El número total de errores de búsqueda de contactos en Exchange  <br/> |
|Número de errores de deserialización  <br/> |El número total de errores de deserialización  <br/> |
|Número de errores de hd photo get  <br/> |El número total de errores al recuperar fotos HD de Exchange  <br/> |
|Sobre el número máximo de suscripciones por aplicación  <br/> |El número de solicitudes de suscripción por encima del máximo permitido por aplicación  <br/> |
|Sobre el número máximo de suscripciones por lote  <br/> |El número de solicitudes de suscripción por encima del máximo permitido por lote  <br/> |
|Errores de suscripción de presencia  <br/> |El número de errores al suscribirse a la presencia  <br/> |
|Registro de errores de puntos de conexión  <br/> |El número de errores para registrar puntos de conexión  <br/> |
|Solicitudes recibidas/segundo  <br/> |Ratio por segundo de solicitudes recibidas  <br/> |
|Solicitudes correctas/segundo  <br/> |Tasa por segundo de solicitudes correctas (códigos de respuesta HTTP 2xx/3xx)  <br/> |
|Creación correcta de solicitudes de aplicación/segundo  <br/> |Tasa por segundo de solicitudes de creación de aplicaciones correctas  <br/> |
|Número de solicitudes pendientes de tiempo de espera con tiempo de espera  <br/> |El número de solicitudes pendientes que se ha quedó el tiempo de espera  <br/> |
|Total de solicitudes de creación de aplicaciones recibidas  <br/> |El número total de solicitudes de creación de aplicaciones recibidas desde que se inició el servicio  <br/> |
|Total de respuestas HTTP 4xx  <br/> |Número total de respuestas HTTP 4xx  <br/> |
|Total de respuestas HTTP 5xx  <br/> |Número total de respuestas HTTP 5xx  <br/> |
|Solicitudes totales recibidas en el canal de comandos  <br/> |Número total de solicitudes recibidas en el canal de comandos  <br/> |
|Solicitudes correctas totales  <br/> |El número total de solicitudes que se han hecho correctamente  <br/> |
|Total de sesiones iniciadas  <br/> |El número total de sesiones que se iniciaron desde que se inició el servicio  <br/> |
|Total de sesiones finalizadas debido al tiempo de espera inactivo  <br/> |Número total de sesiones que han finalizado porque se ha agotado el tiempo de espera de inactividad del usuario  <br/> |
|Total de aplicaciones limitadas  <br/> |El número de aplicaciones limitadas  <br/> |
   
**Contadores de rendimiento para mcx Mobility Service**

|**Contador**|**Descripción**|
|:-----|:-----|
|Duración media de una sesión en milisegundos  <br/> |Duración media de una sesión en milisegundos  <br/> |
|Suscripciones de notificación de inserción actuales  <br/> |Número actual de suscripciones de notificación de inserción. Este número, junto con el recuento de sesiones actualmente activas, representa el subconjunto de sesiones actualmente activas registradas para dispositivos Windows Mobile o iPhone.  <br/> |
|Recuento de sondeos de tiempo de espera agotado de red actualmente activa  <br/> |Número de sondeos de red cuyo tiempo de espera se ha agotado  <br/> |
|Recuento de sondeos actualmente activos  <br/> |Número de sondeos actualmente activos (conexiones largamente mantenidas con el servidor)  <br/> |
|Recuento de sesiones actualmente activas  <br/> |Número actual de extremos registrados en el servicio de movilidad  <br/> |
|Recuento de sesiones actualmente activas con suscripciones de presencia activa  <br/> |Número de sesiones actualmente activas con suscripciones de presencia activa  <br/> |
|Solicitudes de notificación de inserción erróneas/segundo  <br/> |Ratio por segundo de notificaciones de inserción erróneas  <br/> |
|Solicitudes de notificación de inserción correctas/segundo  <br/> |Ratio por segundo de notificaciones de inserción correctas  <br/> |
|Solicitudes de notificación de inserción reducidas/segundo  <br/> |Ratio por segundo de notificaciones de inserción reducidas  <br/> |
|Solicitudes de notificación de inserción/segundo  <br/> |Ratio por segundo de notificaciones de inserción enviadas  <br/> |
|Solicitudes erróneas/segundo  <br/> |Ratio por segundo de solicitudes erróneas  <br/> |
|Solicitudes recibidas/segundo  <br/> |Ratio por segundo de solicitudes recibidas  <br/> |
|Solicitudes rechazadas/segundo  <br/> |Ratio por segundo de solicitudes rechazadas  <br/> |
|Solicitudes correctas/segundo  <br/> |Ratio por segundo de solicitudes correctas  <br/> |
|Solicitudes de inicio de sesión correctas/segundo  <br/> |Ratio por segundo de solicitudes Obtener ubicación correctas. Las solicitudes para iniciar una sesión consumen la mayoría de la CPU en el servidor. La carga máxima admitida es 12/segundo. La sostenibilidad depende de otras cargas en el servidor. Iniciar una sesión normalmente significa un inicio de sesión de un usuario que ha tenido la sesión cerrada durante un período prolongado de tiempo.  <br/> |
|Llamadas de voz entrantes rechazadas totales  <br/> |Número total de llamadas de voz entrantes que se han rechazado  <br/> |
|Llamadas de voz entrantes erróneas totales  <br/> |Número total de llamadas de voz entrantes erróneas  <br/> |
|Llamadas de voz salientes erróneas totales  <br/> |Número total de llamadas de voz salientes erróneas  <br/> |
|Número de sesiones finalizadas por usuario  <br/> |Número de sesiones finalizadas por usuarios  <br/> |
|Solicitudes de notificación de inserción totales  <br/> |Número total de solicitudes de notificación de inserción  <br/> |
|Solicitudes de notificación de inserción erróneas totales  <br/> |Número total de solicitudes de notificación de inserción erróneas  <br/> |
|Solicitudes de notificación de inserción correctas totales  <br/> |Número total de solicitudes de notificación de inserción realizadas correctamente  <br/> |
|Solicitudes de notificación de inserción reducidas totales  <br/> |Número total de solicitudes de notificación de inserción que se han reducido  <br/> |
|Solicitudes erróneas totales  <br/> |Número total de solicitudes erróneas  <br/> |
|Solicitudes totales recibidas en el canal de comandos  <br/> |Número total de solicitudes recibidas en el canal de comandos  <br/> |
|Solicitudes rechazadas totales  <br/> |Número total de solicitudes que se han rechazado  <br/> |
|Solicitudes correctas totales  <br/> |Número total de solicitudes realizadas al servicio de movilidad correctamente  <br/> |
|Recuento de sesiones iniciadas totales  <br/> |Número total de sesiones que se han iniciado desde que se inició el servicio de movilidad  <br/> |
|Sesiones totales finalizadas debido a que se ha agotado el tiempo de espera de inactividad del usuario  <br/> |Número total de sesiones que han finalizado porque se ha agotado el tiempo de espera de inactividad del usuario  <br/> |
|Llamadas de voz entrantes correctas totales  <br/> |Número total de llamadas de voz entradas que se han realizado correctamente  <br/> |
|Llamadas de voz salientes correctas totales  <br/> |Número total de llamadas de voz salientes que se han realizado correctamente  <br/> |
   
> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
