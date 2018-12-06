﻿---
title: 'Lync Server 2013: Informe de detalles de llamadas'
TOCTitle: Informe de detalles de llamadas
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48274960
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de detalles de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El Informe de detalles de llamadas ofrece una vista detallada de las llamadas individuales. El informe incluye prácticamente todas las estadísticas y métricas de calidad de experiencia recopiladas por Lync Server y se divide en secciones como las siguientes:

  - Información de llamada

  - Métricas de dispositivo y señal del autor de la llamada

  - Métricas de dispositivo y señal del destinatario de la llamada

  - Evento de cliente de autor de la llamada

  - Evento de cliente de destinatario de la llamada

  - Secuencia de audio (del autor al destinatario de la llamada)

  - Secuencia de vídeo (del autor al destinatario de la llamada)

  - Secuencia de audio (del destinatario al autor de la llamada)

  - Secuencia de vídeo (del destinatario al autor de la llamada)

Tenga en cuenta que las categorías y las métricas que se muestran en los informes depende de dos cosas: el tipo de sesión y el tipo de extremo utilizado en la sesión. Por ejemplo, no se mostrarán métricas de secuencias de vídeos en llamadas solo de audio, ya que la llamada no tiene ninguna secuencia de vídeo. Del mismo modo, puede que tenga un informe en el que solo se muestren estadísticas del autor de la llamada y no del destinatario. Ello se debe a que el destinatario de la llamada no estaba utilizando ningún dispositivo compatible con SIP. Los extremos son responsables de informar de las estadísticas al final de la llamada; sin embargo, un teléfono móvil (que no usa SIP ni estadísticas SIP) no puede informar de este tipo de información. Por ello, si llama a alguien que responde con un teléfono móvil, obtendrá un informe de dicho teléfono móvil cuando finalice la llamada.

El Informe de detalles de llamadas resulta de gran utilidad para determinar exactamente por qué se han registrado problemas de calidad multimedia en una llamada determinada.

## Acceso al Informe de detalles de llamadas

Es posible tener acceso al Informe de detalles de llamadas desde cualquiera de los informes siguientes:

  - El [Informe de ubicaciones en Lync Server 2013](lync-server-2013-location-report.md) (haciendo clic en la métrica Porcentaje de llamadas deficientes o en el Volumen de llamadas)

  - El [Informe del resumen de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (haciendo clic en la métrica Porcentaje de llamadas deficientes o Volumen de llamadas)

  - El [Informe de comparación de calidad de los medios en Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (haciendo clic en el [Informe de lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) y en la métrica Detalles).

  - El [Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md) (haciendo clic en la métrica Porcentaje de llamadas deficientes o Volumen de llamadas)

  - El [Informe de lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) (haciendo clic en la métrica Detalles)

Desde el Informe de detalles de llamadas, podrá tener acceso al [Informe de dispositivos en Lync Server 2013](lync-server-2013-device-report.md) haciendo clic en cualquiera de las métricas siguientes:

  - Dispositivo de captura

  - Dispositivo de presentación

También se puede tener acceso al Informe de tendencias de calidad de medios de servidor haciendo clic en la métrica del servidor perimetral A/V.

## Cómo sacar el máximo partido al Informe de detalles de llamadas

El Informe de detalles de llamadas incluye más de 250 métricas distintas e incluye elementos como, por ejemplo, el Desfase de marca de tiempo de micrófono, el Tiempo de SNR bajo y el Tiempo de extremo próximo a eco. Si no recuerda qué miden todas estas métricas, coloque el mouse sobre la etiqueta de la métrica para que se muestre información de descripción.

Si tiene problemas para encontrar una métrica, escriba una parte del nombre de la métrica en el cuadro de búsqueda y haga clic en Buscar. Por ejemplo, si no encuentra la métrica Tiempo de SNR bajo, escriba SNR en el cuadro de búsqueda y, a continuación, haga clic en Buscar.

Tenga en cuenta que el informe solo sigue la información de una llamada. La llamada propiamente dicha no queda registrada.

## Filtros

Ninguno. No se puede filtrar el informe de detalles de llamadas.

## Métricas

En la tabla siguiente se muestra la información que recoge el informe de detalles de llamadas sobre cada llamada.

### Métricas del informe de detalles de llamadas

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
<td><p><strong>PAI de autor de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>P-Asserted-Identity del usuario que inició la llamada. P-Asserted-Identity se utiliza para transmitir la identidad demostrada de un usuario en una red de confianza.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI de autor de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Dirección SIP del usuario que inició la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Extremo de autor de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Dispositivo usado para realizar la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente de usuario de autor de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Software usado en el dispositivo que realizó la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Inicio de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Fecha y hora en las que se realizó inicialmente la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Llamada sin pasar por el servidor de mediación</strong></p></td>
<td><p>N.º</p></td>
<td><p>Indica si la llamada se conectó a una puerta de enlace de voz RTC o a un IP PBX cualificado sin pasar por el servidor de mediación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sistema operativo del autor de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Sistema operativo del equipo del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPU de autor de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>CPU instalada en el equipo del usuario que inició la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Número de núcleo de CPU de autor de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número de procesador del equipo usado por la persona que inició la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Velocidad de CPU de autor de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Velocidad del procesador de la CPU del equipo usado por la persona que inició la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Virtualización de CPU de autor de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Virtualización (si la hay) usada en el equipo de la persona que inició la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>PAI de destinatario de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>P-Asserted-Identity del usuario invitado a unirse a la llamada. P-Asserted-Identity se utiliza para transmitir la identidad demostrada de un usuario en una red de confianza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI de destinatario de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Dirección SIP del usuario que recibió la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Extremo de destinatario de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Dispositivo usado para recibir la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente de usuario de destinatario de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Software usado en el dispositivo que recibió la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Duración</strong></p></td>
<td><p>N.º</p></td>
<td><p>Duración de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Marcador de advertencia de desvío de medios</strong></p></td>
<td><p>N.º</p></td>
<td><p>Advertencia emitida cuando se ignora el servidor de mediación.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sistema operativo del destinatario de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Sistema operativo del equipo del usuario que recibió la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPU de destinatario de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>CPU instalada en el equipo del usuario que recibió la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Número de núcleo de destinatario de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número de procesador del equipo usado por la persona que recibió la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Velocidad de CPU de destinatario de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Velocidad del procesador de la CPU del equipo usado por la persona que recibió la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Virtualización de CPU de destinatario de la llamada</strong></p></td>
<td><p>N.º</p></td>
<td><p>Virtualización (si la hay) usada en el equipo de la persona que recibió la llamada.</p></td>
</tr>
</tbody>
</table>

