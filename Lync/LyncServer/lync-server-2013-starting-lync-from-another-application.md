---
title: Inicio de Lync 2010 desde otra aplicación
TOCTitle: Inicio de Lync 2010 desde otra aplicación
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398376(v=OCS.15)
ms:contentKeyID: 52061640
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Inicio de Lync 2010 desde otra aplicación

 

_**Última modificación del tema:** 2015-03-09_

Puede usar parámetros de la línea de comandos para iniciar rápidamente Lync 2013. Por ejemplo, si un usuario hace clic en un número de teléfono de otra aplicación, la aplicación puede iniciar una instancia de Lync 2013 y realizar una llamada a dicho número.

Lync 2013 puede también reconocer listas de nombres de contactos delimitados por punto y coma para conferencias entre varias partes.

Si Lync 2013 está configurado para iniciar sesión automáticamente al iniciarse, entonces al iniciar Lync 2013 con parámetros de la línea de comandos se abrirá la ventana principal de Lync. Si Lync no está configurado para iniciar sesión automáticamente al iniciarse, se abrirá la ventana de inicio de sesión.

En la tabla siguiente se muestran los parámetros disponibles.

### Parámetros de la línea de comandos de Lync 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Extensión</th>
<th>Formato de datos</th>
<th>Acción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>tel:</p></td>
<td><p>URI de tel.</p></td>
<td><p>Abre la ventana Conversación para una llamada de audio pero no marca el número especificado.</p></td>
</tr>
<tr class="even">
<td><p>callto:</p></td>
<td><p>tel:, sip: o URL de tel que se puede editar</p></td>
<td><p>Abre la ventana Conversación para una llamada de audio pero no marca el número especificado.</p></td>
</tr>
<tr class="odd">
<td><p>sip:</p></td>
<td><p>URI del SIP</p></td>
<td><p>Abra la ventana Conversación con el Identificador uniforme de recursos (URI) del SIP especificado en la lista de participantes.</p></td>
</tr>
<tr class="even">
<td><p>Sips:</p></td>
<td><p>URI del SIP</p></td>
<td><p>Si Lync 2013 está configurado para usar el protocolo de seguridad de la capa de transporte (TLS), funciona exactamente igual que sip:. Si no está usando TLS, muestra un cuadro de diálogo para informar al usuario de que se requiere un nivel de seguridad más alto.</p></td>
</tr>
<tr class="odd">
<td><p>conf:</p></td>
<td><p>URI del SIP de la conferencia a la que se va a unir</p></td>
<td><p>Si el URI es automático, crea instancias del foco y solo abre una vista de la lista. En caso contrario, abre una vista de la lista pero no envía INVITE.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>im:</p></td>
<td><p>URI del SIP</p></td>
<td><p>Muestra la ventana Conversación solo de mensajería instantánea con el URI del SIP. Acepta varios URI del SIP especificados entre corchetes angulares de apertura y cierre (&lt;&gt;) sin ningún separador.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


En la tabla siguiente se proporcionan ejemplos de estos parámetros de línea de comandos.

### Ejemplos de parámetros de línea de comandos

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Instancia</th>
<th>Resultados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel:+14255550101</p></td>
<td><p>Abre una vista de solo teléfonos con +14255550101.</p></td>
</tr>
<tr class="even">
<td><p>Callto:tel:+ 14255550101</p></td>
<td><p>Abre una vista de solo teléfonos con +14255550101.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Abre una vista de solo teléfonos con kazuto@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Abre una ventana Conversación con kazuto@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p>conf:sip:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Abre una ventana Conversación y muestra las opciones para unirse a audio de reunión.</p></td>
</tr>
</tbody>
</table>

