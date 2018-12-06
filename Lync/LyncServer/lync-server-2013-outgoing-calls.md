---
title: 'Lync Server 2013: Llamadas salientes'
TOCTitle: Llamadas salientes
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994049(v=OCS.15)
ms:contentKeyID: 52061705
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Llamadas salientes en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El enrutamiento de llamadas salientes para usuarios habilitados para el enrutamiento según ubicación se ve afectado por la ubicación de red del extremo del usuario. En la siguiente tabla se ilustra cómo afecta el enrutamiento según ubicación al enrutamiento de las llamadas salientes según la ubicación del extremo del autor de la llamada.

### El autor de la llamada hace una llamada saliente al RTC

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>El extremo del usuario se encuentra en un sitio de red habilitado para el enrutamiento según ubicación</th>
<th>El extremo del usuario se encuentra en un sitio de red desconocido o no habilitado para el enrutamiento según ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorización de llamadas salientes</p></td>
<td><p>La llamada se autoriza según la directiva de voz del usuario</p></td>
<td><p>La llamada se autoriza según la directiva de voz del usuario</p></td>
</tr>
<tr class="even">
<td><p>Enrutamiento de llamadas salientes</p></td>
<td><p>La llamada se enruta según la directiva de enrutamiento de voz del sitio de red</p></td>
<td><p>La llamada se enruta según la directiva de voz del usuario y solo a través de troncos no habilitados para el enrutamiento según ubicación (si está disponible)</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Otros recursos

[Escenarios para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

