﻿---
title: 'Lync Server 2013: Informe de detalles de sesiones punto a punto'
TOCTitle: Informe de detalles de sesiones punto a punto
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48275569
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de detalles de sesiones punto a punto en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El informe de detalles de sesiones punto a punto devuelve información detallada sobre una sesión punto a punto. Por ejemplo, si selecciona una sesión de mensajería instantánea, el informe reflejará el número de mensajes enviado por cada usuario durante la sesión.

## Acceso al informe de detalles de sesiones punto a punto

Se puede acceder al informe de detalles de sesiones punto a punto desde cualquiera de los siguientes informes (todos se encuentran en la página principal de informes de supervisión):

  - Informe de inventario de teléfono IP

  - Informe de actividad de usuario

  - Informe de control de admisión de llamadas

  - Informe de lista de errores

Desde el informe de detalles de sesiones punto a punto se puede acceder al [Informe de diagnósticos en Lync Server 2013](lync-server-2013-diagnostic-report.md); para ello, solo hay que hacer clic en la métrica de informe de diagnóstico (detalles). También se puede acceder al informe de errores principales haciendo clic en cualquiera de estas dos métricas:

  - Respuesta

  - Id. de diagnóstico

## Usar el informe de detalles de sesiones punto a punto de la mejor forma posible

El informe de detalles de sesiones punto a punto condensa un gran número de métricas, de las cuales probablemente muchas no sean muy conocidas para los administradores de sistema. No obstante, muchas veces se puede acceder a información sobre herramientas en la que se ofrece una breve descripción de la métrica; para ello, basta con mantener el mouse encima de la etiqueta de la métrica.

Recuerde que las métricas reales que aparecen reflejadas en un informe determinado dependerán del tipo de sesión punto a punto seleccionado. Así, las métricas de una sesión de audio/vídeo serán distintas de las de una sesión de mensajería instantánea.

El mouse también se puede mantener sobre las métricas Código de respuesta e Id. de diagnóstico para obtener una descripción de dichos valores:

## Filtros

Ninguno. El informe de detalles de sesiones punto a punto no se puede filtrar.

## Métricas de información de la sesión

En la siguiente tabla se recoge la información que el informe de detalles de sesiones punto a punto proporciona sobre cada sesión.

### Métricas de información de la sesión

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
<td><p><strong>FQDN del grupo de servidores</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de registrador o servidor perimetral involucrado en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de invitación</strong></p></td>
<td><p>Fecha y hora en que se envió inicialmente la invitación a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tiempo de respuesta</strong></p></td>
<td><p>Fecha y hora en que se recibió la aceptación de la invitación.</p></td>
</tr>
<tr class="even">
<td><p><strong>Remitente</strong></p></td>
<td><p>Dirección SIP del usuario que inició la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente de remitente</strong></p></td>
<td><p>Software usado por el extremo del usuario que inició la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>¿Es el remitente interno?</strong></p></td>
<td><p>Indica si el usuario que inició la sesión estaba conectado a la red interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>¿Tiene el remitente un teléfono de escritorio integrado?</strong></p></td>
<td><p>Indica si el extremo que utilizó el usuario que inició sesión está integrado en su teléfono de escritorio integrado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prioridad de sesión</strong></p></td>
<td><p>Prioridad asignada a la sesión. Entre las propiedades válidas se encuentran Desconocido, No urgente, Normal, Urgente y Emergencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Código de respuesta</strong></p></td>
<td><p>Código de respuesta SIP enviado cuando se produjo un error en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Front-end</strong></p></td>
<td><p>Nombre del servidor front-end que se usó en la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de captura</strong></p></td>
<td><p>Fecha y hora en que se registró la información de la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de finalización</strong></p></td>
<td><p>Fecha y hora en que la sesión finalizó.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Destinatario</strong></p></td>
<td><p>Dirección SIP del usuario invitado a la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente de destinatario</strong></p></td>
<td><p>Software utilizado por el extremo del usuario invitado a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>¿Es el destinatario interno?</strong></p></td>
<td><p>Indica si el usuario invitado a la sesión estaba conectado a la red interna.</p></td>
</tr>
<tr class="even">
<td><p><strong>¿Tiene el destinatario un teléfono de escritorio integrado?</strong></p></td>
<td><p>Indica si el extremo que utilizó el usuario invitado a la sesión está integrado en su teléfono de escritorio integrado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>¿Es un reintento de sesión?</strong></p></td>
<td><p>Indica si se trata de un reintento de una sesión que no se pudo iniciar correctamente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>Identificador único (en forma de encabezado de tipo ms-diagnostics) que se adjunta a un mensaje SIP y que suele ofrecer información de utilidad para resolver errores. Mantenga el mouse encima del número del identificador para ver más información al respecto.</p></td>
</tr>
</tbody>
</table>


## Métricas de modalidades

En la siguiente tabla se recoge la información que el informe de detalles de sesiones punto a punto proporciona sobre cada modalidad de sesión.

### Métricas de modalidades

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
<td><p><strong>Modalidades</strong></p></td>
<td><p>N.º</p></td>
<td><p>Modalidades usadas en la sesión (por ejemplo, mensajería instantánea o transferencia de archivos).</p></td>
</tr>
<tr class="even">
<td><p><strong>Mensajes del remitente</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número de mensajes que envió el usuario que inició la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Mensajes del destinatario</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número de mensajes que envió el usuario invitado a unirse a la sesión.</p></td>
</tr>
</tbody>
</table>


## Métricas de informes de diagnóstico

En la siguiente tabla se recoge la información que el informe de detalles de sesiones punto a punto proporciona sobre cada informe de diagnóstico.

### Métricas de informes de diagnóstico

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
<td><p>Cuando se hace clic en este elemento, el informe muestra el informe de diagnóstico correspondiente a la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora del informe</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha y hora en que se registró el informe.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Solicitud</strong></p></td>
<td><p>N.º</p></td>
<td><p>Tipo de solicitud SIP (por ejemplo, INVITE o BYE).</p></td>
</tr>
<tr class="even">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>N.º</p></td>
<td><p>Identificador único (con formato de encabezado ms-diagnostics) que se adjunta a un mensaje SIP y que suele ofrecer información útil para solucionar errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de contenido</strong></p></td>
<td><p>N.º</p></td>
<td><p>Tipo de contenido multimedia usado en la conferencia (por ejemplo, un tipo de contenido bastante habitual es Application/sdp). El protocolo SDP es un protocolo de Internet estándar que se usa en anuncios de sesiones, invitaciones a sesiones y otras formas de inicio de sesiones multimedia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Informe realizado por</strong></p></td>
<td><p>N.º</p></td>
<td><p>Equipo (cliente o servidor) que notificó el problema.</p></td>
</tr>
</tbody>
</table>

