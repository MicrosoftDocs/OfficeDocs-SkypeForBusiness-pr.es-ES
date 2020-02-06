---
title: Contadores de rendimiento de movilidad en Skype empresarial Server
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
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Resumen: Obtenga información sobre los contadores de rendimiento que puede usar para supervisar los servidores que ejecutan la API Web de comunicaciones unificadas (UCWA) y el servicio de movilidad de Skype empresarial Server MCX.'
ms.openlocfilehash: e9a3ade40694ef18e1022388d48838822d409625
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817769"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Contadores de rendimiento de movilidad en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre los contadores de rendimiento que puede usar para supervisar los servidores que ejecutan la API Web de comunicaciones unificadas (UCWA) y el servicio de movilidad de Skype empresarial Server MCX.
  
En las siguientes tablas se enumeran los nombres y descripciones de los contadores de rendimiento que puede usar para supervisar los servidores que ejecutan la API Web de comunicaciones unificadas (UCWA) y el servicio de movilidad de Skype empresarial Server MCX. 
  
El nombre de la categoría de los contadores de la tabla de UCWA es **LS: Web-UCWA**.
  
El nombre de categoría de los contadores de la tabla relativa al servicio de movilidad Mcx es **LS:WEB - Mobile Communication Service**.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
## <a name="performance-counters-for-ucwa"></a>Contadores de rendimiento para UCWA

