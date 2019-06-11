---
title: 'Lync Server 2013: Inicio de Lync desde otra aplicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e2d28a8083a7e7f1e693ddf55c5cfe3e758e96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>Iniciar Lync desde otra aplicación

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Puede usar parámetros de la línea de comandos para iniciar rápidamente Lync 2013. Por ejemplo, si un usuario hace clic en un número de teléfono de otra aplicación, la aplicación puede iniciar una instancia de Lync 2013 e iniciar una llamada a ese número.

Lync 2013 también puede reconocer una lista de nombres de contactos delimitados por punto y coma para las conferencias de varias partes.

Si Lync 2013 está configurado para iniciar sesión automáticamente al iniciarse, al iniciar Lync 2013 con parámetros de línea de comandos se abrirá la ventana principal de Lync. Si Lync no está configurado para iniciar sesión automáticamente al iniciarse, se abrirá la ventana de inicio de sesión.

En la tabla siguiente se muestran los parámetros disponibles.

### <a name="lync-2013-command-line-parameters"></a>Parámetros de la línea de comandos de Lync 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Extensiones</th>
<th>Formato de datos</th>
<th>Acción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel</p></td>
<td><p>URI de Tel</p></td>
<td><p>Abre la ventana de conversación de una llamada de audio, pero no marca el número especificado.</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>Tel:, SIP:, o URI de Tel.</p></td>
<td><p>Abre la ventana de conversación de una llamada de audio, pero no marca el número especificado.</p></td>
</tr>
<tr class="odd">
<td><p>SIP</p></td>
<td><p>URI del SIP</p></td>
<td><p>Abre la ventana de conversación con el identificador uniforme de recursos (URI) SIP especificado en la lista de participantes.</p></td>
</tr>
<tr class="even">
<td><p>SIPs</p></td>
<td><p>URI del SIP</p></td>
<td><p>Si Lync 2013 está configurado para usar el protocolo seguridad de la capa de transporte (TLS), funciona exactamente igual que SIP:. Si no se usa TLS, se muestra un cuadro de diálogo que informa al usuario de que se requiere un mayor nivel de seguridad.</p></td>
</tr>
<tr class="odd">
<td><p>Conferencia</p></td>
<td><p>URI SIP de conferencia para unirse</p></td>
<td><p>Si el URI es self, crea una instancia del foco y abre la vista de solo configuración. De lo contrario, muestra la vista de lista, pero no envía la invitación.</p></td>
</tr>
<tr class="even">
<td><p>mensajería</p></td>
<td><p>URI del SIP</p></td>
<td><p>Muestra una ventana de conversación de mensajería instantánea solo con el URI del SIP. Acepta varios URI de SIP especificados entre corchetes angulares (&lt;&gt;) sin separador.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


En la tabla siguiente se muestran algunos ejemplos de estos parámetros de la línea de comandos.

### <a name="command-line-parameter-examples"></a>Ejemplos de parámetros de la línea de comandos

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Vez</th>
<th>Obtenidos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel: + 14255550101</p></td>
<td><p>Abre una vista de solo teléfono con + 14255550101.</p></td>
</tr>
<tr class="even">
<td><p>Callto: Tel: + 14255550101</p></td>
<td><p>Abre una vista de solo teléfono con + 14255550101.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Abre una vista solo para teléfono con kazuto@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Abre una ventana de conversación con kazuto@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p>conf: SIP:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Abre una ventana de conversación y muestra las opciones de combinación de audio de la reunión.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

