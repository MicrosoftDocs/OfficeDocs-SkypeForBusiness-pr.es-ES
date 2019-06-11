---
title: 'Lync Server 2013: informe Resumen de calidad de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c967c6d6b120c73cb933281d4edb17be1868900
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a>Informe Resumen de calidad de medios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-06-29_

El Informe de resumen de calidad de medios es, quizás, la mejor opción para analizar la calidad de las llamadas en su organización: este informe proporciona métricas de llamadas de calidad de la experiencia (QoE) detalladas y desglosadas en las siguientes categorías:

  - Llamadas de par a par de UC (como una llamada de Microsoft Lync 2013 a Microsoft Lync 2013)

  - Sesiones de conferencia de UC

  - Sesiones de conferencia de RTC

  - Llamadas RTC: desvío de medios

  - Llamadas RTC (sin desvío): sección de UC

  - Llamadas RTC (sin desvío): sección de puerta de enlace

  - Otros tipos de llamada

Al abrir el informe por primera vez, se ve la información de resumen de cada una de estas categorías. Sin salir del informe, puede expandir cada categoría para ver subcategorías, como las llamadas realizadas desde Office Communicator 2007 R2 a Lync 2013. A su vez, puede profundizar en esas subcategorías para ver detalles sobre cada llamada realizada dentro de esa subcategoría.

En Microsoft Lync Server 2013, el informe Resumen de la calidad de medios también divide los datos en tres tipos de llamadas: llamadas de audio, videollamadas y llamadas de uso compartido de aplicaciones. Cada tipo de llamada tiene su propia sección en el informe y su propio conjunto personalizado de métricas de llamada.

El Informe de resumen de calidad de medios también permite aplicar filtros para poder comparar la calidad de las llamadas: llamadas por cable frente a inalámbricas, llamadas internas frente a externas y llamadas de VPN frente a llamadas distintas de VPN.

<div>

## <a name="accessing-the-media-quality-summary-report"></a>Acceso al Informe de resumen de calidad de medios

Al Informe de resumen de calidad de medios se obtiene acceso desde la página principal de Informes de supervisión. Puede explorar en profundidad el [Informe de la lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) haciendo clic en cualquiera de las siguientes métricas:

  - Volumen de llamadas

  - Porcentaje de llamadas deficientes

Además, puede obtener acceso al Informe de resumen de calidad de medios haciendo clic en cualquiera de las siguientes métricas de llamadas de audio:

  - Recorrido de ida y vuelta (ms)

  - Degradación (MOS)

  - Pérdida de paquetes

  - Vibración (ms)

  - Tasa de recuperación de muestras ocultas

  - Tasa de recuperación de muestras extendidas

  - Tasa de recuperación de muestras comprimidas

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de resumen de calidad de los medios permite filtrar los datos devueltos por el tipo de acceso (acceso interno o externo) o por tipo de conexión de red (cableada o inalámbrica). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.

En la tabla siguiente se muestran los filtros que se pueden utilizar en el informe de resumen de calidad de los medios.

