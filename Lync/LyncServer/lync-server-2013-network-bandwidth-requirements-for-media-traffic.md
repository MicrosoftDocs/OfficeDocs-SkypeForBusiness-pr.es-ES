---
title: Lync Server 2013 requisitos de ancho de banda de red para el tráfico multimedia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network bandwidth requirements for media traffic
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49733716
ms.date: 09/25/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f02f87e0cc7adc9cdfbd5e7ba1a9b7a4a6b736ee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-09-24_

Una parte importante de la planeación de red está asegurando que su red pueda asegurar el tráfico de medios generado por el Lync Server. Esta sección le ayudará a planear para ese tráfico de medios.

<div>

## <a name="media-traffic-network-usage"></a>Uso de red de tráfico de medios

El uso del ancho de banda de tráfico de medios puede resultar difícil de calcular debido a la cantidad de variables diferentes, como el uso de códecs, la resolución y los niveles de actividad. El uso de ancho de banda es una función del códec usado y la actividad de la secuencia y ambos varían entre escenarios. En la siguiente tabla se enumeran los códecs de audio que se usan con más frecuencia en escenarios de Lync Server 2013.

### <a name="audio-codec-bandwidth"></a>Ancho de banda del códec de audio

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Códec de audio</th>
<th>Escenarios</th>
<th>Velocidad de bits de carga de audio (KBPS)</th>
<th>Solo ancho de banda de carga de audio y encabezado IP (Kbps)</th>
<th>Ancho de banda de carga de audio, encabezado IP, UDP, RTP y SRTP (Kbps)</th>
<th>Ancho de banda de carga de audio, encabezado IP, UDP, RTP, SRTP y corrección de error de reenvío (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Banda ancha de RTAudio</p></td>
<td><p>Punto a punto</p></td>
<td><p>29,0</p></td>
<td><p>45,0</p></td>
<td><p>57,0</p></td>
<td><p>86,0</p></td>
</tr>
<tr class="even">
<td><p>Banda estrecha de RTAudio</p></td>
<td><p>Punto a punto, RTC</p></td>
<td><p>11,8</p></td>
<td><p>27,8</p></td>
<td><p>39,8</p></td>
<td><p>51,6</p></td>
</tr>
<tr class="odd">
<td><p>G. 722</p></td>
<td><p>Conferencia</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>95,6</p></td>
<td><p>159,6</p></td>
</tr>
<tr class="even">
<td><p>G.722 estéreo</p></td>
<td><p>Punto a punto, conferencias</p></td>
<td><p>128,0</p></td>
<td><p>144,0</p></td>
<td><p>159,6</p></td>
<td><p>223,6</p></td>
</tr>
<tr class="odd">
<td><p>G. 711</p></td>
<td><p>RTC, conferencias</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>92,0</p></td>
<td><p>156,0</p></td>
</tr>
<tr class="even">
<td><p>Siren</p></td>
<td><p>Conferencia</p></td>
<td><p>16,0</p></td>
<td><p>32,0</p></td>
<td><p>47,6</p></td>
<td><p>63,6</p></td>
</tr>
</tbody>
</table>


Los números del ancho de banda en la tabla anterior están basados en los paquetes de 20ms (50 paquetes por segundo) y para Sirena y G.722 se incluyen los gastos del protocolo seguro en tiempo real (SRTP) adicional de los escenarios de conferencia y asumen que la secuencia está 100% activa. La corrección de error de reenvío (FEC) se utiliza de forma dinámica cuando existe una pérdida de paquete en el vínculo para ayudar a mantener la calidad de la secuencia de audio.

La versión en estéreo del códec G. 722 se usa en sistemas basados en el sistema de salas de Lync, que permite la captura de micrófono estéreo para permitir a los oyentes distinguir mejor a varios de los chats de la sala de reuniones.

Para vídeo, el códec predeterminado es el estándar de codificación de video avanzado H.264/MPEG-4 Parte 10 junto con sus extensiones de codificación de video escalable. Para mantener la interoperabilidad con los clientes de Lync 2010 o Office Communicator 2007 R2, el códec RTVideo se sigue usando para las llamadas punto a punto entre Lync 2013 y los clientes heredados. En sesiones de conferencia con los clientes de Lync 2013 y heredados, el punto de conexión de Lync 2013 puede codificar el vídeo con ambos códecs de vídeo y enviar el Bitstream de H. 264 al Lync 2013 y al RTVideo Bitstream a clientes de Lync 2010 u Office Communicator 2007 R2.

El ancho de banda requerido depende de la resolución, calidad y frecuencia de marco. Para cada resolución, existen dos secuencias de bits interesantes:

  - **Velocidad de bits**   de carga máxima es la velocidad de bits que un punto de conexión 2013 de Lync usará para la resolución a la velocidad de fotogramas máxima admitida para esta resolución. Este valor es interesante debido a que permite la mayor calidad y video con velocidad de fotogramas.

  - **Velocidad de bits**   de carga mínima es la velocidad de bits a partir de la cual un punto final de Lync 2013 cambiará a la siguiente resolución más baja. Para poder garantizar una determinada resolución, la velocidad de bits de carga de vídeo disponible no debe ser menor que esta velocidad de bits mínima para esta resolución. Este valor es interesante para que pueda comprender el menor valor posible en los casos donde la velocidad de bits máxima no está disponible o no resulta práctica. Para algunos usuarios, esta baja velocidad de bits de vídeo puede ser considerada una experiencia de video no aceptada, por lo que aconsejamos precaución al considerar estas velocidades de bits mínimas de vídeo. Tenga en cuenta que para las escenas de vídeo con poco o sin movimiento del usuario también pueden temporalmente caer por debajo de la velocidad de bits mínima.

Lync 2013 admite muchas más resoluciones. Esto permite que ajuste mejor los diferentes anchos de banda y recibir mejor las capacidades de los clientes. Además, la relación de aspecto predeterminada para Lync 2013 se ha cambiado a 16:9. La relación de aspecto 4:3 aún se admite para cámaras web que no permiten una captura con un radio de 16:9 relación de aspecto.

### <a name="video-resolution-bandwidth"></a>Ancho de banda de resolución de video

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Códec de video</th>
<th>Resolución y relación de aspecto</th>
<th>Velocidad de bits máxima de carga de video (Kbps)</th>
<th>Velocidad de bits mínima de carga de video (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>15 </p></td>
</tr>
<tr class="even">
<td><p>H. 264/RTVideo</p></td>
<td><p>424x240 (16:9))</p>
<p>320x240 (4:3</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>480x270 (16:9)</p>
<p>424x320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H. 264/RTVideo</p></td>
<td><p>640 x 360 (16:9)</p>
<p>640x480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>848x480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>960x540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H. 264/RTVideo</p></td>
<td><p>1280x720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>1920 x 1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H. 264/RTVideo</p></td>
<td><p>960x144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>15 </p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>1280x192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>1920 x 288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


La FEC de vídeo se incluye en la velocidad de bits de carga de vídeo cuando se usa para que no existan valores independientes con FEC de video y sin esta.

Los extremos no hacen fluir los paquetes de audio y video continuamente. Dependiendo del escenario existen varios niveles de actividades de secuencia que indican la frecuencia con los que los paquetes se envían a una secuencia. La actividad de una secuencia depende de los medios y el escenario, y no depende del códec que se utiliza. En un escenario entre pares:

  - Los extremos envían secuencias de audio solo cuando los usuarios hablan.

  - Ambos participantes reciben secuencias de audio.

  - Si se utiliza video, ambos extremos envían y reciben secuencias de vídeo durante toda la llamada.

  - Para las escenas de video con poco o nada de movimiento, la velocidad de bits real puede ser temporalmente muy baja debido a que el códec de video omitirá las regiones de codificación del video sin cambio.

En un escenario de conferencias:

  - Los extremos envían secuencias de audio solo cuando los usuarios hablan.

  - Todos los participantes reciben secuencias de audio.

  - Si se utiliza video, los participantes pueden recibir hasta cinco secuencias de vídeo y uno panorámico (por ejemplo, con relación de aspecto 20:3). De forma predeterminada, los cinco reciben secuencias de vídeo basadas en el historial de hablantes activos, pero los usuarios también pueden seleccionar de forma manual de los que desea recibir una secuencia de video.

  - Cada participante que enciende la secuencia de video del usuario enviará una o más secuencias de video. Lync 2013 agrega la capacidad de enviar hasta cinco secuencias de vídeo para optimizar la calidad de vídeo para todos los clientes receptores. La cantidad real de secuencias de vídeo que se envía automáticamente está determinado por quien envía, según la capacidad de la computadora, ancho de banda ascendente disponible y la cantidad de recibir clientes que solicitan cierta secuencia de video. El caso más común es el de H.264 y una secuencia de video de RTVideo se envían en caso de que un cliente heredado se una a la conferencia. Otro escenario común es que varias secuencias de vídeo H.264 (por ejemplo, con resoluciones de video diferente) se envían para acomodar diferentes solicitudes de receptor.

Además del ancho de banda requerido para el tráfico de protocolo seguro en tiempo real (RTP) para los medios de audio o video, el ancho de banda es necesario para el protocolo de control de transporte en tiempo real (RTCP). El RTCP se utiliza para informar estadísticas y control fuera de banda de la secuencia RTP. Para la planificación, use los números del ancho de banda en la tabla siguiente para el tráfico RTCP. Estos valores representan el ancho de banda máximo para RTCP y difieren entre las secuencias de audio y vídeo debido a las diferencias en los datos de control

### <a name="rtcp-bandwidth"></a>Ancho de banda de RTCP

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Multimedia</th>
<th>Ancho de banda máximo RTCP (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>Video (solo se envía/recibe H.264 o RTVideo)</p></td>
<td><p>10 </p></td>
</tr>
<tr class="odd">
<td><p>Video (se envía/recibe H.264 y RTVideo)</p></td>
<td><p>15 </p></td>
</tr>
</tbody>
</table>


Para los fines de planificación, los siguientes dos anchos de banda son de interés:

  - **Ancho de banda máximo sin FEC**   el ancho de banda máximo que consumirá un flujo, incluida la actividad típica de la secuencia y el códec típico que se usa en el escenario sin FEC.Este es el ancho de banda cuando la secuencia está con el 100% de actividad y no existe una pérdida de paquetes que desencadena el uso de FEC.Esto resulta interesante para contabilizar cuánto ancho de banda debe asignarse para permitir que el códec se utilice en un escenario determinado. 

  - **Ancho de banda máximo con FEC**   el ancho de banda máximo que consume una secuencia, incluida la actividad típica de la secuencia y el códec típico usado en el escenario con FEC. Este es el ancho de banda cuando la secuencia está con el 100% de actividad y existe una pérdida de paquetes que desencadena el uso de FEC para mejorar la calidad. Esto resulta interesante para contabilizar cuánto ancho de banda debe asignarse para permitir que el códec se utilice en un escenario determinado y permite el uso de FEC para preservar la calidad en condiciones de pérdida de paquetes. 

Las siguientes tablas también enumeran un valor adicional de ancho de banda, **Ancho de banda típico**. Este es el ancho de banda típico que consume una secuencia, incluso la actividad típica de la secuencia y el códec típico usado en el escenario. Este ancho de banda puede utilizarse para calcular cuánto ancho de banda en cualquier momento se está utilizando en el tráfico de medios, pero no deberá utilizarse para la planificación de capacidad, debido a que las llamadas individuales excederán este valor cuando todo el nivel de actividad es superior que el promedio. El ancho de banda de secuencia de video típico en las tablas a continuación se basa en una mezcla de resoluciones de video tal como se observan en los datos cliente medidos. Por ejemplo, en sesiones de punto a punto, la mayoría de los usuarios utilizarían la ventana presentación de vídeo predeterminada, mientras que un porcentaje de usuarios aumentaría o maximizaría la aplicación Lync para permitir resoluciones de vídeo de mayor nivel.

Las siguientes tablas proporcionan estos tres valores de ancho de banda para los diferentes escenarios.

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>Planificación de la capacidad de audio/video para sesiones entre pares

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Multimedia</th>
<th>Códec</th>
<th>Ancho de banda de secuencia típica (Kbps)</th>
<th>Ancho de banda de secuencia máximo sin FEC</th>
<th>Ancho de banda de secuencia máximo con FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>Banda ancha de RTAudio</p></td>
<td><p>39,8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Banda estrecha de RTAudio</p></td>
<td><p>29,3</p></td>
<td><p>44,8</p></td>
<td><p>56,6</p></td>
</tr>
<tr class="odd">
<td><p>Vídeo principal al llamar a puntos de conexión de Lync 2013</p></td>
<td><p>H. 264</p></td>
<td><p>460</p></td>
<td><p>4010 (para una resolución máxima de 1920x1080)</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>Vídeo principal al llamar a los puntos de conexión de Lync 2010 o Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (para una resolución máxima de 1920x720)</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>Vídeo panorámico al llamar a los puntos de conexión de Lync 2013</p></td>
<td><p>H. 264</p></td>
<td><p>190</p></td>
<td><p>2010 (para una resolución máxima de 1920x288)</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>Vídeo panorámico al llamar a los puntos de conexión de Lync 2010 o Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (para una resolución máxima de 1920x144)</p></td>
<td><p>No aplicable</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>Planificación de la capacidad de audio/video para conferencias

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Multimedia</th>
<th>Códec típico</th>
<th>Ancho de banda de secuencia típica (Kbps)</th>
<th>Ancho de banda de secuencia máximo sin FEC</th>
<th>Ancho de banda de secuencia máximo con FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>G. 722</p></td>
<td><p>46,1</p></td>
<td><p>100,6</p></td>
<td><p>164,6</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Siren</p></td>
<td><p>25,5</p></td>
<td><p>52,6</p></td>
<td><p>68,6</p></td>
</tr>
<tr class="odd">
<td><p>Recepción principal de video</p></td>
<td><p>H.264 y/o RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>Envío principal de video</p></td>
<td><p>H.264 y/o RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>Recepción de video panorámico</p></td>
<td><p>H.264 y/o RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010 (para una resolución máxima de 1920x288)</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>Envío de video panorámico</p></td>
<td><p>H.264 y/o RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (para enviar secuencias de bit usando varias resoluciones/códecs</p></td>
<td><p>No aplicable</p></td>
</tr>
</tbody>
</table>


Para el vídeo principal, la secuencia típica y máximo del ancho de banda es el ancho de banda agregado sobre todos las secuencias de vídeo del receptor y en todos las secuencias de video respectivamente. Aún con varias secuencias de vídeo, el ancho de banda típico para vídeo es más pequeño que el escenario punto a punto debido a que muchas conferencias de vídeo están utilizando para compartir contenido que dirige a ventanas más pequeñas de video y, pro lo tanto, menores resoluciones. La carga de video agregada máxima compatible es de 8000 Kbps para ambos, enviar y recibir secuencias que se utilizarán, es decir, si hay dos secuencias de vídeo entrantes de 1920x1080p.

El ancho de banda típico para el video panorámico se basa en los dispositivos actualmente disponibles que solo envían hasta 960x144 de video panorámico. Después de que se dispone de un video panorámico de 1920x288, se espera que aumente el ancho de banda típico.

### <a name="audio-capacity-planning-for-pstn"></a>Planificación de la capacidad de audio para el RTC

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Multimedia</th>
<th>Códec típico</th>
<th>Ancho de banda de secuencia típica (Kbps)</th>
<th>Ancho de banda de secuencia máximo sin FEC</th>
<th>Ancho de banda de secuencia máximo con FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>G. 711 (esto incluye a los participantes de la RTC en conferencias)</p></td>
<td><p>64,8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Banda estrecha de RTAudio</p></td>
<td><p>30,9</p></td>
<td><p>44,8</p></td>
<td><p>56,6</p></td>
</tr>
</tbody>
</table>


los números del ancho de banda de red en estas tablas representa solo el tráfico de una vía e incluye 5 Kbps para los gastos del tráfico RTCP. Para obtener la velocidad de bits máxima de video se utiliza para la secuencia máxima del PC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

