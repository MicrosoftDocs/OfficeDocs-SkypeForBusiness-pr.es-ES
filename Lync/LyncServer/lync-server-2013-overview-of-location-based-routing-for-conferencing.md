---
title: 'Lync Server 2013: información general sobre el enrutamiento de Location-Based para conferencias'
description: 'Lync Server 2013: información general sobre el enrutamiento de Location-Based para conferencias.'
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
ms.openlocfilehash: 2a8fe9cdf4a797243c3ec04b3466011f374fb0d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577376"
---
# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Información general sobre el enrutamiento de Location-Based para conferencias en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-19_

La aplicación de conferencia de Location-Based enrutamiento proporciona a las conferencias de Lync un mecanismo para evitar el desvío de peajes RTC. La aplicación supervisa las conferencias activas y aplica Location-Based restricciones de enrutamiento en función de la ubicación de los usuarios de Lync que participan.

La aplicación de conferencia de Location-Based enrutamiento determina si se debe aplicar Location-Based el enrutamiento en una reunión de Lync si se cumplen los siguientes criterios:

  - El organizador de la reunión está habilitado para Location-Based enrutamiento. Location-Based restricciones de enrutamiento solo se aplicarán a las conferencias organizadas por usuarios habilitados para Location-Based enrutamiento.

  - Al menos un participante de la reunión es un punto de conexión RTC. Location-Based restricciones de enrutamiento solo son aplicables a las conferencias que incluyen extremos de RTC.

  - El sitio de red en el que se ubica la puerta de enlace RTC que se usa para salvar la Conferencia a la RTC se encuentra, así como los sitios de red desde donde se conectan los organizadores y participantes.

La aplicación de conferencia de Location-Based enrutamiento evita la participación de los usuarios de Lync y los extremos de RTC de distintos sitios de red en la misma conferencia. Si el organizador de una reunión está habilitado para Location-Based el enrutamiento, la aplicación de conferencia exige las siguientes restricciones:

  - Los puntos de conexión que se pueden unir a una reunión de Lync dependen de los extremos que ya se hayan unido a la Conferencia, y esta restricción se ajusta como extremos Unidos y los nuevos puntos de conexión se unen a la Conferencia. Si los organizadores y participantes se unen a una reunión de Lync desde el mismo sitio de red, se permite unirse a otro participante de un sitio de red diferente o a un participante de un sitio de red desconocido desde el mismo sitio de red.

  - Si los organizadores y participantes se unen a la reunión desde sitios de red diferentes o desconocidos, un extremo de RTC no puede unirse a la reunión si la llamada RTC Progress desde un tronco SIP habilitado para Location-Based enrutamiento.

  - Si todos los organizadores y participantes se unen a la reunión desde el mismo sitio de red y hay participantes que se unen a la misma reunión desde la RTC, un punto de conexión de Lync desde un sitio de red diferente no puede unirse a la reunión.

En la tabla siguiente se resumen las restricciones de enrutamiento Location-Based la Conferencia.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Usuario (s) en una conferencia en un punto determinado</p></td>
<td><p>Usuarios que han permitido unirse a la Conferencia</p></td>
<td><p>Usuario (s) sin permiso para unirse a la Conferencia</p></td>
</tr>
<tr class="even">
<td><p>Usuarios de Lync VoIP Client (s) de un único sitio de red</p></td>
<td><p>Usuario de cliente VoIP de Lync desde el mismo sitio de red</p>
<p>Usuario de cliente VoIP de Lync desde un sitio de red diferente</p>
<p>Usuario de cliente VoIP de Lync desde un sitio de red desconocido</p>
<p>Usuario de cliente VoIP de Lync federado</p>
<p>Unirse a un usuario desde un punto de conexión RTC</p></td>
<td><p>Ninguno</p></td>
</tr>
<tr class="odd">
<td><p>Usuarios de Lync VoIP Client (s) desde un sitio de red desconocido</p></td>
<td><p>Usuario de cliente VoIP de Lync desde cualquier sitio</p>
<p>Usuario del cliente VoIP de Lync desde un sitio desconocido</p>
<p>Usuario de cliente VoIP de Lync federado</p></td>
<td><p>Unión de usuarios a través de un punto de conexión RTC</p></td>
</tr>
<tr class="even">
<td><p>Usuarios de clientes de VoIP de Lync de distintos sitios de red</p></td>
<td><p>Usuario de cliente VoIP de Lync desde cualquier sitio de red</p>
<p>Usuario de cliente VoIP de Lync desde un sitio de red desconocido</p>
<p>Usuario de cliente VoIP de Lync federado</p></td>
<td><p>Unión de usuarios a través de un punto de conexión RTC</p></td>
</tr>
<tr class="odd">
<td><p>Usuarios del cliente de VoIP de Lync de un único sitio de red y usuarios que se unen desde un punto de conexión de RTC</p></td>
<td><p>Usuario de cliente VoIP de Lync desde el mismo sitio de red</p></td>
<td><p>Usuario de cliente VoIP de Lync desde un sitio de red diferente</p>
<p>Usuario de cliente VoIP de Lync desde un sitio de red desconocido</p>
<p>Usuario de cliente VoIP de Lync federado</p></td>
</tr>
</tbody>
</table>


Las siguientes son características adicionales de la aplicación de conferencia de enrutamiento de Location-Based:

  - Cuando un usuario no está autorizado para unirse a una conferencia dada Location-Based restricciones de enrutamiento, se rechazarán las llamadas de los usuarios a la Conferencia y su cliente de Lync informará de que la llamada no se completó o ha finalizado.

  - Un punto de conexión RTC que se une a una conferencia con Location-Based las fuerzas de enrutamiento no se verá restringido a unirse a la Conferencia independientemente de su estado si el punto de conexión se une a través de un tronco que no está habilitado para Location-Based enrutamiento.

  - Un sistema PBX conectado a un servidor de mediación a través de un tronco SIP que no esté de salida las llamadas a la RTC tendrán las mismas fuerzas que los usuarios de Lync que se encuentran en el mismo sitio de red en el que se define el tronco SIP. Por ejemplo, un extremo de RTC podrá unirse a una conferencia con un usuario de PBX y un usuario de Lync si se encuentran en el mismo sitio de red; de lo contrario, el punto de conexión de RTC no podrá unirse a la Conferencia si el usuario de PBX se encuentra en un sitio de red diferente del usuario de Lync.

</div>

<span> </span>

</div>

</div>

</div>

