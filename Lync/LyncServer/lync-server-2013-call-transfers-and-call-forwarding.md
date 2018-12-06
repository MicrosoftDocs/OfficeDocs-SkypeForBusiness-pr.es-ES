---
title: 'Lync Server 2013: Transferencia y desvío de llamadas'
TOCTitle: Transferencia y desvío de llamadas
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994051(v=OCS.15)
ms:contentKeyID: 52061687
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Transferencia y desvío de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cuando interviene un extremo de RTC, el enrutamiento basado en ubicación analiza la ubicación del extremo del autor de la llamada y del extremo al que se transferirá o se desviará la llamada (el destino de la transferencia o el desvío). El enrutamiento basado en ubicación determina si la llamada se debe transferir o desviar según la ubicación de ambos extremos.

La siguiente tabla representa un escenario en el que un usuario de Lync tiene una llamada en curso con un extremo de RTC, y el usuario de Lync transfiere la llamada a otro usuario de Lync. Dependiendo de la ubicación del sitio de red del extremo del usuario al que se transfiere la llamada, el enrutamiento basado en ubicación afectará a la transferencia o el desvío de la llamada.

### Inicio de la transferencia o el desvío de la llamada

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Usuario que inicia la transferencia o el desvío de la llamada</th>
<th>El extremo de destino está en el mismo sitio de red que el usuario que inicia la transferencia o el desvío de la llamada</th>
<th>El extremo de destino está en un sitio de red diferente del del usuario que inicia la transferencia o el desvío de la llamada</th>
<th>El extremo de destino está en un sitio de red desconocido o en un sitio de red que no está habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuario de Lync</p></td>
<td><p>Se permite el desvío o la transferencia de la llamada</p></td>
<td><p>No se permite el desvío ni la transferencia de la llamada</p></td>
<td><p>No se permite el desvío ni la transferencia de la llamada</p></td>
</tr>
</tbody>
</table>

  

Por ejemplo: un usuario de Lync que tiene una llamada en curso con un extremo de RTC transfiere la llamada a otro usuario de Lync que está en el mismo sitio de red. En este caso, se permite la transferencia de la llamada.

La siguiente tabla representa un escenario en el que un usuario de Lync tiene una llamada en curso con otro usuario de Lync, y uno de los usuarios transfiere la llamada a un extremo de RTC. La tabla recoge los detalles de cómo el enrutamiento basado en ubicación afecta a la llamada en función de la ubicación del usuario al que se va a transferir la llamada.

### Transferencia o desvío de la llamada al extremo de RTC

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino de extremo de la transferencia o el desvío de la llamada</th>
<th>Usuarios de Lync en el mismo sitio de red</th>
<th>Usuarios de Lync en sitios de red distintos</th>
<th>Uno de los usuarios de Lync o los dos están en un sitio de red desconocido, o bien el sitio de red no está habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extremo RTC</p></td>
<td><p>Desvío o transferencia de llamada permitido por la directiva de enrutamiento de voz del sitio del usuario al que se transfiere la llamada</p></td>
<td><p>Desvío o transferencia de llamada permitido por la directiva de enrutamiento de voz del sitio del usuario al que se transfiere la llamada</p></td>
<td><p>Desvío o transferencia de llamada permitido por la directiva de voz del usuario al que se transfiere la llamada únicamente a través de troncos no habilitados para el enrutamiento basado en ubicación</p></td>
</tr>
</tbody>
</table>

  
Por ejemplo: un usuario de Lync que tiene una llamada en curso con otro usuario de Lync que está en el mismo sitio de red transfiere la llamada a un extremo de RTC y la transferencia de la llamada se permite.

## Vea también

#### Otros recursos

[Escenarios para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

