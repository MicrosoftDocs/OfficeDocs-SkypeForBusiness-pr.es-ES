---
title: Lync Server 2013 experiencia del usuario durante un error de grupo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd2d6733f2db3a988f604554df55a25f866f5099
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530197"
---
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Experiencia del usuario durante un error de grupo de servidores en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Si un grupo se conmuta por error, se fuerza a todos los usuarios del grupo afectado a cerrar sesión y, a continuación, iniciar sesión en el grupo de copia de seguridad. Durante un breve período, los usuarios que inicien sesión en el grupo de copia de seguridad pueden estar en el modo de resistencia. En el modo de resistencia, los usuarios no pueden realizar tareas que provocarían un cambio persistente en Lync Server, como agregar un contacto. Una vez completada la conmutación por error, todos los usuarios pueden obtener todos los servicios del grupo de copia de seguridad.

Las sesiones que tiene un usuario cuando se produce un error en el grupo de servidores se interrumpen y el usuario debe volver a establecer esas sesiones después de la conmutación por error para continuar.

Los usuarios no se reubican durante la conmutación por error o conmutación por recuperación. Los usuarios hospedados en un grupo en el que se produce un error se darán de forma temporal a través del grupo de copia de seguridad. Cuando se restaura el grupo de servidores principales, el administrador puede conmutar por recuperación a estos usuarios para que los dé servicio de su grupo de servidores principal original.

Nota en Lync 2013, la base de datos del servidor de información de ubicación no se replica en el grupo de copia de seguridad. Para un procedimiento recomendado, el administrador debe hacer una copia de seguridad de la base de datos de LIS y usar la copia de seguridad más reciente para restaurar la base de datos LIS en el grupo de copia de seguridad después de la conmutación por error.

<div>

## <a name="user-experience-during-failover"></a>Experiencia de usuario durante la conmutación por error

Cuando un usuario se encuentra en un grupo de servidores que genera un error, el usuario ha cerrado la sesión. Se finalizan todas las sesiones punto a punto en las que participe el usuario, como las conferencias organizadas por dicho usuario. El usuario no puede volver a iniciar sesión hasta que expire el temporizador de resistencia del registrador o el administrador inicie los procedimientos de conmutación por error, lo que suceda primero. Cuando el usuario vuelva a iniciar sesión, iniciará sesión en el grupo de copia de seguridad. Si inician sesión antes de que se complete la conmutación por error, estarán en modo de resistencia hasta que se complete la conmutación por error. Solo entonces el usuario puede establecer nuevas sesiones o restablecer sesiones anteriores.

</div>

<div>

## <a name="user-experience-during-failback"></a>Experiencia de usuario durante la conmutación por recuperación

La conmutación por recuperación de un grupo de servidores puede ocurrir mientras un usuario afectado inicia sesión en el grupo de copia de seguridad y el usuario permanece conectado y en funcionamiento durante la conmutación por recuperación. Tenga en cuenta que el proceso de conmutación por error tarda en completarse.Como referencia, un grupo de 20.000  usuarios suele tardar 60 minutos.

En las siguientes tablas se muestran más detalles sobre cómo un usuario con un cliente de Lync 2013 o un cliente de Microsoft Lync 2010 se ve afectado durante y después de la conmutación por recuperación, así como la forma en que los usuarios de otros grupos de servidores ven e interactúan con un usuario de un grupo de servidores que se está recuperando tras error. Los usuarios con los clientes de Microsoft Office Communicator 2007 R2 no pueden iniciar sesión hasta que el grupo de servidores front-end no pueda realizar una copia de seguridad completa.