|Contador|Descripción|
|:-----|:-----|
|Recuento de aplicaciones activas  <br/> |Número actual de aplicaciones  <br/> |
|Recuento de modalidad de uso compartido de aplicaciones activa  <br/> |Número actual de modalidad de uso compartido de aplicaciones  <br/> |
|Recuento de modalidad de audio activa  <br/> |Número actual de modalidad de audio  <br/> |
|Recuento de modalidad de colaboración de datos activa  <br/> |Número actual de modalidad de colaboración de datos  <br/> |
|Latencia de recuperación de foto de Active Directory (ms)  <br/> |Contador que refleja el promedio de tiempo (en milisegundos) que se invierte en recuperar una foto de Active Directory  <br/> |
|Recuento de modalidad de mensajería activa  <br/> |Número actual de modalidad de mensajería  <br/> |
|Recuento de modalidad de vídeo panorámico activa  <br/> |Número actual de modalidad de vídeo panorámico  <br/> |
|Recuento de solicitudes GET pendientes activas  <br/> |Número de solicitudes GET pendientes activas actualmente; conexiones largamente mantenidas con el servidor  <br/> |
|Recuento de sesiones activas  <br/> |Número actual de extremos registrados en UCWA por aplicación y total  <br/> |
|Recuento de instancias de usuario activas  <br/> |Número actual de instancias de usuario  <br/> |
|Instancias de usuario activas sin aplicación  <br/> |Número actual de instancias de usuario sin aplicación  <br/> |
|Recuento de modalidad de vídeo de aplicaciones activa  <br/> |Número actual de modalidad de vídeo  <br/> |
|Solicitudes de creación de aplicación recibidas/segundo  <br/> |Ratio por segundo de solicitudes de creación de aplicación recibidas  <br/> |
|Errores de unión a sesión de MCU de AS  <br/> |Número de errores de unión a sesión de MCU de AS  <br/> |
|Errores de unión a sesión de MCU de AV  <br/> |Errores de unión a sesión de MCU de AV  <br/> |
|Tiempo medio de inicio de aplicación (ms)  <br/> |Promedio de tiempo de inicio de la aplicación en milisegundos  <br/> |
|Duración media de sesión (ms)  <br/> |Duración media de una sesión en milisegundos  <br/> |
|Errores de unión a sesión de MCU de datos  <br/> |Número de errores de unión a sesión de MCU de datos  <br/> |
|Latencia de búsqueda de contacto de Exchange (ms)  <br/> |Contador que refleja el promedio de tiempo (en milisegundos) que se invierte en buscar un contacto en Exchange  <br/> |
|Latencia de recuperación de foto HD de Exchange (ms)  <br/> |Contador que refleja el promedio de tiempo (en milisegundos) que se invierte en recuperar una foto de Exchange  <br/> |
|Respuestas HTTP 4xx/segundo  <br/> |Ratio por segundo de respuestas con código HTTP 4xx  <br/> |
|Respuestas HTTP 5xx/segundo  <br/> |Ratio por segundo de respuestas con código HTTP 5xx  <br/> |
|Errores de unión a sesión de MCU de MI  <br/> |Cantidad de errores de unión a sesión de MCU de MI  <br/> |
|Cantidad de errores de recuperación de foto de Active Directory  <br/> |Cantidad total de errores en recuperar fotos de Active Directory  <br/> |
|Cantidad de errores de búsqueda de contacto  <br/> |Cantidad total de errores de búsqueda de contactos en Exchange  <br/> |
|Cantidad de errores de deserialización  <br/> |Cantidad total de errores de deserialización  <br/> |
|Número de errores de obtención de fotos de alta definición  <br/> |Cantidad total de errores en recuperar fotos HD de Exchange  <br/> |
|Exceso de número máximo de suscripciones por aplicación  <br/> |Cantidad de solicitudes de suscripción por encima del máximo permitido por aplicación  <br/> |
|Exceso de número máximo de suscripciones por lote  <br/> |Cantidad de solicitudes de suscripción por encima del máximo permitido por lote  <br/> |
|Errores de suscripción de presencia  <br/> |Cantidad de errores al suscribir la presencia  <br/> |
|Errores de registro de extremos  <br/> |Cantidad de errores al registrar extremos  <br/> |
|Solicitudes recibidas/segundo  <br/> |Ratio por segundo de solicitudes recibidas  <br/> |
|Solicitudes correctas/segundo  <br/> |Ratio por segundo de solicitudes correctas (códigos de respuesta HTTP 2xx/3xx)  <br/> |
|Solicitudes de creación de aplicación correctas/segundo  <br/> |Ratio por segundo de solicitudes de creación de aplicación correctas  <br/> |
|Recuento de solicitudes GET pendientes de tiempo agotado  <br/> |Cantidad de solicitudes GET pendientes que han agotado el tiempo  <br/> |
|Total de solicitudes de creación de aplicación recibidas  <br/> |Cantidad total de solicitudes de creación de aplicaciones recibido desde que se inició el servicio  <br/> |
|Total de respuestas HTTP 4xx  <br/> |Cantidad total de respuestas HTTP 4xx  <br/> |
|Total de respuestas HTTP 5xx  <br/> |Cantidad total de respuestas HTTP 5xx  <br/> |
|Solicitudes totales recibidas en el canal de comandos  <br/> |Cantidad total de solicitudes recibidas en el canal de comandos  <br/> |
|Total de solicitudes correctas  <br/> |Cantidad total de solicitudes correctas  <br/> |
|Total de sesiones iniciadas  <br/> |Cantidad total de sesiones que se han iniciado desde que se inició el servicio  <br/> |
|Sesiones totales finalizadas ya que se ha agotado el tiempo de espera de inactividad  <br/> |Cantidad total de sesiones que han finalizado porque se ha agotado el tiempo de espera de inactividad del usuario  <br/> |
|Total de aplicaciones limitadas  <br/> |Cantidad total de aplicaciones limitadas  <br/> |
   
**Contadores de rendimiento para el servicio de movilidad Mcx**

