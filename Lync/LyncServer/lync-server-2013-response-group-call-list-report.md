---
title: 'Lync Server 2013: informe de lista de llamadas de grupo de respuesta'
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
ms.openlocfilehash: 0b9ec44aa0b4c6063dd6c0a3cf1ae9e5b0c10356
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a>Informe de lista de llamadas de grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

La aplicación de grupo de respuesta ofrece una forma de que Microsoft Lync Server 2013 responda y enrute llamadas telefónicas en función del número marcado y, opcionalmente, de las respuestas del autor de la llamada a una serie de preguntas. Normalmente, las llamadas de grupo de respuesta no se enrutan a una persona individual pero, en su lugar, se redirigen a un equipo de personas a las que se hace referencia como grupo de agentes. Por ejemplo, si alguien llama al número de teléfono de su Departamento de soporte técnico, Lync Server 2013 puede enrutar automáticamente esa llamada al primer agente del Departamento de soporte disponible. Como alternativa, Lync Server podría formular una serie de preguntas ("Presione 1 si tiene problemas de hardware. Presione 2 Si tiene problemas de software. Presione 3 Si tiene problemas de red. ") y luego enrutar la llamada al representante del Departamento de soporte técnico más adecuado en función de la respuesta a esas preguntas.

El informe de lista de llamadas de grupo de respuesta representa una colección de llamadas realizadas para un período de tiempo especificado y para un tipo de llamada especificado. El informe de uso del grupo de respuesta (que debe abrirse primero para poder abrir el informe de lista de llamadas de grupo de respuesta) reconoce los siguientes tipos de llamadas:

  - **Llamadas recibidas**. Número total de llamadas recibidas por todas las instancias de la aplicación Grupo de respuesta.

  - **Llamadas correctas**. Número total de llamadas que ha seleccionado la aplicación grupo de respuesta.

  - **Llamadas ofrecidas**. Número total de llamadas transferidas a un agente de Grupo de respuesta.

  - **Llamadas contestadas**. Número total de llamadas contestadas realmente por un agente de Grupo de respuesta.

  - Porcentaje de llamadas abandonadas. Porcentaje de llamadas recibidas por la aplicación Grupo de respuesta que nunca contestó un agente. Este valor se calcula restando las llamadas contestadas a las llamadas recibidas y, a continuación, dividiendo el valor obtenido entre el número de Llamadas recibidas. Por ejemplo, si se han recibido 10 llamadas y 7 no se contestaron, debe restar 7 a 10, lo que da un resultado de 3 llamadas no respondidas. A continuación, dicho valor se divide entre 10, con lo que obtiene un porcentaje de llamadas abandonadas del 30%.

  - **Llamadas transferidas**. Número total de llamadas de Grupo de repuesta transferidas porque se agotó un tiempo de espera de cola o porque una cola está desbordada.

<div>

## <a name="accessing-the-response-group-call-list-report"></a>Acceso al informe de lista de llamadas de grupo de respuesta

Solo se puede tener acceso al informe de lista de llamadas de grupo de respuesta haciendo clic en una de las siguientes métricas del [Informe de uso del grupo de respuesta en Lync Server 2013](lync-server-2013-response-group-usage-report.md):

  - Llamadas recibidas

  - Llamadas correctas

  - Llamadas ofrecidas

  - Llamadas contestadas

  - Llamadas transferidas

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Aprovechar al máximo el informe de lista de llamadas de grupo de respuesta

El informe de lista de llamadas de grupo de respuesta le permite limitar los datos que se muestran a llamadas que impliquen a un flujo de trabajo determinado del grupo de respuesta. Para ello, debe especificar el URI del flujo de trabajo (dirección SIP del flujo de trabajo) en el cuadro URI del flujo de trabajo. Sin embargo, antes de poder hacerlo, debe poder ver el cuadro URI de flujo de trabajo. Para mostrar las opciones de filtrado del informe de lista de llamadas de grupo de respuesta, haga clic en el botón Mostrar u ocultar parámetros en la parte superior izquierda de la ventana del informe.

Tenga en cuenta que la lista de llamadas de grupo de respuesta no muestra información sobre el código de respuesta o el identificador de diagnóstico si mantiene el mouse sobre cualquiera de esas métricas. Si necesita más información, puede anotar el código de respuesta o el identificador de diagnóstico y, a continuación, buscar esos valores en el [Informe de errores principales en Lync Server 2013](lync-server-2013-top-failures-report.md).

una pregunta como esta: "¿qué flujo de trabajo individual recibió más llamadas?", puede hacer lo siguiente:

1.  En el informe de uso del grupo de respuesta, establezca el período de tiempo deseado y, a continuación, haga clic en la métrica llamadas recibidas. Se abrirá el informe de lista de llamadas de grupo de respuesta.

2.  Exportar los datos que se muestran en el informe de lista de llamadas de grupo de respuesta. Por ejemplo, puede exportar los datos en formato de Microsoft Excel y, a continuación, usar Excel para convertir los datos en un archivo de valores separados por comas.

3.  Ejecute los análisis con Windows PowerShell.

Por ejemplo, si ha guardado los datos en un archivo denominado C\\: Data\\Response\_Group\_\_List\_Report. csv, puede usar el siguiente comando para devolver el número total de llamadas recibidas para cada flujo de trabajo que se muestra en el informe:

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

Esta información será similar a la siguiente:

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

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la siguiente tabla se enumeran los filtros que se pueden usar con el informe de lista de llamadas de grupo de respuesta.

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
<td><p><strong>From</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</p>
<p>7/7/2012 1:00 pm</p>
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
<td><p><strong>URI de flujo de trabajo</strong></p></td>
<td><p>Permite limitar los datos devueltos al flujo de trabajo de grupo de respuesta especificado. Para usar este filtro, escriba la dirección SIP del grupo de trabajo. Por ejemplo:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>Llamadas</strong></p></td>
<td><p>Puede seleccionar uno de los siguientes tipos de llamada:</p>
<ul>
<li><p>Llamadas recibidas</p></li>
<li><p>Llamadas correctas</p></li>
<li><p>Llamadas ofrecidas</p></li>
<li><p>Llamadas respondidas</p></li>
<li><p>Llamadas transferidas</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la siguiente tabla se muestra la información proporcionada en el informe de lista de llamadas de grupo de respuesta para cada llamada recibida por la aplicación grupo de respuesta.

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
<th>¿Se pueden ordenar los datos en este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Caller</strong></p></td>
<td><p>No</p></td>
<td><p>Dirección SIP del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Flujo de trabajo</strong></p></td>
<td><p>No</p></td>
<td><p>Dirección SIP del flujo de trabajo del grupo de respuesta.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de comienzo</strong></p></td>
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