El término *usuario afectado* se refiere a cualquier usuario que haya realizado una conmutación por error en el grupo de servidores principales y que esté siendo el servicio del grupo de copia de seguridad. Por definición, cualquier usuario hospedado originalmente en el grupo de copia de seguridad no es un usuario afectado.

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>Experiencia del usuario para un usuario afectado en un grupo de servidores en failback

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tarea o estado de usuario</th>
<th>Durante la conmutación por recuperación</th>
<th>Después de completar la conmutación por recuperación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Estado del usuario que ya ha iniciado sesión</p></td>
<td><p>El usuario mantiene la sesión iniciada y conectada al grupo de copia de seguridad. En algún momento, el usuario se cerrará y volverá a iniciar sesión en el grupo principal original, en el modo de resistencia.</p></td>
<td><p>El usuario mantiene la sesión iniciada y entra en el modo normal.</p></td>
</tr>
<tr class="even">
<td><p>Nuevo inicio de sesión de usuario</p></td>
<td><p>El usuario puede iniciar sesión en el grupo principal en el modo de resistencia.</p></td>
<td><p>El usuario puede iniciar sesión en el grupo principal original en modo normal.</p></td>
</tr>
<tr class="odd">
<td><p>Conferencias en curso organizadas por el usuario afectado</p></td>
<td><p>Se terminan todas las modalidades de conferencia. Aparecerá el botón volver a unir, pero ningún usuario podrá volver a unirse mientras el usuario afectado esté en modo de resistencia.</p></td>
<td><p>Todas las modalidades funcionan ahora. Cada participante tiene que hacer clic para volver a unirse a la Conferencia.</p></td>
</tr>
<tr class="even">
<td><p>Conferencias en curso organizadas por un usuario no afectado</p></td>
<td><p>La Conferencia sigue y el usuario afectado puede permanecer en la Conferencia. El usuario afectado está restringido a lo que puede hacer en el modo de resistencia.</p></td>
<td><p>La Conferencia sigue y el usuario afectado puede permanecer en la Conferencia y todas las modalidades funcionan después de que el usuario salga del modo de resistencia.</p></td>
</tr>
<tr class="odd">
<td><p>Programación o modificación de reuniones programadas, creación de conferencias ad-hoc</p></td>
<td><p>No es posible mientras el usuario está en modo de resistencia.</p></td>
<td><p>Disponible para todas las modalidades.</p></td>
</tr>
<tr class="even">
<td><p>Presencia según lo ven otros usuarios en el mismo grupo de servidores</p></td>
<td><p>Presencia desconocida mientras el usuario inició sesión en el grupo de servidores de reserva durante el modo de resistencia.</p></td>
<td><p>Muestra el último estado de presencia establecido por el usuario, y los cambios de presencia ahora se reflejarán.</p></td>
</tr>
<tr class="odd">
<td><p>Disponibilidad del servicio de libreta de direcciones y lista de contactos</p></td>
<td><p>No disponible</p></td>
<td><p>Disponible</p></td>
</tr>
<tr class="even">
<td><p>Todas las sesiones de punto a punto y las modalidades</p></td>
<td><p>Disponible</p></td>
<td><p>Disponible</p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>Experiencia del usuario para un usuario hospedado en un grupo de servidores no afectado durante la conmutación por recuperación de otro grupo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tarea de usuario</th>
<th>Durante la conmutación por recuperación</th>
<th>Después de completar la conmutación por recuperación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Visualización de la presencia del usuario afectado</p></td>
<td><p>Muestra el último estado de presencia establecido por el usuario afectado.</p></td>
<td><p>Trabaje. Los usuarios no afectados ven las actualizaciones realizadas por los usuarios afectados.</p></td>
</tr>
<tr class="even">
<td><p>Conferencias en curso organizadas por el usuario afectado</p></td>
<td><p>Se terminan todas las modalidades de conferencia.</p></td>
<td><p>Todas las modalidades funcionan ahora. Cada participante tiene que hacer clic para volver a unirse a la Conferencia.</p></td>
</tr>
<tr class="odd">
<td><p>Conferencias en curso organizadas por un usuario no afectado</p></td>
<td><p>La Conferencia sigue y el usuario afectado puede permanecer en la Conferencia y todas las modalidades funcionan.</p></td>
<td><p>La Conferencia sigue y el usuario afectado puede permanecer en la Conferencia y todas las modalidades funcionan.</p></td>
</tr>
<tr class="even">
<td><p>Todas las sesiones de punto a punto y las modalidades</p></td>
<td><p>Disponible</p></td>
<td><p>Disponible</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

