---
title: 'Lync Server 2013: experiencia de estacionamiento de llamadas durante un error de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1834c9872dc9b8c1045c6e5e638f86f760b4ad4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>Experiencia de estacionamiento de llamadas en Lync Server 2013 durante un error de grupo

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-10_

Cuando un grupo de servidores front-end no está disponible debido a un incidente no planeado, las llamadas que se han estacionado pero todavía no se han recuperado se desconectan. Durante la conmutación por error a un grupo de servidores de copia de seguridad, los usuarios son redirigidos al grupo de servidores de copia de seguridad y están en modo de resistencia. En el modo de resistencia, los usuarios no pueden estacionar llamadas, pero pueden realizar llamadas en espera y transferirlas. Cuando finaliza la conmutación por error, las llamadas se pueden volver a estacionar y recuperar como de costumbre. Durante la conmutación por recuperación, los usuarios no pueden estacionar llamadas hasta que estén fuera del modo de resistencia.

Durante la recuperación ante desastres, los usuarios que se han redirigido al grupo de copia de seguridad como parte del proceso de conmutación por error usan la aplicación estacionamiento de llamadas que se implementa en el grupo de copia de seguridad. Por lo tanto, los usuarios que se redirigen al grupo de copia de seguridad usan la configuración del estacionamiento de llamadas que están configurados para la aplicación estacionamiento de llamadas en el grupo de copia de seguridad.

En la tabla siguiente se resume la experiencia del estacionamiento de llamadas a través de las fases de recuperación ante desastres.

### <a name="user-experience-during-disaster-recovery"></a>Experiencia del usuario durante la recuperación ante desastres

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
<th>Cuando se produce la interrupción</th>
<th>Durante la conmutación por error</th>
<th>Durante la conmutación por recuperación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamada no estacionada aún</p></td>
<td><p>La llamada permanece conectada pero no se puede estacionar.</p></td>
<td><ul>
<li><p>Durante la conmutación por error, la llamada no se puede estacionar mientras los usuarios están en modo de resistencia, pero se puede poner en espera y transferirse.</p></li>
<li><p>Cuando se completa la conmutación por error, la llamada se puede estacionar y recuperar.</p></li>
</ul></td>
<td><ul>
<li><p>Durante la conmutación por recuperación, la llamada no se puede estacionar mientras los usuarios están en modo de resistencia, pero se puede poner en espera y transferirse</p></li>
<li><p>Cuando se completa la conmutación por recuperación, la llamada se puede estacionar y recuperar.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamada estacionada pero no recuperada aún</p></td>
<td><p>La llamada está desconectada.</p></td>
<td><p>No hay llamadas en este estado.</p></td>
<td><p>La llamada permanece estacionada.</p></td>
</tr>
<tr class="odd">
<td><p>Llamada estacionada ya recuperada</p></td>
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

