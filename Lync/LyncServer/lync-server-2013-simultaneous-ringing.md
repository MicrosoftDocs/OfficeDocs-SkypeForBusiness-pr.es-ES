---
title: 'Lync Server 2013: Tono de llamada simultáneo'
TOCTitle: Tono de llamada simultáneo
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994079(v=OCS.15)
ms:contentKeyID: 52061808
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tono de llamada simultáneo en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cuando el destinatario de la llamada tiene habilitadas las llamadas simultáneas, el enrutamiento basado en ubicación analiza la ubicación del autor de la llamada y de los extremos de los destinatarios para determinar si se debe enrutar la llamada.

En la siguiente tabla se muestra un usuario con la configuración de llamadas simultáneas habilitada y el destino de llamadas simultáneas es un usuario en el mismo sitio de red, en un sitio de red diferente o en un sitio de red desconocido.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Llamada RTC entrante para</th>
<th>Ubicado en el mismo sitio de red que el destinatario</th>
<th>Ubicado en un sitio de red diferente que el del destinatario</th>
<th>Ubicado en un sitio de red desconocido o no habilitado para enrutamiento según ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuario de Lync</p></td>
<td><p>Llamadas simultáneas permitidas</p></td>
<td><p>Llamadas simultáneas no permitidas</p></td>
<td><p>Llamadas simultáneas no permitidas</p></td>
</tr>
</tbody>
</table>

  
En la siguiente tabla se muestra una llamada de un usuario de Lync (es decir, el autor de la llamada de Lync) en el mismo sitio de red, en un sitio de red diferente o desde un sitio de red desconocido. El destinatario de la llamada tiene un extremo RTC (es decir, un teléfono celular) configurado como destino de llamadas simultáneas. En este escenario, el enrutamiento basado en la ubicación determinará si la llamada debe derivarse o no al destino de llamadas simultáneas (es decir, el teléfono celular) del destinatario de la llamada.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino de llamadas simultáneas</th>
<th>Ubicado en el mismo sitio de red que el destinatario</th>
<th>Ubicado en un sitio de red diferente que el del destinatario</th>
<th>Ubicado en un sitio de red desconocido o no habilitado para enrutamiento según ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extremo RTC</p></td>
<td><p>Llamadas simultáneas permitidas mediante la directiva de enrutamiento de voz del sitio del autor de la llamada</p></td>
<td><p>Llamadas simultáneas permitidas mediante la directiva de enrutamiento de voz del sitio del autor de la llamada</p></td>
<td><p>Llamadas simultáneas permitidas mediante la directiva de enrutamiento de voz del autor de la llamada para troncos no habilitados para el enrutamiento basado en la ubicación</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Otros recursos

[Escenarios para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

