---
title: 'Lync Server 2013: informe actividad de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 583c647ac3cdab290f1833539abbbd033ea89410
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a>Informe de actividad de usuario en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-02-27_

El Informe de actividad de usuario proporciona una lista detallada de sesiones de conferencia y de punto a punto realizadas por sus usuarios en un período determinado. A diferencia de muchos de los Informes de supervisión, el Informe de actividad de usuario une cada llamada a usuarios individuales. Por ejemplo, las sesiones de punto a punto especifican los URI del SIP de la persona que inició la llamada (el usuario De) y la persona a la que se realizó la llamada (el usuario Para). Si expande la información de una conferencia, verá una lista de todos los participantes de la conferencia y el rol que desempeñaban en esa conferencia.

Al Informe de actividad de usuario a veces se lo conoce como "informe de asistencia técnica" porque a menudo el personal de asistencia técnica lo utiliza para recuperar información de sesión para un usuario específico. Es posible establecer filtros para llamadas realizadas a o por un usuario particular con tan solo escribir el URI del SIP del usuario en el cuadro de prefijo de URI del usuario.

Si hace esto, el informe de actividad del usuario devolverá la información de cualquier usuario cuyo URI SIP empiece por la cadena especificada. Por ejemplo, si escribe **ken** en el cuadro URI, el Informe de actividad de usuario encontrará **Ken**.Myer@litwareinc.com. Pero, también encontrará a estos usuarios:

  - **ken**azi@litwareinc.com

  - **ken**burg@litwareinc.com

  - **Ken**.Sanchez@litwareinc.com

  - **Ken**nedy@litwareinc.com

Para garantizar que solo se devuelva información para Ken Myer, escriba su URI completo (Ken.Myer@litwareinc.com) en el cuadro de búsqueda o al menos parte suficiente del URI de Ken que lo distinga específicamente a él entre otros usuarios de su organización. Por ejemplo:

Ken.my

<div>

## <a name="to-access-the-user-activity-report"></a>Acceso al informe de actividad de usuario

