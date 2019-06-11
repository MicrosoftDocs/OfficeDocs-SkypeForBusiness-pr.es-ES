---
title: 'Lync Server 2013: administración de la recogida de llamadas de grupo durante la recuperación de desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed21a672dfecab4c3cc8d828fd40f52bd82a363
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Administrar la recogida de llamadas grupales durante la recuperación de desastres en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Cuando un grupo front-end no está disponible debido a un incidente no planeado, el servicio se conmuta por error al grupo de copias de seguridad. Durante la conmutación por error al grupo de copia de seguridad, los usuarios se redirigen al grupo de copia de seguridad y están en el modo de resistencia. En el modo de resistencia, los usuarios no pueden atender las llamadas de otros usuarios ni hacer que sus llamadas las recojan otros usuarios. Cuando se completa la conmutación por error, los usuarios pueden volver a usar la recogida de llamadas de grupo de la forma habitual.

Durante la conmutación por recuperación al grupo principal, los usuarios se redirigen al grupo principal y vuelven a estar en el modo de resistencia. La función de recogida de llamadas grupales no está disponible hasta que los usuarios no tengan el modo de resistencia.

En esta sección se explican algunas consideraciones sobre la recogida de llamadas grupales durante la recuperación de desastres y también se describe la experiencia del usuario.

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>Consideraciones para la recogida de llamadas grupales durante la recuperación de desastres

Durante la recuperación de desastres, los usuarios que se han redirigido al grupo de copia de seguridad como parte del proceso de conmutación por error usan la aplicación estacionamiento de llamadas que se ejecuta en el grupo de copias de seguridad para los números del grupo de recogida de llamadas. Por lo tanto, la compatibilidad con la recogida de llamadas grupales durante la recuperación de desastres requiere que la aplicación de estacionamiento de llamadas se implemente y se habilite en el grupo primario y en el grupo de copia de seguridad.

Los intervalos de número de recogida de llamada grupal de la tabla llamada de estacionamiento orbital deben ser redireccionados al grupo de copia de seguridad una vez completado el proceso de conmutación por error al grupo de copias de seguridad. Los intervalos de números deben redirigirse al grupo principal una vez que se haya completado el proceso de conmutación por recuperación en el grupo primario. Para desviar los intervalos de recogida de llamadas grupales, use el cmdlet **set-CsCallParkOrbit** .

Si implementa un nuevo grupo de servidores con un nombre de dominio completo (FQDN) diferente para reemplazar el grupo primario, tendrá que reasignar todos los intervalos de números de recogida de llamadas de grupo asociados con el grupo primario al FQDN del nuevo grupo. Para reasignar intervalos numéricos a la nueva sección, puede usar el cmdlet **set-CsCallParkOrbit** . Para obtener más información sobre el cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>Experiencia de recogida de llamada grupal durante un error de grupo

La siguiente tabla resume la experiencia de recopilación de llamadas grupales a través de las fases de recuperación de desastres.

### <a name="user-experience-during-disaster-recovery"></a>Experiencia del usuario durante la recuperación de desastres

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Estado de la llamada</th>
<th>Conmutación por error de grupo de copia</th>
<th>Conmutación por recuperación al grupo principal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas nuevas</p></td>
<td><p><strong>Durante el proceso de conmutación por error:</strong></p>
<ul>
<li><p>La recogida de llamada grupal no está disponible para los usuarios en el modo de resistencia</p></li>
</ul>
<p><strong>Después de completar la conmutación por error:</strong></p>
<ul>
<li><p>La recogida de llamadas grupales está disponible cuando los usuarios de la resistencia y los intervalos numéricos de recogida de llamadas se redirigen al grupo de copia de seguridad</p></li>
</ul></td>
<td><p><strong>Durante el proceso de failback:</strong></p>
<ul>
<li><p>La recogida de llamada grupal no está disponible para los usuarios en el modo de resistencia</p></li>
</ul>
<p><strong>Una vez completada la conmutación por recuperación:</strong></p>
<ul>
<li><p>La recogida de llamadas grupales está disponible cuando los usuarios de la resistencia y los intervalos numéricos de recogida de llamadas se redirigen al grupo principal</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamadas en la cola de recopilación de llamadas de grupo</p></td>
<td><p><strong>Durante el proceso de conmutación por error:</strong></p>
<ul>
<li><p>Las llamadas en cola no se pueden responder a través de la recogida de llamadas grupales.</p></li>
</ul>
<p><strong>Después de completar la conmutación por error:</strong></p>
<ul>
<li><p>No hay llamadas en este estado</p></li>
</ul></td>
<td><p><strong>Durante el proceso de failback:</strong></p>
<ul>
<li><p>Las llamadas en cola no se pueden responder a través de la recogida de llamadas grupales.</p></li>
</ul>
<p><strong>Una vez completada la conmutación por recuperación:</strong></p>
<ul>
<li><p>Las llamadas en cola no se pueden responder a través de la recogida de llamadas grupales.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Llamada establecida</p></td>
<td><p><strong>Durante el proceso de conmutación por error:</strong></p>
<ul>
<li><p>Las llamadas permanecen conectadas</p></li>
</ul>
<p><strong>Después de completar la conmutación por error:</strong></p>
<ul>
<li><p>Las llamadas permanecen conectadas</p></li>
</ul></td>
<td><p><strong>Durante el proceso de failback:</strong></p>
<ul>
<li><p>Las llamadas permanecen conectadas</p></li>
</ul>
<p><strong>Una vez completada la conmutación por recuperación:</strong></p>
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

