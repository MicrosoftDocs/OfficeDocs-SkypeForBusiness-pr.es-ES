---
title: 'Lync Server 2013: Informe de uso del grupo de respuesta'
TOCTitle: Informe de uso del grupo de respuesta
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48274872
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de uso del grupo de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La aplicación Grupo de respuesta permite que Microsoft Lync Server 2013 conteste y enrute llamadas telefónicas basándose en el número marcado y, de manera opcional, en la respuesta del autor de la llamada a una serie de preguntas. Por lo general, las llamadas de Grupo de respuesta no se enrutan a una persona concreta, sino a un equipo de personas denominadas "grupo de agentes". Por ejemplo, si alguien llama al número de teléfono de su servicio de asistencia técnica, Lync Server 2013 puede enrutar automáticamente esa llamada al primer agente de asistencia técnica que se quede disponible. Otra opción es que Lync Server haga una serie de preguntas ("Presione 1 si tiene problemas de hardware. Presione 2 si tiene problemas de software. Presione 3 si tiene problemas de red.") y luego enrute la llamada al agente de asistencia técnica más apropiado según la respuesta a dichas preguntas.

El Informe de uso del grupo de respuesta ofrece una perspectiva detallada del número de llamadas de teléfono que se han recibido en todos los flujos de trabajo de grupo de respuesta y, a continuación, separa dichas llamadas en categorías finitas como, por ejemplo, Llamadas ofrecidas, Llamadas contestadas o Llamadas abandonadas.

La clave para trabajar con el Informe de uso del grupo de respuesta está en comprender la diferencia entre los tipos de llamadas incluidas en el informe:

  - **Llamadas recibidas**. Número total de llamadas recibidas por todas las instancias de la aplicación Grupo de respuesta.

  - **Llamadas correctas**. Número total de llamadas respondidas por la aplicación Grupo de respuesta.

  - **Llamadas ofrecidas**. Número total de llamadas transferidas a un agente de Grupo de respuesta.

  - **Llamadas contestadas**. Número total de llamadas contestadas realmente por un agente de Grupo de respuesta.

  - **Porcentaje de llamadas abandonadas**. Porcentaje de llamadas recibidas por la aplicación Grupo de respuesta que nunca contestó un agente. Este valor se calcula restando las llamadas contestadas a las llamadas recibidas y, a continuación, dividiendo el valor obtenido entre el número de Llamadas recibidas. Por ejemplo, si se han recibido 10 llamadas y 7 no se contestaron, debe restar 7 a 10, lo que da un resultado de 3 llamadas no respondidas. A continuación, dicho valor se divide entre 10, con lo que obtiene un porcentaje de llamadas abandonadas del 30%.

  - **Llamadas transferidas**. Número total de llamadas de Grupo de repuesta transferidas porque se agotó un tiempo de espera de cola o porque una cola está desbordada.

Si no recuerda la definición de los tipos de llamadas del Informe de uso del grupo de respuesta, basta con mantener el mouse sobre la etiqueta del tipo de llamada correspondiente. Aparecerá una información sobre herramientas con una descripción breve del tipo de llamada.

El Informe de uso del grupo de respuesta permite filtrar URI de flujos de trabajo (dirección SIP asociada a dicho flujo de trabajo). Sin embargo, los URI de flujos de trabajo no se muestran en el informe. Si desea conocer aspectos como, por ejemplo, qué flujos de trabajo están respondiendo a la mayoría de las llamadas o qué flujos de trabajo están transfiriendo más llamadas, haga clic en la métrica correspondiente para abrir el Informe de lista de llamadas de grupo de respuesta para dicho periodo. Este informe no muestra los URI de flujos de trabajo.

## Acceso al Informe de uso del grupo de respuesta

Es posible tener acceso al Informe de uso del grupo de respuesta desde la página de inicio de informes de supervisión. Puede obtener más detalles sobre el [Informe de lista de llamadas de grupo de respuesta en Lync Server 2013](lync-server-2013-response-group-call-list-report.md) haciendo clic en cualquiera de las métricas siguientes:

  - Llamadas recibidas

  - Llamadas correctas

  - Llamadas ofrecidas

  - Llamadas contestadas

  - Llamadas transferidas

## Cómo sacar el máximo partido al Informe de uso del grupo de respuesta

Uno de los usos más interesantes del Informe de uso del grupo de respuesta puede no resultar obvio a primera vista: la capacidad para recuperar información sobre el uso de un único flujo de trabajo de grupo de respuesta.

> [!WARNING]  
> Básicamente, un flujo de trabajo de grupo de respuesta es un conjunto de instrucciones que determina qué acción lleva a cabo Lync Server cuando un usuario llama a un número de teléfono determinado. Para ello, cada flujo de trabajo está asociado a un único número de teléfono. Cuando alguien llama a dicho número, el flujo de trabajo determina cómo se administrará la llamada. Por ejemplo, el flujo de trabajo puede enrutar la llamada a través de una serie de preguntas de respuesta de voz interactiva (IVR) que indican al autor de la llamada que debe especificar información adicional (&quot;Presione 1 si necesita asistencia para hardware. Presione 2 si necesita asistencia para software.&quot;). De forma alternativa, el flujo de trabajo también puede poner la llamada en cola y mantener al autor de la llamada en espera hasta que haya un agente disponible para atender la llamada. La disponibilidad de los agentes para responder a llamadas también está determinada por el flujo de trabajo: los flujos de trabajo se usan para configurar el horario laboral (días de la semana y horas del día en que los agentes están disponibles para responder a llamadas) y los festivos (días en los que no hay agentes disponibles para responder a llamadas). Cuando realiza llamadas a números de teléfono que pertenecen a una aplicación de grupo de respuesta, básicamente está llamando a un flujo de trabajo de grupo de respuesta.



