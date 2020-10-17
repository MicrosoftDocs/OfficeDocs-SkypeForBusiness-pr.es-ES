---
title: 'Lync Server 2013: requisitos para el enrutamiento Location-Based para conferencias'
description: 'Lync Server 2013: requisitos para el enrutamiento de Location-Based para conferencias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbaa1af2690c3148d2ecfb173b13be288a21d80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542526"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Requisitos para Location-Based el enrutamiento para conferencias en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-19_

Los siguientes son los requisitos necesarios para la instalación y configuración de la aplicación de conferencia de enrutamiento de Location-Based:

  - Lync Server 2013 la actualización acumulativa 2 debe implementarse en todos los servidores o grupos de servidores de la topología.

<div>


> [!NOTE]  
> Si un servidor de Lync o un grupo de servidores de la topología no tienen instalado la actualización acumulativa 2 o posterior de Lync Server 2013, no se podrá garantizar la aplicación de Location-Based el enrutamiento de reuniones de Lync.



</div>

  - Lync Server 2013 Location-Based el enrutamiento es un requisito previo para Location-Based aplicación de conferencia de enrutamiento. Para obtener más información sobre cómo configurar el enrutamiento de Lync Server 2013 Location-Based, consulte [configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).

  - Los requisitos de Location-Based aplicación de conferencia de enrutamiento son los mismos que los de Lync Server 2013 Location-Based el enrutamiento. Para obtener más información, consulte [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Servidores compatibles

La aplicación de Location-Based de conferencia de enrutamiento requiere que se implemente la actualización acumulativa 2 de Lync Server 2013 en todos los grupos de Front-End y servidores Standard Edition de la topología. Si Lync Server 2013 la actualización acumulativa 2 no está instalada en algunos servidores de Lync de la topología, Location-Based restricciones de enrutamiento no se pueden aplicar completamente en las reuniones y las transferencias de llamadas de consultoría de Lync.

En la siguiente tabla se identifica la combinación de roles de servidor y versiones que admiten el enrutamiento Location-Based.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Versión del grupo de Front-End</p></td>
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

Los clientes de Lync que admiten el enrutamiento Location-Based de reuniones de Lync son los mismos clientes que admiten el enrutamiento de Lync Server 2013 Location-Based. Para obtener más información, consulte compatibilidad con el [cliente y el servidor para Location-Based enrutamiento](lync-server-2013-client-and-server-support-for-location-based-routing.md).

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Requisitos del servidor de mediación para las transferencias de llamadas de consultoría

La aplicación de conferencia de Location-Based enrutamiento requiere la implementación de servidores de mediación independientes para imponer Location-Based restricciones de enrutamiento en las transferencias de llamadas de consultoría.

Para aplicar Location-Based el enrutamiento de las transferencias de llamadas de consultoría, el servidor de mediación debe estar asociado solamente a un servidor de mediación del mismo nivel (es decir, PBX, puerta de enlace SIP, etc.) en las regiones de red en las que se requiere Location-Based enrutamiento. Si se implementan más del servidor de mediación en la misma región de red, el servidor de mediación del mismo nivel debe estar asociado a un servidor de mediación diferente. Este requisito se detalla a continuación:

  - Servidor de mediación único por parte del mismo nivel del servidor de mediación cuando una transferencia de llamada de consulta se enruta a un servidor de mediación del mismo nivel a través de un servidor de mediación configurado con varios troncos SIP a varios interlocutores (es decir, PBX y puertas de enlace), se bloquea la transferencia de llamadas de consulta para evitar el desvío de peajes de RTC.
    
    Por ejemplo, en el caso de un servidor de mediación único que atiende un servidor de mediación de puerta de enlace RTC y un servidor del mismo nivel de mediación de PBX, se observará el siguiente comportamiento:
    
      - Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un punto de conexión de RTC a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) mediante transferencia Consultiva, la llamada no se permitirá para evitar el desvío de llamadas RTC.
    
      - Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un extremo de PBX en el mismo sitio (sitio 1) a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) mediante la transferencia Consultiva, la llamada no se permitirá incluso si no incurre en la posible omisión de peajes RTC.

  - Servidores de mediación independientes por servidor de mediación del mismo nivel
    
    Cuando una transferencia de consulta se destina a un servidor de mediación del mismo nivel, la transferencia de consulta se evalúa en el servidor de mediación único que el servidor de mediación presta. La llamada no se permitirá o se permitirá en función de su potencial de incurrir en la omisión de peaje RTC, independientemente del resto de servidores de mediación del sitio que sean proporcionados por servidores de mediación independientes.
    
    Por ejemplo, en el caso de los servidores de mediación independientes que atienden un servidor de mediación de puerta de enlace RTC y un servidor del mismo nivel del servidor de mediación de PBX, se observará el siguiente comportamiento:
    
      - Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un punto de conexión de RTC a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) mediante transferencia Consultiva, la llamada no se permitirá para evitar el desvío de llamadas RTC.
    
      - Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un extremo de PBX en el mismo sitio (sitio 1) a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) mediante la transferencia Consultiva, la llamada se permitirá ya que no se produce en la posible omisión de peajes RTC.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Capacidades no admitidas por la aplicación de conferencia de enrutamiento de Location-Based

Las siguientes funciones no son compatibles con la aplicación de Location-Based de conferencia de enrutamiento:

  - Conferencia de acceso telefónico local. No se puede aplicar el enrutamiento Location-Based para las conferencias de acceso telefónico local. Cualquier solicitud de acceso telefónico a una conferencia determinada no estará restringida por el Location-Based el enrutamiento, incluso si el organizador de la Conferencia es un usuario de Lync habilitado para Location-Based el enrutamiento.

  - Se recomienda no aprovisionar los números de acceso a la Conferencia en las regiones donde se deben aplicar las restricciones de enrutamiento de Location-Based.

</div>

</div>

<span> </span>

</div>

</div>

</div>

