---
title: 'Lync Server 2013: informe de distribución de errores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65735c6b5eba4ff8d15aced6fcc94e38591bdb3e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515397"
---
# <a name="failure-distribution-report-in-lync-server-2013"></a>Informe de distribución de errores en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-21_

El Informe de distribución de errores clasifica las sesiones con error en las categorías siguientes:

  - Motivos del diagnóstico principales

  - Modalidades principales

  - Grupos principales

  - Fuentes principales

  - Componentes principales

  - Usuarios de origen principales

  - Usuarios de destino principales

  - Agentes de usuarios de origen principales

Puede usar estas categorías para determinar dónde se está produciendo exactamente el problema y, en determinados casos, por qué se está produciendo el problema. Por ejemplo, supongamos que ha registrado 242 sesiones de audio/vídeo con error en un día determinado. El Informe de distribución de errores puede mostrar que 237 de dichas sesiones con error tuvieron lugar en el grupo de Dublín. Esto supone un buen punto de partida para el seguimiento y el diagnóstico de las causas de dichos errores. Si hace clic en el grupo de Dublín en la categoría **Grupos principales**, verá un Informe de distribución de errores solo para dicho grupo. Desde ahí, podrá comenzar a analizar las razones por las que el grupo de Dublín tenía tantos problemas.

<div>

## <a name="viewing-the-failure-distribution-report"></a>Visualización del Informe de distribución de errores

