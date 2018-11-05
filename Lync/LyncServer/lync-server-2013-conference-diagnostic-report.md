﻿---
title: 'Lync Server 2013: Informe de diagnósticos de conferencia'
TOCTitle: Informe de diagnósticos de conferencia
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48277052
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de diagnósticos de conferencia en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El Informe de diagnósticos de conferencia facilita información sobre las sesiones de conferencia que se han completado correctamente y las que han presentado algún error. Observe que Microsoft Lync Server distingue entre diferentes tipos de error:

  - **Error esperado** . Un error esperado es, generalmente, un error en el sentido más técnico. Por ejemplo, supongamos que alguien inicia una conferencia, pero la comunicación se cuelga antes de que otros usuarios puedan unirse a ella. Técnicamente, eso es un error: la conferencia se ha iniciado, pero no se ha completado. Sin embargo, es un error que cabe esperar que ocurra, porque si el organizador cancela la conferencia antes de que otros usuarios se unan a ella, no podemos esperar que la conferencia se complete.

  - **Error inesperado** . Un error inesperado es exactamente lo que su nombre sugiere: un error que, en las circunstancias actuales, no se espera que ocurra. Por ejemplo, una conferencia que no se puede llevar a cabo porque no se ha podido recuperar la directiva de reunión del organizador. Ese es un error inesperado ya que siempre se deberían poder recuperar las directivas de reunión de un usuario.

Observe que las métricas Correcta, Error esperado y Error inesperado podrían no incluirse en la métrica Total de sesiones. Por ejemplo, podría ver los siguientes valores en el informe:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Correctas</th>
<th>Errores esperados</th>
<th>Errores inesperados</th>
<th>Total de sesiones</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16</p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


Si sumamos 2024 + 469 + 16, obtenemos un total de 2.509 sesiones y, sin embargo, la columna Total de sesiones muestra 2.521 sesiones. Las 12 sesiones "que faltan" son las sesiones que el sistema no ha podido clasificar como de correcta ni de error. Estos casos pueden englobar los productos de terceros que introducen un código de diagnóstico nuevo, desconocido para el servidor de supervisión. Cuando esto ocurre, las llamadas realizadas mediante este producto que ocasionen ese código de diagnóstico no siempre se clasificarán como Correcta, Error esperado o Error inesperado.

## Acceso al Informe de diagnósticos de conferencia

Al Informe de diagnósticos de conferencia, se accede desde la página de inicio de Informes de supervisión. Puede acceder al [Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md) haciendo clic en cualquiera de las siguientes métricas:

  - Volumen de errores inesperados

  - Volumen de errores esperados

## Cómo hacer el mejor uso del Informe de diagnósticos de conferencia

El Informe de diagnósticos de conferencia incluye una serie de gráficos. Cada una de las columnas mostradas en el gráfico es, en realidad, un hipervínculo. Al hacer clic en una columna, accederá al [Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md) de ese período de tiempo y ese tipo de conferencia.

## Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el Informe de diagnósticos de conferencia le permite filtrar elementos tales como el tipo de conferencia que se realiza (por ejemplo, una conferencia basada en un tema) o por el servidor perimetral que se usa en la conferencia. También puede elegir cómo agrupar los datos. En este caso, las conferencias se agrupan por hora, día, semana o mes.

En la tabla siguiente se muestran los filtros que se pueden utilizar con el Informe de diagnósticos de conferencia

### Filtros del Informe de diagnósticos de conferencia

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
<td><p><strong>Grupo de servidores</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones de conferencia</strong></p></td>
<td><p>Indica el tipo de sesión de conferencia. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Sesiones de foco</p></li>
<li><p>Todas las sesiones de MCU</p></li>
<li><p>Conferencia de mensajería instantánea</p></li>
<li><p>Uso compartido de aplicaciones</p></li>
<li><p>Conferencia A/V</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Métricas

En la siguiente tabla se enumera la información proporcionada en el Informe de diagnósticos de conferencia para cada tipo de sesión de conferencia.

### Métricas del Informe de diagnósticos de conferencia

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
<td><p><strong>Volumen de corrección</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de conferencias correctas</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de corrección</strong></p></td>
<td><p>N.º</p></td>
<td><p>Porcentaje de conferencias que se realizaron con problemas considerables. Se calcula dividiendo el volumen de sesiones correctas por el total de sesiones.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volumen de errores esperados</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de conferencias donde ocurrió un &quot;error esperado&quot;.</p>
<p>Un error esperado es aquel que se prevé que vaya a producirse. Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de errores esperados</strong></p></td>
<td><p>N.º</p></td>
<td><p>Porcentaje de conferencias en las que se produjo un error esperado. Se calcula dividiendo el volumen de errores esperados por el total de sesiones.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volumen de errores inesperados</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de conferencias donde ocurrió un &quot;error inesperado&quot;.</p>
<p>Un error inesperado es aquel que se produce en un sistema que está aparentemente en buen estado. Por ejemplo, una llamada no debería finalizarse si el autor de la llamada está en espera. De ser así, dicha situación se identificaría como un error inesperado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de errores inesperados</strong></p></td>
<td><p>N.º</p></td>
<td><p>Porcentaje de conferencias en las que se produjo un error inesperado. Se calcula dividiendo el volumen de errores inesperados por el total de sesiones.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de sesiones</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de conferencias, incluyendo conferencias correctas, conferencias con errores (tanto errores esperados como inesperados) y conferencias no categorizadas.</p></td>
</tr>
</tbody>
</table>

