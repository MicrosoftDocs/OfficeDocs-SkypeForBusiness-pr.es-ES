---
title: 'Lync Server 2013: informe de comparación de calidad multimedia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bcec69db6154aa346fc4545dc3b50fcfe0f2d6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a>Informe de comparación de calidad multimedia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-22_

El informe de comparación de calidad de medios sirve para comparar los valores de calidad de diferentes tipos de llamadas de audio (por ejemplo, de las llamadas realizadas en una red inalámbrica frente a las que usan una conexión cableada).

<div>

## <a name="accessing-the-media-quality-comparison-report"></a>Obtener acceso al informe de comparación de calidad de medios

Al informe de comparación de calidad de medios se obtiene acceso desde la página principal de informes de supervisión.

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos que se devuelven de distintas formas. En la tabla siguiente se muestran los filtros que puede usar en el informe.

### <a name="media-quality-comparison-report-filters"></a>Filtros del informe de comparación de calidad de medios

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
<td><p><strong>Llamadas</strong></p></td>
<td><p>Tipo de llamada que se va a usar como elemento de comparación principal. Los valores permitidos son:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Externa</p></li>
<li><p>Interna</p></li>
<li><p>VPN</p></li>
<li><p>Distinto de VPN</p></li>
<li><p>Cableada</p></li>
<li><p>Inalámbrica</p></li>
<li><p>Externa y cableada</p></li>
<li><p>Externa e inalámbrica</p></li>
<li><p>Externa y VPN</p></li>
<li><p>Externa y distinta de VPN</p></li>
<li><p>Interna y cableada</p></li>
<li><p>Interna e inalámbrica</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Comparar con llamadas</strong></p></td>
<td><p>Tipo de llamada que se va a usar como elemento de comparación secundario. Los valores permitidos son:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Externa</p></li>
<li><p>Interna</p></li>
<li><p>VPN</p></li>
<li><p>Distinto de VPN</p></li>
<li><p>Cableada</p></li>
<li><p>Inalámbrica</p></li>
<li><p>Externa y cableada</p></li>
<li><p>Externa e inalámbrica</p></li>
<li><p>Externa y VPN</p></li>
<li><p>Externa y distinta de VPN</p></li>
<li><p>Interna y cableada</p></li>
<li><p>Interna e inalámbrica</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalo</strong></p></td>
<td><p>Intervalo de tiempo. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Cada hora (se puede ver un máximo de 25 horas)</p></li>
<li><p>Cada día (se puede ver un máximo de 31 días)</p></li>
<li><p>Cada semana (se puede ver un máximo de 12 semanas)</p></li>
</ul>
<p>Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de comparación de calidad de medios.

### <a name="media-quality-comparison-report-metrics"></a>Métricas del informe de comparación de calidad de medios

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
<td><p><strong>Volumen de llamadas</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradación (MOS)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad promedio de la degradación de la media (puntuación de opinión) durante una llamada. Los valores de degradación pueden oscilar entre un mínimo de 0,0 y un alto de 5,0. un valor de 0,5 o menos representa una degradación aceptable. Históricamente, los resultados de la media se calcularon haciendo que los usuarios calificaran la calidad de una llamada en una escala de 1 a 5. Lync Server usa un conjunto de algoritmos para predecir cómo los usuarios habrían calificado una llamada.</p>
<p>Los valores elevados de degradación pueden ser producto de la congestión, la falta de ancho de banda, la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un extremo o servidor multimedia. Una degradación elevada causa la distorsión o la pérdida del audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de llamadas deficientes</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella en la que al menos uno de los valores medidos supera el valor permitido (por ejemplo, una llamada con un exceso de vibraciones).</p></td>
</tr>
<tr class="even">
<td><p><strong>Recorrido de ida y vuelta (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</p>
<p>Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pérdida de paquetes</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Vibración (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevada suelen estar causados por una congestión o un servidor multimedia sobrecargado y tienen como resultado una distorsión o pérdida de audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasa de recuperación de muestras ocultas</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de muestras de audio ocultas respecto a la cantidad total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tasa de recuperación de muestras extendidas</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de muestras de audio extendidas respecto a la cantidad total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasa de recuperación de muestras comprimidas</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de muestras de audio comprimidas respecto a la cantidad total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

