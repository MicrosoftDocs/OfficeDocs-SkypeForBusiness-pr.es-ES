---
title: Interpretación de los resultados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dcb1d84392cf9f56f2996281eb53e798690ba1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>Interpretación de los resultados

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

La herramienta Lync Server 2013 stress and Performance (LyncPerfTool. exe) tiene muchos contadores que puede usar para comprender lo que hace el cliente y si se están encontrando problemas.

<div>

## <a name="client-counters"></a>Contadores de cliente

Cada instancia de LyncPerfTool. exe que se está ejecutando tiene una instancia independiente de los contadores. Cada instancia se denomina mediante su identificador de proceso.

Si los clientes están sobrecargados, pueden producirse problemas. Para evitar estos problemas, haga lo siguiente:

1.  Supervise la CPU y el uso de memoria en los equipos cliente. Si la CPU es sistemática por encima del 90 por ciento, reduzca el número de usuarios.

2.  Si el tamaño de la memoria es alto, puede tener problemas si el archivo de paginación no es lo suficientemente grande. Compruebe que el cargo de asignación no haya alcanzado el límite en el equipo. Si se encuentran límites de memoria, considere la posibilidad de aumentar el tamaño del archivo de paginación o reducir el número de usuarios.

En las siguientes tablas se enumeran los contadores de rendimiento de LyncPerfTool clave.

**Información general**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de rendimiento</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tiempo invertido en minutos</p></td>
<td><p>Tiempo transcurrido desde que se inició el proceso.</p></td>
</tr>
<tr class="even">
<td><p>Puntos de conexión activos</p></td>
<td><p>Número de puntos finales conectados actualmente al servidor.</p></td>
</tr>
<tr class="odd">
<td><p>Inicios de sesión erróneos</p></td>
<td><p>Número total de errores de inicio de sesión de extremo.</p></td>
</tr>
<tr class="even">
<td><p>Intentos de inicio de sesión</p></td>
<td><p>Número total de intentos de inicio de sesión de punto final.</p></td>
</tr>
<tr class="odd">
<td><p>Puntos de conexión desconectados</p></td>
<td><p>Número total de puntos de conexión que se han desconectado.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**Información de presencia**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de rendimiento</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas de SetPresence</p></td>
<td><p>Número total de intentos de cambio de presencia. Para los distintos tipos de cambios de presencia, vea el contador de rendimiento llamadas de SetPresence (tipo de presencia).</p></td>
</tr>
<tr class="even">
<td><p>NNN respuestas para SetPresence</p></td>
<td><p>Número total de los códigos de respuesta nnn recibidos desde el servidor.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas a GetPresence</p></td>
<td><p>Número total de intentos de solicitud de presencia.</p></td>
</tr>
<tr class="even">
<td><p>NNN respuestas para GetPresence</p></td>
<td><p>Número total de los códigos de respuesta nnn recibidos desde el servidor.</p></td>
</tr>
</tbody>
</table>


**Información del servicio de libreta de direcciones**

Esta categoría incluye los contadores usados para supervisar las solicitudes de servicio de descargas de archivos del servicio de libreta de direcciones (ABS) y la libreta de direcciones web de la libreta de direcciones.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de rendimiento</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Intento de descarga de archivos completo/Delta de ABS</p></td>
<td><p>Número total de solicitudes de descarga de archivos completas o delta intentadas.</p></td>
</tr>
<tr class="even">
<td><p>Descarga de archivo completo/Delta de ABS correctamente</p></td>
<td><p>Número total de solicitudes de descarga de archivos completas o delta intentadas.</p></td>
</tr>
<tr class="odd">
<td><p>Contadores relacionados con el servicio de la libreta de direcciones</p></td>
<td><p>Descarga de archivos de la libreta de direcciones.</p></td>
</tr>
<tr class="even">
<td><p>Intentos de llamadas de ABS WS</p></td>
<td><p>Número total de solicitudes de servicio de consulta Web de la libreta de direcciones intentadas.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas ABS WS correctas</p></td>
<td><p>Número total de solicitudes de servicio de consulta Web de la libreta de direcciones que devolvieron un código de respuesta correcto.</p></td>
</tr>
<tr class="even">
<td><p>Error en las llamadas de ABS WS</p></td>
<td><p>Número total de solicitudes de servicio de consulta Web de la libreta de direcciones que devolvieron un código de respuesta de error.</p></td>
</tr>
</tbody>
</table>


**Información de la lista de distribución (DL)**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de rendimiento</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas intentadas</p></td>
<td><p>Número total de solicitudes de servicio Web de expansión de la lista de distribución (DLX) intentadas.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas correctas</p></td>
<td><p>Número total de solicitudes de servicio Web de DLX que devolvieron un código de respuesta satisfactorio.</p></td>
</tr>
<tr class="odd">
<td><p>Error en las llamadas</p></td>
<td><p>Número total de solicitudes de servicio Web de DLX que devolvieron un código de respuesta de error.</p></td>
</tr>
</tbody>
</table>


**Información básica de VoIP**

