---
title: 'Lync Server 2013: iniciar Lync desde otra aplicación'
description: 'Lync Server 2013: iniciar Lync desde otra aplicación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd64b8b9f335638b54a0bf6473b5d159c97a0e7f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562706"
---
# <a name="starting-lync-from-another-application"></a>Iniciar Lync desde otra aplicación

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Puede usar los parámetros de la línea de comandos para iniciar rápidamente Lync 2013. Por ejemplo, si un usuario hace clic en un número de teléfono en otra aplicación, la aplicación puede iniciar una instancia de Lync 2013 e iniciar una llamada a ese número.

Lync 2013 también puede reconocer una lista delimitada por punto y coma de nombres de contacto para conferencias con varios participantes.

Si Lync 2013 está configurado para iniciar sesión automáticamente cuando se inicia, al iniciar Lync 2013 con parámetros de línea de comandos se abrirá la ventana principal de Lync. Si Lync no está configurado para que inicie la sesión automáticamente al iniciarse, se abre la ventana de inicio de sesión.

En la tabla siguiente se muestran los parámetros disponibles.

### <a name="lync-2013-command-line-parameters"></a>Parámetros de Command-Line de Lync 2013

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
<td><p>Tel</p></td>
<td><p>URI de tel.</p></td>
<td><p>Abre la ventana Conversación para una llamada de audio pero no marca el número especificado.</p></td>
</tr>
<tr class="even">
<td><p>protocolos callto</p></td>
<td><p>tel:, sip: o URL de tel que se puede editar</p></td>
<td><p>Abre la ventana Conversación para una llamada de audio pero no marca el número especificado.</p></td>
</tr>
<tr class="odd">
<td><p>SIP</p></td>
<td><p>URI del SIP</p></td>
<td><p>Abra la ventana Conversación con el Identificador uniforme de recursos (URI) del SIP especificado en la lista de participantes.</p></td>
</tr>
<tr class="even">
<td><p>Módulos</p></td>
<td><p>URI del SIP</p></td>
<td><p>Si Lync 2013 está configurado para usar el protocolo de seguridad de la capa de transporte (TLS), funciona exactamente igual que SIP:. Si no está usando TLS, muestra un cuadro de diálogo para informar al usuario de que se requiere un alto nivel de seguridad.</p></td>
</tr>
<tr class="odd">
<td><p>multipunto</p></td>
<td><p>URI del SIP de la conferencia a la que se va a unir</p></td>
<td><p>Si el URI es automático, crea instancias del foco y solo abre una vista de la lista. En caso contrario, abre una vista de la lista pero no envía INVITE.</p></td>
</tr>
<tr class="even">
<td><p>conversaciones</p></td>
<td><p>URI del SIP</p></td>
<td><p>Muestra la ventana Conversación solo de mensajería instantánea con el URI del SIP. Acepta varios URI de SIP especificados entre corchetes angulares ( &lt; &gt; ) sin ningún separador.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


En la tabla siguiente se proporcionan ejemplos de estos parámetros de línea de comandos.

### <a name="command-line-parameter-examples"></a>Ejemplos de parámetros de línea de comandos

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
<td><p>Tel: + 14255550101</p></td>
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
<td><p>conf: SIP:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Abre una ventana de conversación y muestra las opciones de unión de audio de la reunión.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

