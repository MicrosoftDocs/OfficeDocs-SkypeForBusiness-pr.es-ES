---
title: Interpretación de los resultados
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3a15880de861b850d3e0355491e85219ba3579d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499917"
---
# <a name="interpreting-the-results"></a>Interpretación de los resultados

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

La herramienta stress and Performance (LyncPerfTool.exe) de Lync Server 2013 tiene muchos contadores que puede usar para comprender lo que hace el cliente y si se encuentra con problemas.

<div>

## <a name="client-counters"></a>Contadores del cliente

Cada instancia de LyncPerfTool.exe que se ejecuta tiene una instancia independiente de los contadores. Cada instancia se nombra mediante su identificador de proceso.

Si los clientes están sobrecargados, pueden producirse problemas. Para evitar estos problemas, haga lo siguiente:

1.  Supervise la CPU y el uso de memoria en los equipos cliente. Si la CPU es constantemente superior al 90 por ciento, reduzca el número de usuarios.

2.  Si el tamaño de la memoria es alto, puede tener problemas si el archivo de paginación no es lo suficientemente grande. Compruebe que la carga de asignación no alcanza el límite del equipo. Si está teniendo en cuenta los límites de memoria, considere la posibilidad de aumentar el tamaño del archivo de paginación o reducir el número de usuarios.

En las tablas siguientes se enumeran los contadores de rendimiento LyncPerfTool clave.

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
<td><p>Número de extremos conectados actualmente al servidor.</p></td>
</tr>
<tr class="odd">
<td><p>Inicios de sesión con errores</p></td>
<td><p>Número total de errores de inicio de sesión de extremo.</p></td>
</tr>
<tr class="even">
<td><p>Intentos de inicio de sesión</p></td>
<td><p>Número total de intentos de inicio de sesión en el extremo.</p></td>
</tr>
<tr class="odd">
<td><p>Extremos desconectados</p></td>
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
<td><p>Llamadas SetPresence</p></td>
<td><p>Número total de intentos de cambio de presencia. Para diferentes tipos de cambios de presencia, vea el contador de rendimiento de llamadas de SetPresence (tipo de presencia).</p></td>
</tr>
<tr class="even">
<td><p>NNN respuestas para SetPresence</p></td>
<td><p>Número total de los códigos de respuesta nnn recibidos desde el servidor.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas a GetPresence</p></td>
<td><p>Número total de intentos de obtener solicitud de presencia.</p></td>
</tr>
<tr class="even">
<td><p>NNN respuestas para GetPresence</p></td>
<td><p>Número total de los códigos de respuesta nnn recibidos desde el servidor.</p></td>
</tr>
</tbody>
</table>


**Información del servicio de libreta de direcciones**

En esta categoría se incluyen los contadores usados para supervisar las solicitudes de servicio de descarga de archivos del servicio de libreta de direcciones (ABS) y de la libreta de direcciones web de consultas.


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
<td><p>Intento de descarga de archivo completo/Delta de ABS</p></td>
<td><p>Número total de solicitudes de descarga de archivos completos o delta que se intentaron.</p></td>
</tr>
<tr class="even">
<td><p>Descargas de archivos completos/Delta de ABS correctamente</p></td>
<td><p>Número total de solicitudes de descarga de archivos completos o delta que se intentaron.</p></td>
</tr>
<tr class="odd">
<td><p>Contadores relacionados con el servicio de consulta Web de libreta de direcciones</p></td>
<td><p>Descarga de archivos de la libreta de direcciones: contadores relacionados.</p></td>
</tr>
<tr class="even">
<td><p>Intentos de llamadas de ABS WS</p></td>
<td><p>Número total de solicitudes de servicio de consulta Web de libreta de direcciones que se intentaron.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas de ABS WS correctas</p></td>
<td><p>Número total de solicitudes de servicio de consulta Web de libreta de direcciones que devolvieron un código de respuesta correcto.</p></td>
</tr>
<tr class="even">
<td><p>Error en las llamadas de ABS WS</p></td>
<td><p>Número total de solicitudes de servicio de consulta Web de libreta de direcciones que devolvieron un código de respuesta de error.</p></td>
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
<td><p>Número total de solicitudes de servicio Web de expansión de la lista de distribución (DLX) que se intentaron.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas correctas</p></td>
<td><p>Número total de solicitudes de servicio Web de DLX que devolvieron un código de respuesta correcto.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas fallidas</p></td>
<td><p>Número total de solicitudes de servicio Web de DLX que devolvieron un código de respuesta de error.</p></td>
</tr>
</tbody>
</table>


