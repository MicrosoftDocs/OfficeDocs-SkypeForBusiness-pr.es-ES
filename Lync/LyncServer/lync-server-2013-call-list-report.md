---
title: 'Lync Server 2013: informe de la lista de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce2954f848d448676aea2931cda4dffa8ddc0c5d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a>Informe de la lista de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

El informe de lista de llamadas proporciona métricas relativas a la calidad de la experiencia para las llamadas individuales realizadas y recibidas en su organización. Tenga en cuenta que las métricas reales que se incluyan dependerán de cómo obtenga acceso al informe de lista de llamadas. Por ejemplo, si abre el informe desde el [Informe de dispositivos en Lync Server 2013](lync-server-2013-device-report.md), verá las métricas como las siguientes, métricas que también se notifican en el informe de dispositivo:

  - Micrófono del autor de la llamada

  - Altavoz del autor de la llamada

  - Micrófono del destinatario de la llamada

  - Altavoz del destinatario de la llamada

  - Relación de tiempo de conmutación de voz

Sin embargo, si abre el informe de la lista de llamadas desde el [Informe de ubicación en Lync Server 2013](lync-server-2013-location-report.md), no verá ninguna de esas métricas; en su lugar, verás métricas como las siguientes:

  - Recorrido de ida y vuelta (ms)

  - Degradación (MOS)

  - Pérdida de paquetes

  - Vibración (ms)

Esas son las métricas incluidas en el informe de ubicaciones. No obstante, siempre puede hacer clic en la métrica Detalles, en el informe de lista de llamadas, para obtener información completa sobre la calidad de la experiencia de cualquier llamada.

<div>

## <a name="accessing-the-call-list-report"></a>Acceso al informe de lista de llamadas

El informe de lista de llamadas es accesible desde cualquiera de los siguientes informes:

  - El [Informe de ubicación en Lync Server 2013](lync-server-2013-location-report.md) (haciendo clic en el volumen de la llamada o en la métrica de porcentaje de llamada deficiente)

  - El [Informe del dispositivo en Lync Server 2013](lync-server-2013-device-report.md) (haciendo clic en el volumen de la llamada o en la métrica de porcentaje de llamada deficiente)

  - El [informe Resumen de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (haciendo clic en el volumen de la llamada o en la métrica de porcentaje de llamada deficiente)

  - El [Informe rendimiento del servidor de Lync Server 2013](lync-server-2013-server-performance-report.md) (haciendo clic en el volumen de la llamada o en la métrica de porcentaje de llamada deficiente)

Desde el informe de la lista de llamadas puede acceder al [Informe de detalles de llamadas en Lync Server 2013](lync-server-2013-call-detail-report.md) haciendo clic en la métrica de detalles.

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>Optimización del uso del informe de lista de llamadas

Si no recuerda qué miden algunas de las métricas del informe de lista de llamadas (por ejemplo, Relación de tiempo de conmutación de voz), mantenga el mouse sobre la etiqueta de la métrica y aparecerá una información sobre la herramienta con una breve descripción de la métrica.

</div>

<div>

## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el informe de lista de llamadas.

</div>

<div>

## <a name="metrics"></a>Métricas

En la siguiente tabla se detalla la información facilitada en el informe de lista de llamadas para cada llamada.

### <a name="call-list-report-metrics"></a>Métricas del informe de lista de llamadas

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
<td><p><strong>Detalles</strong></p></td>
<td><p>No</p></td>
<td><p>Al hacer clic en este elemento, el informe muestra información adicional sobre la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Autor de llamada</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dirección SIP de la persona que inició la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Destinatario de la llamada</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dirección SIP de la persona que recibió la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de inicio</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que se inició la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de finalización</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que finalizó la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente de usuario de autor de la llamada</strong></p></td>
<td><p>Sí</p></td>
<td><p>Software utilizado por el extremo de la persona que inició la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente de usuario de destinatario de la llamada</strong></p></td>
<td><p>Sí</p></td>
<td><p>Software utilizado por el extremo de la persona que recibió la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Recorrido de ida y vuelta (ms)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.</p>
<p>Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Degradación (MOS)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0. Un valor de 0,5 o menos constituye una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. En Lync Server, Lync Server usa un conjunto de algoritmos para predecir cómo los usuarios habrían calificado una llamada.</p>
<p>Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pérdida de paquetes</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Vibración</strong></p></td>
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
<tr class="odd">
<td><p><strong>Conectividad</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tipo de vínculo de comunicación inalámbrica. Normalmente es uno de los siguientes:</p>
<ul>
<li><p>Retransmisión</p></li>
<li><p>Directo</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