Puede tener acceso al Informe de distribución de errores desde cualquiera de los informes siguientes haciendo clic en la métrica **Volumen de errores esperados** o **Volumen de errores inesperados**:

  - [Informe de errores principales en Lync Server 2013](lync-server-2013-top-failures-report.md)

  - [Informe de diagnósticos de conferencia en Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)

  - [Informe de diagnósticos de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

Desde el informe de distribución de errores, puede hacer clic en cualquiera de las métricas siguientes para ver el [Informe de lista de errores en Lync Server 2013](lync-server-2013-failure-list-report.md):

  - Motivos del diagnóstico principales (sesiones)

  - Modalidades principales (sesiones)

  - Grupos principales (sesiones)

  - Fuentes principales (sesiones)

  - Componentes principales (sesiones)

  - Usuarios de origen principales (sesiones)

  - Usuarios de destino principales (sesiones)

  - Agentes de usuarios de origen principales (sesiones)

</div>

<div>

## <a name="using-the-failure-distribution-report"></a>Uso del Informe de distribución de errores

Dependiendo del tamaño de su monitor y de la resolución de la pantalla, es posible que algunos de los datos del Informe de distribución de errores aparezcan truncados. Esto se produce, sobre todo, en métricas como, por ejemplo, las de los agentes de usuarios que tienen etiquetas muy largas. Por ejemplo, es posible que un agente de usuario con el nombre "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" solo se muestre de forma parcial en la pantalla:

UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...

Afortunadamente, basta con mantener el mouse sobre el valor truncado para ver la etiqueta completa.

Una métrica interesante que puede filtrar con el Informe de distribución de errores es la del Id. de diagnóstico. Si se muestra el mismo Id. de diagnóstico en otros informes, podrá filtrar dicho Id. de diagnóstico en el Informe de distribución de errores y obtener una vista detallada del lugar exacto y la frecuencia con la que se ha informado de dicho Id. en la sesión con errores.

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de distribución de errores le permite filtrar por tipo de actividad (sesión de punto a punto o sesión de conferencias) o por el Id. de diagnóstico que contenía cada sesión con errores.

La siguiente tabla muestra los filtros que puede utilizar con el informe de resumen de conferencia.

### <a name="failure-distribution-report-filters"></a>Filtros de informes de distribución de errores

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
<td><p><strong>Grupo</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de actividad</strong></p></td>
<td><p>Tipo de actividad para filtrar. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Todos</p></li>
<li><p>Punto a punto</p></li>
<li><p>Conferencia</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Categoría de sesión</strong></p></td>
<td><p>Indica si la actividad correspondiente se desarrolló correctamente o causó errores. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Todos</p></li>
<li><p>Correcto</p></li>
<li><p>Error esperado</p></li>
<li><p>Error inesperado</p></li>
</ul>
<p>Un error &quot; esperado &quot; es un error que se espera que suceda. Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen. Un &quot; error inesperado &quot; es un error que se produce en lo que parecería ser un sistema en mal estado. Por ejemplo, una llamada no debería finalizarse si el autor de la llamada está en espera. De ser así, tal cosa se identificaría como un error inesperado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a>Métricas para motivos del diagnóstico destacados

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en el Id. de diagnóstico que aparece con mayor frecuencia.

### <a name="metrics-for-top-diagnostic-reasons"></a>Métricas para motivos del diagnóstico destacados

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
<td><p>No</p></td>
<td><p>Clasificación relativa de sesiones con errores basándose en los Id. de diagnóstico. El Id. de diagnóstico es un identificador único (con el formato de un encabezado de diagnóstico MS) adjunto a un mensaje SIP que suele proporcionar información útil para resolver errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principales motivos de diagnóstico</strong></p></td>
<td><p>No</p></td>
<td><p>Id. de diagnóstico generado en una sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones con errores en las que generó el Id. de diagnóstico especificado.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a>Métricas para modalidades destacadas

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en las modalidades de sesiones que experimentaron más errores.

### <a name="metrics-for-top-modalities"></a>Métricas para modalidades destacadas

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
<td><p>No</p></td>
<td><p>Clasificación relativa de sesiones con errores basándose en los tipos de sesiones (por ejemplo, una conferencia de audio o vídeo o una sesión de transferencia de archivos de punto a punto).</p></td>
</tr>
<tr class="even">
<td><p><strong>Principales modalidades</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo de sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones con errores en las que aparece la modalidad especificada.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a>Métricas para grupos destacados

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en los grupos de servidores que experimentaron más errores.

### <a name="metrics-for-top-pools"></a>Métricas para grupos destacados

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
<td><p>No</p></td>
<td><p>Clasificación relativa de sesiones con errores basándose en el grupo de registradores o servidor perimetral en el que se realizó la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principales grupos de servidores</strong></p></td>
<td><p>No</p></td>
<td><p>Nombre del grupo de registrador o servidor perimetral.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones con errores por grupo de registrador o servidor perimetral.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a>Métricas para fuentes destacadas

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en los equipos que experimentaron más errores.

### <a name="metrics-for-top-sources"></a>Métricas para fuentes destacadas

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
<td><p>No</p></td>
<td><p>Clasificación relativa de sesiones con errores por equipo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principales fuentes</strong></p></td>
<td><p>No</p></td>
<td><p>Nombre del equipo que participó en la sesión con errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones con errores por equipo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a>Métricas para componentes destacados

En la siguiente tabla se muestra la información proporcionada en el informe de distribución de errores en función de los componentes de Microsoft Lync Server 2010 que experimentaron más errores.

### <a name="metrics-for-top-components"></a>Métricas para componentes destacados

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
<td><p>No</p></td>
<td><p>Clasificación relativa de sesiones con errores basadas en el componente 2010 de Lync Server (por ejemplo, ExumRouting, GroupChat o MediationServer).</p></td>
</tr>
<tr class="even">
<td><p><strong>Principales componentes</strong></p></td>
<td><p>No</p></td>
<td><p>Nombre del componente que participó en la sesión con errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones con errores por componente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a>Métricas para usuarios destacados

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en los usuarios que experimentaron más errores al intentar llamar a otra persona (denominados remitentes).

### <a name="metrics-for-top-from-users"></a>Métricas para usuarios destacados

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
<td><p>No</p></td>
<td><p>Clasificación relativa de sesiones con errores basándose en el usuario invitado a unirse a la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principales remitentes</strong></p></td>
<td><p>No</p></td>
<td><p>Dirección SIP del usuario invitado a unirse a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de sesiones con error por usuario.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a>Métricas para principales destinatarios

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en los usuarios que experimentaron más errores cuando otro usuario intentó llamarlos (denominados destinatarios).


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
<td><p>No</p></td>
<td><p>Clasificación relativa de sesiones con errores basándose en el usuario que inició la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principales destinatarios</strong></p></td>
<td><p>No</p></td>
<td><p>Dirección SIP del usuario que inició la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de sesiones con error por usuario.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a>Métricas para agentes de usuario destacados

La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en el software extremo que experimentó más errores.

### <a name="metrics-for-top-user-agents"></a>Métricas para agentes de usuario destacados

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
<td><p>No</p></td>
<td><p>Clasificación relativa de sesiones con errores basándose en el agente de usuario (software) que participa en la sesión. Por ejemplo: RTCC/4.0.0.0 Enrutamiento de entrada/4.0.0.0.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principales agentes de usuario</strong></p></td>
<td><p>No</p></td>
<td><p>Nombre del agente de usuario que participó en la sesión con errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones con errores por agente de usuario.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

