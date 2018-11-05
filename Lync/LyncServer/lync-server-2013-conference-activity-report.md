---
title: 'Lync Server 2013: Informe de actividad de conferencia'
TOCTitle: Informe de actividad de conferencia
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48274677
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de actividad de conferencia en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El informe de actividad de conferencia le facilita que responda a preguntas como cuántas conferencias se están celebrando cada día y cuántas se celebran. La información como esta no es solo útil por sí misma sino también como herramienta de solución de problemas. Por ejemplo, supongamos que los usuarios se están quejando de que la red parece particularmente lenta a mitad del día. Un rápido vistazo a los informes de actividad de conferencia pueden sugerir una posible razón: se están programando muchas más conferencias entre las 10 de la mañana y las 2 de la tarde que en cualquier otra hora.

Si la red lenta está causando problemas, puede animar a los usuarios a reprogramar algunas de sus conferencias durante las horas de menor tráfico del día.

## Acceso al informe de actividad de conferencia

Al informe de actividad de conferencia se obtiene acceso desde el [Informe de resumen de conferencia en Lync Server 2013](lync-server-2013-conference-summary-report.md) haciendo clic en cualquiera de las siguientes métricas:

  - Total de conferencias

  - Total de participantes

## Aprovechar al máximo el informe de actividad de conferencia

De manera predeterminada, el informe de actividad de conferencia le muestra el número total de conferencias para el período de tiempo especificado (por ejemplo, el número total de conferencias por día o el número total de conferencias por hora del día). Sin embargo, puede elegir visualizar el número total de participantes para ese período de tiempo o el número total de minutos de participante. Para ello, haga clic en el botón Mostrar u ocultar parámetros para visualizar las opciones de filtrado y, a continuación, seleccione uno de los siguientes en la lista desplegable Informe por:

  - Recuento de participantes

  - Minutos de participantes

  - Recuento de conferencias

## Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de actividad de conferencia.

### Filtros del informe de actividad de conferencia

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
<p>Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 00:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hasta</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de finalización, el informe finalizará automáticamente a las 00:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
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
<p>Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/8/2012 y una fecha de finalización del 28/9/2012, aparecerán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</p></td>
</tr>
<tr class="even">
<td><p><strong>Informe por</strong></p></td>
<td><p>Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes:</p>
<ul>
<li><p>Recuento de participantes</p></li>
<li><p>Minutos de participante</p></li>
<li><p>Recuento de conferencias</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Métricas para conferencias por grupo

En la tabla siguiente, se muestra la información proporcionada en el informe de actividad de conferencia para cada grupo.

### Métricas para conferencias por grupo

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
<td><p><strong>Grupo de servidores</strong></p></td>
<td><p>N.º</p></td>
<td><p>Nombre del grupo de registradores o servidor perimetral utilizado en la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fecha y hora</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha y hora en que se desarrolló la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>N.º</p></td>
<td><p>Recuento total de participantes, minutos totales por participante o recuento total de conferencias.</p></td>
</tr>
</tbody>
</table>


## Métricas para conferencias por tipo de servidor

En la tabla siguiente, se muestra la información proporcionada en el informe de actividad de conferencia para cada tipo de servidor.

### Métricas para conferencias por tipo de servidor

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
<td><p><strong>Tipo de servidor de conferencia</strong></p></td>
<td><p>N.º</p></td>
<td><p>Tipo de servidor usado en la conferencia, generalmente, uno de los siguientes:</p>
<ul>
<li><p>Servidor de conferencia web</p></li>
<li><p>Servidor de conferencia de mensajería instantánea</p></li>
<li><p>Servidor de conferencia con telefonía</p></li>
<li><p>Servidor de conferencia A/V</p></li>
<li><p>Uso compartido de aplicaciones</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Fecha y hora</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha y hora en que se desarrolló la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>N.º</p></td>
<td><p>Recuento total de participantes, minutos totales por participante o recuento total de conferencias.</p></td>
</tr>
</tbody>
</table>

