---
title: 'Lync Server 2013: informe de errores principales'
description: 'Lync Server 2013: informe de errores principales.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 768c9a99916dece9eb76877b0cd65b057697ff95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561276"
---
# <a name="top-failures-report-in-lync-server-2013"></a>Informe de errores principales en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

El Informe de errores principales proporciona una presentación de los errores más frecuentes y las tendencias en el tiempo. Los errores se basan en una combinación de las dos métricas siguientes:

  - **Id. de diagnóstico**. Identificador único (en forma de un encabezado de ms-diagnostics) que se adjunta a un mensaje SIP. Los Id. de diagnóstico proporcionan información útil para la solución de problemas relacionados con la llamada.

  - **Código de respuesta**. Los códigos de respuesta se usan en las sesiones de comunicación SIP para responder a solicitudes SIP. Por ejemplo, supongamos que Ken envía la solicitud INVITE a Pilar Ackerman (es decir, supongamos que Ken Myer llama Pilar Ackerman). Si Pilar responde, su teléfono le enviará el código de respuesta 200 (OK), indicando al teléfono de Ken que Pilar ha respondido. El informe de errores principales solo incluye los códigos de respuesta que se enviaron en respuesta a un error de llamada; Lync Server no mantiene un seguimiento de todos los códigos de respuesta emitidos durante el curso de una llamada.

No solo se proporciona información del número total de sesiones donde se produjo un error, sino también del número total de usuarios a los que afectó el error.

<div>

## <a name="accessing-the-top-failures-report"></a>Acceso al Informe de errores principales

Desde la página Informes supervisión se obtiene acceso al Informe de errores principales. Al hacer clic en la métrica sesiones notificadas irá al [Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md).

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a>Hacer el mejor uso del Informe de errores principales

El Informe de errores principales es inusual en un sentido: le permite filtrar a la vez hasta 5 Id. de diagnóstico. (Normalmente solo se filtra por un elemento cada vez, como una dirección SIP de usuario). Para filtrar por varios Id. de diagnóstico, simplemente introduzca cada Id. en el cuadro Id. de diagnóstico, separe los identificadores con comas. (Si desea, puede dejar un espacio en blanco después de cada coma). Por ejemplo:

1011, 2412, 1033, 52116, 1008

Haga eso y solo aparecerán las llamadas erróneas que notificaron al menos uno de esos cinco Id. de diagnóstico.

Si coloca el mouse sobre un código de respuesta verá una información sobre herramientas que le indica el significado del código de respuesta en cuestión. Por ejemplo, si coloca el mouse sobre el código de respuesta 486 verá este mensaje:

No disponible aquí.

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de errores más comunes le permite filtrar los datos en función de aspectos tales como el tipo de actividad (sesión punto a punto o sesión de conferencia) o por el código de respuesta SIP que acompañó a la sesión fallida. Es posible también elegir la forma en la que los datos deben agruparse. En este caso, los usos se agrupan por hora, día, semana o mes.

La siguiente tabla muestra los filtros que puede utilizar con el informe de errores más comunes.

### <a name="top-failures-report-filters"></a>Filtros del informe de errores más comunes

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
<td><p><strong>From</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de actividad</strong></p></td>
<td><p>Tipo de actividad. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Todos</p></li>
<li><p>Punto a punto</p></li>
<li><p>Conferencia</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalidad</strong></p></td>
<td><p>En este momento, la única opción disponible es <strong>[Todas]</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Grupo</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Categoría</strong></p></td>
<td><p>Tipo de error. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Error esperado e inesperado</p></li>
<li><p>Error inesperado</p></li>
</ul>
<p>Un error &quot; esperado &quot; es un error que se espera que suceda. Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen. Un &quot; error inesperado &quot; es un error que se produce en lo que parecería ser un sistema en mal estado. Por ejemplo, una llamada no debería finalizarse si el autor de la llamada está en espera. De ser así, tal cosa se identificaría como un error inesperado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Código de respuesta</strong></p></td>
<td><p>Código de respuesta SIP enviado cuando la conferencia ha fallado. Escriba el código de respuesta en su totalidad, como por ejemplo:</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de errores más comunes.

### <a name="top-failures-report-metrics"></a>Métricas del informe de errores más comunes

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
<td><p><strong>Rank</strong></p></td>
<td><p>Sí</p></td>
<td><p>Clasificación relativa basada en el número de sesiones de las que se informa.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones de las que se informa</strong></p></td>
<td><p>Sí</p></td>
<td><p>Número total de sesiones con error basadas en el Id. de diagnóstico y en el código de respuesta SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Usuarios afectados</strong></p></td>
<td><p>Sí</p></td>
<td><p>Número total de usuarios afectados por la sesión con error.</p></td>
</tr>
<tr class="even">
<td><p><strong>Información del error</strong></p></td>
<td><p>No</p></td>
<td><p>Información detallada sobre el error, incluido el Id. de diagnóstico, el código de respuesta SIP y la descripción de los motivos por los que se produjo un error en la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tendencia en el pasado</strong></p></td>
<td><p>No</p></td>
<td><p>Gráfico de sesiones con error a lo largo del tiempo.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

