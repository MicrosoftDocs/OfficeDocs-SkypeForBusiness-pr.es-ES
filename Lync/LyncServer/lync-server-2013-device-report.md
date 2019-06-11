---
title: 'Lync Server 2013: informe de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e172837622c4ad40a29cca74dcaf42497c4b2bd5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a>Informe de dispositivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-12_

El informe de dispositivos tendría que llamarse más bien Informe de micrófono y altavoces porque el informe de dispositivos recupera las métricas relacionadas con las llamadas (como porcentaje de llamadas deficientes, eco y tiempo de conmutación de voz) agrupadas por los micrófonos y los altavoces utilizados durante la llamada. Si está interesado en teléfonos IP (también conocidos como "dispositivos"), use el [Informe de inventario telefónico de IP en Lync Server 2013 en](lync-server-2013-ip-phone-inventory-report.md) su lugar.

El informe de dispositivos es muy útil para los administradores a la hora de determinar si un tipo concreto de dispositivo está sufriendo un número de llamadas de calidad deficiente superior al de otros. A su vez, puede influir en las decisiones que se tomen respecto a comprar nuevos dispositivos o sustituir los actuales.

De forma predeterminada, la información mostrada en el informe de dispositivos también atañe al micrófono (el dispositivo de captura) y los altavoces o auriculares (los dispositivos de presentación) empleados durante la llamada. Por ejemplo, si hay varios usuarios que utilizan el siguiente dispositivo de captura y el siguiente dispositivo de presentación:

  - Dispositivo de captura: micrófono (audio HD digital integrado SoundMAX)

  - Dispositivo de presentación: auriculares (Microsoft LifeChat LX-3000)