Aunque los URI de los flujos de trabajo no se muestran en el Informe de uso del grupo de respuesta, pueden verse las estadísticas de uso de un flujo de trabajo determinado, cosa que a menudo es de gran utilidad. Por ejemplo, supongamos que ha lanzado una nueva campaña publicitaria y tiene curiosidad por saber si se están registrando llamadas para obtener información sobre el producto. Si tiene un flujo de trabajo de grupo de respuesta asociado al número de teléfono de la campaña publicitaria, podrá comprobar fácilmente cuántas personas están llamando a dicho número.

Puede utilizar un enfoque similar para evaluar el número de llamadas atendidas por su servicio de asistencia interno o por el departamento de atención al cliente.

Para revisar las estadísticas de uso de un flujo de trabajo determinado, escriba el URI del flujo de trabajo en el cuadro URI de flujo de trabajo. Tal como se ha mencionado, los URI de flujos de trabajo (dirección SIP asociada a un flujo de trabajo) no se muestran en el informe. Esto implica que deberá buscar otra forma de determinar el URI de un flujo de trabajo. Una forma de llevar a cabo esta tarea es mediante el Windows PowerShell y el Shell de administración de Lync Server. Por ejemplo, este comando devuelve los URI de todos los flujos de trabajo de grupo de respuesta:

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

Se devolverán datos similares a estos:

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

Este comando devuelve información de un único flujo de trabajo, el flujo de trabajo con el nombre New Ad Campaign:

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

## Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de uso del grupo de respuesta le permite ver datos de todos los flujos de trabajo del grupo de respuesta o ver datos de un flujo de trabajo concreto. También se puede elegir cómo agrupar los datos. En este caso, los usos se agrupan por hora, día, semana o mes.

En la tabla siguiente se muestran los filtros que se pueden utilizar en el informe de uso del grupo de respuesta.

### Filtros del informe de uso del grupo de respuesta

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
<td><p><strong>Desde</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 AM del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hasta</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 AM del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalo</strong></p></td>
<td><p>Intervalo de tiempo. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Cada hora (se puede ver un máximo de 25 horas)</p></li>
<li><p>Cada día (se puede ver un máximo de 31 días)</p></li>
<li><p>Cada semana (se puede ver un máximo de 12 semanas)</p></li>
<li><p>Cada mes (se puede ver un máximo de 12 meses)</p></li>
</ul>
<p>Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/7/2012 y una fecha de finalización del 2/28/2012, aparecerán los datos correspondientes a los días entre el 8/7/2012 12:00 AM y el 9/7/2012 12:00 AM (es decir, datos para un total de 31 días).</p></td>
</tr>
<tr class="even">
<td><p><strong>URI de flujo de trabajo</strong></p></td>
<td><p>Permite limitar los datos devueltos al flujo de trabajo de grupo de respuesta especificado. Para usar este filtro, escriba la dirección SIP del grupo de trabajo. Por ejemplo:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
</tbody>
</table>


## Métricas

En la tabla siguiente se muestra la información que recoge el informe de uso del grupo de respuesta.

### Métricas del informe de uso del grupo de respuesta

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
<td><p><strong>Cada hora</strong></p>
<p><strong>Cada día</strong></p>
<p><strong>Cada semana</strong></p>
<p><strong>Cada mes</strong></p></td>
<td><p>N.º</p></td>
<td><p>Indica el intervalo temporal seleccionado. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si está usando el intervalo de Cada día y hace clic en 7/7/2012, verá un desglose por horas de la actividad de registro del usuario correspondiente para esa fecha.</p></td>
</tr>
<tr class="even">
<td><p><strong>Llamadas recibidas</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de llamadas recibidas por todas las instancias de la aplicación Grupo de respuesta. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Llamadas correctas</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de llamadas respondidas por la aplicación Grupo de respuesta. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Llamadas ofrecidas</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de llamadas transferidas a un agente de Grupo de respuesta. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Llamadas contestadas</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de llamadas contestadas realmente por un agente de Grupo de respuesta. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de llamadas abandonadas</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de llamadas recibidas por la aplicación Grupo de respuesta que nunca contestó un agente. Este número se calcula restando las llamadas contestadas a las llamadas recibidas y, a continuación, dividiendo el valor obtenido entre el número de llamadas recibidas. Por ejemplo, si tiene 10 llamadas recibidas y siete no se contestaron, resta siete a 10, lo que da un resultado de tres llamadas no respondidas. A continuación, dicho valor se divide entre 10, con lo que obtiene un porcentaje de llamadas abandonadas del 30%.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Media de minutos de llamada por agente</strong></p></td>
<td><p>N.º</p></td>
<td><p>Media de tiempo que dedica cada agente de Grupo de respuesta a una llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Llamadas transferidas</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de llamadas de Grupo de repuesta transferidas porque se agotó un tiempo de espera de cola o porque una cola está desbordada. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</p></td>
</tr>
</tbody>
</table>

