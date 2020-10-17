---
title: 'Lync Server 2013: informe de uso del grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 649fb55f6c7b698986c4c31057b3a0a8f1b00a76
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511627"
---
# <a name="response-group-usage-report-in-lync-server-2013"></a>Informe de uso del grupo de respuesta en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

La aplicación de grupo de respuesta ofrece una forma de que Microsoft Lync Server 2013 responda y enrute llamadas telefónicas en función del número marcado y, opcionalmente, de las respuestas del autor de la llamada a una serie de preguntas. Normalmente, las llamadas de grupo de respuesta no se enrutan a una persona individual pero, en su lugar, se redirigen a un equipo de personas a las que se hace referencia como grupo de agentes. Por ejemplo, si alguien llama al número de teléfono de su Departamento de soporte técnico, Lync Server 2013 puede enrutar automáticamente esa llamada al primer agente del Departamento de soporte disponible. Como alternativa, Lync Server podría formular una serie de preguntas ("Presione 1 si tiene problemas de hardware. Presione 2 Si tiene problemas de software. Presione 3 Si tiene problemas de red. ") y luego enrutar la llamada al representante del Departamento de soporte técnico más adecuado en función de la respuesta a esas preguntas.

El Informe de uso del grupo de respuesta ofrece una perspectiva detallada del número de llamadas de teléfono que se han recibido en todos los flujos de trabajo de grupo de respuesta y, a continuación, separa dichas llamadas en categorías finitas como, por ejemplo, Llamadas ofrecidas, Llamadas contestadas o Llamadas abandonadas.

La clave para trabajar con el Informe de uso del grupo de respuesta está en comprender la diferencia entre los tipos de llamadas incluidas en el informe:

  - **Llamadas recibidas**. Número total de llamadas recibidas por todas las instancias de la aplicación Grupo de respuesta.

  - **Llamadas correctas**. Número total de llamadas que ha seleccionado la aplicación grupo de respuesta.

  - **Llamadas ofrecidas**. Número total de llamadas transferidas a un agente de Grupo de respuesta.

  - **Llamadas contestadas**. Número total de llamadas contestadas realmente por un agente de Grupo de respuesta.

  - **Porcentaje de llamadas abandonadas**. Porcentaje de llamadas recibidas por la aplicación Grupo de respuesta que nunca contestó un agente. Este valor se calcula restando las llamadas contestadas a las llamadas recibidas y, a continuación, dividiendo el valor obtenido entre el número de Llamadas recibidas. Por ejemplo, si se han recibido 10 llamadas y 7 no se contestaron, debe restar 7 a 10, lo que da un resultado de 3 llamadas no respondidas. A continuación, dicho valor se divide entre 10, con lo que obtiene un porcentaje de llamadas abandonadas del 30%.

  - **Llamadas transferidas**. Número total de llamadas de Grupo de repuesta transferidas porque se agotó un tiempo de espera de cola o porque una cola está desbordada.

Si no recuerda la definición de los tipos de llamadas del Informe de uso del grupo de respuesta, basta con mantener el mouse sobre la etiqueta del tipo de llamada correspondiente. Aparecerá una información sobre herramientas con una descripción breve del tipo de llamada.

El Informe de uso del grupo de respuesta permite filtrar URI de flujos de trabajo (dirección SIP asociada a dicho flujo de trabajo). Sin embargo, los URI de flujos de trabajo no se muestran en el informe. Si desea conocer aspectos como, por ejemplo, qué flujos de trabajo están respondiendo a la mayoría de las llamadas o qué flujos de trabajo están transfiriendo más llamadas, haga clic en la métrica correspondiente para abrir el Informe de lista de llamadas de grupo de respuesta para dicho periodo. Este informe no muestra los URI de flujos de trabajo.

<div>

## <a name="accessing-the-response-group-usage-report"></a>Acceso al Informe de uso del grupo de respuesta

Es posible tener acceso al Informe de uso del grupo de respuesta desde la página de inicio de informes de supervisión. Puede profundizar en el [Informe de lista de llamadas de grupo de respuesta en Lync Server 2013](lync-server-2013-response-group-call-list-report.md) haciendo clic en cualquiera de las métricas siguientes:

  - Llamadas recibidas

  - Llamadas correctas

  - Llamadas ofrecidas

  - Llamadas contestadas

  - Llamadas transferidas

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>Cómo sacar el máximo partido al Informe de uso del grupo de respuesta

Uno de los usos más interesantes del Informe de uso del grupo de respuesta puede no resultar obvio a primera vista: la capacidad para recuperar información sobre el uso de un único flujo de trabajo de grupo de respuesta.

<div>


> [!WARNING]  
> Un flujo de trabajo de grupo de respuesta es básicamente un conjunto de instrucciones que determina qué hace Lync Server cuando un usuario marca un número de teléfono determinado. Para ello, cada flujo de trabajo está asociado a un único número de teléfono. Cuando alguien llama a dicho número, el flujo de trabajo determina cómo se administrará la llamada. Por ejemplo, el flujo de trabajo puede enrutar la llamada a través de una serie de preguntas de respuesta de voz interactiva (IVR) que indican al autor de la llamada que debe especificar información adicional ("Presione 1 si necesita asistencia para hardware. Presione 2 si necesita asistencia para software."). De forma alternativa, el flujo de trabajo también puede poner la llamada en cola y mantener al autor de la llamada en espera hasta que haya un agente disponible para atender la llamada. La disponibilidad de los agentes para responder a llamadas también está determinada por el flujo de trabajo: los flujos de trabajo se usan para configurar el horario laboral (días de la semana y horas del día en que los agentes están disponibles para responder a llamadas) y los festivos (días en los que no hay agentes disponibles para responder a llamadas). Cuando realiza llamadas a números de teléfono que pertenecen a una aplicación de grupo de respuesta, básicamente está llamando a un flujo de trabajo de grupo de respuesta.



