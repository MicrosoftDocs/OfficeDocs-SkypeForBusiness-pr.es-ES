---
title: 'Lync Server 2013: enrutamiento basado en la ubicación y transferencias de llamadas Consultiva'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e433baf180b8e4abf50ec374848204bf6628eb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Enrutamiento basado en la ubicación y transferencias de llamadas Consultiva en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-31_

Además de exigir el enrutamiento basado en la ubicación para las reuniones de Lync, la aplicación de conferencia de enrutamiento basada en la ubicación aplica restricciones de enrutamiento basadas en la ubicación en las transferencias de llamadas Consultiva que salida a puntos de conexión RTC. Una transferencia de llamadas Consultiva es una llamada establecida entre dos partes cuando una de las partes la transfiere a un nuevo usuario. Por ejemplo, un punto final de RTC llama al usuario A (llamada de Lync). El usuario A determina que el usuario de RTC debe reenviarse al usuario B (usuario de Lync). El usuario A coloca la llamada con el usuario de la RTC en espera y llama al usuario B. el usuario B acepta hablar con el usuario de la RTC. El usuario A transfiere la llamada en espera al usuario B.

**Flujo de llamadas de transferencia de llamada de consulta**

![Enrutamiento basado en ubicación para diagrama de conferencias](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Enrutamiento basado en ubicación para diagrama de conferencias")

Cuando un usuario habilitado para el enrutamiento basado en la ubicación inicia una llamada Consultiva de un extremo RTC (tal como se muestra en la ilustración anterior), se crean dos llamadas activas, una llamada entre el usuario de la RTC y el usuario de Lync A y la otra entre el usuario de Lync A y el usuario B de Lync. el comportamiento siguiente es aplicado por la aplicación de conferencia de enrutamiento basada en ubicación:

  - Si el enrutamiento de troncal del SIP la llamada RTC está autorizada para redirigir la llamada RTC al sitio de red donde se encuentra el usuario de Lync B (es decir, el destino de transferencia), se permitirá la transferencia de llamadas; de lo contrario, la transferencia de llamadas Consultiva se bloqueará. Esta autorización se realiza en función de si la ubicación de la entidad transferida es el mismo sitio de red que el tronco SIP que está redirigiendo la llamada activa al extremo de RTC.

  - Si el enrutamiento de troncal del SIP, la llamada RTC entrante no está autorizada para enrutar llamadas al sitio de red donde se encuentra la entidad transferida (usuario de Lync B) o la parte transferida se encuentra en un sitio de red desconocido y, después, la transferencia de la llamada consultiva a la RTC. se bloqueará el punto de conexión (es decir, el destino de transferencia de llamadas).

En la tabla siguiente se describe cómo aplica la aplicación de conferencia de enrutamiento basada en ubicación las restricciones de enrutamiento basadas en la ubicación. A pesar de que los extremos de PBX no están directamente asociados con un sitio de red, el tronco SIP al cual está conectado la PBX se puede asignar a un sitio de red. Por lo tanto, el extremo de PBX se puede asociar indirectamente con el sitio de red.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Sitio de red de la entidad de origen de la transferencia de la llamada</p></td>
<td><p>Sitio de red del destino de la transferencia de la llamada</p></td>
<td><p>Comportamiento</p></td>
</tr>
<tr class="even">
<td><p>Extremo de RTC</p></td>
<td><p>Usuario de Lync en el mismo sitio de red (es decir, sitio 1)</p></td>
<td><p>Se permitirá la transferencia de consulta</p></td>
</tr>
<tr class="odd">
<td><p>Extremo de RTC</p></td>
<td><p>Usuario de Lync en diferentes sitios de red (p. ej., sitio 2)</p></td>
<td><p>No se permitirá la transferencia de consulta</p></td>
</tr>
<tr class="even">
<td><p>Extremo de RTC</p></td>
<td><p>Usuario de Lync en un sitio de red desconocido</p></td>
<td><p>No se permitirá la transferencia de consulta</p></td>
</tr>
<tr class="odd">
<td><p>Extremo de RTC</p></td>
<td><p>Usuario federado de Lync</p></td>
<td><p>No se permitirá la transferencia de consulta</p></td>
</tr>
<tr class="even">
<td><p>Extremo de RTC</p></td>
<td><p>Extremo de PBX en el mismo sitio (es decir, el sitio 1)</p></td>
<td><p>Se permitirá la transferencia de consulta</p></td>
</tr>
<tr class="odd">
<td><p>Extremo de RTC</p></td>
<td><p>Extremo de PBX en un sitio diferente (es decir, el sitio 2)</p></td>
<td><p>No se permitirá la transferencia de consulta</p></td>
</tr>
<tr class="even">
<td><p>Extremo de PBX en el mismo sitio (es decir, el sitio 1)</p></td>
<td><p>Extremo de RTC</p></td>
<td><p>Se permitirá la transferencia de consulta</p></td>
</tr>
<tr class="odd">
<td><p>Extremo de PBX en un sitio diferente (es decir, el sitio 2)</p></td>
<td><p>Extremo de RTC</p></td>
<td><p>No se permitirá la transferencia de consulta</p></td>
</tr>
<tr class="even">
<td><p>Extremo de PBX en cualquier sitio</p></td>
<td><p>Usuario de Lync en el mismo sitio de red (es decir, sitio 1)</p></td>
<td><p>Se permitirá la transferencia de consulta</p></td>
</tr>
<tr class="odd">
<td><p>Extremo de PBX en cualquier sitio</p></td>
<td><p>Usuario de Lync en diferentes sitios de red (p. ej., sitio 2)</p></td>
<td><p>Se permitirá la transferencia de consulta</p></td>
</tr>
<tr class="even">
<td><p>Extremo de PBX en cualquier sitio</p></td>
<td><p>Usuario de Lync en un sitio de red desconocido</p></td>
<td><p>Se permitirá la transferencia de consulta</p></td>
</tr>
<tr class="odd">
<td><p>Extremo de PBX en cualquier sitio</p></td>
<td><p>Usuario federado de Lync</p></td>
<td><p>Se permitirá la transferencia de consulta</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

