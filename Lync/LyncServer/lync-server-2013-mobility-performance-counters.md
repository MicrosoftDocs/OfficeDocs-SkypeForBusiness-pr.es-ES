---
title: Contadores de rendimiento de movilidad
TOCTitle: Contadores de rendimiento de movilidad
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48276758
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Contadores de rendimiento de movilidad

 

_**Última modificación del tema:** 2015-03-09_

En las siguientes tablas se recogen los nombres y las descripciones de los contadores de rendimiento que se pueden usar para supervisar los servidores que ejecutan la API web de comunicaciones unificadas (UCWA) y el servicio de movilidad Mcx de Lync Server 2013.

El nombre de categoría de los contadores de la tabla relativa a UCWA es **LS:WEB – UCWA**.

El nombre de categoría de los contadores de la tabla relativa al servicio de movilidad Mcx es **LS:WEB - Mobile Communication Service**.

## Contadores de rendimiento para UCWA


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contador</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Recuento de aplicaciones activas</p></td>
<td><p>Número actual de aplicaciones</p></td>
</tr>
<tr class="even">
<td><p>Recuento de modalidad de uso compartido de aplicaciones activa</p></td>
<td><p>Número actual de modalidad de uso compartido de aplicaciones</p></td>
</tr>
<tr class="odd">
<td><p>Recuento de modalidad de audio activa</p></td>
<td><p>Número actual de modalidad de audio</p></td>
</tr>
<tr class="even">
<td><p>Recuento de modalidad de colaboración de datos activa</p></td>
<td><p>Número actual de modalidad de colaboración de datos</p></td>
</tr>
<tr class="odd">
<td><p>Latencia de recuperación de foto de Active Directory (ms)</p></td>
<td><p>Contador que refleja el promedio de tiempo (en milisegundos) que se invierte en recuperar una foto de Active Directory</p></td>
</tr>
<tr class="even">
<td><p>Recuento de modalidad de mensajería activa</p></td>
<td><p>Número actual de modalidad de mensajería</p></td>
</tr>
<tr class="odd">
<td><p>Recuento de modalidad de vídeo panorámico activa</p></td>
<td><p>Número actual de modalidad de vídeo panorámico</p></td>
</tr>
<tr class="even">
<td><p>Recuento de solicitudes GET pendientes activas</p></td>
<td><p>Número de solicitudes GET pendientes activas actualmente; conexiones largamente mantenidas con el servidor</p></td>
</tr>
<tr class="odd">
<td><p>Recuento de sesiones activas</p></td>
<td><p>Número actual de extremos registrados en UCWA por aplicación y total</p></td>
</tr>
<tr class="even">
<td><p>Recuento de instancias de usuario activas</p></td>
<td><p>Número actual de instancias de usuario</p></td>
</tr>
<tr class="odd">
<td><p>Instancias de usuario activas sin aplicación</p></td>
<td><p>Número actual de instancias de usuario sin aplicación</p></td>
</tr>
<tr class="even">
<td><p>Recuento de modalidad de vídeo de aplicaciones activa</p></td>
<td><p>Número actual de modalidad de vídeo</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes de creación de aplicación recibidas/segundo</p></td>
<td><p>Ratio por segundo de solicitudes de creación de aplicación recibidas</p></td>
</tr>
<tr class="even">
<td><p>Errores de unión a sesión de MCU de AS</p></td>
<td><p>Número de errores de unión a sesión de MCU de AS</p></td>
</tr>
<tr class="odd">
<td><p>Errores de unión a sesión de MCU de AV</p></td>
<td><p>Errores de unión a sesión de MCU de AV</p></td>
</tr>
<tr class="even">
<td><p>Tiempo medio de inicio de aplicación (ms)</p></td>
<td><p>Promedio de tiempo de inicio de la aplicación en milisegundos</p></td>
</tr>
<tr class="odd">
<td><p>Duración media de sesión (ms)</p></td>
<td><p>Duración media de una sesión en milisegundos</p></td>
</tr>
<tr class="even">
<td><p>Errores de unión a sesión de MCU de datos</p></td>
<td><p>Número de errores de unión a sesión de MCU de datos</p></td>
</tr>
<tr class="odd">
<td><p>Latencia de búsqueda de contacto de Exchange (ms)</p></td>
<td><p>Contador que refleja el promedio de tiempo (en milisegundos) que se invierte en buscar un contacto en Exchange</p></td>
</tr>
<tr class="even">
<td><p>Latencia de recuperación de foto HD de Exchange (ms)</p></td>
<td><p>Contador que refleja el promedio de tiempo (en milisegundos) que se invierte en recuperar una foto de Exchange</p></td>
</tr>
<tr class="odd">
<td><p>Respuestas HTTP 4xx/segundo</p></td>
<td><p>Ratio por segundo de respuestas con código HTTP 4xx</p></td>
</tr>
<tr class="even">
<td><p>Respuestas HTTP 5xx/segundo</p></td>
<td><p>Ratio por segundo de respuestas con código HTTP 5xx</p></td>
</tr>
<tr class="odd">
<td><p>Errores de unión a sesión de MCU de MI</p></td>
<td><p>Número de errores de unión a sesión de MCU de MI</p></td>
</tr>
<tr class="even">
<td><p>Número de errores de recuperación de foto de Active Directory</p></td>
<td><p>Número total de errores en recuperar fotos de Active Directory</p></td>
</tr>
<tr class="odd">
<td><p>Número de errores de búsqueda de contacto</p></td>
<td><p>Número total de errores de búsqueda de contactos en Exchange</p></td>
</tr>
<tr class="even">
<td><p>Número de errores de deserialización</p></td>
<td><p>Número total de errores de deserialización</p></td>
</tr>
<tr class="odd">
<td><p>Número de errores de recuperación de foto HD</p></td>
<td><p>Número total de errores en recuperar fotos HD de Exchange</p></td>
</tr>
<tr class="even">
<td><p>Exceso de número máximo de suscripciones por aplicación</p></td>
<td><p>Número de solicitudes de suscripción por encima del máximo permitido por aplicación</p></td>
</tr>
<tr class="odd">
<td><p>Exceso de número máximo de suscripciones por lote</p></td>
<td><p>Número de solicitudes de suscripción por encima del máximo permitido por lote</p></td>
</tr>
<tr class="even">
<td><p>Errores de suscripción de presencia</p></td>
<td><p>Número de errores al suscribir la presencia</p></td>
</tr>
<tr class="odd">
<td><p>Errores de registro de extremos</p></td>
<td><p>Número de errores al registrar extremos</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes recibidas/segundo</p></td>
<td><p>Ratio por segundo de solicitudes recibidas</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes correctas/segundo</p></td>
<td><p>Ratio por segundo de solicitudes correctas (códigos de respuesta HTTP 2xx/3xx)</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes de creación de aplicación correctas/segundo</p></td>
<td><p>Ratio por segundo de solicitudes de creación de aplicación correctas</p></td>
</tr>
<tr class="odd">
<td><p>Recuento de solicitudes GET pendientes de tiempo agotado</p></td>
<td><p>Número de solicitudes GET pendientes que han agotado el tiempo</p></td>
</tr>
<tr class="even">
<td><p>Total de solicitudes de creación de aplicación recibidas</p></td>
<td><p>Número total de solicitudes de creación de aplicaciones recibido desde que se inició el servicio</p></td>
</tr>
<tr class="odd">
<td><p>Total de respuestas HTTP 4xx</p></td>
<td><p>Número total de respuestas HTTP 4xx</p></td>
</tr>
<tr class="even">
<td><p>Total de respuestas HTTP 5xx</p></td>
<td><p>Número total de respuestas HTTP 5xx</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes totales recibidas en el canal de comandos</p></td>
<td><p>Número total de solicitudes recibidas en el canal de comandos</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes correctas totales</p></td>
<td><p>Número total de solicitudes correctas</p></td>
</tr>
<tr class="odd">
<td><p>Total de sesiones iniciadas</p></td>
<td><p>Número total de sesiones que se han iniciado desde que se inició el servicio</p></td>
</tr>
<tr class="even">
<td><p>Sesiones totales finalizadas debido a que se ha agotado el tiempo de espera de inactividad</p></td>
<td><p>Número total de sesiones que han finalizado porque se ha agotado el tiempo de espera de inactividad del usuario</p></td>
</tr>
<tr class="odd">
<td><p>Total de aplicaciones limitadas</p></td>
<td><p>Número total de aplicaciones limitadas</p></td>
</tr>
</tbody>
</table>


