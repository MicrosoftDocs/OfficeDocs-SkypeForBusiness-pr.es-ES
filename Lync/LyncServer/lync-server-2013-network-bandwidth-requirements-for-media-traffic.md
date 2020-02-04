---
title: Requisitos de ancho de banda de red de Lync Server 2013 para el tráfico multimedia
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
ms.openlocfilehash: 684f13a10c066e8902bed0024d7546017450ee9e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-09-24_

Una parte importante de la planificación de la red es asegurarse de que la red puede controlar el tráfico multimedia generado por Lync Server. Esta sección le ayudará a planear dicho tráfico multimedia.

<div>

## <a name="media-traffic-network-usage"></a>Uso de red de tráfico de medios

El uso del ancho de banda de tráfico multimedia puede resultar difícil de calcular por la cantidad de variables distintas, como el uso de códecs, la resolución y los niveles de actividad. El uso del ancho de banda es una función del códec usado y la actividad de la secuencia, y ambos varían entre los escenarios. En la tabla siguiente se enumeran los códecs de audio que se usan con más frecuencia en escenarios de 2013 de Lync Server.

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
<th>Velocidad de carga de audio (KBPS)</th>
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
<td><p>G.722</p></td>
<td><p>Conferencias</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>95,6</p></td>
<td><p>159,6</p></td>
</tr>
<tr class="even">
<td><p>G.722 estéreo</p></td>
<td><p>Conferencia punto a punto, Conferencia</p></td>
<td><p>128,0</p></td>
<td><p>144,0</p></td>
<td><p>159,6</p></td>
<td><p>223,6</p></td>
</tr>
<tr class="odd">
<td><p>G.711</p></td>
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


Los números de ancho de banda de la tabla anterior se basan en la 20ms de paquetes (50 paquetes por segundo) y para Siren y G. 722 incluyen la sobrecarga de protocolo de transporte seguro adicional (SRTP) de los escenarios de conferencia y Supongamos que la transmisión es 100% activa. La corrección de errores de reenvío (FEC) se usa dinámicamente cuando se pierde el paquete en el vínculo para ayudar a mantener la calidad de la secuencia de audio.

La versión estéreo del códec G. 722 es usada por los sistemas basados en el sistema de salas de Lync, que permite que la captura de micrófono estéreo permita a las escuchas distinguir mejor a varios de los hablantes de la sala de reuniones.

Para vídeo, el códec predeterminado es el estándar de codificación de video H. 264/MPEG-4, parte 10, junto con sus extensiones de codificación de video escalables para la escalabilidad temporal. Para mantener la interoperabilidad con los clientes de Lync 2010 o de Office Communicator 2007 R2, el códec RTVideo se sigue usando para las llamadas de punto a punto entre Lync 2013 y los clientes heredados. En sesiones de conferencia con los clientes heredados y de Lync 2013, el punto de conexión de Lync 2013 puede codificar el vídeo con ambos códecs de vídeo y enviar el Bitstream H. 264 a Lync 2013 y a RTVideo Bitstream a Lync 2010 o a clientes de Office Communicator 2007 R2.

El ancho de banda necesario depende de la resolución, la calidad y la velocidad de fotogramas. Para cada resolución, hay dos tarifas de bits interesantes:

  - **Velocidad de carga máxima**   es la velocidad de bits que un punto de conexión de Lync 2013 usará para la resolución a la velocidad de fotogramas máxima admitida para esta resolución. Este valor es interesante porque permite el vídeo de mayor calidad y velocidad de fotogramas.

  - **Velocidad de carga mínima**   : es la velocidad de bits a partir de la cual un punto final de Lync 2013 cambiará a la siguiente resolución más baja. Para garantizar una determinada resolución, la velocidad de carga de vídeo disponible no debe ser inferior a la de la velocidad de bits mínima para esa resolución. Este valor es interesante para que pueda comprender el valor más bajo posible en los casos en los que la velocidad de bits máxima no está disponible o es factible. En el caso de algunos usuarios, un vídeo con una velocidad de bits baja puede considerarse una experiencia de video inaceptable, por lo que debe tener cuidado cuando considere estas velocidades mínimas de carga de video. Ten en cuenta que, para las escenas de video con muy poco o ningún movimiento del usuario, la velocidad de bits real también puede descender temporalmente por debajo de la velocidad de bits mínima.

Lync 2013 admite muchas más resoluciones. Esto le permite ajustarse mejor a diferentes anchos de banda de red y a recibir capacidades de cliente. Además, la relación de aspecto predeterminada para Lync 2013 se ha cambiado a 16:9. La relación de aspecto 4:3 aún es compatible con las cámaras Web que no permiten la captura en la relación de aspecto 16:9.