|**Contador**|**Descripción**|
|:-----|:-----|
|Duración media de una sesión en milisegundos  <br/> |Duración media de una sesión en milisegundos  <br/> |
|Suscripciones de notificación de inserción actuales  <br/> |Cantidad actual de suscripciones de notificación de inserción. Esta cantidad representa, junto con el recuento de sesiones actualmente activas, el subconjunto de sesiones actualmente activas que hay registradas para dispositivos Windows Mobile o iPhone.  <br/> |
|Recuento de sondeos de tiempo de espera agotado de red actualmente activa  <br/> |Cantidad de sondeos de red cuyo tiempo de espera se ha agotado  <br/> |
|Recuento de sondeos actualmente activos  <br/> |Cantidad de sondeos actualmente activos (conexiones largamente mantenidas con el servidor)  <br/> |
|Recuento de sesiones actualmente activas  <br/> |Cantidad actual de extremos registrados en el servicio de movilidad  <br/> |
|Recuento de sesiones actualmente activas con suscripciones de presencia activa  <br/> |Cantidad de sesiones actualmente activas con suscripciones de presencia activa  <br/> |
|Solicitudes de notificación de inserción erróneas/segundo  <br/> |Ratio por segundo de notificaciones de inserción erróneas  <br/> |
|Solicitudes de notificación de inserción correctas/segundo  <br/> |Ratio por segundo de notificaciones de inserción correctas  <br/> |
|Solicitudes de notificación de inserción reducidas/segundo  <br/> |Ratio por segundo de notificaciones de inserción reducidas  <br/> |
|Solicitudes de notificación de inserción/segundo  <br/> |Ratio por segundo de notificaciones de inserción enviadas  <br/> |
|Solicitudes erróneas/segundo  <br/> |Ratio por segundo de solicitudes erróneas  <br/> |
|Solicitudes recibidas/segundo  <br/> |Ratio por segundo de solicitudes recibidas  <br/> |
|Solicitudes rechazadas/segundo  <br/> |Ratio por segundo de solicitudes rechazadas  <br/> |
|Solicitudes correctas/segundo  <br/> |Ratio por segundo de solicitudes correctas  <br/> |
|Solicitudes de inicio de sesión correctas/segundo  <br/> |Ratio por segundo de solicitudes Obtener ubicación correctas. Las solicitudes para iniciar una sesión consumen la mayoría de la CPU en el servidor. La carga máxima admitida es 12/segundo. La sostenibilidad depende de otras cargas en el servidor. Iniciar una sesión normalmente significa un inicio de sesión de un usuario que ha tenido la sesión cerrada durante un período prolongado de tiempo.  <br/> |
|Llamadas de voz entrantes rechazadas totales  <br/> |Cantidad total de llamadas de voz entrantes que se han rechazado  <br/> |
|Llamadas de voz entrantes erróneas totales  <br/> |Cantidad total de llamadas de voz entrantes erróneas  <br/> |
|Llamadas de voz salientes erróneas totales  <br/> |Cantidad total de llamadas de voz salientes erróneas  <br/> |
|Cantidad de sesiones finalizadas por usuario  <br/> |Cantidad de sesiones finalizadas por usuarios  <br/> |
|Solicitudes de notificación de inserción totales  <br/> |Cantidad total de solicitudes de notificación de inserción  <br/> |
|Solicitudes de notificación de inserción erróneas totales  <br/> |Cantidad total de solicitudes de notificación de inserción erróneas  <br/> |
|Solicitudes de notificación de inserción correctas totales  <br/> |Cantidad total de solicitudes de notificación de inserción realizadas correctamente  <br/> |
|Solicitudes de notificación de inserción reducidas totales  <br/> |Cantidad total de solicitudes de notificación de inserción que se han reducido  <br/> |
|Solicitudes erróneas totales  <br/> |Cantidad total de solicitudes erróneas  <br/> |
|Solicitudes totales recibidas en el canal de comandos  <br/> |Cantidad total de solicitudes recibidas en el canal de comandos  <br/> |
|Solicitudes rechazadas totales  <br/> |Cantidad total de solicitudes que se han rechazado  <br/> |
|Total de solicitudes correctas  <br/> |Cantidad total de solicitudes realizadas al servicio de movilidad correctamente  <br/> |
|Recuento de sesiones iniciadas totales  <br/> |Cantidad total de sesiones que se han iniciado desde que se inició el servicio de movilidad  <br/> |
|Sesiones totales finalizadas ya que se ha agotado el tiempo de espera de inactividad del usuario  <br/> |Cantidad total de sesiones que han finalizado porque se ha agotado el tiempo de espera de inactividad del usuario  <br/> |
|Llamadas de voz entrantes correctas totales  <br/> |Cantidad total de llamadas de voz entradas que se han realizado correctamente  <br/> |
|Llamadas de voz salientes correctas totales  <br/> |Cantidad total de llamadas de voz salientes que se han realizado correctamente  <br/> |
   
> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