### <a name="media-quality-summary-report-filters"></a>Filtros del informe de resumen de calidad de los medios

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
<td><p><strong>Tipo de acceso</strong></p></td>
<td><p>Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Interno</p></li>
<li><p>Externo</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de red</strong></p></td>
<td><p>Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Cableada</p></li>
<li><p>Inalámbrica</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>VPN</p></li>
<li><p>Distinto de VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de resumen de calidad de los medios.

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a>Métricas del Informe de resumen de calidad de medios: resumen de llamadas de audio

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
<td><p><strong>Tipo de llamada/tipo de extremo</strong></p></td>
<td><p>No</p></td>
<td><p>Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son:</p>
<ul>
<li><p>Llamadas de punto a punto de UC</p></li>
<li><p>Sesiones de conferencia de UC</p></li>
<li><p>Sesiones de conferencia de RTC</p></li>
<li><p>Llamadas RTC: desvío de medios</p></li>
<li><p>Llamadas RTC (sin desvío): sección de UC</p></li>
<li><p>Llamadas RTC (sin desvío): sección de puerta de enlace</p></li>
<li><p>Otros tipos de llamada</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Volumen de llamadas</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas por tipo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de llamadas deficientes</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la que al menos uno de los valores medidos supera el valor permitido, por ejemplo, una llamada con un exceso de vibraciones.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volumen de llamadas (llamada inalámbrica)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas que ha empleado una conexión inalámbrica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volumen de llamadas (llamada VPN)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas que ha empleado una conexión VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volumen de llamadas (llamada externa)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad de llamadas que ha empleado una conexión externa, es decir, una conexión fuera de la red interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Recorrido de ida y vuelta (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.</p>
<p>Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradación (MOS)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0. Un valor de 0,5 o menos constituye una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. En Lync Server, Lync Server usa un conjunto de algoritmos para predecir cómo los usuarios habrían calificado una llamada.</p>
<p>Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pérdida de paquetes</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</p></td>
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


### <a name="media-quality-summary-report-metrics-video-call-summary"></a>Métricas del Informe de resumen de calidad de medios: resumen de videollamadas

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
<td><p><strong>Tipo de llamada/tipo de extremo</strong></p></td>
<td><p>No</p></td>
<td><p>Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son:</p>
<ul>
<li><p>Llamadas de punto a punto de UC</p></li>
<li><p>Sesiones de conferencia de UC</p></li>
<li><p>Sesiones de conferencia de RTC</p></li>
<li><p>Llamadas RTC: desvío de medios</p></li>
<li><p>Llamadas RTC (sin desvío): sección de UC</p></li>
<li><p>Llamadas RTC (sin desvío): sección de puerta de enlace</p></li>
<li><p>Otros tipos de llamada</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Volumen de llamadas</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas por tipo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de llamadas deficientes</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la que al menos uno de los valores medidos supera el valor permitido, por ejemplo, una llamada con un exceso de vibraciones.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volumen de llamadas (llamada inalámbrica)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas que ha empleado una conexión inalámbrica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volumen de llamadas (llamada VPN)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas que ha empleado una conexión VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volumen de llamadas (llamada externa)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad de llamadas que ha empleado una conexión externa, es decir, una conexión fuera de la red interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Velocidad de bits media (Kbits/s)</strong></p></td>
<td><p>No</p></td>
<td><p>Velocidad de bits de vídeo media (en kilobits por segundo).</p></td>
</tr>
<tr class="even">
<td><p><strong>% de velocidad de bits baja</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de la llamada con una velocidad de bits baja.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pérdida de paquetes de salida</strong></p></td>
<td><p>No</p></td>
<td><p>Pérdida de paquetes del Protocolo de transporte en tiempo real (RTP) correspondiente a los paquetes salientes (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, la falta de ancho de banda, la congestión o las interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>% fotogramas congelados</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de fotogramas "congelados". En un fotograma congelado, el vídeo detiene su avance mientras que la parte de audio de la llamada continúa.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Velocidad de fotogramas media de salida</strong></p></td>
<td><p>No</p></td>
<td><p>Velocidad de fotogramas media para las transmisiones de salida durante la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Velocidad de fotogramas media de entrada</strong></p></td>
<td><p>No</p></td>
<td><p>Velocidad de fotogramas media para las transmisiones de entrada durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>% de velocidad de fotogramas baja de entrada</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de la llamada con una velocidad de bits baja para el vídeo de entrada.</p></td>
</tr>
<tr class="even">
<td><p><strong>% de estado del cliente</strong></p></td>
<td></td>
<td><p>Indica el estado relativo del dispositivo cliente durante la llamada.</p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a>Métricas del Informe de resumen de calidad de medios: resumen de llamadas de uso compartido de aplicaciones

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
<td><p><strong>Tipo de llamada/tipo de extremo</strong></p></td>
<td><p>No</p></td>
<td><p>Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son:</p>
<ul>
<li><p>Llamadas de punto a punto de UC</p></li>
<li><p>Sesiones de conferencia de UC</p></li>
<li><p>Sesiones de conferencia de RTC</p></li>
<li><p>Llamadas RTC: desvío de medios</p></li>
<li><p>Llamadas RTC (sin desvío): sección de UC</p></li>
<li><p>Llamadas RTC (sin desvío): sección de puerta de enlace</p></li>
<li><p>Otros tipos de llamada</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Volumen de llamadas</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas por tipo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de llamadas deficientes</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la que al menos uno de los valores medidos supera el valor permitido, por ejemplo, una llamada con un exceso de vibraciones.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volumen de llamadas (llamada inalámbrica)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas que ha empleado una conexión inalámbrica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volumen de llamadas (llamada VPN)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas que ha empleado una conexión VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volumen de llamadas (llamada externa)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad de llamadas que ha empleado una conexión externa, es decir, una conexión fuera de la red interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Vibración (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevada suelen estar causados por una congestión o un servidor multimedia sobrecargado y tienen como resultado una distorsión o pérdida de audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Unidireccional relativo medio</strong></p></td>
<td><p>No</p></td>
<td><p>Retraso unidireccional relativo medio entre dos extremos de medios. Es una medición de la latencia de un solo salto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Latencia media de procesamiento de iconos RDP</strong></p></td>
<td><p>No</p></td>
<td><p>La latencia media de procesamiento de iconos RDP en el servidor de conferencias AS durante el transcurso de la sesión de visualización. Una media alta refleja un retraso mayor en la experiencia de visualización e incluye latencia de red. Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos.</p></td>
</tr>
<tr class="even">
<td><p><strong>% total de iconos dañados</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje total de iconos RDP dañados.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

