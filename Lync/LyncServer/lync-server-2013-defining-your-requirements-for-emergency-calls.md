---
title: 'Lync Server 2013: Definición de los requisitos para llamadas de emergencia'
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
ms.openlocfilehash: beb4b1e196a95d19a06c502cc9aeb989d6806b06
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a>Definición de los requisitos para llamadas de emergencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-06_

Antes de empezar una implementación de Microsoft Lync Server 2013 E9-1-1, primero debe poder responder a las preguntas detalladas en las siguientes secciones. La planeación que necesite dependerá del tipo de solución E9-1-1 que haya decidido implementar, ya sea un proveedor de servicios E9-1-1 por medio de un tronco SIP o una puerta de enlace de número de identificación de ubicación de emergencia (ELIN). En la siguiente tabla figuran las secciones de este manual de planificación que necesitará repasar según cada solución.

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
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definir los elementos de red que se usan para determinar la ubicación en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definir los elementos de red que se usan para determinar la ubicación en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Habilitar usuarios para E9-1-1 en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Habilitar usuarios para E9-1-1 en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Administración de ubicaciones para proveedores de servicios de tronco de SIP en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Administrar ubicaciones de puertas de enlace de ELIN en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definir la experiencia de usuario para la adquisición manual de una ubicación en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definir la experiencia de usuario para la adquisición manual de una ubicación en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Diseño del tronco del SIP para E9-1-1 en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">Incluido el escritorio de seguridad de Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">Incluido el escritorio de seguridad de Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Definir la Directiva de ubicación de Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Elección de un proveedor de servicios de E9-1-1 para Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Asignación de un ámbito de directivas de ubicación en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Definir la Directiva de ubicación de Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Asignación de un ámbito de directivas de ubicación en Lync Server 2013</a></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>En esta sección

  - [Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [Definir los elementos de red que se usan para determinar la ubicación en Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [Habilitar usuarios para E9-1-1 en Lync Server 2013](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [Administración de ubicaciones para proveedores de servicios de tronco de SIP en Lync Server 2013](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [Administrar ubicaciones de puertas de enlace de ELIN en Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [Definir la experiencia de usuario para la adquisición manual de una ubicación en Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [Diseño del tronco del SIP para E9-1-1 en Lync Server 2013](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [Incluido el escritorio de seguridad de Lync Server 2013](lync-server-2013-including-the-security-desk.md)

  - [Elección de un proveedor de servicios de E9-1-1 para Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [Definir la Directiva de ubicación de Lync Server 2013](lync-server-2013-defining-the-location-policy.md)

  - [Asignación de un ámbito de directivas de ubicación en Lync Server 2013](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

