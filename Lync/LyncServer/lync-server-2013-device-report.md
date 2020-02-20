---
title: 'Lync Server 2013: informe de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dbfb056107d84aa0f3c483100619b27251feff4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a>Informe de dispositivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-12_

Puede que el informe del dispositivo sea mejor titulado el informe de micrófonos y altavoces; Esto se debe a que el informe de dispositivos recupera las métricas relacionadas con llamadas (por ejemplo, el porcentaje de llamadas deficientes, el eco y el tiempo de conmutación de voz) agrupados por los micrófonos y los altavoces que se usan en la llamada. Si está interesado en los teléfonos IP (también conocidos como "dispositivos"), use el [Informe de inventario de teléfono IP en Lync Server 2013 en](lync-server-2013-ip-phone-inventory-report.md) su lugar.

El informe de dispositivos es muy útil para los administradores que determinan si un tipo específico de dispositivo está experimentando grandes cantidades de llamadas de mala calidad que otras. A su vez, esto podría influir en las decisiones que debe tomar cuando llegue el momento de comprar nuevos dispositivos o reemplazar los dispositivos existentes.

De forma predeterminada, la información que se muestra en el informe de dispositivos también se basa en el micrófono (el dispositivo de captura) y los altavoces y los auriculares (el dispositivo de presentación) que se usan en la llamada. Por ejemplo, supongamos que tiene varios usuarios que usan el siguiente dispositivo de captura y el siguiente dispositivo de representación: de forma predeterminada, la información que se muestra en el informe de dispositivos también se basa en el micrófono (el dispositivo de captura) y los altavoces y los auriculares (el dispositivo de presentación) que se usan en la llamada. Por ejemplo, supongamos que tiene varios usuarios que usan el siguiente dispositivo de captura y el siguiente dispositivo de representación:

  - Dispositivo de captura: micrófono (audio HD digital integrado SoundMAX)

  - Dispositivo de representación: Presentación: de auriculares (Microsoft LifeChat LX-3000)

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
<td><p>Micrófono (audio HD digital integrado SoundMAX)</p></td>
<td><p>Auriculares con presentación: (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


Ahora, supongamos que tiene una serie de usuarios que usan el mismo dispositivo de captura, pero un dispositivo de representación diferente. En ese caso, tendrá una segunda entrada de línea en el informe, una para esa combinación única de dispositivo de captura y dispositivo de presentación:


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
<td><p>Micrófono (audio HD digital integrado SoundMAX)</p></td>
<td><p>Auriculares con presentación: (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>Micrófono (audio HD digital integrado SoundMAX)</p></td>
<td><p>Altavoces (audio HD digital integrado SoundMAX)</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


Si prefiere ver los totales combinados de un dispositivo determinado (por ejemplo, para el dispositivo de captura de SoundMAX, independientemente del dispositivo de representación usado), seleccione la opción adecuada en la lista desplegable tipo de dispositivo (dispositivo de captura o dispositivo de presentación). Si selecciona dispositivo de captura en este ejemplo, obtendrá un resultado similar al siguiente:


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
<td><p>Micrófono (audio HD digital integrado SoundMAX)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a>Acceso al informe de dispositivos

El acceso al informe de dispositivos se suele obtener desde la Página principal de informes de supervisión. Sin embargo, si está viendo el [Informe de detalles de llamadas en Lync Server 2013](lync-server-2013-call-detail-report.md) , puede hacer clic en cualquiera de las siguientes métricas para obtener acceso al informe de dispositivos de un dispositivo específico:

  - Dispositivo de captura

  - Dispositivo de representación

En el informe de dispositivos, puede profundizar hasta el [Informe de lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) haciendo clic en cualquiera de las métricas siguientes:

  - Volumen de llamadas

  - Porcentaje de llamadas deficientes

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a>Cómo hacer el mejor uso del informe de dispositivos

En cuanto a los nombres de dispositivo, el informe de dispositivo es muy detallado; por ejemplo, supongamos que tiene los dispositivos de captura siguientes:

  - Micrófono Aastra 3002 (2-Aastra 3002)

  - Micrófono Aastra 3002 (3-Aastra 3002)

  - Micrófono Aastra 3002 (Aastra 3002)

  - Aastra 6725ip

  - Micrófono 6725ip Aastra (10-Aastra 6725ip)

  - Micrófono 6725ip Aastra (10-Aastra 6725ip)-v0

  - Micrófono 6725ip Aastra (2-Aastra 6725ip)

  - Micrófono 6725ip Aastra (3-Aastra 6725ip)

  - Micrófono 6725ip Aastra (4-Aastra 6725ip)

  - Micrófono 6725ip Aastra (5-Aastra 6725ip)

  - Micrófono 6725ip Aastra (6-Aastra 6725ip)

  - Micrófono 6725ip Aastra (7-Aastra 6725ip)

  - Micrófono 6725ip Aastra (9-Aastra 6725ip)

  - Micrófono 6725ip Aastra (9-Aastra 6725ip)-v0

  - Micrófono 6725ip de Aastra (Aastra 6725ip)

  - Aastra 6725ip micrófono (Aastra 6725ip)-v0

  - Micrófono 6725ip Aastra (dispositivo de audio USB)

  - Aastra 6725ip micrófono (dispositivo de audio USB)-v0

<div>


> [!NOTE]  
> Tenga en cuenta que los nombres de los dispositivos de captura podrían no ser los mismos si ejecuta versiones localizadas de Lync Server 2013. Un dispositivo denominado Aastra 6725ip micrófono (Aastra 6725ip)-v0 en Inglés de Estados Unidos podría tener un nombre distinto en francés o en español.



</div>

A menudo deseará un nivel de detalle; en otras ocasiones, sin embargo, es posible que solo le interese el número de llamadas que usan un micrófono Aastra, independientemente del número de modelo. Una forma de obtener información como ésta es exportar los datos del informe de dispositivos a Microsoft Excel y, a continuación, guardarlos en un archivo de valores separados por comas (\\por\\ejemplo\_, C: Data Devices Report. csv). A continuación, puede usar un conjunto de comandos similares a estos para importar el. CSV en Windows PowerShell e Informe sobre el número total de llamadas realizadas con un dispositivo de captura de Aastra:

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

Esto devolverá un valor único que representa el número total de llamadas realizadas mediante un dispositivo de captura Aastra. Por ejemplo:

    384

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de dispositivos le permite filtrar en aspectos como el tipo de llamada (es decir, que fue la llamada a una llamada de cliente), una llamada de conferencia o una llamada de red telefónica conmutada (RTC). También se puede elegir cómo agrupar los datos. En este caso, los dispositivos se agrupan por hora, día, semana o mes.

En la siguiente tabla se enumeran los filtros que se pueden usar con el informe de dispositivos.

### <a name="device-report-filters"></a>Filtros de informes de dispositivos

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
<td><p><strong>From</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</p>
<p>7/7/2012 1:00 pm</p>
<p>Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Causa del cambio de voz</strong></p></td>
<td><p>Razón por la que se ha tenido que poner una llamada en modo de dúplex medio para evitar el eco. En el modo de dúplex medio, la comunicación sólo puede realizarse en una dirección a la vez, de manera similar a como se convierten los usuarios al comunicarse con un walkie-talkie. Seleccione una de las siguientes opciones:</p>
<dl>
<dt><span></span></dt>
<dd><p>Todos</p>
</dd>
<dt><span></span></dt>
<dd><p>Ninguno</p>
</dd>
<dt><span></span></dt>
<dd><p>Marca de hora incorrecta</p>
</dd>
<dt><span></span></dt>
<dd><p>Echo</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (procesador no lineal dinámico)</p>
</dd>
<dt><span></span></dt>
<dd><p>Complejidad baja</p>
</dd>
<dt><span></span></dt>
<dd><p>Estado de dispositivo incorrecto</p>
</dd>
<dt><span></span></dt>
<dd><p>Eco posterior a AEC (cancelación del eco acústico)</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Causa del eco</strong></p></td>
<td><p>Razón por la que se detectó un eco por encima del nivel aceptado en una llamada. (En telecomunicaciones, ECHO es un reflejo del sonido, el mismo fenómeno que oirá si Yell a la parte inferior de un bien.) Seleccione una de las siguientes opciones:</p>
<dl>
<dt><span></span></dt>
<dd><p>Todos</p>
</dd>
<dt><span></span></dt>
<dd><p>Ninguno</p>
</dd>
<dt><span></span></dt>
<dd><p>Marca de hora incorrecta</p>
</dd>
<dt><span></span></dt>
<dd><p>Eco posterior a AEC (cancelación del eco acústico)</p>
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
<td><p>Indica el tipo de llamada que se realizó. Seleccione una de las siguientes opciones:</p>
<dl>
<dt><span></span></dt>
<dd><p>Todos</p>
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
<dd><p>Todos</p>
</dd>
<dt><span></span></dt>
<dd><p>Interno</p>
</dd>
<dt><span></span></dt>
<dd><p>External</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de red</strong></p></td>
<td><p>Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</p>
<dl>
<dt><span></span></dt>
<dd><p>Todos</p>
</dd>
<dt><span></span></dt>
<dd><p>Cableada</p>
</dd>
<dt><span></span></dt>
<dd><p>Wireless</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</p>
<dl>
<dt><span></span></dt>
<dd><p>Todos</p>
</dd>
<dt><span></span></dt>
<dd><p>VPN</p>
</dd>
<dt><span></span></dt>
<dd><p>No VPN</p>
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
<dd><p>Par de dispositivos de captura/representación</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Nombre de dispositivo</strong></p></td>
<td><p>Nombre del dispositivo de captura o representación. Puede escribir el nombre completo del dispositivo o cualquier parte del nombre del dispositivo. Por ejemplo, para encontrar el micrófono del dispositivo (Microsoft LifeCam VX-1000.), puede escribir el nombre completo del dispositivo de la siguiente manera:</p>
<p>Micrófono (Microsoft LifeCam VX-1000.)</p>
<p>O bien, puede escribir sólo una parte del nombre. Por ejemplo:</p>
<p>LifeCam</p>
<p>Tenga en cuenta que el filtro anterior devuelve cualquier dispositivo que contenga la cadena &quot;LifeCam&quot; en cualquier lugar en su nombre.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la siguiente tabla se muestra la información proporcionada en el informe de dispositivos.

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
<th>¿Se pueden ordenar los datos en este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Dispositivo de captura</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dispositivo (por ejemplo, un micrófono o una cámara web) que se usa para transmitir audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dispositivo de presentación</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dispositivo (por ejemplo, unos auriculares o altavoces) que se usa para recibir audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volumen de llamadas</strong></p></td>
<td><p>Sí</p></td>
<td><p>Número total de llamadas realizadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de llamadas deficientes</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de llamadas que se han clasificado &quot;como malas. &quot; Una llamada deficiente es cualquier llamada que al menos una de las métricas medidas superó el valor permitido (por ejemplo, una llamada que experimentó una vibración excesiva).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Usuarios únicos</strong></p></td>
<td><p>Sí</p></td>
<td><p>Usuarios únicos que han usado el dispositivo. Si un usuario ha utilizado el dispositivo 13 veces, puede contar como un usuario único, igual que un usuario que solo usó el dispositivo una sola vez.</p></td>
</tr>
<tr class="even">
<td><p><strong>Relación de tiempo de conmutación de voz</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de la llamada que tuvo que realizarse en modo de dúplex medio para evitar el eco. En el modo de dúplex medio, la comunicación sólo puede realizarse en una dirección a la vez, de manera similar a como se convierten los usuarios al comunicarse con un walkie-talkie.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relación de que el micrófono no funciona</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de la llamada en la que el dispositivo de captura no estaba funcionando a un nivel aceptable. Un valor alto sugiere que los problemas de calidad con la llamada se deben principalmente a que el dispositivo de captura no funciona como se esperaba.</p></td>
</tr>
<tr class="even">
<td><p><strong>Relación de que el altavoz no funciona</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de la llamada en la que el dispositivo de representación no funcionaba a un nivel aceptable. Un valor alto sugiere que los problemas de calidad con la llamada se deben principalmente a que el dispositivo de presentación no funciona como se esperaba.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Llamadas con conmutación de voz (%)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje del total de llamadas que se han tenido que poner en modo de dúplex medio. En el modo de dúplex medio, la comunicación sólo puede realizarse en una dirección a la vez, de manera similar a como se convierten los usuarios al comunicarse con un walkie-talkie.</p></td>
</tr>
<tr class="even">
<td><p><strong>Eco de micrófono en (%)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de tiempo durante el que se detectó el eco en la secuencia de captura del micrófono. Normalmente, los valores son bajos para auriculares o auriculares, y más arriba para los teléfonos de altavoces o los altavoces autónomos. Para los dispositivos que admiten la cancelación del eco acústico en la tarjeta, los valores altos indican la pérdida de eco. Para otros dispositivos, esta métrica no debe usarse para evaluar la calidad del dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Envío de Eco (%)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de eco transmitido a otros usuarios.</p></td>
</tr>
<tr class="even">
<td><p><strong>Llamadas con Eco (%)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje del total de llamadas que ha tenido un eco que supera el nivel aceptable.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

