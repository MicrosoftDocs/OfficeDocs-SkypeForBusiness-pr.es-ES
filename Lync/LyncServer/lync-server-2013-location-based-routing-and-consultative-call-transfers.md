---
title: 'Lync Server 2013: enrutamiento basado en ubicación y transferencias de llamadas de asesoría'
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
ms.openlocfilehash: 2dff8b723889be65f26e2c04d7f6a594515bfd09
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Enrutamiento basado en ubicación y transferencias de llamadas de asesoría en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-31_

Además de aplicar el enrutamiento basado en ubicación a las reuniones de Lync, la aplicación de conferencia de enrutamiento basada en ubicación aplica las restricciones de enrutamiento basadas en ubicación en las transferencias de llamadas de consulta que se transfieren a los extremos de RTC. Una transferencia de llamada Consultiva es una llamada establecida entre dos partes en la que una de las partes transfiere la llamada a un nuevo usuario. Por ejemplo, un punto de conexión RTC llama al usuario A (llamado de Lync). El usuario A determina el usuario de RTC que se debe reenviar al usuario B (usuario de Lync). El usuario A realiza la llamada con el usuario RTC en espera y llama al usuario B. el usuario B acuerda hablar con el usuario RTC. El usuario A transfiere la llamada en espera al usuario B.

**Flujo de llamada de transferencia de llamada Consultiva**

![Enrutamiento basado en ubicación para diagrama de conferencia](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Enrutamiento basado en ubicación para diagrama de conferencia")

Cuando un usuario habilitado para el enrutamiento basado en ubicación inicia una transferencia de llamada Consultiva de un extremo de RTC (como se muestra en la figura anterior), se crean dos llamadas activas, una llamada entre el usuario de RTC y el usuario de Lync A, y la otra entre el usuario de Lync A y el usuario B de Lync. la aplicación de conferencia de enrutamiento basada en ubicación aplica el siguiente comportamiento:

  - Si el enrutamiento de tronco SIP la llamada RTC está autorizada para redirigir la llamada RTC al sitio de red donde se encuentra el usuario B de Lync (por ejemplo, el destino de transferencia), se permitirá la transferencia de llamadas; de lo contrario, se bloqueará la transferencia de la llamada Consultiva. Esta autorización se realiza en función de la ubicación de la entidad transferida que se encuentra en el mismo sitio de red que el tronco SIP que enruta la llamada activa al punto de conexión de RTC.

  - Si el enrutamiento de tronco SIP, la llamada RTC entrante no está autorizada para enrutar llamadas al sitio de red donde se encuentra la entidad de transferencia (usuario de Lync B) o la entidad transferida se encuentra en un sitio de red desconocido y, a continuación, la transferencia de la llamada consultiva a la RTC. se bloqueará el punto de conexión (por ejemplo, el destino de transferencia de llamadas).

En la tabla siguiente se describe el modo en que la aplicación de conferencia de enrutamiento basada en ubicación aplica las restricciones de enrutamiento basadas en ubicación para las transferencias de llamadas de consultoría. Aunque los extremos de PBX no están directamente asociados a un sitio de red, el tronco SIP al que se conecta la PBX se puede asignar a un sitio de red. Por lo tanto, el extremo de PBX se puede asociar indirectamente con un sitio de red.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Sitio de red de la persona que ha transferido la llamada</p></td>
<td><p>Sitio de red del destino de transferencia de llamadas</p></td>
<td><p>Comportamiento</p></td>
</tr>
<tr class="even">
<td><p>Extremo de RTC</p></td>
<td><p>Usuario de Lync en el mismo sitio de red (por ejemplo, sitio 1)</p></td>
<td><p>Se permitirá la transferencia Consultiva</p></td>
</tr>
<tr class="odd">
<td><p>Extremo de RTC</p></td>
<td><p>Usuario de Lync en sitios de red diferentes (por ejemplo, sitio 2)</p></td>
<td><p>La transferencia Consultiva no se permitirá</p></td>
</tr>
<tr class="even">
<td><p>Extremo de RTC</p></td>
<td><p>Usuario de Lync en un sitio de red desconocido</p></td>
<td><p>La transferencia Consultiva no se permitirá</p></td>
</tr>
<tr class="odd">
<td><p>Extremo de RTC</p></td>
<td><p>Usuario de Lync federado</p></td>
<td><p>La transferencia Consultiva no se permitirá</p></td>
</tr>
<tr class="even">
<td><p>Extremo de RTC</p></td>
<td><p>Extremo de PBX en el mismo sitio (por ejemplo, sitio 1)</p></td>
<td><p>Se permitirá la transferencia Consultiva</p></td>
</tr>
<tr class="odd">
<td><p>Extremo de RTC</p></td>
<td><p>Extremo de PBX en sitios diferentes (por ejemplo, sitio 2)</p></td>
<td><p>La transferencia Consultiva no se permitirá</p></td>
</tr>
<tr class="even">
<td><p>Extremo de PBX en el mismo sitio (por ejemplo, sitio 1)</p></td>
<td><p>Extremo de RTC</p></td>
<td><p>Se permitirá la transferencia Consultiva</p></td>
</tr>
<tr class="odd">
<td><p>Extremo de PBX en un sitio diferente (por ejemplo, sitio 2)</p></td>
<td><p>Extremo de RTC</p></td>
<td><p>La transferencia Consultiva no se permitirá</p></td>
</tr>
<tr class="even">
<td><p>Extremo de PBX en cualquier sitio</p></td>
<td><p>Usuario de Lync en el mismo sitio de red (por ejemplo, sitio 1)</p></td>
<td><p>Se permitirá la transferencia Consultiva</p></td>
</tr>
<tr class="odd">
<td><p>Extremo de PBX en cualquier sitio</p></td>
<td><p>Usuario de Lync en sitios de red diferentes (por ejemplo, sitio 2)</p></td>
<td><p>Se permitirá la transferencia Consultiva</p></td>
</tr>
<tr class="even">
<td><p>Extremo de PBX en cualquier sitio</p></td>
<td><p>Usuario de Lync en un sitio de red desconocido</p></td>
<td><p>Se permitirá la transferencia Consultiva</p></td>
</tr>
<tr class="odd">
<td><p>Extremo de PBX en cualquier sitio</p></td>
<td><p>Usuario de Lync federado</p></td>
<td><p>Se permitirá la transferencia Consultiva</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

