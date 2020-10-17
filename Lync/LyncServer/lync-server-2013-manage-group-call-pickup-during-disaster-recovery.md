---
title: 'Lync Server 2013: administrar la recogida de llamadas de grupo durante la recuperación ante desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d181570b55ce175a63ac1ac1f218ee99aec7a5a0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534537"
---
# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Administrar la recepción de llamadas de grupo durante la recuperación ante desastres en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Cuando un grupo de servidores front-end deja de estar disponible debido a un incidente no planeado, el servicio se conmuta por error al grupo de copia de seguridad. Durante la conmutación por error en el grupo de copia de seguridad, los usuarios se redirigen al grupo de copia de seguridad y están en modo de resistencia. Mientras se está en el modo de resistencia, los usuarios no pueden recoger las llamadas de otros usuarios ni hacer que sus llamadas las recojan otros usuarios. Una vez completada la conmutación por error, los usuarios pueden volver a usar la recopilación de llamadas de grupo de la forma habitual.

Durante la conmutación por recuperación al grupo principal, los usuarios se redirigen al grupo principal y vuelven a estar en el modo de resistencia. La funcionalidad de recogida de llamadas de grupo no está disponible hasta que los usuarios no tengan el modo de resistencia.

En esta sección se describen algunas consideraciones sobre la recogida de llamadas de grupo durante la recuperación ante desastres y también se describe la experiencia del usuario.

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>Consideraciones para la recogida de llamadas de grupo durante la recuperación ante desastres

Durante la recuperación ante desastres, los usuarios que se han redirigido al grupo de copia de seguridad como parte del proceso de conmutación por error usan la aplicación estacionamiento de llamadas que se ejecuta en el grupo de copia de seguridad para los números del grupo de recogida de llamadas. Por lo tanto, la compatibilidad con la recogida de llamadas de grupo durante la recuperación ante desastres requiere que la aplicación de estacionamiento de llamadas se implemente y esté habilitada en el grupo principal y en el grupo de copia de seguridad.

Los intervalos de números de atención de llamadas grupales en la tabla de órbitas de estacionamiento de llamadas deben redirigirse al grupo de copia de seguridad una vez completado el proceso de conmutación por error al grupo de copia de seguridad. Los intervalos de números se deben redirigir de vuelta al grupo principal una vez que se haya completado el proceso de conmutación por recuperación en el grupo principal. Para redirigir los intervalos de recogida de llamadas de grupo, use el cmdlet **set-CsCallParkOrbit** .

Si implementa un nuevo grupo de servidores con un nombre de dominio completo (FQDN) diferente para reemplazar el grupo principal, tendrá que reasignar todos los intervalos de números de atención de llamadas de grupo asociados con el grupo principal al FQDN del nuevo grupo de servidores. Para reasignar intervalos de números a la nueva agrupación, puede usar el cmdlet **set-CsCallParkOrbit** . Para obtener más información sobre el cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>Experiencia de recopilación de llamadas de grupo durante un error de grupo

En la tabla siguiente se resume la experiencia de llamada de llamada de grupo a través de las fases de recuperación ante desastres.

### <a name="user-experience-during-disaster-recovery"></a>Experiencia del usuario durante la recuperación ante desastres

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Estado de la llamada</th>
<th>Conmutación por error en el grupo de copia de seguridad</th>
<th>Conmutación por recuperación al grupo principal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas nuevas</p></td>
<td><p><strong>Durante el proceso de conmutación por error:</strong></p>
<ul>
<li><p>La recopilación de llamadas de grupo no está disponible para los usuarios en el modo de resistencia</p></li>
</ul>
<p><strong>Una vez finalizada la conmutación por error:</strong></p>
<ul>
<li><p>La recogida de llamadas de grupo está disponible cuando los usuarios de la resistencia y los intervalos de números de llamada de grupo se redirigen al grupo de copia de seguridad</p></li>
</ul></td>
<td><p><strong>Durante el proceso de conmutación por recuperación:</strong></p>
<ul>
<li><p>La recopilación de llamadas de grupo no está disponible para los usuarios en el modo de resistencia</p></li>
</ul>
<p><strong>Una vez finalizada la conmutación por recuperación:</strong></p>
<ul>
<li><p>La recogida de llamadas de grupo está disponible cuando los usuarios de fuera de la resistencia y los intervalos de números de atención de llamadas de grupo se redirigen de vuelta al grupo principal</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamadas en la cola de recogida de llamadas de grupo</p></td>
<td><p><strong>Durante el proceso de conmutación por error:</strong></p>
<ul>
<li><p>No se puede responder a las llamadas de la cola a través de la llamada de llamadas grupales.</p></li>
</ul>
<p><strong>Una vez finalizada la conmutación por error:</strong></p>
<ul>
<li><p>No hay llamadas en este estado</p></li>
</ul></td>
<td><p><strong>Durante el proceso de conmutación por recuperación:</strong></p>
<ul>
<li><p>No se puede responder a las llamadas de la cola a través de la llamada de llamadas grupales.</p></li>
</ul>
<p><strong>Una vez finalizada la conmutación por recuperación:</strong></p>
<ul>
<li><p>No se puede responder a las llamadas de la cola a través de la llamada de llamadas grupales.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Llamada establecida</p></td>
<td><p><strong>Durante el proceso de conmutación por error:</strong></p>
<ul>
<li><p>Las llamadas permanecen conectadas</p></li>
</ul>
<p><strong>Una vez finalizada la conmutación por error:</strong></p>
<ul>
<li><p>Las llamadas permanecen conectadas</p></li>
</ul></td>
<td><p><strong>Durante el proceso de conmutación por recuperación:</strong></p>
<ul>
<li><p>Las llamadas permanecen conectadas</p></li>
</ul>
<p><strong>Una vez finalizada la conmutación por recuperación:</strong></p>
<ul>
<li><p>Las llamadas permanecen conectadas</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