Los contadores de rendimiento que aparecen a continuación indican números para todas las llamadas de voz a través de IP (VoIP), incluidas las llamadas a servidor de mediación, el servidor de conferencia a/V, el servidor perimetral, la aplicación de grupo de respuesta y el operador automático de conferencia, cuando se habilitan estos escenarios.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de rendimiento</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas activas</p></td>
<td><p>Número total de llamadas de voz entrantes y salientes actualmente en curso.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas finalizadas</p></td>
<td><p>Número total de llamadas de voz entrantes y salientes que ya han finalizado.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas rechazadas</p></td>
<td><p>Número total de llamadas de voz entrantes rechazadas.</p></td>
</tr>
<tr class="even">
<td><p>Intentos de llamadas entrantes y salientes</p></td>
<td><p>Número total de llamadas de voz entrantes y salientes intentadas.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas entrantes y salientes establecidas</p></td>
<td><p>Número total de llamadas de voz entrantes y salientes establecidas.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas recibidas NNN</p></td>
<td><p>Número total de los códigos de respuesta nnn recibidos desde el servidor.</p></td>
</tr>
<tr class="odd">
<td><p>Tasa de transferencia de VoIP (%)</p></td>
<td><p>Llamadas totales establecidas/llamadas totales realizadas.</p></td>
</tr>
</tbody>
</table>


**Información de llamada del servicio de grupo de respuesta**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de rendimiento</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas activas</p></td>
<td><p>Número total de llamadas activas a la aplicación de grupo de respuesta.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas intentadas</p></td>
<td><p>Número total de intentos de llamada.</p></td>
</tr>
</tbody>
</table>


**Información de la llamada de mensajería instantánea (mi)**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de rendimiento</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas activas</p></td>
<td><p>Número total de llamadas entrantes y salientes de mensajería instantánea en curso.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas finalizadas</p></td>
<td><p>Número total de llamadas de mensajería instantánea entrantes o salientes que ya han finalizado.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas recibidas NNN</p></td>
<td><p>Número total de los códigos de respuesta nnn recibidos desde el servidor.</p></td>
</tr>
<tr class="even">
<td><p>Mensajes INSTANTÁNEos recibidos/enviados</p></td>
<td><p>Número total de mensajes recibidos o enviados para todas las sesiones.</p></td>
</tr>
<tr class="odd">
<td><p>Intentos de llamadas entrantes y salientes</p></td>
<td><p>Número total de intentos de llamadas entrantes y salientes de mensajes instantáneos.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas entrantes y salientes establecidas</p></td>
<td><p>Número total de llamadas de mensajes instantáneos entrantes o salientes que se han establecido.</p></td>
</tr>
</tbody>
</table>


**Información de llamadas de uso compartido de aplicaciones**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de rendimiento</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas activas</p></td>
<td><p>Número total de llamadas de uso compartido de aplicaciones entrantes y salientes en curso.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas finalizadas</p></td>
<td><p>Número total de llamadas de uso compartido de aplicaciones entrantes o salientes que ya se han finalizado.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas recibidas NNN</p></td>
<td><p>Número total de los códigos de respuesta nnn recibidos desde el servidor.</p></td>
</tr>
<tr class="even">
<td><p>Intentos de llamadas entrantes y salientes</p></td>
<td><p>Número total de llamadas de uso compartido de aplicaciones entrantes o salientes.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas entrantes y salientes establecidas</p></td>
<td><p>Número total de llamadas de uso compartido de aplicaciones entrantes o salientes establecidas.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**Información de la llamada de CAA**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de rendimiento</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas activas</p></td>
<td><p>Número total de llamadas de red telefónica conmutada (RTC) entrantes y salientes actualmente en curso.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas finalizadas</p></td>
<td><p>Número total de llamadas RTC entrantes y salientes que ya se han finalizado.</p></td>
</tr>
<tr class="odd">
<td><p>Intentos de llamadas entrantes y salientes</p></td>
<td><p>Número total de intentos de llamadas RTC entrantes y salientes.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas entrantes y salientes establecidas</p></td>
<td><p>Número total de llamadas RTC entrantes y salientes establecidas.</p></td>
</tr>
</tbody>
</table>


**Información sobre la Conferencia**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de rendimiento</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Conferencias de mensajería instantánea activas</p></td>
<td><p>Número total de conferencias de mensajería instantánea en curso.</p></td>
</tr>
<tr class="even">
<td><p>Conferencias de audio y vídeo activas</p></td>
<td><p>Número total de conferencias de audio o vídeo (A/V) en curso.</p></td>
</tr>
<tr class="odd">
<td><p>Conferencias de uso compartido de aplicaciones activas</p></td>
<td><p>Número total de conferencias de uso compartido de aplicaciones en curso.</p></td>
</tr>
<tr class="even">
<td><p>Número de participantes</p></td>
<td><p>Número total de participantes actualmente conectados a conferencias.</p></td>
</tr>
<tr class="odd">
<td><p>Error de programación en Conferencia</p></td>
<td><p>Número total de errores al intentar programar una conferencia.</p></td>
</tr>
<tr class="even">
<td><p>Error al unirse a la Conferencia</p></td>
<td><p>Número total de errores al intentar conectarse a una conferencia.</p></td>
</tr>
</tbody>
</table>


**Contadores de cliente de UCWA**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de rendimiento</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Número total de combinaciones de IMMCU correctas</p></td>
<td><p>Número total de conferencias de mensajería instantánea combinadas.</p></td>
</tr>
<tr class="even">
<td><p>Número total de combinaciones de DMCU correctas</p></td>
<td><p>Número total de conferencias A/V combinadas.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

