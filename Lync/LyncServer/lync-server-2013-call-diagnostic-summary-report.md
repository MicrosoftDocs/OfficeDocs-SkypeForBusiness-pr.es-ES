﻿---
title: 'Lync Server 2013: Informe de resumen de diagnósticos de llamadas'
TOCTitle: Informe de resumen de diagnósticos de llamadas
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48276018
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de resumen de diagnósticos de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El informe de resumen de diagnósticos de llamadas proporciona un resumen general de las sesiones de punto a punto y las sesiones de conferencia con errores. El informe muestra el porcentaje general de errores para ambos tipos de sesiones y desglosa la información sobre los errores por tipo de modalidad de sesión:

  - Mensajería instantánea

  - Uso compartido de aplicaciones

  - Transferencia de archivos

  - Audio

  - Vídeo

## Acceso al informe de resumen de diagnósticos de llamadas

El informe de resumen de diagnósticos de llamadas es accesible desde la página principal de informes de supervisión. Desde el informe de resumen de diagnóstico de llamadas puede acceder al [Informe de diagnóstico de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) haciendo clic en la métrica Porcentaje de errores en la sección Resumen de sesiones de punto a punto del informe. También puede acceder al [Informe de diagnósticos de conferencia en Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) haciendo clic en las siguientes métricas de conferencia:

  - Porcentaje de errores de sesión generales

  - Porcentaje de errores de foco

  - Porcentaje de errores de MCU

## Optimización del uso del informe de resumen de diagnósticos de llamadas

El informe de resumen de diagnóstico de llamadas incluye gráficos que comparan los porcentajes de error de las distintas modalidades usadas en Microsoft Lync Server 2013. Las columnas de estos gráficos en realidad son vínculos activos; por ejemplo, si hace clic en la columna Mensajería instantánea de las sesiones punto a punto, irá a una instancia del [Informe de diagnóstico de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), que proporciona información adicional sobre todas las sesiones de mensajería instantánea incluidas en el informe de resumen de diagnósticos de llamadas.

## Filtros

Los filtros constituyen un modo de obtener un conjunto de datos más acorde con lo que se busca o de ver los datos devueltos de diversas formas. Por ejemplo, el informe de resumen de diagnósticos de llamadas permite filtrar por elementos como el grupo de registradores o el servidor perimetral empleado en la sesión. También puede elegir el modo en que los datos deben agruparse (en este caso, las llamadas se agrupan por hora, día, semana o mes).

En la siguiente tabla se muestran los filtros que se pueden usar en el informe de resumen de diagnósticos de llamadas.

### Filtros del informe de resumen de diagnósticos de llamadas

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
<td><p><strong>Grupo de servidores</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</p></td>
</tr>
</tbody>
</table>


## Métricas de las sesiones punto a punto

En la siguiente tabla se muestra la información recogida el informe de resumen de diagnósticos de llamadas de las sesiones punto a punto (esto es, sesiones en las que solo participan dos usuarios).

### Métricas de las sesiones punto a punto

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
<td><p><strong>Total de sesiones</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones punto a punto que ha tenido lugar.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de errores</strong></p></td>
<td><p>N.º</p></td>
<td><p>Porcentaje de las sesiones punto a punto con errores. Al hacer clic en este elemento, el informe muestra el informe de diagnósticos de actividad punto a punto, que contiene información más detallada sobre las sesiones punto a punto con errores.</p></td>
</tr>
</tbody>
</table>


## Métricas de las sesiones de conferencia

En la siguiente tabla se muestra la información recogida el informe de resumen de diagnósticos de llamadas de las sesiones de conferencia (esto es, sesiones en las que participan tres o más usuarios).

### Métricas de las sesiones de conferencia

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
<td><p><strong>Total de conferencias</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de conferencias que ha tenido lugar.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sesiones de conferencias</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones de conferencia que ha tenido lugar.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores de sesión generales</strong></p></td>
<td><p>N.º</p></td>
<td><p>Porcentaje del total de sesiones de conferencia con errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones de foco</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de las sesiones de conferencia basadas en foco con errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores de foco</strong></p></td>
<td><p>N.º</p></td>
<td><p>Porcentaje de las sesiones de conferencia basadas en foco con errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones MCU</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de conferencias basadas en servidor de conferencia (antes denominadas unidades de control multipunto o MCU) con errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores de MCU</strong></p></td>
<td><p>N.º</p></td>
<td><p>Porcentaje de las conferencias basadas en servidor de conferencia (antes denominadas unidades de control multipunto o MCU) con errores.</p></td>
</tr>
</tbody>
</table>

