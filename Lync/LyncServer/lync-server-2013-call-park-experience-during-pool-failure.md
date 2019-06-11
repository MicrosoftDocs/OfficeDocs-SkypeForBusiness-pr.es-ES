---
title: 'Lync Server 2013: Experiencia de estacionamiento de llamadas durante un error del grupo de servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b175e5029749ea4e3a344aaf9f3bcc7a403c1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>Experiencia de estacionamiento de llamadas durante un error del grupo de servidores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-10_

Cuando un grupo front-end no está disponible debido a un incidente no planeado, se desconectan las llamadas que se han detenido pero que aún no se han recuperado. Durante la conmutación por error a un grupo de copia de seguridad, los usuarios se redirigen al grupo de copia de seguridad y están en el modo de resistencia. Mientras se encuentra en el modo de resistencia, los usuarios no pueden detener las llamadas, pero pueden poner las llamadas en espera y transferirlas. Cuando se completa la conmutación por error, las llamadas se pueden detener de nuevo y recuperar de la forma habitual. Durante la conmutación por recuperación, los usuarios no pueden detener las llamadas hasta que no estén fuera del modo de resistencia.

Durante la recuperación de desastres, los usuarios que se han redirigido al grupo de copia de seguridad como parte del proceso de conmutación por error usan la aplicación estacionamiento de llamadas que se implementa en el grupo de copia de seguridad. Por lo tanto, los usuarios redirigidos al grupo de copias de seguridad usan la configuración de estacionamiento de llamadas que están configurados para la aplicación de estacionamiento de llamada en el grupo de copias de seguridad.

La siguiente tabla resume la experiencia del parque de llamadas a través de las fases de la recuperación de desastres.

### <a name="user-experience-during-disaster-recovery"></a>Experiencia del usuario durante la recuperación de desastres

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Estado de la llamada</th>
<th>Cuando se produce una interrupción</th>
<th>Durante la conmutación por error</th>
<th>Durante la conmutación por recuperación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamada aún no deestacionada</p></td>
<td><p>La llamada permanece conectada, pero no se puede detener.</p></td>
<td><ul>
<li><p>Durante la conmutación por error, no se puede detener la llamada cuando los usuarios están en modo de resistencia, pero se pueden suspender y transferir.</p></li>
<li><p>Cuando se complete la conmutación por error, se podrá detener y recuperar la llamada.</p></li>
</ul></td>
<td><ul>
<li><p>Durante la conmutación por recuperación, la llamada no se puede detener cuando los usuarios tienen el modo de resistencia, pero se pueden suspender y transferir.</p></li>
<li><p>Cuando se complete la conmutación por recuperación, se podrá detener y recuperar la llamada.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamada estacionada, pero no recuperada aún</p></td>
<td><p>La llamada está desconectada.</p></td>
<td><p>No hay llamadas en este estado.</p></td>
<td><p>La llamada permanece aparcada.</p></td>
</tr>
<tr class="odd">
<td><p>Ya se ha recuperado una llamada estacionada</p></td>
<td><p>La llamada permanece conectada.</p></td>
<td><p>La llamada permanece conectada.</p></td>
<td><p>La llamada permanece conectada.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