Para obtener al Informe de actividad de usuario hay que ir a la página de inicio de Informes de supervisión. También puede comunicarse con el informe de actividad del usuario haciendo clic en la métrica de URI de usuario en el [Informe de inventario de teléfono IP en Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md). Desde el Informe de actividad de usuario, puede hacer clic en el URI de conferencia (para una conferencia) para obtener acceso al Informe de detalles de conferencia. De forma similar, al hacer clic en la métrica de detalle de una llamada de punto a punto, se le lleva al [informe detallado de sesión de punto a punto de Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a>Hacer el mejor uso del informe de actividad de usuario

Aunque hay mucha información buena en el Informe de actividad de usuario, esa información puede a veces ser difícil de encontrar. Por ejemplo, toda la actividad de usuario que tiene lugar en la organización durante un período específico se incluye en el informe actividad de usuario. eso significa que, en el informe, la información sobre qué usuarios realmente usaba Microsoft Lync Server 2013 de algún modo.

<div>


> [!WARNING]  
> Técnicamente, es posible que algunas actividades de usuario no se registren: Si bien Lync Server se esfuerza por mantener la información sobre todas las llamadas telefónicas, es posible que se haya realizado una llamada sin que la información sobre la llamada se escriba en la base de datos. Lync Server está diseñado para ofrecer un aspecto extremadamente preciso, pero no necesariamente perfecto, de la forma en que se usa Lync Server 2013. (El hecho de que no haya garantía de que el 100% de todas las llamadas se grabe explica por qué no se debe usar la supervisión de Lync Server como sistema de facturación).<BR>En segundo lugar, un informe de informe de supervisión solo puede mostrar, como máximo, 1.000 registros. Según la cantidad de actividad de usuario que tenga y el período de tiempo con el que trabaje, eso significa que su consulta podría no devolverle todos los datos realmente almacenados en la base de datos.



</div>

  - ¿Qué usuarios utilizaron en realidad el sistema durante este período?

  - ¿Cuáles de mis usuarios fueron los más activos durante este período?

  - ¿Los usuarios que realizan la mayor cantidad de llamadas telefónicas también son los usuarios que participan en la mayoría de las sesiones de mensajería instantánea?

Si necesita responder preguntas como estas, puede exportar los datos recuperados por los Informes de supervisión a una hoja de cálculos de Excel. Luego utiliza esa hoja de cálculos o un archivo de valores separados por comas para analizar los datos del modo en que no permite el Informe de actividad de usuario. Por ejemplo, imaginemos que ha exportado los datos del informe a Excel y luego a un archivo de valores separados por comas. En ese momento, puede importar los datos desde el. CSV a Windows PowerShell con un comando parecido a este:

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

Una vez importados los datos, puede usar comandos sencillos de Windows PowerShell para responder a sus preguntas. Por ejemplo, este comando devuelve una lista de usuarios únicos que han tenido el rol de "usuario De" en al menos una sesión:

    $x | Group-Object "From user" | Select Name | Sort-Object Name

Dicho de otra manera:

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

Este comando enumera los usuarios únicos (en función de la cantidad total de sesiones en las que participaron):

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

Eso devuelve datos similares a esto:

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

Este comando limita las sesiones informadas a aquellas que incluyeron audio como modalidad:

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

Si mantiene el cursor del mouse sobre cualquier identificador de diagnóstico mostrado en el informe, aparecerá una información sobre herramientas que describirá ese identificador.

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de actividad de usuario le permite filtrar los datos devueltos en función de aspectos tales como el tipo de actividad (es decir, sesiones punto a punto o sesiones de conferencia) o por la dirección SIP del usuario (permitiéndole ver las actividades de un usuario). Es posible también elegir la forma en la que tienen que agruparse los datos. En este caso, los usos se agrupan por hora, día, semana o mes.

La siguiente tabla muestra los filtros que puede utilizar con el informe de actividad de usuario.

### <a name="user-activity-report-filters"></a>Filtros del informe de actividad de usuario

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
<td><p><strong>De</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</p>
<p>7/17/12012 1:00 P.M.</p>
<p>Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/17/12012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/13/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hasta</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</p>
<p>7/17/12012 1:00 P.M.</p>
<p>Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/17/12012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/13/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de actividad</strong></p></td>
<td><p>Tipo de actividad. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Punto a punto</p></li>
<li><p>Una conferencia</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalidad</strong></p></td>
<td><p>La modalidad que tenga disponible dependerá de la opción seleccionada en Tipo de actividad. Si el tipo de actividad es de punto a punto, puede seleccionar mi; Transferencia de archivos; Uso compartido de aplicaciones; Facturación o vídeo como modalidad.</p>
<p>Si el Tipo de actividad es Conferencia, podrá seleccionar mensajería instantánea, conferencia telefónica; conferencia web; uso compartido de aplicaciones; conferencia de voz/vídeo o conferencia telefónica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Categoría de sesión</strong></p></td>
<td><p>Indica si la actividad correspondiente se desarrolló correctamente o causó errores. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Correcto</p></li>
<li><p>Error esperado</p></li>
<li><p>Error inesperado</p></li>
</ul>
<p>Un &quot;error&quot; esperado es un error que se espera que suceda; por ejemplo, si un usuario ha establecido su estado en no molestar, cabría esperar cualquier llamada a ese usuario. Un &quot;error&quot; inesperado es un error que se produce en lo que parecería ser un sistema saludable en otro caso. Por ejemplo, una llamada no tendría que finalizarse si el autor de la llamada está en espera. De ser así, dicha situación se identificaría como un error inesperado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prefijo de URI de usuario</strong></p></td>
<td><p>Dirección SIP del usuario. Para ver únicamente registros del usuario Ken Myer necesita introducir la dirección SIP de Ken Myer. Por ejemplo:</p>
<p>sip:kenmyer@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas de las sesiones punto a punto

En la siguiente tabla se muestra la información proporcionada en el informe de actividad de usuario correspondiente a sesiones punto a punto (es decir, sesiones con solo dos participantes).

### <a name="metrics-for-peer-to-peer-sessions"></a>Métricas de las sesiones punto a punto

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
<td><p>No</p></td>
<td><p>Al hacer clic en este elemento, el informe le muestra el informe de detalles de sesiones punto a punto correspondiente a la sesión seleccionada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Remitente</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dirección SIP del usuario que inició la sesión punto a punto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Destinatario</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dirección SIP del usuario que se unió a la sesión punto a punto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalidades</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tipo de comunicación usado en la sesión. Por ejemplo, mensajería instantánea, sonido o transferencia de archivos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de invitación</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en las que se envió la invitación inicial a unirse a la sesión punto a punto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tiempo de respuesta</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que &quot;el&quot; usuario aceptó la invitación a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de finalización</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en las que finalizó la sesión punto a punto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>Sí</p></td>
<td><p>Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Métricas de las sesiones de conferencia

En la siguiente tabla se muestra la información proporcionada en el informe de actividad de usuario correspondiente a sesiones de conferencia (es decir, sesiones con tres o más participantes).

### <a name="metrics-for-conferencing-sessions"></a>Métricas de las sesiones de conferencia

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
<td><p>Identificador único de la conferencia. Al hacer clic en este elemento, el informe le muestra el informe de detalles de conferencia de la sesión seleccionada. Al desplegar este elemento, el informe le muestra información sobre los participantes en la conferencia. Para obtener más información, &quot;vea la sección métrica de&quot; los participantes de la Conferencia más adelante en este tema.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizador</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dirección SIP del usuario que organizó la conferencia</p></td>
</tr>
<tr class="odd">
<td><p><strong>Grupo de servidores</strong></p></td>
<td><p>Sí</p></td>
<td><p>Nombre del servidor perimetral (si lo hay) usado en la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de inicio</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en las que comenzó la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de finalización</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que la conferencia finalizó.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a>Métricas de los participantes en conferencias

En la tabla siguiente se muestra la información que recoge el informe de actividad de usuario sobre cada participante en una conferencia.

### <a name="metrics-for-conference-participants"></a>Métricas de los participantes en conferencias

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
<td><p>No</p></td>
<td><p>Rol del usuario en la conferencia (por ejemplo, moderador).</p></td>
</tr>
<tr class="even">
<td><p><strong>Participante</strong></p></td>
<td><p>No</p></td>
<td><p>Dirección SIP del usuario.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Conectividad</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo de conexión de red. Por ejemplo &quot;, interno&quot; para una conexión interna &quot;o desde&quot; RTC para usuarios de acceso telefónico.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de conexión</strong></p></td>
<td><p>No</p></td>
<td><p>Fecha y hora en las que el usuario se unió a la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de desconexión</strong></p></td>
<td><p>No</p></td>
<td><p>Fecha y hora en las que el usuario dejó la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>No</p></td>
<td><p>Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

