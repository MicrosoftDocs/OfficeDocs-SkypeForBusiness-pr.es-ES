---
title: Transferencias de llamadas de consulta y enrutamiento basado en ubicación
TOCTitle: Transferencias de llamadas de consulta y enrutamiento basado en ubicación
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56271355
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Transferencias de llamadas de consulta y enrutamiento basado en ubicación

 

_**Última modificación del tema:** 2015-03-09_

Además de aplicar el enrutamiento basado en ubicación en las reuniones de Lync, la aplicación de conferencias de enrutamiento basado en ubicación aplica las restricciones de esta característica en las consultas de transferencia de llamada que se realizan a extremos RTC. Las consultas de transferencia de llamada son llamadas que se establecen entre dos partes, en las que una de ellas transfiere la llamada a un nuevo usuario. Por ejemplo, un extremo RTC llama al usuario A (destinatario de la llamada de Lync). El usuario A determina que el usuario de RTC se debe transferir al usuario B (usuario de Lync). El usuario A llama al usuario B con el usuario de RTC en espera. El usuario B acepta hablar con el usuario de RTC. El usuario A transfiere la llamada en espera al usuario B.

**Flujo de llamadas de consultas de transferencia de llamada**

![Enrutamiento basado en ubicación para diagrama de conferencias](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Enrutamiento basado en ubicación para diagrama de conferencias")

Cuando un usuario habilitado para el enrutamiento basado en ubicación inicia una consulta de transferencia de llamada de un extremo RTC (como se muestra en la ilustración anterior), se crean dos llamadas activas: una entre el usuario de RTC y el usuario A de Lync, y otra entre el usuario A de Lync y el usuario B de Lync. La aplicación de conferencias de enrutamiento basado en ubicación aplica el siguiente comportamiento:

  - Si el tronco SIP que enruta la llamada RTC tiene autorización para reenrutarla al sitio de red en el que se encuentra el usuario B de Lync (es decir, el destino de la transferencia), se permitirá la transferencia de la llamada. De lo contrario, la consulta de transferencia de llamada se bloqueará. Esta autorización se concede si la parte transferida se encuentra en el mismo sitio de red que el tronco SIP que enruta la llamada activa al extremo RTC.

  - Si el tronco SIP que enruta la llamada RTC entrante no tiene autorización para enrutar llamadas al sitio de red en el que se encuentra la parte transferida (el usuario B de Lync) o la parte transferida se encuentra en un sitio de red desconocido, la consulta de transferencia de llamada al extremo RTC (es decir, el destino de la transferencia) se bloqueará.

En la siguiente tabla se describe cómo la aplicación de conferencias de enrutamiento basado en ubicación aplica las restricciones correspondientes para las consultas de transferencia de llamada. Si bien los extremos PBX no se asocian directamente con ningún sitio de red, se puede asignar uno al tronco SIP al que el PBX está conectado. De esta forma, el extremo PBX estará asociado a un sitio de red indirectamente.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Sitio de red de la parte transferida</p></td>
<td><p>Sitio de red del destino de la transferencia de llamada</p></td>
<td><p>Comportamiento</p></td>
</tr>
<tr class="even">
<td><p>Extremo RTC</p></td>
<td><p>Usuario de Lync en el mismo sitio de red (es decir, en el sitio 1)</p></td>
<td><p>Se permitirá la consulta de transferencia</p></td>
</tr>
<tr class="odd">
<td><p>Extremo RTC</p></td>
<td><p>Usuario de Lync en otros sitios de red (es decir, en el sitio 2)</p></td>
<td><p>No se permitirá la consulta de transferencia</p></td>
</tr>
<tr class="even">
<td><p>Extremo RTC</p></td>
<td><p>Usuario de Lync en un sitio de red desconocido</p></td>
<td><p>No se permitirá la consulta de transferencia</p></td>
</tr>
<tr class="odd">
<td><p>Extremo RTC</p></td>
<td><p>Usuario de Lync federado</p></td>
<td><p>No se permitirá la consulta de transferencia</p></td>
</tr>
<tr class="even">
<td><p>Extremo RTC</p></td>
<td><p>Extremo PBX en el mismo sitio (es decir, en el sitio 1)</p></td>
<td><p>Se permitirá la consulta de transferencia</p></td>
</tr>
<tr class="odd">
<td><p>Extremo RTC</p></td>
<td><p>Extremo PBX en otro sitio (es decir, en el sitio 2)</p></td>
<td><p>No se permitirá la consulta de transferencia</p></td>
</tr>
<tr class="even">
<td><p>Extremo PBX en el mismo sitio (es decir, en el sitio 1)</p></td>
<td><p>Extremo RTC</p></td>
<td><p>Se permitirá la consulta de transferencia</p></td>
</tr>
<tr class="odd">
<td><p>Extremo PBX en otro sitio (es decir, en el sitio 2)</p></td>
<td><p>Extremo RTC</p></td>
<td><p>No se permitirá la consulta de transferencia</p></td>
</tr>
<tr class="even">
<td><p>Extremo PBX en cualquier sitio</p></td>
<td><p>Usuario de Lync en el mismo sitio de red (es decir, en el sitio 1)</p></td>
<td><p>Se permitirá la consulta de transferencia</p></td>
</tr>
<tr class="odd">
<td><p>Extremo PBX en cualquier sitio</p></td>
<td><p>Usuario de Lync en otros sitios de red (es decir, en el sitio 2)</p></td>
<td><p>Se permitirá la consulta de transferencia</p></td>
</tr>
<tr class="even">
<td><p>Extremo PBX en cualquier sitio</p></td>
<td><p>Usuario de Lync en un sitio de red desconocido</p></td>
<td><p>Se permitirá la consulta de transferencia</p></td>
</tr>
<tr class="odd">
<td><p>Extremo PBX en cualquier sitio</p></td>
<td><p>Usuario de Lync federado</p></td>
<td><p>Se permitirá la consulta de transferencia</p></td>
</tr>
</tbody>
</table>

