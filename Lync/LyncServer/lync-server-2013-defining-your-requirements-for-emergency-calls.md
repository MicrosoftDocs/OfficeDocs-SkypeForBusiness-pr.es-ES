---
title: 'Lync Server 2013: definición de los requisitos para las llamadas de emergencia'
description: 'Lync Server 2013: definición de los requisitos para las llamadas de emergencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d3c9908dcb4008a1442af86971e42eb4096a98b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545406"
---
# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a>Definición de los requisitos para las llamadas de emergencia en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-06_

Antes de comenzar una implementación de Microsoft Lync Server 2013 E9-1-1, primero debe poder responder a las preguntas que se detallan en las siguientes secciones. La planeación que necesite dependerá del tipo de solución E9-1-1 que haya decidido implementar, ya sea un proveedor de servicios E9-1-1 mediante troncales SIP o una puerta de enlace de número de identificación de ubicación de emergencia (ELIN). En la siguiente tabla figuran las secciones de este manual de planeación que deberá repasar según cada solución.

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a>Pasos de planeación por tipo de E9-1-1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Proveedor de servicios troncales SIP</th>
<th>Puerta de enlace ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definición de los elementos de red que se usan para determinar la ubicación en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definición de los elementos de red que se usan para determinar la ubicación en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Habilitación de usuarios para E9-1-1 en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Habilitación de usuarios para E9-1-1 en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Administración de ubicaciones para proveedores de servicio de tronco de SIP en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Administración de ubicaciones para puertas de enlace de ELIN en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definir la experiencia de usuario para adquirir manualmente una ubicación en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definir la experiencia de usuario para adquirir manualmente una ubicación en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Diseño del tronco SIP para E9-1-1 en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">Incluir el Departamento de seguridad en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">Incluir el Departamento de seguridad en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Definición de la Directiva de ubicación para Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Selección de un proveedor de servicios E9-1-1 para Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Asignar el ámbito de la Directiva de ubicación en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Definición de la Directiva de ubicación para Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Asignar el ámbito de la Directiva de ubicación en Lync Server 2013</a></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>En esta sección

  - [Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [Definición de los elementos de red que se usan para determinar la ubicación en Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [Habilitación de usuarios para E9-1-1 en Lync Server 2013](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [Administración de ubicaciones para proveedores de servicio de tronco de SIP en Lync Server 2013](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [Administración de ubicaciones para puertas de enlace de ELIN en Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [Definir la experiencia de usuario para adquirir manualmente una ubicación en Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [Diseño del tronco SIP para E9-1-1 en Lync Server 2013](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [Incluir el Departamento de seguridad en Lync Server 2013](lync-server-2013-including-the-security-desk.md)

  - [Selección de un proveedor de servicios E9-1-1 para Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [Definición de la Directiva de ubicación para Lync Server 2013](lync-server-2013-defining-the-location-policy.md)

  - [Asignar el ámbito de la Directiva de ubicación en Lync Server 2013](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

