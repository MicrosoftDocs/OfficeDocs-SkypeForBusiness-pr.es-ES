---
title: Experiencia de usuario de Lync Server 2013 durante un error de grupo
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
ms.openlocfilehash: 2e6506ac67415ca19b33ee968d698d0ed574df8d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Experiencia de usuario durante un error de grupo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Si se conmuta por error un grupo, todos los usuarios del grupo afectado estarán obligados a cerrar sesión y, a continuación, iniciar sesión en el grupo de copias de seguridad. Durante un período breve los usuarios que inicien sesión en el grupo de copia de seguridad pueden encontrarse en modo de resistencia. En el modo de resistencia, los usuarios no pueden realizar tareas que provocarían un cambio continuo en Lync Server, como agregar un contacto. Una vez finalizada la conmutación por error, todos los usuarios pueden utilizar todos los servicios del grupo de copia de seguridad.

Todas las sesiones que tiene un usuario cuando se produce un error en el grupo, y el usuario debe volver a establecer esas sesiones después de la conmutación por error para continuar.

No se vuelven a ubicar los usuarios durante la conmutación por error o la conmutación por recuperación. Los usuarios que están hospedados en un grupo donde se produce un error se hospedarán temporalmente en el grupo de copia de seguridad. Cuando se restaura el grupo de inicio, el administrador puede migrar por error a estos usuarios para que sean atendidas por su grupo original.

Nota en Lync 2013, la base de datos de la información de ubicación no se replica en el grupo de copias de seguridad. Como procedimiento recomendado, el administrador tiene que realizar una copia de seguridad de la base de datos LIS periódicamente y usar la última versión de dicha copia para restaurar la base de datos LIS en el grupo de copia de seguridad tras la conmutación por error.

<div>

## <a name="user-experience-during-failover"></a>Experiencia del usuario durante la conmutación por error

Cuando un usuario se encuentra en un grupo que falla, el usuario ha cerrado sesión. Todas las sesiones de punto a punto en las que participó el usuario están terminadas, al igual que las conferencias organizadas por dicho usuario. El usuario no puede volver a iniciar sesión hasta que caduque el temporizador de resistencia del registrador o el administrador inicie los procedimientos de conmutación por error, lo que ocurra primero. Cuando el usuario reinicia sesión, iniciará la sesión en el grupo de copia de seguridad. Si inicia sesión antes de que finalice la conmutación por error, estará en modo de resistencia hasta que finalice la conmutación por error. Solo entonces el usuario puede establecer sesiones nuevas o volver a establecer sesiones anteriores.

</div>

<div>

## <a name="user-experience-during-failback"></a>Experiencia de usuario durante la conmutación por recuperación

La conmutación por recuperación de un grupo puede ocurrir cuando un usuario afectado ha iniciado sesión en el grupo de copia de seguridad y el usuario permanece conectado y sigue trabajando durante la conmutación por recuperación. Tenga en cuenta que el proceso de recuperación tras error tarda varios minutos en completarse.Como referencia, se espera que tarde 60 minutos como máximo para un grupo de 20 000 usuarios.

En las tablas siguientes se muestran más detalles sobre cómo un usuario con un cliente de Lync 2013 o de Microsoft Lync 2010 se ve afectado durante y después de la conmutación por recuperación, y también cómo los usuarios de otros grupos ven e interactúan con un usuario de un grupo que se vuelve a enviar. Los usuarios con clientes de Microsoft Office Communicator 2007 R2 no pueden iniciar sesión hasta que el grupo de servidores front-end no se haya realizado correctamente.

