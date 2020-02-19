---
title: 'Lync Server 2013: informe de diagnóstico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57d62e5938fd2d3b3d6966410a99e2f2e106325f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a>Informe de diagnósticos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-07_

El informe de diagnóstico ofrece información de diagnóstico y solución de problemas para una sesión con error. Esta información incluye el identificador de diagnóstico y el encabezado de diagnóstico que se notificaron cuando se produjo un error en la sesión. El identificador de diagnóstico es un identificador único (en forma de un encabezado MS-Diagnostics) que se adjunta a un mensaje SIP, mientras que el encabezado de diagnóstico proporciona una descripción complementaria del identificador de diagnóstico. El informe también puede contener detalles de solución de problemas valiosos que el componente de informes conoce. Por ejemplo:

  - El código de causa proporcionado por la puerta de enlace RTC que generó el error. Cuando se produce un error en una llamada realizada en la red RTC, se genera automáticamente un código de causa de parte del usuario RDSI (ISUP). Por ejemplo, una puerta de enlace RTC podría enviar el código de causa 34 para indicar que no se disponía de ningún circuito ni canal para completar la llamada.

  - Errores de conectividad, puerto y FQDN del mismo nivel para errores de conectividad.

  - Nombres que se buscan en busca de errores de resolución DNS. La resolución DNS tiene su comportamiento cada vez que un cliente se pone en contacto con un servidor de nombres y solicita la dirección IP que corresponde al nombre de dispositivo especificado.

<div>

## <a name="accessing-the-diagnostic-report"></a>Acceso al informe de diagnósticos

Para obtener acceso al informe de diagnóstico, haga clic en la métrica informe de diagnóstico (detalle) en el [Informe de detalles de sesiones punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) o en el informe de detalles de conferencia.

</div>

<div>

## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el informe de diagnóstico.

</div>

<div>

## <a name="metrics"></a>Métricas

En la siguiente tabla se muestra la información proporcionada en el informe de diagnóstico para cada sesión.

### <a name="diagnostic-report-metrics"></a>Métricas del informe de diagnóstico

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>¿Se pueden ordenar los datos en este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Hora del informe</strong></p></td>
<td><p>No</p></td>
<td><p>Fecha y hora en que se registró el informe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Código de respuesta</strong></p></td>
<td><p>No</p></td>
<td><p>Código de respuesta SIP enviado cuando se produjo un error en la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de solicitud</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo de solicitud SIP fallida. Por ejemplo, INVITE, BYE o SERVICE.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>No</p></td>
<td><p>Origen del error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI de usuario de remitente</strong></p></td>
<td><p>No</p></td>
<td><p>Dirección SIP del usuario que inició la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente de remitente</strong></p></td>
<td><p>No</p></td>
<td><p>Software que utiliza el extremo del usuario que inició la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>No</p></td>
<td><p>Identificador único (en forma de encabezado de tipo ms-diagnostics) que se adjunta a un mensaje SIP y que suele ofrecer información de utilidad para resolver errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de contenido</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo de contenido multimedia con errores. Por ejemplo, un tipo de contenido común es Application/SDP. Session Description Protocol (SDP) es un protocolo estándar de Internet que se usa para anuncios de sesiones, invitaciones a sesiones y otras formas de inicio de sesión multimedia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Aplicación</strong></p></td>
<td><p>No</p></td>
<td><p>Aplicación implicada en el error.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI de usuario</strong></p></td>
<td><p>No</p></td>
<td><p>Dirección SIP del usuario invitado a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p>Tiempos de combinación de conferencia (MS)</p></td>
<td><p>No</p></td>
<td><p>Cantidad de tiempo (en milisegundos) que tardó el usuario en unirse a la Conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Encabezado de diagnóstico</strong></p></td>
<td><p>No</p></td>
<td><p>Descripción del identificador de diagnóstico.</p></td>
</tr>
</tbody>
</table>


Se puede encontrar una lista de errores de diagnóstico en la [Página de encabezado de MS-Diagnostics](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