**Información básica de VoIP**

Los contadores de rendimiento que se enumeran a continuación para todas las llamadas de voz sobre IP (VoIP), incluidas las llamadas a servidor de mediación, el servidor de conferencia A/V, el servidor perimetral, la aplicación de grupo de respuesta y el operador automático de conferencia, cuando estos escenarios están habilitados.


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
<td><p>Número total de llamadas de voz entrantes y salientes ya finalizadas.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas rechazadas</p></td>
<td><p>Número total de llamadas de voz entrantes rechazadas.</p></td>
</tr>
<tr class="even">
<td><p>Intentos de llamadas entrantes o salientes</p></td>
<td><p>Número total de llamadas de voz entrantes y salientes que se intentaron realizar.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas entrantes/salientes establecidas</p></td>
<td><p>Número total de llamadas de voz entrantes y salientes establecidas.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas recibidas NNN</p></td>
<td><p>Número total de los códigos de respuesta nnn recibidos desde el servidor.</p></td>
</tr>
<tr class="odd">
<td><p>Tasa de transferencia de VoIP (%)</p></td>
<td><p>Total de llamadas establecidas/total de llamadas intentadas.</p></td>
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
<td><p>Número total de llamadas activas a la aplicación del grupo de respuesta.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas intentadas</p></td>
<td><p>Número total de intentos de llamadas.</p></td>
</tr>
</tbody>
</table>


**Información de llamada de la mensajería instantánea (mi)**


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
<td><p>Número total de llamadas entrantes o salientes de mensajería instantánea en curso.</p></td>
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
<td><p>Mensajes de mensajería instantánea recibidos o enviados</p></td>
<td><p>Número total de mensajes recibidos o enviados para todas las sesiones.</p></td>
</tr>
<tr class="odd">
<td><p>Intentos de llamadas entrantes o salientes</p></td>
<td><p>Número total de llamadas entrantes o salientes de mensajería instantánea que se intentaron.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas entrantes/salientes establecidas</p></td>
<td><p>Número total de llamadas entrantes o salientes de mensajes instantáneos establecidas.</p></td>
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
<td><p>Número total de llamadas de uso compartido de aplicaciones entrantes o salientes en curso.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas finalizadas</p></td>
<td><p>Número total de llamadas entrantes o salientes de uso compartido de aplicaciones ya finalizadas.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas recibidas NNN</p></td>
<td><p>Número total de los códigos de respuesta nnn recibidos desde el servidor.</p></td>
</tr>
<tr class="even">
<td><p>Intentos de llamadas entrantes o salientes</p></td>
<td><p>Número total de llamadas de uso compartido de aplicaciones entrantes o salientes que se intentaron.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas entrantes/salientes establecidas</p></td>
<td><p>Número total de llamadas de uso compartido de aplicaciones entrantes/salientes establecidas.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**Información de llamada de CAA**


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
<td><p>Número total de llamadas RTC entrantes o salientes que ya han finalizado.</p></td>
</tr>
<tr class="odd">
<td><p>Intentos de llamadas entrantes o salientes</p></td>
<td><p>Número total de llamadas RTC entrantes o salientes que se intentaron.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas entrantes/salientes establecidas</p></td>
<td><p>Número total de llamadas RTC entrantes y salientes establecidas.</p></td>
</tr>
</tbody>
</table>


**Información de conferencia**


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
<td><p>Número total de conferencias de audio/vídeo (A/V) en curso.</p></td>
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
<td><p>Error de programación de conferencia</p></td>
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
<td><p>Número total de combinaciones IMMCU correctas</p></td>
<td><p>Número total de conferencias de mensajería instantánea Unidas.</p></td>
</tr>
<tr class="even">
<td><p>Número total de combinaciones DMCU correctas</p></td>
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