El término *usuario afectado* hace referencia a cualquier usuario que sufrió una conmutación por error en el grupo principal y está hospedado ahora en el grupo de copia de seguridad. Por definición, cualquier usuario que haya alojado originalmente en el grupo de copias de seguridad no es un usuario afectado.

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>Experiencia de un usuario afectado en un grupo de conmutación por recuperación

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tarea o estado del usuario</th>
<th>Durante la conmutación por recuperación</th>
<th>Una vez finalizada la conmutación por recuperación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Estado del usuario que ya ha iniciado sesión</p></td>
<td><p>El usuario permanece en su sesión y sigue conectado al grupo de copia de seguridad. En algún momento, se cerrará la sesión del usuario y volverá a la sesión en el grupo principal original, en el modo de resistencia.</p></td>
<td><p>El usuario continúa en su sesión y se coloca en modo normal.</p></td>
</tr>
<tr class="even">
<td><p>Inicio de sesión de un nuevo usuario</p></td>
<td><p>El usuario puede iniciar sesión en el grupo principal en el modo de resistencia.</p></td>
<td><p>El usuario puede iniciar sesión en el grupo principal original en modo normal.</p></td>
</tr>
<tr class="odd">
<td><p>Conferencias en curso organizadas por un usuario afectado</p></td>
<td><p>Se terminan todas las modalidades de conferencia. Se mostrará el botón Unirse de nuevo, pero ningún usuario puede volver a unirse mientras el usuario afectado está en modo de resistencia.</p></td>
<td><p>Ahora funcionan todas las modalidades. Cada participante tiene que hacer clic para volver a unirse a la conferencia.</p></td>
</tr>
<tr class="even">
<td><p>Conferencias en curso organizadas por un usuario no afectado</p></td>
<td><p>La conferencia continúa y el usuario afectado puede permanecer en la conferencia. El usuario afectado está limitado a lo que se puede hacer en el modo de resistencia.</p></td>
<td><p>La conferencia continúa y el usuario afectado puede permanecer en la conferencia y todas las modalidades funcionan después de que el usuario sale del modo de resistencia.</p></td>
</tr>
<tr class="odd">
<td><p>Programación o modificación de las reuniones programadas, creación de conferencias ad-hoc</p></td>
<td><p>No son posibles mientras el usuario está en modo de resistencia.</p></td>
<td><p>Disponibles para todas las modalidades.</p></td>
</tr>
<tr class="even">
<td><p>Presencia según otros usuarios en el mismo grupo</p></td>
<td><p>Presencia desconocida mientras el usuario está conectado al grupo de copia de seguridad durante el modo de resistencia.</p></td>
<td><p>Muestra el último estado de presencia establecido por el usuario, y los cambios de presencia ahora se reflejarán.</p></td>
</tr>
<tr class="odd">
<td><p>Disponibilidad del servicio de la libreta de direcciones y la lista de contactos</p></td>
<td><p>No disponible</p></td>
<td><p>Disponible</p></td>
</tr>
<tr class="even">
<td><p>Todas las sesiones punto a punto y las modalidades</p></td>
<td><p>Disponible</p></td>
<td><p>Disponible</p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>Experiencia de un usuario hospedado en un grupo de servidores no afectado durante la conmutación por recuperación de otro grupo

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
<th>Una vez finalizada la conmutación por recuperación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Visualización de la presencia del usuario afectado</p></td>
<td><p>Muestra el último estado de presencia establecido por el usuario afectado.</p></td>
<td><p>En funcionamiento. Los usuarios no afectados verán las actualizaciones realizadas por los usuarios afectados.</p></td>
</tr>
<tr class="even">
<td><p>Conferencias en curso organizadas por un usuario afectado</p></td>
<td><p>Se terminan todas las modalidades de conferencia.</p></td>
<td><p>Ahora funcionan todas las modalidades. Cada participante tiene que hacer clic para volver a unirse a la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p>Conferencias en curso organizadas por un usuario no afectado</p></td>
<td><p>La conferencia continúa, el usuario afectado puede permanecer en la conferencia y funcionan todas las modalidades.</p></td>
<td><p>La conferencia continúa, el usuario afectado puede permanecer en la conferencia y funcionan todas las modalidades.</p></td>
</tr>
<tr class="even">
<td><p>Todas las sesiones punto a punto y las modalidades</p></td>
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