### <a name="video-resolution-bandwidth"></a>Ancho de banda de resolución de vídeo

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Códec de vídeo</th>
<th>Resolución y relación de aspecto</th>
<th>Velocidad máxima de carga de vídeo (kbps)</th>
<th>Velocidad de carga de vídeo mínima (kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>320 x 180 (16:9)</p>
<p>212 x 160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>4,5</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>424 x 240 (16:9))</p>
<p>320 x 240 (4:3</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>480 x 270 (16:9)</p>
<p>424 x 320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>640 x 360 (16:9)</p>
<p>640 x 480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>848 x 480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>960 x 540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>1280 x 720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1920 x 1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>960 x 144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>4,5</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1280 x 192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>1920 x 288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


El vídeo FEC se incluye en la tasa de bits de carga de vídeo cuando se usa, por lo que no hay valores separados con FEC de video y sin FEC de video.

Los extremos no hacen fluir los paquetes de audio y vídeo continuamente. Dependiendo del escenario existen varios niveles de actividades de secuencia que indican la frecuencia con los que los paquetes se envían a una secuencia. La actividad de una secuencia depende de los medios y el escenario, y no depende del códec que se utiliza. En un escenario entre pares:

  - Los extremos envían secuencias de audio solo cuando los usuarios hablan.

  - Ambos participantes reciben secuencias de audio.

  - Si se usa vídeo, ambos puntos de conexión envían y reciben transmisiones de video durante toda la llamada.

  - Para escenas de video con poco o ningún movimiento, la velocidad de bits real es muy baja, ya que el códec de vídeo omitirá las regiones de codificación del vídeo sin cambiar.

En un escenario de conferencias:

  - Los extremos envían secuencias de audio solo cuando los usuarios hablan.

  - Todos los participantes reciben secuencias de audio.

  - Si se utiliza el vídeo, los participantes pueden recibir hasta cinco secuencias de vídeo de recepción y una panorámica (por ejemplo, con una relación de aspecto de 20:3). De forma predeterminada, las cinco secuencias de vídeo de recepción se basan en el historial de hablantes activos, pero los usuarios también pueden seleccionar de forma manual los participantes de los que desean recibir una secuencia de vídeo.

  - Cada participante que enciende la secuencia de vídeo del usuario enviará una o más secuencias de vídeo. Lync 2013 agregar hasta cinco transmisiones de vídeo para optimizar la calidad de video para todos los clientes receptores. La cantidad real de secuencias de vídeo que se envía automáticamente está determinado por quien envía, según la capacidad de la CPU, ancho de banda ascendente disponible y la cantidad de recibir clientes que solicitan cierta secuencia de vídeo. El caso más común es el de H.264 y una secuencia de vídeo de RTVideo se envían en caso de que un cliente heredado se una a la conferencia. Otro escenario común es que varias secuencias de vídeo H.264 (por ejemplo, con resoluciones de vídeo diferente) se envían para acomodar diferentes solicitudes de receptor.

Además del ancho de banda necesario para el tráfico del protocolo de transporte seguro en tiempo real (RTP) para los medios de audio o vídeo, el ancho de banda es necesario para el protocolo de control de transporte en tiempo real (RTCP). El RTCP se utiliza para informar de estadísticas y del control fuera de banda de la secuencia RTP. Para la planificación, use los números del ancho de banda de la tabla siguiente para el tráfico RTCP. Estos valores representan el ancho de banda máximo que se usa para RTCP y difieren entre las transmisiones de audio y vídeo a causa de las diferencias en los datos de control

### <a name="rtcp-bandwidth"></a>Ancho de banda de RTCP

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Medios</th>
<th>Ancho de banda máximo RTCP (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>Vídeo (solo se envía/recibe H.264 o RTVideo)</p></td>
<td><p>base10</p></td>
</tr>
<tr class="odd">
<td><p>Vídeo (se envía/recibe H.264 y RTVideo)</p></td>
<td><p>4,5</p></td>
</tr>
</tbody>
</table>


Con fines de planeación de capacidad, los dos anchos de banda siguientes son de interés:

  - **Ancho de banda máximo sin FEC**   el ancho de banda máximo que consumirá una secuencia, incluida la actividad típica de la transmisión y el códec típico que se usa en el escenario sin FEC.Este es el ancho de banda cuando la transmisión está al 100% de actividad y no hay pérdida de paquetes que activen el uso de FEC.Esto es interesante para calcular la cantidad de ancho de banda que se debe asignar para permitir que el códec se use en un escenario determinado. 

  - **Ancho de banda máximo con FEC**   el ancho de banda máximo que consume una transmisión, incluida la actividad típica de la transmisión y el códec típico que se usa en el escenario con FEC. Este es el ancho de banda cuando la transmisión está al 100% de actividad y se produce una pérdida de paquetes al activar el uso de FEC para mejorar la calidad. Esto es interesante para calcular cuánto ancho de banda debe asignarse para permitir que el códec se use en un escenario determinado y permitir el uso de FEC para preservar la calidad en condiciones de pérdida de paquetes. 

En las siguientes tablas también se muestra un valor de ancho de banda adicional, un **ancho de banda típico**. Este es el ancho de banda medio que consume una secuencia, incluida la actividad típica de la secuencia y el códec típico usado en el escenario. Este ancho de banda se puede usar para aproximar cuánto ancho de banda en un momento dado está siendo consumido por el tráfico multimedia pero que no debe usarse para el plan de capacidad, porque las llamadas individuales superarán este valor cuando el nivel de actividad es superior al promedio. El ancho de banda de la secuencia de vídeo típica de las tablas siguientes se basa en una combinación de diferentes resoluciones de video, como se observa en los datos medidos de los clientes. Por ejemplo, en sesiones de punto a punto, la mayoría de los usuarios usaría la ventana de representación de video predeterminada, mientras que un porcentaje de usuarios aumentaría o maximizaría la aplicación de Lync para ofrecer una resolución de video superior.

En las siguientes tablas se proporcionan estos tres valores de ancho de banda para los diversos escenarios.

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>Planificación de la capacidad de audio/vídeo para sesiones entre pares

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
<th>Media</th>
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
<td><p>H.264</p></td>
<td><p>460</p></td>
<td><p>4010 (para una resolución máxima de 1920 x 1080)</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>Vídeo principal al llamar a los puntos de conexión de Lync 2010 o de Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (para una resolución máxima de 1920 x 720)</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>Vídeo panorámico al llamar a puntos de conexión de Lync 2013</p></td>
<td><p>H.264</p></td>
<td><p>190</p></td>
<td><p>2010 (para una resolución máxima de 1920 x 288)</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>Vídeo panorámico al llamar a Lync 2010 o a los puntos de conexión de Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (para una resolución máxima de 1920 x 144)</p></td>
<td><p>No aplicable</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>Planificación de la capacidad de audio/vídeo para conferencias

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
<th>Media</th>
<th>Códec típico</th>
<th>Ancho de banda de secuencia típica (Kbps)</th>
<th>Ancho de banda de secuencia máximo sin FEC</th>
<th>Ancho de banda de secuencia máximo con FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>G.722</p></td>
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
<td><p>Recepción principal de vídeo</p></td>
<td><p>H. 264 y/o RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>Envío principal de vídeo</p></td>
<td><p>H. 264 y/o RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="odd">
<td><p>Recepción de vídeo panorámico</p></td>
<td><p>H. 264 y/o RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010 (para una resolución máxima de 1920 x 288)</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>Envío de vídeo panorámico</p></td>
<td><p>H. 264 y/o RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (para enviar bitstreams con varias resoluciones o códecs)</p></td>
<td><p>No aplicable</p></td>
</tr>
</tbody>
</table>


En el vídeo principal, el ancho de banda de transmisión máximo y típico es el ancho de banda agregado en todas las transmisiones de vídeo recibidas y en todas las videollamadas de envío. Incluso con varias secuencias de vídeo, el ancho de banda de vídeo típico es menor que en el caso de punto a punto, ya que muchas videoconferencias usan contenido compartido que genera una gran cantidad de vídeos y pequeñas resoluciones de video. El ancho de banda máximo admitido de carga de vídeo agregado es de 8000 Kbps para ambas, enviar y recibir transmisiones que se usarían, por ejemplo, si hay dos flujos de video 1920x1080p entrantes.

El ancho de banda típico para videos panorámicos se basa en los dispositivos disponibles actualmente que solo se transmiten a 960x144 panorámico de vídeo. Una vez que los dispositivos con video panorámico 1920x288 estén disponibles, se espera que aumente el ancho de banda típico de la secuencia.

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
<th>Media</th>
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


Las cifras de ancho de banda de red de estas tablas representan solamente tráfico unidireccional; incluyen 5 Kpbs para sobrecarga de tráfico RTPC de cada secuencia. Para el vídeo, se usa la máxima tasa de bits de vídeo para calcular la transmisión máxima.

</div>

</div>

<span> </span>

</div>

</div>

</div>

