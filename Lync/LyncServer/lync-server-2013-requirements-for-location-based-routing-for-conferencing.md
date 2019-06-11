---
title: 'Lync Server 2013: requisitos para el enrutamiento basado en la ubicación para conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 925b71497012d7e6ed9c19042a079a7b30630c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Requisitos para el enrutamiento basado en la ubicación de las conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-19_

A continuación se indican los requisitos necesarios para la instalación y configuración de la aplicación de conferencia de enrutamiento basado en la ubicación:

  - La actualización acumulativa 2 de Lync Server 2013 debe implementarse en todos los servidores o grupos de servidores de su topología.

<div>


> [!NOTE]  
> Si un servidor de Lync o un grupo de servidores de su topología no tienen instalado la actualización acumulativa 2 de Lync Server 2013 o una versión posterior, no se puede garantizar la aplicación del enrutamiento basado en la ubicación de las reuniones de Lync.



</div>

  - El enrutamiento basado en la ubicación 2013 de Lync Server es un requisito previo para la aplicación de conferencia de enrutamiento basada en la ubicación. Para obtener más información sobre cómo configurar el enrutamiento basado en la ubicación 2013 de Lync Server, consulte [configurar el enrutamiento basado en la ubicación](lync-server-2013-configuring-location-based-routing.md).

  - Los requisitos de la aplicación de conferencia de enrutamiento basado en ubicación son los mismos que los requisitos para el enrutamiento basado en la ubicación 2013 de Lync Server. Para obtener más información, consulte [planificación para el enrutamiento basado en la ubicación](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Servidores compatibles

La aplicación de conferencia de enrutamiento basada en la ubicación requiere que se implemente la actualización acumulativa 2 de Lync Server 2013 en todos los grupos de aplicaciones para usuario y servidores Standard Edition de su topología. Si la actualización acumulativa 2 de Lync Server 2013 no está instalada en algunos servidores de Lync de su topología, las restricciones de enrutamiento basadas en la ubicación no se pueden aplicar por completo en las reuniones de Lync ni las transferencias de llamadas Consultiva.

En la siguiente tabla se identifica la combinación de las versiones y los roles de servidor que admiten el enrutamiento basado en la ubicación.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Versión del grupo de servidores front-end</p></td>
<td><p>Versión del servidor de mediación</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="even">
<td><p>Actualización acumulativa 2 de Lync Server 2013</p></td>
<td><p>Actualización acumulativa 2 de Lync Server 2013</p></td>
<td><p>Sí</p></td>
</tr>
<tr class="odd">
<td><p>Actualización acumulativa 2 de Lync Server 2013</p></td>
<td><p>Actualización acumulativa 1 de Lync Server 2013</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Actualización acumulativa 2 de Lync Server 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Actualización acumulativa 2 de Lync Server 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Actualización acumulativa 1 de Lync Server 2013</p></td>
<td><p>Cualquiera</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>Cualquiera</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Cualquiera</p></td>
<td><p>No</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>Clientes compatibles

Los clientes de Lync que admiten el enrutamiento basado en la ubicación de las reuniones de Lync son los mismos clientes que admiten el enrutamiento basado en la ubicación 2013 de Lync Server. Para obtener más información, consulte [compatibilidad de cliente y servidor para el enrutamiento basado en la ubicación](lync-server-2013-client-and-server-support-for-location-based-routing.md).

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Requisitos del servidor de mediación para las transferencias de llamadas Consultiva

La aplicación de conferencia de enrutamiento basada en la ubicación requiere la implementación de servidores de mediación independientes para poder aplicar restricciones de enrutamiento basadas en la ubicación en las transferencias de llamadas Consultiva.

Para aplicar el enrutamiento basado en la ubicación de las transferencias de llamadas Consultiva, el servidor de mediación debe estar asociado solo con un servidor de mediación del mismo nivel (es decir, PBX, puerta de enlace SIP, etc.) en las regiones de red donde se requiere el enrutamiento basado en la ubicación. Si se implementan pares de servidores de mediación adicionales en la misma región de red, el servidor de mediación del mismo nivel debe estar asociado a un servidor de mediación diferente. Este requisito se detalla de la siguiente manera:

  - Servidor de mediación único por punto de servidor de mediación cuando una transferencia de llamada Consultiva se dirige a un servidor de mediación del mismo nivel a través de un servidor de mediación que está configurado con varios troncos SIP a varios colegas (es decir, PBX y puertas de enlace), el consultoría la transferencia de llamadas está bloqueada para evitar un omisión de peaje si la transferencia de llamadas Consultiva está permitida a través de algunos troncos SIP, pero no permitido a través de otros troncos SIP.
    
    Por ejemplo, en el caso de un único servidor de mediación que atienda un servidor de mediación de puerta de enlace RTC y un servidor de mediación de PBX, se observará el siguiente comportamiento:
    
      - Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un punto final de la RTC a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) a través de una transferencia Consultiva, la llamada no se permitirá para evitar la omisión de llamadas RTC.
    
      - Cuando un usuario de Lync de un sitio determinado (es decir, el sitio 1) intenta transferir una llamada con un extremo de PBX en el mismo sitio (sitio 1) a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) a través de una transferencia Consultiva, la llamada no se permitirá incluso si no tiene incurrir en la tol. l.

  - Servidores de mediación independientes por servidor de mediación del mismo nivel
    
    Cuando una transferencia Consultiva se dirige a un interlocutor de servidor de mediación, la transferencia Consultiva se evaluará en relación con el servidor de mediación que atendida el servidor de mediación. La llamada no se permitirá o se autorizará en función de su potencial de incurrir en una omisión de peaje de RTC, independientemente del resto de los servidores de mediación del sitio que sean atendidas por servidores de mediación independientes.
    
    Por ejemplo, en el caso de un servidor de mediación independiente que está atendiendo a un servidor de mediación de puerta de enlace RTC y un servidor de mediación de PBX, se observará el siguiente comportamiento:
    
      - Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un punto final de la RTC a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) a través de una transferencia Consultiva, la llamada no se permitirá para evitar la omisión de llamadas RTC.
    
      - Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un extremo de PBX en el mismo sitio (sitio 1) a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) a través de una transferencia Consultiva, la llamada se permitirá porque no se produce en el posible omisión de llamadas RTC. Ing.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Funciones no compatibles con la aplicación de conferencia de enrutamiento basado en ubicación

Las siguientes características no son compatibles con la aplicación de conferencia de enrutamiento basada en ubicación:

  - Conferencias de acceso telefónico local. No se puede aplicar el enrutamiento basado en la ubicación para las conferencias de acceso telefónico local. Cualquier solicitud de acceso telefónico a una conferencia determinada no se verá restringida por enrutamiento basado en la ubicación, incluso si el organizador de la Conferencia es un usuario de Lync habilitado para el enrutamiento basado en la ubicación.

  - Se recomienda no suministrar números de acceso a la Conferencia en regiones donde sea necesario exigir la aplicación de restricciones de enrutamiento basadas en la ubicación.

</div>

</div>

<span> </span>

</div>

</div>

</div>

