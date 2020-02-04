---
title: 'Lync Server 2013: información general sobre el enrutamiento basado en la ubicación para conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adb103d1f2314e033d9ef0958dd05a7648012bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Información general de enrutamiento basado en ubicación para conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-19_

La aplicación de conferencia de enrutamiento basada en la ubicación proporciona a las conferencias de Lync un mecanismo para la prevención de la omisión de llamadas RTC. La aplicación supervisa las conferencias activas e impone restricciones de enrutamiento basadas en la ubicación en función de la ubicación de los usuarios de Lync que participan.

La aplicación de conferencia de enrutamiento basada en la ubicación determina si se debe aplicar el enrutamiento basado en la ubicación en una reunión de Lync si se cumplen los criterios siguientes:

  - El organizador de la reunión está habilitado para el enrutamiento basado en la ubicación. Las restricciones de enrutamiento basadas en la ubicación solo se aplicarán a conferencias organizadas por usuarios que están habilitados para el enrutamiento basado en la ubicación.

  - Al menos uno de los participantes de la reunión es un extremo de RTC. Las restricciones de enrutamiento basadas en la ubicación solo se aplican a las conferencias que incluyen puntos de conexión RTC.

  - El sitio de red donde se utiliza la puerta de enlace RTC para conectar la conferencia con la RTC se encuentra (al igual que los sitios de red) en la ubicación desde donde se conectan los organizadores y los participantes.

La aplicación de conferencia de enrutamiento basado en la ubicación impide la participación de los usuarios de Lync y los puntos finales de RTC de diferentes sitios de red en la misma conferencia. Si el organizador de una reunión está habilitado para el enrutamiento basado en la ubicación, la aplicación de conferencias aplicará las siguientes restricciones:

  - Los puntos de conexión que pueden unirse a una reunión de Lync dependen de los puntos de conexión que ya se hayan unido a la Conferencia, y esta restricción se ajusta como puntos de conexión Unidos y los puntos de conexión nuevos se unen a la Conferencia. Si los organizadores y los participantes se unen a una reunión de Lync desde el mismo sitio de red, se permite que otro participante de RTC, otro participante del mismo sitio de red, otro participante de un sitio de red diferente o de un participante de un sitio de red desconocido participación.

  - Si organizadores y participantes se unen a la reunión desde diferentes sitios de red o sitios de red desconocidos, no se permite la entrada a la reunión de un extremo de RTC, si la llamada de RTC entra de un tronco SIP habilitado para el enrutamiento basado en ubicación.

  - Si todos los organizadores y participantes se unen a la reunión desde el mismo sitio de red y hay participantes que se unen a la misma reunión de la RTC, no se permite unirse a la reunión con un punto de conexión de Lync desde un sitio de red diferente.

En la tabla siguiente se resumen las restricciones de enrutamiento basadas en la ubicación de las conferencias.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Usuario(s) en una conferencia en un momento determinado</p></td>
<td><p>Usuarios(s) con permiso para unirse a la conferencia</p></td>
<td><p>Usuarios(s) sin permiso para unirse a la conferencia</p></td>
</tr>
<tr class="even">
<td><p>Usuarios del cliente de VoIP de Lync desde un único sitio de red</p></td>
<td><p>Usuario de cliente de VoIP de Lync desde el mismo sitio de red</p>
<p>Usuario de cliente de VoIP de Lync desde un sitio de red diferente</p>
<p>Usuario de cliente de VoIP de Lync desde un sitio de red desconocido</p>
<p>Usuario del cliente VoIP de Lync federado</p>
<p>Usuario que se une desde un extremo de RTC</p></td>
<td><p>Ninguno</p></td>
</tr>
<tr class="odd">
<td><p>Usuarios del cliente de VoIP de Lync desde un sitio de red desconocido</p></td>
<td><p>Usuario de cliente de VoIP de Lync desde cualquier sitio</p>
<p>Usuario de cliente de VoIP de Lync desde un sitio desconocido</p>
<p>Usuario del cliente VoIP de Lync federado</p></td>
<td><p>Usuario que se une a través de un extremo de RTC</p></td>
</tr>
<tr class="even">
<td><p>Usuarios de Lync VoIP clientes de diferentes sitios de red</p></td>
<td><p>Usuario de cliente de VoIP de Lync desde cualquier sitio de red</p>
<p>Usuario de cliente de VoIP de Lync desde un sitio de red desconocido</p>
<p>Usuario del cliente VoIP de Lync federado</p></td>
<td><p>Usuario que se une a través de un extremo de RTC</p></td>
</tr>
<tr class="odd">
<td><p>Usuarios del cliente de VoIP de Lync desde un único sitio de red y usuarios que se unen desde un punto final de RTC</p></td>
<td><p>Usuario de cliente de VoIP de Lync desde el mismo sitio de red</p></td>
<td><p>Usuario de cliente de VoIP de Lync desde un sitio de red diferente</p>
<p>Usuario de cliente de VoIP de Lync desde un sitio de red desconocido</p>
<p>Usuario del cliente VoIP de Lync federado</p></td>
</tr>
</tbody>
</table>


A continuación se muestran características adicionales de la aplicación de conferencia de enrutamiento basada en ubicación:

  - Cuando un usuario no puede unirse a una conferencia con las restricciones de enrutamiento basadas en la ubicación, se rechazarán las llamadas de los usuarios a la Conferencia y su cliente de Lync informará de que la llamada no se completó o ha finalizado.

  - Un punto final de RTC que se une a una conferencia con las fuerzas de enrutamiento basadas en la ubicación no se verá restringido a unirse a la Conferencia, independientemente de su estado, si el punto de conexión se une a través de un tronco que no está habilitado para el enrutamiento basado en la ubicación.

  - Un sistema PBX conectado a un servidor de mediación a través de un tronco de SIP que no esté de salida las llamadas a la RTC tendrán las mismas fuerzas que los usuarios de Lync que se encuentren en el mismo sitio de red en el que se define el tronco del SIP. Por ejemplo, un punto final de RTC podrá unirse a una conferencia con un usuario de PBX y un usuario de Lync si se encuentran en el mismo sitio de red; de lo contrario, el punto final de RTC no podrá unirse a la Conferencia si el usuario de PBX se encuentra en otro sitio de red que el usuario de Lync.

</div>

<span> </span>

</div>

</div>

</div>

