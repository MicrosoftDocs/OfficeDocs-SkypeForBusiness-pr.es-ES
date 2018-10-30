﻿---
title: 'Lync Server 2013: Informe de resumen de conferencia RTC'
TOCTitle: Informe de resumen de conferencia RTC
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48275972
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de resumen de conferencia RTC en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En Microsoft Lync Server 2013, una conferencia RTC es cualquier conferencia en la que al menos un participante accede por teléfono a la parte de audio utilizando un teléfono RTC (red telefónica conmutada). (Un teléfono RTC es un teléfono fijo, un teléfono móvil o cualquier otro teléfono que no utilice voz sobre IP). Aunque en los informes de supervisión se denominan conferencias RTC, son más conocidas como conferencias de acceso telefónico.

El informe de resumen de conferencias RTC proporciona información acerca de todas las conferencias RTC mantenidas en su organización (es decir, todas las conferencias en las que hubo al menos un usuario de acceso telefónico). El informe incluye información acerca del número total de conferencias RTC, el número total de personas que participaron en dichas conferencias y, quizás lo más importante, el número total de usuarios de acceso telefónico (métrica Total de participantes RTC).

## Acceso al informe de resumen de conferencias RTC

El informe de resumen de conferencias RTC solo es accesible desde la página principal de informes de supervisión. Este informe no está vinculado a ningún otro informe. Tenga en cuenta que no se puede recuperar información detallada sobre llamadas para una conferencia RTC, en parte debido a que los responsables de enviar esta información son extremos individuales. Los teléfonos RTC no pueden realizar el seguimiento ni enviar información detallada sobre llamadas.

## Optimización del uso del informe de resumen de conferencias RTC

Para determinar el porcentaje de todas las conferencias que incluyen usuarios de acceso telefónico, compare el valor de la métrica Total de conferencias RTC con la métrica Total de conferencias que se encuentra en el [Informe de resumen de conferencia en Lync Server 2013](lync-server-2013-conference-summary-report.md).

Si no ve el número de conferencias RTC que esperaba ver, tenga en cuenta que la capacidad para organizar una conferencia que admita usuarios de acceso telefónico depende de la directiva de conferencias que se haya asignado a un usuario; si muy pocos usuarios pueden organizar conferencias RTC, obviamente verá pocas conferencias RTC. Para comprobar rápidamente cuáles de las directivas de conferencias (si hubiera) permiten a los usuarios programar conferencias RTC, ejecute el siguiente comando desde el Shell de administración de Lync Server:

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

Se devolverán datos similares a estos:

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

Se devolverán datos similares a estos:

## Filtros

Los filtros constituyen un modo de obtener un conjunto de datos más acorde con lo que se busca o de ver los datos devueltos de diversas formas. Por ejemplo, el informe de resumen de conferencia RTC permite elegir el modo en que los datos deben agruparse (en este caso, las conferencias se agrupan por hora, día, semana o mes).

La siguiente tabla contiene los filtros que se pueden usar con el informe de resumen de conferencia RTC.

### Filtros del informe de resumen de conferencia RTC

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
<p>7/7/2012 13:00</p>
<p>Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 00:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>07.07.12</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>03.07.12</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hasta</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</p>
<p>7/7/2012 13:00</p>
<p>Si no escribe una hora de finalización, el informe finalizará automáticamente a las 00:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>07.07.12</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>03.07.12</p>
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
</tbody>
</table>


## Métricas

La siguiente tabla contiene la información que recoge el informe de resumen de conferencia RTC.

### Métricas del informe de resumen de conferencia RTC

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
<td><p><strong>Total de conferencias RTC</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de conferencias donde se permitió el acceso telefónico.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de participantes</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de personas que participaron en conferencias donde se permitió el acceso telefónico.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de minutos de conferencia A/V</strong></p></td>
<td><p>N.º</p></td>
<td><p>Tiempo total de la conferencia audiovisual.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de minutos de participantes en conferencia A/V</strong></p></td>
<td><p>N.º</p></td>
<td><p>Tiempo total de participación en la conferencia audiovisual. Por ejemplo, si un participante invirtió cinco minutos en una conferencia A/V y otro, tres minutos en la misma conferencia, el tiempo total de participantes en dicha conferencia será de ocho minutos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de participantes RTC</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de usuarios que accedió telefónicamente en conferencias donde se permitió el acceso telefónico.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de minutos de participantes RTC</strong></p></td>
<td><p>N.º</p></td>
<td><p>Tiempo total que los usuarios de acceso telefónico dedicaron a la conferencia. Por ejemplo, si un participante de acceso telefónico invirtió cinco minutos en una conferencia A/V y otro, tres minutos en la misma conferencia, el tiempo total de participantes RTC será de ocho minutos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizadores de conferencia distintos</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de usuarios que organizaron al menos una conferencia donde se permitió el acceso telefónico. Los usuarios que hayan organizado más de una conferencia se consideran como un único organizador, igual que los que solo han organizado una conferencia.</p></td>
</tr>
</tbody>
</table>