</div>

Aunque los URI de los flujos de trabajo no se muestran en el Informe de uso del grupo de respuesta, pueden verse las estadísticas de uso de un flujo de trabajo determinado, cosa que a menudo es de gran utilidad. Por ejemplo, supongamos que ha lanzado una nueva campaña publicitaria y tiene curiosidad por saber si se están registrando llamadas para obtener información sobre el producto. Si tiene un flujo de trabajo de grupo de respuesta asociado al número de teléfono de la campaña publicitaria, podrá comprobar fácilmente cuántas personas están llamando a dicho número.

Puede utilizar un enfoque similar para evaluar el número de llamadas atendidas por su servicio de asistencia interno o por el departamento de atención al cliente.

Para revisar las estadísticas de uso de un flujo de trabajo determinado, escriba el URI del flujo de trabajo en el cuadro URI de flujo de trabajo. Tal como se ha mencionado, los URI de flujos de trabajo (dirección SIP asociada a un flujo de trabajo) no se muestran en el informe. Esto implica que deberá buscar otra forma de determinar el URI de un flujo de trabajo. Una forma de hacerlo es usar Windows PowerShell y el shell de administración de Lync Server. Por ejemplo, este comando devuelve los URI de todos los flujos de trabajo de grupo de respuesta:

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

Ese comando devuelve unos datos similares a los siguientes:

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

Este comando devuelve información de un único flujo de trabajo, el flujo de trabajo con el nombre New Ad Campaign:

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de uso del grupo de respuesta le permite ver datos de todos los flujos de trabajo del grupo de respuesta o ver datos de un flujo de trabajo concreto. También se puede elegir cómo agrupar los datos. En este caso, los usos se agrupan por hora, día, semana o mes.

En la tabla siguiente se muestran los filtros que se pueden utilizar en el informe de uso del grupo de respuesta.

### <a name="response-group-usage-report-filters"></a>Filtros del informe de uso del grupo de respuesta

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
<td><p><strong>Intervalo de</strong></p></td>
<td><p>Intervalo de tiempo. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Cada hora (se puede ver un máximo de 25 horas)</p></li>
<li><p>Cada día (se puede ver un máximo de 31 días)</p></li>
<li><p>Cada semana (se puede ver un máximo de 12 semanas)</p></li>
<li><p>Cada mes (se puede ver un máximo de 12 meses)</p></li>
</ul>
<p>Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio 7/7/2012 y una fecha de finalización 28/2/2012, se mostrarán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</p></td>
</tr>
<tr class="even">
<td><p><strong>URI de flujo de trabajo</strong></p></td>
<td><p>Permite limitar los datos devueltos al flujo de trabajo de grupo de respuesta especificado. Para usar este filtro, escriba la dirección SIP del grupo de trabajo. Por ejemplo:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de uso del grupo de respuesta.

### <a name="response-group-usage-report-metrics"></a>Métricas del informe de uso del grupo de respuesta

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
<td><p><strong>Cada hora</strong></p>
<p><strong>Diario</strong></p>
<p><strong>Semanal</strong></p>
<p><strong>Mensualmente</strong></p></td>
<td><p>No</p></td>
<td><p>Indica el intervalo temporal seleccionado. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si está usando el intervalo de Cada día y hace clic en 7/7/2012, verá un desglose por horas de la actividad de registro del usuario correspondiente para esa fecha.</p></td>
</tr>
<tr class="even">
<td><p><strong>Llamadas recibidas</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de llamadas recibidas por todas las instancias de la aplicación Grupo de respuesta. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Llamadas correctas</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de llamadas respondidas por la aplicación Grupo de respuesta. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Llamadas ofrecidas</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de llamadas transferidas a un agente de Grupo de respuesta. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Llamadas contestadas</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de llamadas contestadas realmente por un agente de Grupo de respuesta. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de llamadas abandonadas</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de llamadas recibidas por la aplicación Grupo de respuesta que nunca contestó un agente. Este número se calcula restando las llamadas contestadas a las llamadas recibidas y, a continuación, dividiendo el valor obtenido entre el número de llamadas recibidas. Por ejemplo, si tiene 10 llamadas recibidas y siete no se contestaron, resta siete a 10, lo que da un resultado de tres llamadas no respondidas. A continuación, dicho valor se divide entre 10, con lo que obtiene un porcentaje de llamadas abandonadas del 30%.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Media de minutos de llamada por agente</strong></p></td>
<td><p>No</p></td>
<td><p>Media de tiempo que dedica cada agente de Grupo de respuesta a una llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Llamadas transferidas</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de llamadas de Grupo de repuesta transferidas porque se agotó un tiempo de espera de cola o porque una cola está desbordada. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

