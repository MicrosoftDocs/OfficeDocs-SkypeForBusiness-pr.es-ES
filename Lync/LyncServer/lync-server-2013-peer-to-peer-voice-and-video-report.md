---
title: 'Lync Server 2013: Informe de voz y vídeo punto a punto'
TOCTitle: Informe de voz y vídeo punto a punto
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48276926
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de voz y vídeo punto a punto en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El Informe de voz y vídeo punto a punto da una visión detallada de la distribución de las llamadas de voz y de las videollamadas en un período de tiempo especificado (por ejemplo, llamadas por hora o llamadas por día). El informe también da la opción de visualizar todas las llamadas de voz y videollamadas que se efectuaron, o de visualizar únicamente las llamadas correctas o las erróneas. Los informes muestran la información de las llamadas desglosadas en las agrupaciones siguientes:

  - Llamadas por grupo de servidores

  - Llamadas por tipo de llamada (por ejemplo, una llamada de Lync a Lync comparada con una llamada de Lync a una persona que está en la red RTC)

  - Llamadas por tipo de acceso (los usuarios que iniciaron sesión en la red interna comparados con los usuarios que iniciaron sesión en la red externa)

  - Llamadas por Servidor de mediación

## Para obtener acceso al informe de voz y vídeo punto a punto

Acceda al informe de voz y vídeo punto a punto abriendo el Informe de resumen de actividad punto a punto y haciendo clic en una de las métricas siguientes:

  - Total de sesiones de audio punto a punto

  - Total de minutos de audio punto a punto

  - Total de sesiones de vídeo punto a punto

  - Total de minutos de vídeo punto a punto

## Para sacar el máximo provecho del informe de voz y vídeo punto a punto

Existen varias formas de filtrar el informe de voz y vídeo punto a punto. No obstante, normalmente esas opciones de filtrado están ocultas a la vista. Para ver las opciones de filtrado que tiene disponibles, haga clic en el botón **Mostrar u ocultar parámetros** en la esquina superior derecha de la ventana del informe.

## Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos de diferentes formas. En la siguiente tabla se enumeran los filtros que puede utilizar con el informe de voz y vídeo punto a punto.

### Filtros del informe de voz y vídeo punto a punto

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
<td><p><strong>Tipo de medio</strong></p></td>
<td><p>Indica el tipo de medio utilizado en la sesión. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Ambos</p></li>
<li><p>Audio</p></li>
<li><p>Vídeo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Disposición de llamada</strong></p></td>
<td><p>Indica el resultado de la sesión. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Llamadas correctas</p></li>
<li><p>Llamadas con error</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Informe por</strong></p></td>
<td><p>Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes:</p>
<ul>
<li><p>Recuento de sesiones</p></li>
<li><p>Minutos de la llamada</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Métricas de actividad de voz y vídeo punto a punto por grupo

En la siguiente tabla se enumera la información provista en el Informe de voz y vídeo punto a punto para cada grupo.

### Métricas de actividad de voz y vídeo punto a punto por grupo

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
<td><p>Nombre del Grupo de registradores o del Servidor perimetral utilizado para la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fecha y hora</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha/hora en que se produjo la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones o recuento total de mensajes.</p></td>
</tr>
</tbody>
</table>


## Métricas de actividad de voz y vídeo punto a punto por tipo de llamada

En la siguiente tabla se enumera la información proporcionada en el Informe de voz y vídeo punto a punto para cada tipo de llamada realizada.

### Métricas de actividad de voz y vídeo punto a punto por tipo de llamada

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
<td><p><strong>Tipo de llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Indica el tipo de llamada que se realizó. Los valores son uno de los siguientes:</p>
<ul>
<li><p>UC-a-UC</p></li>
<li><p>UC-a-PSTN</p></li>
<li><p>PSTN-a-UC</p></li>
<li><p>PSTN-a-PSTN</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Fecha y hora</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha/hora en que se produjo la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones o recuento total de mensajes.</p></td>
</tr>
</tbody>
</table>


## Métricas de actividad de voz y vídeo punto a punto por tipo de acceso

En la siguiente tabla se enumera la información proporcionada en el Informe de voz y vídeo punto a punto para cada tipo de acceso a la red.

### Métricas de actividad de voz y vídeo punto a punto por tipo de acceso

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
<td><p><strong>Tipo de actividad</strong></p></td>
<td><p>N.º</p></td>
<td><p>Indica si los clientes habían iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Generalmente, los valores son los siguientes:</p>
<ul>
<li><p>Interna</p></li>
<li><p>Externa</p></li>
<li><p>Mixta</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Fecha y hora</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha/hora en que se produjo la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones o recuento total de mensajes.</p></td>
</tr>
</tbody>
</table>


## Métricas de actividad de voz y vídeo punto a punto por servidor de mediación

En la siguiente tabla se enumera la información proporcionada en el Informe de voz y vídeo punto a punto para cada Servidor de mediación..

### Métricas de actividad de voz y vídeo punto a punto por servidor de mediación

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
<td><p><strong>Servidor de mediación</strong></p></td>
<td><p>N.º</p></td>
<td><p>Nombre del Servidor de mediación.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fecha y hora</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha/hora en que se produjo la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones o recuento total de mensajes.</p></td>
</tr>
</tbody>
</table>

