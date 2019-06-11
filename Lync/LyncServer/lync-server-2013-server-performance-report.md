---
title: 'Lync Server 2013: informe de rendimiento del servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5a08104f33fc07d6a0ec1c3241a7f14fa1227a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a>Informe de rendimiento del servidor en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

El informe rendimiento del servidor proporciona una lista de servidores de Microsoft Lync Server 2013 que han experimentado el mayor porcentaje de llamadas inadecuadas. El informe desglosa los servidores por tipo de servidor y notifica diferentes estadísticas para los siguientes tipos:

  - Servidor de mediación

  - Servidor de conferencia A/V

  - Servidor perimetral A/V

  - Puerta de enlace (servidor de mediación)

  - Puerta de enlace (desvío del servidor de mediación)

  - Vídeo (incluye métricas de vídeo para servidores de conferencia A/V y servidores perimetrales A/V)

  - Uso compartido de aplicaciones (incluye métricas de uso compartido de aplicaciones para servidores de conferencia A/V y servidores perimetrales A/V)

Es importante recordar que la clasificación mostrada en este informe es una clasificación relativa. Por ejemplo, supongamos que el servidor con el peor rendimiento tuvo una llamada deficiente entre las 1000 llamadas realizadas. Eso supone un porcentaje más que aceptable del 0,1 %. Pero, si es el servidor de peor rendimiento (es decir, todos los demás servidores tienen un porcentaje de llamadas deficientes incluso inferior al 0,1 %), aparecerá en el informe de rendimiento del servidor.

<div>

## <a name="accessing-the-server-performance-report"></a>Acceso al informe de rendimiento del servidor

El informe de acceso del servidor es accesible desde la página principal de informes de supervisión. Puede explorar en profundidad el [Informe de la lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) haciendo clic en cualquiera de las siguientes métricas:

  - Volumen de llamadas

  - Porcentaje de llamadas deficientes

Además, puede navegar hasta el informe de tendencias de calidad de medios del servidor haciendo clic en las métricas siguientes:

  - Tendencia

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a>Uso óptimo del informe de rendimiento del servidor

El informe de rendimiento del servidor ofrece varias maneras de filtrar los datos; por ejemplo, puede filtrar por tipo de red (llamadas realizadas desde una conexión cableada frente a las llamadas realizadas desde una conexión inalámbrica) y tipo de acceso (llamadas realizadas desde dentro del firewall frente a las llamadas realizadas desde fuera del firewall). Para ver el informe de rendimiento del servidor, es buena idea utilizar estos filtros. Por ejemplo, supongamos que tiene un servidor de mediación con un porcentaje de llamadas deficientes del 3,24 %. Si solo consulta las llamadas inalámbricas, el mismo servidor podría tener un porcentaje de llamadas deficientes cercano al 20 %. Eso significa que el servidor tenía dificultades con las llamadas inalámbricas, un problema que quedó oculto en parte porque el servidor no tenía problemas con las llamadas cableadas.

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros constituyen un modo de obtener un conjunto de datos más acorde con lo que se busca o para ver los datos devueltos de diversas formas. Por ejemplo, el informe de rendimiento del servidor permite realizar tareas como filtrar los datos devueltos por el tipo de servidor o por el tipo de red (con cable o inalámbrica). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.

En la siguiente tabla se muestran los filtros que se pueden usar en el informe de rendimiento del servidor.

### <a name="server-performance-report-filters"></a>Filtros del informe de rendimiento del servidor

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
<td><p><strong>Tipo de servidor</strong></p></td>
<td><p>Indica el tipo de servidor cuyo rendimiento necesita notificarse. Seleccione una de las opciones siguientes:</p>
<ol>
<li><p>[Todas]</p></li>
<li><p>Servidor de mediación</p></li>
<li><p>Servidor de conferencia A/V</p></li>
<li><p>Servidor perimetral A/V</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>Superior N</strong></p></td>
<td><p>Indica la cantidad de servidores (en función de su escaso porcentaje de llamadas) que se va a mostrar en cada categoría. Por ejemplo, si selecciona <strong>5</strong>, aparecerán los cinco servidores con peor rendimiento. Seleccione una de las opciones siguientes:</p>
<ol>
<li><p>[Todas]</p></li>
<li><p>5</p></li>
<li><p>base10</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de acceso</strong></p></td>
<td><p>Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:</p>
<ol>
<li><p>[Todas]</p></li>
<li><p>Interno</p></li>
<li><p>Externo</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de red</strong></p></td>
<td><p>Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</p>
<ol>
<li><p>[Todas]</p></li>
<li><p>Cableada</p></li>
<li><p>Inalámbrica</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</p>
<ol>
<li><p>[Todas]</p></li>
<li><p>VPN</p></li>
<li><p>Distinto de VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de rendimiento del servidor.

### <a name="server-performance-report-metrics-audio-call-summary"></a>Métricas del informe de rendimiento del servidor: resumen de llamadas de audio

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
<td><p><strong>Servidor</strong></p></td>
<td><p>No</p></td>
<td><p>Nombre/dirección IP del servidor.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volumen de llamadas</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas realizadas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de llamadas deficientes</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la que al menos uno de los valores medidos supera el valor permitido, por ejemplo, una llamada con un exceso de vibraciones.</p></td>
</tr>
<tr class="even">
<td><p><strong>Recorrido de ida y vuelta (ms)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.</p>
<p>Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Degradación (MOS)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0. Un valor de 0,5 o menos constituye una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. En Lync Server, el servidor de supervisión usa un conjunto de algoritmos para predecir cómo los usuarios habrían calificado una llamada.</p>
<p>Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pérdida de paquetes</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Vibración (ms)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevada suelen estar causados por una congestión o un servidor multimedia sobrecargado y tienen como resultado una distorsión o pérdida de audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tasa de recuperación de muestras ocultas</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de muestras de audio ocultas respecto a la cantidad total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasa de recuperación de muestras extendidas</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de muestras de audio extendidas respecto a la cantidad total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tasa de recuperación de muestras comprimidas</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de muestras de audio comprimidas respecto a la cantidad total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a>Métricas del informe de rendimiento del servidor: resumen de llamadas de vídeo

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
<td><p>Pérdida de paquetes de salida del Protocolo de transporte en tiempo real (RTP). (La pérdida de paquetes se produce cuando los paquetes de RTP, un protocolo usado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Las altas tasas de pérdidas suelen estar causadas por congestión, falta de ancho de banda, congestión inalámbrica o interferencias, o un servidor de medios sobrecargado. La pérdida de paquetes suele producir distorsión o pérdida de audio.</p></td>
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


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a>Métricas del informe de rendimiento del servidor: resumen de llamadas de uso compartido de aplicaciones

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
<td><p>Latencia media de procesamiento de iconos RDP en el servidor de conferencias AS durante el transcurso de la sesión de visualización. Esta métrica no incluye la latencia de red. Una media alta refleja un retraso mayor en la experiencia de visualización. Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos.</p></td>
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

