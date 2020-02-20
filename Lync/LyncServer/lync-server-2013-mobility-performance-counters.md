---
title: 'Lync Server 2013: contadores de rendimiento de movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb5363ef31f44abdb9c8ea07938668f17b95c471
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a>Contadores de rendimiento de movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

En las tablas siguientes se enumeran los nombres y las descripciones de los contadores de rendimiento que puede usar para supervisar los servidores que ejecutan la API Web de comunicaciones unificadas (UCWA) y el servicio de movilidad Lync Server 2013 MCX.

El nombre de categoría de los contadores de la tabla UCWA es **LS: Web – UCWA**.

El nombre de categoría de los contadores de la tabla MCX Mobility Service es **LS: web-Mobile Communication Service**.

<div>

## <a name="performance-counters-for-ucwa"></a>Contadores de rendimiento para UCWA


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Counter</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Recuento de aplicaciones activas</p></td>
<td><p>Número actual de aplicaciones</p></td>
</tr>
<tr class="even">
<td><p>Recuento de modalidad de uso compartido de aplicaciones activas</p></td>
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
<td><p>Latencia de la obtención de foto de Active Directory (MS)</p></td>
<td><p>Este contador muestra el promedio de tiempo (en milisegundos) que se tarda en recuperar una foto de Active Directory</p></td>
</tr>
<tr class="even">
<td><p>Recuento de modalidad de mensajería activa</p></td>
<td><p>Número actual de modalidad de mensajería</p></td>
</tr>
<tr class="odd">
<td><p>Recuento de modalidad de vídeo panorámico activo</p></td>
<td><p>Número actual de modalidad de vídeo panorámico</p></td>
</tr>
<tr class="even">
<td><p>Recuento de Get pendientes activos</p></td>
<td><p>Número de dependientes actualmente activas. conexiones de larga duración con el servidor</p></td>
</tr>
<tr class="odd">
<td><p>Recuento de sesiones activas</p></td>
<td><p>Número actual de extremos registrados en UCWA por aplicación y totales</p></td>
</tr>
<tr class="even">
<td><p>Número de instancias de usuario activas</p></td>
<td><p>Número actual de instancias de usuario</p></td>
</tr>
<tr class="odd">
<td><p>Instancias de usuario activas sin aplicación</p></td>
<td><p>Número actual de instancias de usuario sin aplicación</p></td>
</tr>
<tr class="even">
<td><p>Recuento de modalidad de vídeo activo</p></td>
<td><p>Número actual de modalidad de vídeo</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes de creación de aplicación recibidas/segundo</p></td>
<td><p>Tasa por segundo de solicitudes de creación de aplicaciones recibidas</p></td>
</tr>
<tr class="even">
<td><p>Como errores de unión de MCU</p></td>
<td><p>El número de errores de Unión en MCU</p></td>
</tr>
<tr class="odd">
<td><p>Errores de unión a un MCU AV</p></td>
<td><p>Número de errores de unión a un MCU AV</p></td>
</tr>
<tr class="even">
<td><p>Tiempo medio de inicio de la aplicación (MS)</p></td>
<td><p>Tiempo medio de inicio de la aplicación en milisegundos</p></td>
</tr>
<tr class="odd">
<td><p>Duración media de la sesión (MS)</p></td>
<td><p>Duración media de una sesión en milisegundos</p></td>
</tr>
<tr class="even">
<td><p>Errores de unión a Data MCU</p></td>
<td><p>Número de errores de unión a datos MCU</p></td>
</tr>
<tr class="odd">
<td><p>Latencia de búsqueda de contactos de Exchange (MS)</p></td>
<td><p>Este contador muestra el tiempo medio (en milisegundos) para buscar en el contacto en Exchange</p></td>
</tr>
<tr class="even">
<td><p>Latencia de obtención de foto HD de Exchange (MS)</p></td>
<td><p>Este contador muestra el promedio de tiempo (en milisegundos) que se tarda en recuperar una foto de Exchange</p></td>
</tr>
<tr class="odd">
<td><p>Respuestas 4xx HTTP/segundo</p></td>
<td><p>Tasa por segundo de respuestas con código 4xx HTTP</p></td>
</tr>
<tr class="even">
<td><p>Respuestas HTTP 5xx/segundo</p></td>
<td><p>Tasa por segundo de respuestas con código HTTP 5xx</p></td>
</tr>
<tr class="odd">
<td><p>Errores de unión de mi MCU</p></td>
<td><p>Número de errores de unión de mi MCU</p></td>
</tr>
<tr class="even">
<td><p>Número de errores de obtención de foto de Active Directory</p></td>
<td><p>Número total de errores para recuperar fotos de Active Directory</p></td>
</tr>
<tr class="odd">
<td><p>Número de errores de búsqueda de contactos</p></td>
<td><p>Número total de errores en la búsqueda de contactos en Exchange</p></td>
</tr>
<tr class="even">
<td><p>Número de errores de deserialización</p></td>
<td><p>Número total de errores de deserialización</p></td>
</tr>
<tr class="odd">
<td><p>Número de errores de obtención de foto HD</p></td>
<td><p>El número total de errores para recuperar fotos HD de Exchange</p></td>
</tr>
<tr class="even">
<td><p>Sobre el número máximo de suscripciones por aplicación</p></td>
<td><p>El número de solicitudes de suscripción por encima del máximo permitido por aplicación</p></td>
</tr>
<tr class="odd">
<td><p>Superada la cantidad máxima de suscripciones por lote</p></td>
<td><p>El número de solicitudes de suscripción que supera el máximo permitido por lote</p></td>
</tr>
<tr class="even">
<td><p>Errores de suscripción de presencia</p></td>
<td><p>Número de errores para suscribir presencia</p></td>
</tr>
<tr class="odd">
<td><p>Registro de errores de punto de conexión</p></td>
<td><p>Número de errores para registrar los extremos</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes recibidas/segundo</p></td>
<td><p>Ratio por segundo de solicitudes recibidas</p></td>
</tr>
<tr class="odd">
<td><p>Solicitudes correctas/segundo</p></td>
<td><p>Tasa por segundo de solicitudes correctas (códigos de respuesta HTTP 2xx/3xx)</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes de aplicación creadas correctamente/segundo</p></td>
<td><p>Tasa por segundo de solicitudes de creación de aplicaciones correctas</p></td>
</tr>
<tr class="odd">
<td><p>Recuento de peticiones GET pendientes de tiempo de espera agotado</p></td>
<td><p>El número de Get pendientes que agotaron el tiempo de espera</p></td>
</tr>
<tr class="even">
<td><p>Total de solicitudes de creación de aplicaciones recibidas</p></td>
<td><p>Número total de solicitudes de creación de aplicaciones recibidas desde que se inició el servicio</p></td>
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
<td><p>Total de solicitudes recibidas en el canal de comandos</p></td>
<td><p>Número total de solicitudes recibidas en el canal de comandos</p></td>
</tr>
<tr class="even">
<td><p>Solicitudes correctas totales</p></td>
<td><p>Número total de solicitudes que se realizaron correctamente</p></td>
</tr>
<tr class="odd">
<td><p>Total de sesiones iniciadas</p></td>
<td><p>El número total de sesiones que se iniciaron desde que se inició el servicio</p></td>
</tr>
<tr class="even">
<td><p>Total de sesiones finalizadas por un tiempo de espera inactivo</p></td>
<td><p>Número total de sesiones que han finalizado porque se ha agotado el tiempo de espera de inactividad del usuario</p></td>
</tr>
<tr class="odd">
<td><p>Total de aplicaciones limitadas</p></td>
<td><p>El número de aplicaciones limitadas</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Contadores de rendimiento para el servicio de movilidad de MCX

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Counter</th>
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
<td><p>Número actual de suscripciones de notificación de inserción. Este número, junto con el recuento de sesiones actualmente activas, representa el subconjunto de las sesiones actualmente activas registradas para dispositivos Windows Mobile o iPhone.</p></td>
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
<td><p>Solicitudes correctas totales</p></td>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

