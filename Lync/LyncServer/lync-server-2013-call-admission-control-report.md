---
title: 'Lync Server 2013: Informe de control de admisión de llamadas'
TOCTitle: Informe de control de admisión de llamadas
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48277059
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de control de admisión de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El Informe de control de admisión de llamadas ofrece información sobre las sesiones de punto a punto y de conferencia que se han llevado a cabo con restricciones definidas por el Control de admisión de llamadas. El Control de admisión de llamadas, incorporado en Microsoft Lync Server 2010, proporciona a los administradores la forma de permitir (o no) las sesiones de comunicación en función de las restricciones del ancho de banda. Por ejemplo, los administradores pueden crear directivas que impongan un límite a la cantidad de ancho de banda disponible para las llamadas de voz y vídeo. Si se alcanza ese límite de ancho de banda, no se podrán realizar nuevas llamadas de voz o vídeo hasta que finalice alguna de las llamadas en curso y se liberen los recursos de red necesarios.

## Acceso al Informe de control de admisión de llamadas

Al Informe de control de admisión de llamadas se accede desde la página de inicio de Informes de supervisión. Desde el Informe de control de admisión de llamadas, puede acceder a cualquiera de los informes siguientes:

  - Informe de detalles de conferencia: Para acceder a este informe, hada clic en la métrica Detalles desde una sesión de conferencia.

  - Informe de detalles de sesiones punto a punto: Para acceder a este informe, haga clic en la métrica Detalles desde una sesión punto a punto.

## Cómo hacer el mejor uso del Informe de control de admisión de llamadas

Para obtener una lista de las llamadas que no se han podido completar correctamente porque el ancho de banda no era suficiente, seleccione Llamadas rechazadas debido al control de admisión de llamadas en la lista desplegable Categoría de llamada. La mayoría de las llamadas devueltas presentarán seguramente el identificador de diagnóstico 5:

Ancho de banda insuficiente para establecer la sesión. Intente volver a enrutar la llamada a través de RTC.

Este mensaje indica que las limitaciones del Control de admisión de llamadas impidió que la llamada se realizara en la red VoIP.

## Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el Informe de control de admisión de llamadas le permite filtrar llamadas por el usuario que inicia la llamada o por el usuario que recibe la llamada. También puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.

En la tabla siguiente se muestran los filtros que se pueden utilizar con el Informe de control de admisión de llamadas

### Filtros del Informe de control de admisión de llamadas

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Desde</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</p>
<p>17/7/2012 13:00</p>
<p>Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 00:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>17/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>13/7/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hasta</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</p>
<p>17/7/2012 13:00</p>
<p>Si no escribe una hora de finalización, el informe finalizará automáticamente a las 00:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>17/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>13/7/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Grupo de servidores</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de actividad</strong></p></td>
<td><p>Tipo de actividad. Seleccione una de las siguientes actividades:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Punto a punto</p></li>
<li><p>Conferencia</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Categoría de llamada</strong></p></td>
<td><p>Indica el motivo por el que se usó el control de admisión de llamadas para la llamada. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Llamada rechazada debido al control de admisión de llamadas</p></li>
<li><p>Llamadas que se han vuelto a enrutar a través de RTC debido al control de admisión de llamadas</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Métricas de las sesiones punto a punto

En la siguiente tabla se muestra la información proporcionada por el Informe del control de admisión de llamadas para las sesiones punto a punto (es decir, sesiones entre solo dos participantes).

### Métricas de las sesiones punto a punto

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>¿Se pueden ordenar los datos por este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Detalle</strong></p></td>
<td><p>N.º</p></td>
<td><p>Cuando se hace clic en este elemento, el informe muestra un informe detallado de sesión punto a punto de la sesión específica.</p></td>
</tr>
<tr class="even">
<td><p><strong>Remitente</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dirección SIP del usuario que inició la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Destinatario</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dirección SIP del usuario al que se invitó a unirse a la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalidades</strong></p></td>
<td><p>Sí</p></td>
<td><p>Modalidades de comunicación (como audio y vídeo) que se usaron durante la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de invitación</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que se envió al remitente la invitación a la sesión inicial.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tiempo de respuesta</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que se recibió la aceptación de la invitación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de finalización</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que finalizó la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>Sí</p></td>
<td><p>Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.</p></td>
</tr>
</tbody>
</table>


## Métricas de las sesiones de conferencia

En la siguiente tabla se muestra información proporcionada en el Informe de control de admisión de llamadas para las sesiones de conferencia (es decir, sesiones con tres o más participantes).

### Métricas de las sesiones de conferencia

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>¿Se pueden ordenar los datos por este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>URI de conferencia</strong></p></td>
<td><p>Sí</p></td>
<td><p>Identificador único de la conferencia. Cuando se hace clic en este elemento, el informe muestra los participantes individuales de la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizador</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dirección SIP del usuario que organizó la conferencia</p></td>
</tr>
<tr class="odd">
<td><p><strong>Grupo de servidores</strong></p></td>
<td><p>Sí</p></td>
<td><p>Servidor perimetral usado en la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de inicio</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que comenzó la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de finalización</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que la conferencia finalizó.</p></td>
</tr>
</tbody>
</table>


## Métricas de participantes en conferencias individuales

En la siguiente tabla se muestra la información proporcionada en el Informe de control de admisión de llamadas sobre participantes en conferencias individuales.

### Métricas de participantes en conferencias individuales

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>¿Se pueden ordenar los datos por este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Rol</strong></p></td>
<td><p>N.º</p></td>
<td><p>Rol (por ejemplo, Moderador) que ocupó el participante de la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Participante</strong></p></td>
<td><p>N.º</p></td>
<td><p>Dirección SIP del participante de la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Conectividad</strong></p></td>
<td><p>N.º</p></td>
<td><p>Conectividad de red (normalmente Desde conexión interna o Desde conexión externa) del participante.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalidad</strong></p></td>
<td><p>N.º</p></td>
<td><p>Tipo de conferencia (por ejemplo, conferencia A/V).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de conexión</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha y hora en que el participante se unió a la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de desconexión</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha y hora en que el participante abandonó la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>N.º</p></td>
<td><p>Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.</p></td>
</tr>
</tbody>
</table>