Si estos usuarios realizaron un total de 254 llamadas, verá una entrada como la siguiente en el informe:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Dispositivo de captura</th>
<th>Dispositivo de presentación</th>
<th>Volumen de llamadas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Micrófono (Audio HD digital integrado SoundMAX)</p></td>
<td><p>Auriculares (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


Ahora, supongamos que tiene una serie de usuarios que utilizan ese mismo dispositivo de captura, pero un dispositivo de presentación diferente. En ese caso, tendrá una segunda entrada en el informe referente a esta combinación única de dispositivo de captura y dispositivo de presentación:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Dispositivo de captura</th>
<th>Dispositivo de presentación</th>
<th>Volumen de llamadas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Micrófono (Audio HD digital integrado SoundMAX)</p></td>
<td><p>Auriculares (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>Micrófono (Audio HD digital integrado SoundMAX)</p></td>
<td><p>Altavoces (Audio HD digital integrado SoundMAX)</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


Si prefiere ver los totales combinados de un dispositivo concreto (por ejemplo, del dispositivo de captura SoundMAX, independientemente de cual sea el dispositivo de presentación utilizado), seleccione la opción correspondiente en la lista desplegable Tipo de dispositivo (a saber, Dispositivo de captura o Dispositivo de presentación). Si selecciona dispositivo de captura, por ejemplo, el resultado será similar a:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Dispositivo de captura</th>
<th>Volumen de llamadas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Micrófono (Audio HD digital integrado SoundMAX)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a>Acceso al informe de dispositivos

Generalmente, se accede al informe de dispositivos desde la página de inicio de Informes de supervisión. Sin embargo, si visualiza el [Informe de detalles de llamadas en Lync Server 2013](lync-server-2013-call-detail-report.md) puede explorar en profundidad el informe de dispositivos para un dispositivo específico haciendo clic en una de las siguientes métricas:

  - Dispositivo de captura

  - Dispositivo de presentación

En el informe de dispositivos, puede explorar en profundidad el [Informe de la lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) haciendo clic en cualquiera de las siguientes métricas:

  - Volumen de llamadas

  - Porcentaje de llamadas deficientes

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a>Aprovechamiento del informe de dispositivos

En lo que se refiere a los nombres de dispositivos, el informe de dispositivos es muy detallado. Por ejemplo, supongamos que tiene los siguientes dispositivos de captura:

  - Micrófono Aastra 3002 (2- Aastra 3002)

  - Micrófono Aastra 3002 (3- Aastra 3002)

  - Micrófono Aastra 3002 (Aastra 3002)

  - Aastra 6725ip

  - Micrófono Aastra 6725ip (10- Aastra 6725ip)

  - Micrófono Aastra 6725ip (10- Aastra 6725ip)-V0

  - Micrófono Aastra 6725ip (2- Aastra 6725ip)

  - Micrófono Aastra 6725ip (3- Aastra 6725ip)

  - Micrófono Aastra 6725ip (4- Aastra 6725ip)

  - Micrófono Aastra 6725ip (5- Aastra 6725ip)

  - Micrófono Aastra 6725ip (6- Aastra 6725ip)

  - Micrófono Aastra 6725ip (7- Aastra 6725ip)

  - Micrófono Aastra 6725ip (9- Aastra 6725ip)

  - Micrófono Aastra 6725ip (9- Aastra 6725ip)-V0

  - Micrófono Aastra 6725ip (Aastra 6725ip)

  - Micrófono Aastra 6725ip (Aastra 6725ip)-V0

  - Micrófono Aastra 6725ip (USB Audio Device)

  - Micrófono Aastra 6725ip (USB Audio Device)-V0

<div>


> [!NOTE]  
> Recuerde que es posible que los nombres de los dispositivos de captura no sean los mismos si ejecuta versiones localizadas de Lync Server 2013. El dispositivo Aastra 6725ip Microphone (Aastra 6725ip)-V0 en inglés, podría tener otro nombre en francés o en español.



</div>

Habrá casos en los que desee trabajar con ese nivel de detalles, pero habrá otros en los que solo le interese saber cuántas llamadas utilizaron un micrófono Aastra, sea cual sea, sin importar el número de modelo. Una forma de obtener información como esta es exportar los datos del informe de dispositivos a Microsoft Excel y, a continuación, guardarlos en un archivo de valores separados por comas (\\por\\ejemplo\_, C: dispositivos de datos-informe. csv). A continuación, podrá utilizar un conjunto de comandos similar al siguiente para importar el archivo .CSB en Windows PowerShell y crear un informe del total de llamadas realizadas con un dispositivo de captura Aastra:

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

Así se devolverá un único valor correspondiente al número total de llamadas realizadas con un dispositivo de captura Aastra. Por ejemplo:

    384

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de dispositivos permite filtrar elementos como el tipo de llamada (es decir, si la llamada era de un cliente), una llamada de conferencia o una llamada de red telefónica conmutada (RTC). También se puede elegir cómo agrupar los datos. En este caso, los dispositivos se agrupan por hora, día, semana o mes.

En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de dispositivos.

### <a name="device-report-filters"></a>Filtros del informe de dispositivos

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
<td><p><strong>Causa de la conmutación de voz</strong></p></td>
<td><p>Motivo por el que se tuvo que realizar una llamada en modo de dúplex medio para evitar el eco. En el modo de dúplex medio, la comunicación no puede realizarse en ambos sentidos a la vez, es similar al modo por turnos utilizado para comunicarse con un walkie-talkie. Seleccione una de las siguientes opciones:</p>
<dl>
<dt><span></span></dt>
<dd><p>[Todas]</p>
</dd>
<dt><span></span></dt>
<dd><p>Ninguno</p>
</dd>
<dt><span></span></dt>
<dd><p>Marca de tiempo incorrecta</p>
</dd>
<dt><span></span></dt>
<dd><p>Eco</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (procesador no lineal dinámico)</p>
</dd>
<dt><span></span></dt>
<dd><p>Complejidad baja</p>
</dd>
<dt><span></span></dt>
<dd><p>Estado del dispositivo incorrecto</p>
</dd>
<dt><span></span></dt>
<dd><p>Eco posterior a AEC (cancelación de eco acústico)</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Causa del eco</strong></p></td>
<td><p>Motivo por el que se ha detectado en una llamada un eco que supera el nivel aceptado (en las telecomunicaciones, el eco es un reflejo del sonido, el mismo fenómeno que se produce cuando se grita en un pozo). Seleccione una de las siguientes opciones:</p>
<dl>
<dt><span></span></dt>
<dd><p>[Todas]</p>
</dd>
<dt><span></span></dt>
<dd><p>Ninguno</p>
</dd>
<dt><span></span></dt>
<dd><p>Marca de tiempo incorrecta</p>
</dd>
<dt><span></span></dt>
<dd><p>Eco posterior a AEC (cancelación de eco acústico)</p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP (procesador no lineal adaptable)</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (procesador no lineal dinámico)</p>
</dd>
<dt><span></span></dt>
<dd><p>Recorte de micrófono</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de llamada</strong></p></td>
<td><p>Indica el tipo de llamada realizada. Seleccione una de las siguientes opciones:</p>
<dl>
<dt><span></span></dt>
<dd><p>[Todas]</p>
</dd>
<dt><span></span></dt>
<dd><p>Llamada de cliente</p>
</dd>
<dt><span></span></dt>
<dd><p>Llamada RTC</p>
</dd>
<dt><span></span></dt>
<dd><p>Llamada de conferencia</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de acceso</strong></p></td>
<td><p>Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:</p>
<dl>
<dt><span></span></dt>
<dd><p>[Todas]</p>
</dd>
<dt><span></span></dt>
<dd><p>Interno</p>
</dd>
<dt><span></span></dt>
<dd><p>Externo</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de red</strong></p></td>
<td><p>Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</p>
<dl>
<dt><span></span></dt>
<dd><p>[Todas]</p>
</dd>
<dt><span></span></dt>
<dd><p>Cableada</p>
</dd>
<dt><span></span></dt>
<dd><p>Inalámbrica</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</p>
<dl>
<dt><span></span></dt>
<dd><p>[Todas]</p>
</dd>
<dt><span></span></dt>
<dd><p>VPN</p>
</dd>
<dt><span></span></dt>
<dd><p>Distinto de VPN</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de dispositivo</strong></p></td>
<td><p>Indica el tipo de dispositivo. Seleccione una de las siguientes opciones:</p>
<dl>
<dt><span></span></dt>
<dd><p>Dispositivo de captura</p>
</dd>
<dt><span></span></dt>
<dd><p>Dispositivo de presentación</p>
</dd>
<dt><span></span></dt>
<dd><p>Pareja de dispositivos de captura/presentación</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Nombre del dispositivo</strong></p></td>
<td><p>Nombre del dispositivo de captura o presentación. Puede escribir el nombre completo del dispositivo o cualquier parte del mismo. Por ejemplo, para encontrar el dispositivo Micrófono (Microsoft LifeCam VX-1000), puede escribir el nombre completo del dispositivo del modo siguiente:</p>
<p>Micrófono (Microsoft LifeCam VX-1000)</p>
<p>También puede escribir solo una parte del nombre. Por ejemplo:</p>
<p>LifeCam</p>
<p>Observe que el filtro anterior devuelve cualquier dispositivo que contenga la &quot;cadena&quot; LifeCam en su nombre.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la tabla siguiente, se muestra la información que recoge el informe de dispositivos.

### <a name="device-report-metrics"></a>Métricas del informe de dispositivos

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
<td><p><strong>Dispositivo de captura</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dispositivo (por ejemplo, un micrófono o una cámara web) utilizado para transmitir audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dispositivo de presentación</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dispositivo (por ejemplo, unos auriculares o altavoces) utilizado para recibir audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volumen de llamadas</strong></p></td>
<td><p>Sí</p></td>
<td><p>Cantidad total de llamadas realizadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de llamadas deficientes</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de llamadas que se han clasificado &quot;como malas. &quot; Una llamada deficiente es cualquier llamada que al menos una de las métricas medidas superó el valor permitido (por ejemplo, una llamada que experimentó una vibración excesiva).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Usuarios únicos</strong></p></td>
<td><p>Sí</p></td>
<td><p>Usuarios únicos que han utilizado el dispositivo. Si un usuario ha utilizado el dispositivo 13 veces, se contará como un usuario único, igual que un usuario que solo haya utilizado el dispositivo una única vez.</p></td>
</tr>
<tr class="even">
<td><p><strong>Relación de tiempo de conmutación de voz</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de la llamada que se ha tenido que realizar en modo de dúplex medio para evitar el eco. En el modo de dúplex medio, la comunicación no puede realizarse en ambos sentidos a la vez, similar al modo por turnos utilizado para comunicarse con un walkie-talkie.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relación de tiempo durante el que el micrófono estuvo sin funcionar</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de la llamada en el que el dispositivo de captura no funcionaba a un nivel aceptable. Un valor elevado sugiere que los problemas de calidad de la llamada se deben principalmente a que el dispositivo de captura no funciona como debería.</p></td>
</tr>
<tr class="even">
<td><p><strong>Relación de tiempo durante el que el altavoz estuvo sin funcionar</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de la llamada en el que el dispositivo de presentación no funcionaba a un nivel aceptable. Un valor elevado sugiere que los problemas de calidad de la llamada se deben principalmente a que el dispositivo de presentación no funciona como debería.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Llamadas con conmutación de voz (%)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje del total de llamadas que se han tenido que realizar en modo de dúplex medio. En el modo de dúplex medio, la comunicación no puede realizarse en ambos sentidos a la vez, algo similar al modo por turnos utilizado para comunicarse con un walkie-talkie.</p></td>
</tr>
<tr class="even">
<td><p><strong>Eco del micrófono en (%)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de tiempo para la detección del eco en la secuencia de captura del micrófono. En general, los valores son bajos para auriculares, y altos para altavoces de teléfono o independientes. En el caso de dispositivos que son compatibles con la cancelación del eco acústico incorporada, los valores altos indican filtraciones de eco. En otros dispositivos, esta métrica no debe utilizarse para evaluar la calidad del dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Envío de eco (%)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de eco transmitido a otros usuarios.</p></td>
</tr>
<tr class="even">
<td><p><strong>Llamadas con eco (%)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje del total de llamadas cuyo eco superaba el nivel aceptable.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

