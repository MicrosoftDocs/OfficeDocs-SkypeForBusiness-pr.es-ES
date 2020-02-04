---
title: 'Lync Server 2013: informe de la lista de llamadas del grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94c06e2029ca1a22a0a9f73249cff3251e2fcbc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a>Informe de la lista de llamadas a grupos de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

La aplicación de grupo de respuesta proporciona una manera de que Microsoft Lync Server 2013 responda y enrute llamadas telefónicas en función del número que haya marcado y, opcionalmente, de las respuestas de la persona que llama a una serie de preguntas. Normalmente, las llamadas a grupos de respuesta no se dirigen a una persona individual, sino que se dirigen a un equipo de personas a las que se hace referencia como grupo de agentes. Por ejemplo, si alguien llama al número de teléfono del Departamento de soporte técnico, Lync Server 2013 puede enrutar automáticamente esa llamada al primer agente del servicio de asistencia disponible. Como alternativa, Lync Server podría formular una serie de preguntas ("Presione 1 si tiene problemas de hardware. Pulse 2 Si tiene problemas de software. Pulse 3 Si tiene problemas de red. ") y luego enrutar la llamada al agente del servicio de asistencia al cliente más adecuado, en función de la respuesta a esas preguntas.

El Informe de lista de llamadas de grupo de respuesta representa una colección de llamadas que reúnen unas características especificadas (tipo de llamada, periodo de tiempo en que se hizo). El Informe de uso del grupo de respuesta (que necesita abrirse antes de abrir el Informe de lista de llamadas de grupo de respuesta) reconoce los siguientes tipos de llamada:

  - **Llamadas recibidas**. Cantidad total de llamadas recibidas por todas las instancias de la aplicación Grupo de respuesta.

  - **Llamadas correctas**. Cantidad total de llamadas respondidas por la aplicación Grupo de respuesta.

  - **Llamadas ofrecidas**. Cantidad total de llamadas transferidas a un agente de Grupo de respuesta.

  - **Llamadas contestadas**. Cantidad total de llamadas contestadas realmente por un agente de Grupo de respuesta.

  - Porcentaje de llamadas abandonadas. Porcentaje de llamadas recibidas por la aplicación Grupo de respuesta que nunca contestó un agente. Este valor se calcula restando las llamadas contestadas a las llamadas recibidas y, luego, dividiendo el valor obtenido entre el número de Llamadas recibidas. Por ejemplo, si se han recibido 10 llamadas y 7 no se contestaron, necesita restar 7 a 10, lo que da un resultado de 3 llamadas no respondidas. Luego, dicho valor se divide entre 10, con lo que obtiene un porcentaje de llamadas abandonadas del 30 %.

  - **Llamadas transferidas**. Cantidad total de llamadas de Grupo de repuesta transferidas porque se agotó un tiempo de espera de cola o porque una cola está desbordada.

<div>

## <a name="accessing-the-response-group-call-list-report"></a>Acceso al informe de lista de llamadas de grupo de respuesta

Solo se puede acceder al informe de la lista de llamadas del grupo de respuesta haciendo clic en una de las siguientes métricas del [Informe de uso de grupo de respuesta en Lync Server 2013](lync-server-2013-response-group-usage-report.md):

  - Llamadas recibidas

  - Llamadas correctas

  - Llamadas ofrecidas

  - Llamadas contestadas

  - Llamadas transferidas

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Cómo sacar el máximo partido al Informe de lista de llamadas de grupo de respuesta

El Informe de lista de llamadas de grupo de respuesta le permite limitar los datos que se muestran en las llamadas en las que participa un flujo de trabajo de grupos de respuesta en particular. Para ello, tendrá que escribir el URI del flujo de trabajo (es decir, su dirección SIP) en el cuadro URI de flujo de trabajo. Ahora bien, para poder hacer eso, primero tendrá que poder ver el cuadro URI de flujo de trabajo. Para mostrar las opciones de filtrado del Informe de lista de llamadas de grupo de respuesta, haga clic en el botón Mostrar u ocultar parámetros de la esquina superior izquierda de la ventana de informes.

Tenga en cuenta que, al pasar el mouse sobre Código de respuesta o Id. de diagnóstico, la lista de llamadas de grupo de respuesta no muestra información sobre ninguna de esas dos métricas. Si necesita más información, puede anotar el código de respuesta o el identificador de diagnóstico y, a continuación, buscar esos valores en el [Informe de errores superiores de Lync Server 2013](lync-server-2013-top-failures-report.md).

Ante una pregunta como "¿Qué flujo de trabajo concreto recibió más llamadas?", puede hacer lo siguiente:

1.  En el Informe de uso del grupo de respuesta, establezca el periodo de tiempo deseado y luego haga clic en la métrica Llamadas recibidas. Se abrirá el Informe de lista de llamadas de grupo de respuesta.

2.  Exporte los datos que se muestran en el Informe de lista de llamadas de grupo de respuesta. Por ejemplo, puede exportar los datos en formato Microsoft Excel y luego usar Excel para convertir los datos a un archivo de valores separados por comas.

3.  Ejecute sus análisis con Windows PowerShell.

Por ejemplo, si ha guardado los datos en un archivo denominado C\\: informe de\\lista\_\_\_de llamadas\_de grupo de respuesta de datos. csv, puede usar el siguiente comando para devolver el número total de llamadas recibidas de cada flujo de trabajo que aparece en el informe:

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

La información que se mostrará será similar a esta:

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente se muestran los filtros que se pueden utilizar en el informe de lista de llamadas de grupo de respuesta.

### <a name="response-group-call-list-report-filters"></a>Filtros del informe de lista de llamadas de grupo de respuesta

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
<p>7/7/2012 1:00 P.M.</p>
<p>Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hasta</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</p>
<p>7/7/2012 1:00 P.M.</p>
<p>Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI de flujo de trabajo</strong></p></td>
<td><p>Permite limitar los datos devueltos al flujo de trabajo de grupo de respuesta especificado. Para usar este filtro, escriba la dirección SIP del grupo de trabajo. Por ejemplo:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>Llamadas</strong></p></td>
<td><p>Puede seleccionar entre los siguientes tipos de llamada:</p>
<ul>
<li><p>Llamadas recibidas</p></li>
<li><p>Llamadas correctas</p></li>
<li><p>Llamadas ofrecidas</p></li>
<li><p>Llamadas contestadas</p></li>
<li><p>Llamadas transferidas</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la siguiente tabla se detalla la información que facilita el informe de lista de llamadas de grupo de respuesta para cada llamada recibida por la aplicación Grupo de respuesta.

### <a name="response-group-call-list-report-metrics"></a>Métricas del informe de lista de llamadas de grupo de respuesta

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
<td><p><strong>Autor de llamada</strong></p></td>
<td><p>No</p></td>
<td><p>Dirección SIP del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Flujo de trabajo</strong></p></td>
<td><p>No</p></td>
<td><p>Dirección SIP del flujo de trabajo de Grupo de respuesta.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de inicio</strong></p></td>
<td><p>No</p></td>
<td><p>Fecha y hora en que se inició la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de finalización</strong></p></td>
<td><p>No</p></td>
<td><p>Fecha y hora en que finalizó la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Código de respuesta</strong></p></td>
<td><p>No</p></td>
<td><p>Código de respuesta SIP enviado cuando se produjo un error en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>No</p></td>
<td><p>Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

