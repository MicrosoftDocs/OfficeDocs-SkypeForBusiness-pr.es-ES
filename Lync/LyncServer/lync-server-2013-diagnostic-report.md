---
title: 'Lync Server 2013: Informe de diagnósticos'
TOCTitle: Informe de diagnósticos
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48276403
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de diagnósticos en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

El informe de diagnóstico ofrece información de diagnóstico y solución de problemas para las sesiones con errores. Esta información incluye el identificador de diagnóstico y el encabezado de diagnóstico que se notificaron cuando se produjo el error en la sesión. El identificador de diagnóstico es un identificador único (con formato de encabezado ms-diagnostics) que se adjunta a un mensaje SIP, mientras que el encabezado de diagnóstico proporciona una descripción que acompaña al identificador de diagnóstico. El informe también puede contener detalles valiosos sobre la solución de problemas conocidos por el componente del informe. Por ejemplo:

  - El código de causa proporcionado por la puerta de enlace RTC que generó el error. Cuando una llamada saliente presenta errores en la red RTC, se genera automáticamente un código de causa ISUP (ISDN User Part). Por ejemplo, una puerta de enlace RTC puede enviar un código de causa 34 para indicar que no hay ningún canal o circuito disponible para completar la llamada.

  - Errores de Winsock, puerto y FQDN del mismo nivel para detectar errores de conectividad.

  - Comprobación de nombres para detectar errores de resolución DNS. La resolución DNS tiene lugar cada vez que un cliente establece contacto con un servidor de nombres y solicita la dirección IP correspondiente al nombre de dispositivo especificado.

## Obtener acceso al informe de diagnóstico

Para obtener acceso al informe de diagnóstico, puede hacer clic en la métrica Informe de diagnóstico (detalle) en el [Informe de detalles de sesiones punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) o el informe de detalles de conferencia.

## Filtros

Ninguno. No se puede filtrar el informe de diagnóstico.

## Métricas

En la siguiente tabla se detalla la información proporcionada en el informe de diagnóstico para cada sesión.

### Métricas del informe de diagnóstico

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
<td><p><strong>Hora del informe</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha y hora en que se registró el informe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Código de respuesta</strong></p></td>
<td><p>N.º</p></td>
<td><p>Código de respuesta SIP enviado cuando se produjo un error en la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de solicitud</strong></p></td>
<td><p>N.º</p></td>
<td><p>Tipo de solicitud SIP que presentó errores. Por ejemplo, INVITE, BYE o SERVICE.</p></td>
</tr>
<tr class="even">
<td><p><strong>Origen</strong></p></td>
<td><p>N.º</p></td>
<td><p>Origen del error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI de remitente</strong></p></td>
<td><p>N.º</p></td>
<td><p>Dirección SIP del usuario que inició la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente de remitente</strong></p></td>
<td><p>N.º</p></td>
<td><p>Software usado por el extremo del usuario que inició la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>N.º</p></td>
<td><p>Identificador único (con formato de encabezado ms-diagnostics) que se adjunta a un mensaje SIP y que suele ofrecer información útil para solucionar errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de contenido</strong></p></td>
<td><p>N.º</p></td>
<td><p>Tipo de contenido multimedia que presentó errores. Un ejemplo de tipo de contenido habitual es Application/sdp. Session Description Protocol (SDP) es un protocolo estándar de Internet que se usa para anuncios e invitaciones de sesiones, y otras formas de iniciar sesiones multimedia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Aplicación</strong></p></td>
<td><p>N.º</p></td>
<td><p>Aplicación a la que corresponde el error.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI de destinatario</strong></p></td>
<td><p>N.º</p></td>
<td><p>Dirección SIP del usuario invitado a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p>Tiempo en unirse a conferencia (ms)</p></td>
<td><p>N.º</p></td>
<td><p>Cantidad de tiempo (en milisegundos) que tardó el usuario en unirse a la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Encabezado de diagnóstico</strong></p></td>
<td><p>N.º</p></td>
<td><p>Descripción del identificador de diagnóstico.</p></td>
</tr>
</tbody>
</table>


Encontrará una lista de errores de diagnóstico en la [página de encabezado Ms-Diagnostics](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).

