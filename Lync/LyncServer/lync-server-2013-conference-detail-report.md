---
title: Informe de detalles de conferencia
TOCTitle: Informe de detalles de conferencia
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48274623
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de detalles de conferencia

 

_**Última modificación del tema:** 2015-03-09_

El Informe de detalles de conferencia proporciona información detallada sobre todos los usuarios que participaron en una conferencia. Por ejemplo, puede ver información como la fecha y hora en que un usuario se conectó a la conferencia, la fecha y hora en la que el usuario se desconectó de la conferencia y el agente del usuario del extremo que se utilizó para conectar a ese usuario a la conferencia. También puede ver información sobre el rol del usuario en cada conferencia (por ejemplo, moderador o asistente). Quizás lo más importante, puede ver rápidamente qué usuarios se conectan satisfactoriamente y finalizan la conferencia y qué usuarios no pudieron conectarse satisfactoriamente ni finalizar la conferencia.

## Acceso al Informe de detalles de conferencia

Es posible acceder al Informe de detalles de conferencia a partir de los siguientes informes:

  - El [Informe de control de admisión de llamadas en Lync Server 2013](lync-server-2013-call-admission-control-report.md) (haciendo clic en la métrica Detalle de una conferencia)

  - El [Informe de lista de errores en Lync Server 2013](lync-server-2013-failure-list-report.md) (haciendo clic en la métrica Conferencia)

  - El [Informe de actividad de usuario en Lync Server 2013](lync-server-2013-user-activity-report.md) (haciendo clic en la métrica URI de conferencia)

Desde el Informe de detalles de conferencia, puede acceder al [Informe de diagnósticos en Lync Server 2013](lync-server-2013-diagnostic-report.md) haciendo clic en la métrica Informe de diagnósticos (Detalle).

## Filtros

Ninguno. No se puede filtrar el Informe de detalles de conferencia.

## Métricas

La siguiente tabla muestra la información brindada en la sección Información de conferencia del Informe de detalles de conferencia.

### Métricas de Información de conferencia

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
<td><p></p></td>
<td><p>URI asignado a la conferencia. Por ejemplo:</p>
<p>sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDN del grupo de servidores</strong></p></td>
<td><p></p></td>
<td><p>Nombre de dominio completo del grupo de registrador o servidor perimetral involucrado en una sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de inicio</strong></p></td>
<td><p></p></td>
<td><p>Fecha y hora en que comenzó la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizador</strong></p></td>
<td><p></p></td>
<td><p>Dirección SIP del usuario que organizó la conferencia</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de finalización</strong></p></td>
<td><p></p></td>
<td><p>Fecha y hora en que finalizó la conferencia.</p></td>
</tr>
</tbody>
</table>


La siguiente tabla muestra la información brindada en la sección Participación de conferencia del Informe de detalles de conferencia.

### Métricas de Participación de conferencia

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
<td><p><strong>Usuario</strong></p></td>
<td><p></p></td>
<td><p>Dirección SIP del usuario que participó en la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rol</strong></p></td>
<td><p></p></td>
<td><p>Rol (por ejemplo, Moderador) que ocupó el participante de la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Conectividad</strong></p></td>
<td><p></p></td>
<td><p>Conectividad de red (normalmente Desde conexión interna o Desde conexión externa) del participante.</p></td>
</tr>
<tr class="even">
<td><p>Hora de conexión</p></td>
<td><p></p></td>
<td><p>Fecha y hora en que el participante se unió a la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de desconexión</strong></p></td>
<td><p></p></td>
<td><p>Fecha y hora en que el participante abandonó la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente de usuario</strong></p></td>
<td><p></p></td>
<td><p>Identificador del software del extremo del participante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Informes de diagnósticos</strong></p></td>
<td><p></p></td>
<td><p>Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.</p></td>
</tr>
</tbody>
</table>


La siguiente tabla muestra la información brindada en la sección Modalidades de conferencia del Informe de detalles de conferencia.

### Métricas de Modalidades de conferencia

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
<td><p><strong>Usuario</strong></p></td>
<td><p></p></td>
<td><p>Dirección SIP del usuario que participó en la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de conexión</strong></p></td>
<td><p></p></td>
<td><p>Fecha y hora en que el participante se unió a la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de desconexión</strong></p></td>
<td><p></p></td>
<td><p>Fecha y hora en que un participante abandonó la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI del servidor de conferencia</strong></p></td>
<td><p></p></td>
<td><p>URI para el servidor de conferencia utilizado en la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Informes de diagnósticos</strong></p></td>
<td><p></p></td>
<td><p>Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.</p></td>
</tr>
</tbody>
</table>