### Contadores de rendimiento para el servicio de movilidad Mcx

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contador</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Duración media de una sesión en milisegundos</p></td>
<td><p>Duración media de una sesión en milisegundos</p></td>
</tr>
<tr class="even">
<td><p>Suscripciones de notificación de inserción actuales</p></td>
<td><p>Número actual de suscripciones de notificación de inserción. Este número representa, junto con el recuento de sesiones actualmente activas, el subconjunto de sesiones actualmente activas que hay registradas para dispositivos Windows Mobile o iPhone.</p></td>
</tr>
<tr class="odd">
<td><p>Recuento de sondeos de tiempo de espera agotado de red actualmente activa</p></td>
<td><p>Número de sondeos de red cuyo tiempo de espera se ha agotado</p></td>
</tr>
<tr class="even">
<td><p>Recuento de sondeos actualmente activos</p></td>
<td><p>Número de sondeos actualmente activos (conexiones largamente mantenidas con el servidor)</p></td>
</tr>
<tr class="odd">
<td><p>Recuento de sesiones actualmente activas</p></td>
<td><p>Número actual de extremos registrados en el servicio de movilidad</p></td>
</tr>
<tr class="even">
<td><p>Recuento de sesiones actualmente activas con suscripciones de presencia activa</p></td>
<td><p>Número de sesiones actualmente activas con suscripciones de presencia activa</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes de notificación de inserción erróneas/segundo</p></td>
<td><p>Ratio por segundo de notificaciones de inserción erróneas</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes de notificación de inserción correctas/segundo</p></td>
<td><p>Ratio por segundo de notificaciones de inserción correctas</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes de notificación de inserción reducidas/segundo</p></td>
<td><p>Ratio por segundo de notificaciones de inserción reducidas</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes de notificación de inserción/segundo</p></td>
<td><p>Ratio por segundo de notificaciones de inserción enviadas</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes erróneas/segundo</p></td>
<td><p>Ratio por segundo de solicitudes erróneas</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes recibidas/segundo</p></td>
<td><p>Ratio por segundo de solicitudes recibidas</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes rechazadas/segundo</p></td>
<td><p>Ratio por segundo de solicitudes rechazadas</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes correctas/segundo</p></td>
<td><p>Ratio por segundo de solicitudes correctas</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes de inicio de sesión correctas/segundo</p></td>
<td><p>Ratio por segundo de solicitudes Obtener ubicación correctas. Las solicitudes para iniciar una sesión consumen la mayoría de la CPU en el servidor. La carga máxima admitida es 12/segundo. La sostenibilidad depende de otras cargas en el servidor. Iniciar una sesión normalmente significa un inicio de sesión de un usuario que ha tenido la sesión cerrada durante un período prolongado de tiempo.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas de voz entrantes rechazadas totales</p></td>
<td><p>Número total de llamadas de voz entrantes que se han rechazado</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas de voz entrantes erróneas totales</p></td>
<td><p>Número total de llamadas de voz entrantes erróneas</p></td>
</tr>
<tr class="even">
<td><p>Llamadas de voz salientes erróneas totales</p></td>
<td><p>Número total de llamadas de voz salientes erróneas</p></td>
</tr>
<tr class="odd">
<td><p>Número de sesiones finalizadas por usuario</p></td>
<td><p>Número de sesiones finalizadas por usuarios</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes de notificación de inserción totales</p></td>
<td><p>Número total de solicitudes de notificación de inserción</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes de notificación de inserción erróneas totales</p></td>
<td><p>Número total de solicitudes de notificación de inserción erróneas</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes de notificación de inserción correctas totales</p></td>
<td><p>Número total de solicitudes de notificación de inserción realizadas correctamente</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes de notificación de inserción reducidas totales</p></td>
<td><p>Número total de solicitudes de notificación de inserción que se han reducido</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes erróneas totales</p></td>
<td><p>Número total de solicitudes erróneas</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes totales recibidas en el canal de comandos</p></td>
<td><p>Número total de solicitudes recibidas en el canal de comandos</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes rechazadas totales</p></td>
<td><p>Número total de solicitudes que se han rechazado</p></td>
</tr>
<tr class="odd">
<td><p>Total de solicitudes correctas</p></td>
<td><p>Número total de solicitudes realizadas al servicio de movilidad correctamente</p></td>
</tr>
<tr class="even">
<td><p>Recuento de sesiones iniciadas totales</p></td>
<td><p>Número total de sesiones que se han iniciado desde que se inició el servicio de movilidad</p></td>
</tr>
<tr class="odd">
<td><p>Sesiones totales finalizadas debido a que se ha agotado el tiempo de espera de inactividad del usuario</p></td>
<td><p>Número total de sesiones que han finalizado porque se ha agotado el tiempo de espera de inactividad del usuario</p></td>
</tr>
<tr class="even">
<td><p>Llamadas de voz entrantes correctas totales</p></td>
<td><p>Número total de llamadas de voz entradas que se han realizado correctamente</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas de voz salientes correctas totales</p></td>
<td><p>Número total de llamadas de voz salientes que se han realizado correctamente</p></td>
</tr>
</tbody>
</table>

