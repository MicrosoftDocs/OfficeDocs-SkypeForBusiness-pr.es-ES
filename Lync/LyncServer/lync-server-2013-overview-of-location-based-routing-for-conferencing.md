---
title: Introducción al enrutamiento basado en ubicación de las conferencias
TOCTitle: Introducción al enrutamiento basado en ubicación de las conferencias
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56271309
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Introducción al enrutamiento basado en ubicación de las conferencias

 

_**Última modificación del tema:** 2015-03-09_

La aplicación de conferencias de enrutamiento basado en ubicación proporciona a las conferencias de Lync un mecanismo para prevenir la omisión de tarifas RTC. La aplicación supervisa las conferencias activas y aplica restricciones de enrutamiento basado en ubicación según la ubicación de los usuarios de Lync que participan.

La aplicación de conferencias de enrutamiento basado en ubicación determina si se debe aplicar el enrutamiento basado en ubicación en una reunión de Lync si se cumplen los siguientes criterios:

  - El organizador de la reunión tiene habilitado el enrutamiento basado en ubicación. Se aplicarán restricciones de enrutamiento basado en ubicación únicamente a las conferencias organizadas por usuarios que tienen habilitado el enrutamiento basado en ubicación.

  - Al menos un participante de la reunión es un extremo RTC. Se aplicarán restricciones de enrutamiento basado en ubicación únicamente a las conferencias que incluyen extremos RTC.

  - Se localiza el sitio de red que usó la puerta de enlace RTC para conectar la conferencia a la RTC, así como los sitios de red desde donde se conectan los organizadores y participantes.

La aplicación de conferencias de enrutamiento basado en ubicación no permite la participación de usuarios de Lync y extremos RTC de distintos sitios de red en la misma conferencia. Si el organizador de una reunión tiene habilitado el enrutamiento basado en ubicación, la aplicación de conferencias aplica las siguientes restricciones:

  - Los extremos que pueden unirse a una reunión de Lync dependen de los extremos que ya se unieron a la conferencia, y esta restricción se ajusta a medida que los extremos conectados abandonan la conferencia y nuevos extremos se unen a ella. Si los organizadores y participantes se unen a una reunión de Lync desde el mismo sitio de red, entonces pueden unirse un extremo RTC, otro participante del mismo sitio de red, un participante de otro sitio de red y uno de un sitio de red desconocido.

  - Si los organizadores y participantes se unen a una reunión desde sitios de red distintos o desconocidos, no puede unirse un extremo RTC si la llamada RTC ingresa desde un tronco SIP habilitado para el enrutamiento basado en ubicación.

  - Si los organizadores y participantes se unen a la reunión desde el mismo sitio de red y algunos participantes se unen desde la RTC, no puede unirse un extremo de Lync desde otro sitio de red.

Estas restricciones de enrutamiento basado en ubicación para conferencias se resumen en la siguiente tabla.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Usuarios de una conferencia en cualquier punto</p></td>
<td><p>Usuarios que pueden unirse a la conferencia</p></td>
<td><p>Usuarios que no pueden unirse a la conferencia</p></td>
</tr>
<tr class="even">
<td><p>Usuarios del cliente VoIP de Lync de un solo sitio de red</p></td>
<td><p>Usuario del cliente VoIP de Lync del mismo sitio de red</p>
<p>Usuario del cliente VoIP de Lync de otro sitio de red</p>
<p>Usuario del cliente VoIP de Lync de un sitio de red desconocido</p>
<p>Usuario del cliente VoIP de Lync federado</p>
<p>Usuario que se une desde un extremo RTC</p></td>
<td><p>Ninguno</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>Usuarios del cliente VoIP de Lync de un sitio de red desconocido</p></td>
<td><p>Usuario del cliente VoIP de Lync de cualquier sitio</p>
<p>Usuario del cliente VoIP de Lync de un sitio desconocido</p>
<p>Usuario del cliente VoIP de Lync federado</p></td>
<td><p>Usuario que se une a través de un extremo RTC</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>Usuarios del cliente VoIP de Lync de otros sitios de red</p></td>
<td><p>Usuario del cliente VoIP de Lync de cualquier sitio de red</p>
<p>Usuario del cliente VoIP de Lync de un sitio de red desconocido</p>
<p>Usuario del cliente VoIP de Lync federado</p></td>
<td><p>Usuario que se une a través de un extremo RTC</p></td>
</tr>
<tr class="odd">
<td><p>Usuarios del cliente VoIP de Lync de un solo sitio de red y usuarios que se unen desde un extremo RTC</p></td>
<td><p>Usuario del cliente VoIP de Lync del mismo sitio de red</p>
<p></p></td>
<td><p>Usuario del cliente VoIP de Lync de otro sitio de red</p>
<p>Usuario del cliente VoIP de Lync de un sitio de red desconocido</p>
<p>Usuario del cliente VoIP de Lync federado</p></td>
</tr>
</tbody>
</table>


Estas son características adicionales de la aplicación de conferencias de enrutamiento basado en ubicación:

  - Cuando un usuario no puede unirse a una conferencia debido a las restricciones de enrutamiento basado en ubicación, se rechazará su llamada a la conferencia y el cliente Lync informará de que esta no se ha completado o ha finalizado.

  - Independientemente de su estado, no se impedirá la conexión de un extremo RTC que se une a una conferencia con restricciones de enrutamiento basado en ubicación si lo hace a través de un tronco que no tiene habilitado el enrutamiento basado en ubicación.

  - Un sistema PBX conectado a un servidor de mediación a través de un tronco SIP que no realiza llamadas a la RTC tendrá las mismas restricciones que los usuarios de Lync ubicados en el mismo sitio de red en el que está definido el tronco SIP. Por ejemplo, un extremo RTC podrá unirse a una conferencia con un usuario de PBX y uno de Lync si se encuentran en el mismo sitio de red. Por el contrario, el extremo RTC no podrá unirse si el usuario de PBX y el de Lync se encuentran en sitios de red diferentes.

