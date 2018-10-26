---
title: 'Lync Server 2013: Informe de mensajería instantánea punto a punto'
TOCTitle: Informe de mensajería instantánea punto a punto
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48274581
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de mensajería instantánea punto a punto en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El informe de mensajería instantánea punto a punto ofrece información de tendencias acerca de las sesiones de mensajería instantánea (MI) punto a punto, desglosadas por grupo de servidores y por tipo de autenticación. El informe puede mostrar el número total de sesiones mantenidas durante el período de tiempo especificado (por ejemplo, día a día u hora a hora) o bien, puede mostrar el número total de mensajes instantáneos enviados durante ese período de tiempo.

## Obtener acceso al informe de mensajería instantánea de punto a punto

Solo puede obtener acceso al informe de mensajería instantánea de punto a punto abriendo el [Informe de resumen de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) y, a continuación, haciendo clic en cualquiera de las siguientes métricas:

  - Total de sesiones de MI punto a punto

  - Total de mensajes instantáneos punto a punto

## Aprovechar al máximo el informe de mensajería instantánea de punto a punto

De manera predeterminada, el informe de mensajería instantánea de punto a punto le muestra el recuento de mensajes por hora (o día, en función de su configuración). Sin embargo, también puede elegir ver el día por sesiones por hora. Para ello, haga clic en **Mostrar u ocultar parámetros** en la esquina superior derecha de la ventana informes y, a continuación, haga clic en **Recuento de sesiones** en la lista **Informe por**.

## Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de mensajería instantánea punto a punto.

### Filtros del informe de mensajería instantánea punto a punto

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
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</p>
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
<p>Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio 7/7/2012 y una fecha de finalización 28/2/2012, se mostrarán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</p></td>
</tr>
<tr class="even">
<td><p><strong>Informe por</strong></p></td>
<td><p>Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes:</p>
<ul>
<li><p>Recuento de sesiones</p></li>
<li><p>Recuento de mensajes</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Métricas para la mensajería instantánea punto a punto por grupo

En la tabla siguiente, se muestra la información proporcionada en el informe de mensajería instantánea punto a punto.

### Métricas para la mensajería instantánea punto a punto por grupo

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
<td><p>Nombre del Grupo de registradores o del Servidor perimetral.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fecha y hora</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha y hora en las que tuvo lugar la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones o recuento total de mensajes.</p></td>
</tr>
</tbody>
</table>


## Métricas para la mensajería instantánea punto a punto por tipo de autenticación

En la tabla siguiente, se muestra la información proporcionada en el informe de mensajería instantánea punto a punto para cada tipo de autenticación utilizado por los participantes de una sesión punto a punto.

### Métricas para la mensajería instantánea punto a punto por tipo de autenticación

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
<td><p><strong>Tipo de autenticación</strong></p></td>
<td><p>N.º</p></td>
<td><p>Tipo de autenticación utilizado por los participantes de la sesión. Los valores suelen ser los siguientes:</p>
<ul>
<li><p>Enterprise</p></li>
<li><p>Federado</p></li>
<li><p>PIC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Fecha y hora</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha y hora en las que tuvo lugar la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones o recuento total de mensajes.</p></td>
</tr>
</tbody>
</table>

