---
title: Lync Server 2013 experiencia del usuario durante un error de grupo
description: Lync Server 2013 experiencia del usuario durante un error del grupo.
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
ms.openlocfilehash: a0483a01b643d8195e7f8f6259c11ab6fc3561f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569796"
---
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="04fbf-103">Experiencia del usuario durante un error de grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04fbf-103">User experience during pool failure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04fbf-104">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="04fbf-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="04fbf-105">Si un grupo se conmuta por error, se fuerza a todos los usuarios del grupo afectado a cerrar sesión y, a continuación, iniciar sesión en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04fbf-105">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="04fbf-106">Durante un breve período, los usuarios que inicien sesión en el grupo de copia de seguridad pueden estar en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-106">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="04fbf-107">En el modo de resistencia, los usuarios no pueden realizar tareas que provocarían un cambio persistente en Lync Server, como agregar un contacto.</span><span class="sxs-lookup"><span data-stu-id="04fbf-107">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="04fbf-108">Una vez completada la conmutación por error, todos los usuarios pueden obtener todos los servicios del grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04fbf-108">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="04fbf-109">Las sesiones que tiene un usuario cuando se produce un error en el grupo de servidores se interrumpen y el usuario debe volver a establecer esas sesiones después de la conmutación por error para continuar.</span><span class="sxs-lookup"><span data-stu-id="04fbf-109">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="04fbf-110">Los usuarios no se reubican durante la conmutación por error o conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="04fbf-110">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="04fbf-111">Los usuarios hospedados en un grupo en el que se produce un error se darán de forma temporal a través del grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04fbf-111">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="04fbf-112">Cuando se restaura el grupo de servidores principales, el administrador puede conmutar por recuperación a estos usuarios para que los dé servicio de su grupo de servidores principal original.</span><span class="sxs-lookup"><span data-stu-id="04fbf-112">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="04fbf-113">Nota en Lync 2013, la base de datos del servidor de información de ubicación no se replica en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04fbf-113">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="04fbf-114">Para un procedimiento recomendado, el administrador debe hacer una copia de seguridad de la base de datos de LIS y usar la copia de seguridad más reciente para restaurar la base de datos LIS en el grupo de copia de seguridad después de la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="04fbf-114">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="04fbf-115">Experiencia de usuario durante la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="04fbf-115">User Experience During Failover</span></span>

<span data-ttu-id="04fbf-116">Cuando un usuario se encuentra en un grupo de servidores que genera un error, el usuario ha cerrado la sesión. Se finalizan todas las sesiones punto a punto en las que participe el usuario, como las conferencias organizadas por dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="04fbf-116">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="04fbf-117">El usuario no puede volver a iniciar sesión hasta que expire el temporizador de resistencia del registrador o el administrador inicie los procedimientos de conmutación por error, lo que suceda primero.</span><span class="sxs-lookup"><span data-stu-id="04fbf-117">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="04fbf-118">Cuando el usuario vuelva a iniciar sesión, iniciará sesión en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04fbf-118">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="04fbf-119">Si inician sesión antes de que se complete la conmutación por error, estarán en modo de resistencia hasta que se complete la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="04fbf-119">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="04fbf-120">Solo entonces el usuario puede establecer nuevas sesiones o restablecer sesiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="04fbf-120">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="04fbf-121">Experiencia de usuario durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="04fbf-121">User Experience During Failback</span></span>

<span data-ttu-id="04fbf-122">La conmutación por recuperación de un grupo de servidores puede ocurrir mientras un usuario afectado inicia sesión en el grupo de copia de seguridad y el usuario permanece conectado y en funcionamiento durante la conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="04fbf-122">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="04fbf-123">Tenga en cuenta que el proceso de conmutación por error tarda en completarse.</span><span class="sxs-lookup"><span data-stu-id="04fbf-123">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="04fbf-124">Como referencia, un grupo de 20.000  usuarios suele tardar 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="04fbf-124">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="04fbf-125">En las siguientes tablas se muestran más detalles sobre cómo un usuario con un cliente de Lync 2013 o un cliente de Microsoft Lync 2010 se ve afectado durante y después de la conmutación por recuperación, así como la forma en que los usuarios de otros grupos de servidores ven e interactúan con un usuario de un grupo de servidores que se está recuperando tras error.</span><span class="sxs-lookup"><span data-stu-id="04fbf-125">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="04fbf-126">Los usuarios con los clientes de Microsoft Office Communicator 2007 R2 no pueden iniciar sesión hasta que el grupo de servidores front-end no pueda realizar una copia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="04fbf-126">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="04fbf-127">El término *usuario afectado* se refiere a cualquier usuario que haya realizado una conmutación por error en el grupo de servidores principales y que esté siendo el servicio del grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04fbf-127">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="04fbf-128">Por definición, cualquier usuario hospedado originalmente en el grupo de copia de seguridad no es un usuario afectado.</span><span class="sxs-lookup"><span data-stu-id="04fbf-128">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="04fbf-129">Experiencia del usuario para un usuario afectado en un grupo de servidores en failback</span><span class="sxs-lookup"><span data-stu-id="04fbf-129">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04fbf-130">Tarea o estado de usuario</span><span class="sxs-lookup"><span data-stu-id="04fbf-130">User state or task</span></span></th>
<th><span data-ttu-id="04fbf-131">Durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="04fbf-131">During failback</span></span></th>
<th><span data-ttu-id="04fbf-132">Después de completar la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="04fbf-132">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04fbf-133">Estado del usuario que ya ha iniciado sesión</span><span class="sxs-lookup"><span data-stu-id="04fbf-133">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="04fbf-134">El usuario mantiene la sesión iniciada y conectada al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04fbf-134">User stays signed in and connected to backup pool.</span></span> <span data-ttu-id="04fbf-135">En algún momento, el usuario se cerrará y volverá a iniciar sesión en el grupo principal original, en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-135">At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="04fbf-136">El usuario mantiene la sesión iniciada y entra en el modo normal.</span><span class="sxs-lookup"><span data-stu-id="04fbf-136">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04fbf-137">Nuevo inicio de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="04fbf-137">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="04fbf-138">El usuario puede iniciar sesión en el grupo principal en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-138">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="04fbf-139">El usuario puede iniciar sesión en el grupo principal original en modo normal.</span><span class="sxs-lookup"><span data-stu-id="04fbf-139">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04fbf-140">Conferencias en curso organizadas por el usuario afectado</span><span class="sxs-lookup"><span data-stu-id="04fbf-140">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="04fbf-141">Se terminan todas las modalidades de conferencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-141">All modalities of conference are terminated.</span></span> <span data-ttu-id="04fbf-142">Aparecerá el botón volver a unir, pero ningún usuario podrá volver a unirse mientras el usuario afectado esté en modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-142">Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="04fbf-143">Todas las modalidades funcionan ahora.</span><span class="sxs-lookup"><span data-stu-id="04fbf-143">All modalities now work.</span></span> <span data-ttu-id="04fbf-144">Cada participante tiene que hacer clic para volver a unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-144">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04fbf-145">Conferencias en curso organizadas por un usuario no afectado</span><span class="sxs-lookup"><span data-stu-id="04fbf-145">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="04fbf-146">La Conferencia sigue y el usuario afectado puede permanecer en la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-146">Conference continues and affected user can stay in the conference.</span></span> <span data-ttu-id="04fbf-147">El usuario afectado está restringido a lo que puede hacer en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-147">Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="04fbf-148">La Conferencia sigue y el usuario afectado puede permanecer en la Conferencia y todas las modalidades funcionan después de que el usuario salga del modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-148">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04fbf-149">Programación o modificación de reuniones programadas, creación de conferencias ad-hoc</span><span class="sxs-lookup"><span data-stu-id="04fbf-149">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="04fbf-150">No es posible mientras el usuario está en modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-150">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="04fbf-151">Disponible para todas las modalidades.</span><span class="sxs-lookup"><span data-stu-id="04fbf-151">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04fbf-152">Presencia según lo ven otros usuarios en el mismo grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="04fbf-152">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="04fbf-153">Presencia desconocida mientras el usuario inició sesión en el grupo de servidores de reserva durante el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-153">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="04fbf-154">Muestra el último estado de presencia establecido por el usuario, y los cambios de presencia ahora se reflejarán.</span><span class="sxs-lookup"><span data-stu-id="04fbf-154">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04fbf-155">Disponibilidad del servicio de libreta de direcciones y lista de contactos</span><span class="sxs-lookup"><span data-stu-id="04fbf-155">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="04fbf-156">No disponible</span><span class="sxs-lookup"><span data-stu-id="04fbf-156">Not available</span></span></p></td>
<td><p><span data-ttu-id="04fbf-157">Disponible</span><span class="sxs-lookup"><span data-stu-id="04fbf-157">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04fbf-158">Todas las sesiones de punto a punto y las modalidades</span><span class="sxs-lookup"><span data-stu-id="04fbf-158">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="04fbf-159">Disponible</span><span class="sxs-lookup"><span data-stu-id="04fbf-159">Available</span></span></p></td>
<td><p><span data-ttu-id="04fbf-160">Disponible</span><span class="sxs-lookup"><span data-stu-id="04fbf-160">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="04fbf-161">Experiencia del usuario para un usuario hospedado en un grupo de servidores no afectado durante la conmutación por recuperación de otro grupo</span><span class="sxs-lookup"><span data-stu-id="04fbf-161">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04fbf-162">Tarea de usuario</span><span class="sxs-lookup"><span data-stu-id="04fbf-162">User task</span></span></th>
<th><span data-ttu-id="04fbf-163">Durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="04fbf-163">During failback</span></span></th>
<th><span data-ttu-id="04fbf-164">Después de completar la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="04fbf-164">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04fbf-165">Visualización de la presencia del usuario afectado</span><span class="sxs-lookup"><span data-stu-id="04fbf-165">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="04fbf-166">Muestra el último estado de presencia establecido por el usuario afectado.</span><span class="sxs-lookup"><span data-stu-id="04fbf-166">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="04fbf-167">Trabaje.</span><span class="sxs-lookup"><span data-stu-id="04fbf-167">Working.</span></span> <span data-ttu-id="04fbf-168">Los usuarios no afectados ven las actualizaciones realizadas por los usuarios afectados.</span><span class="sxs-lookup"><span data-stu-id="04fbf-168">Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04fbf-169">Conferencias en curso organizadas por el usuario afectado</span><span class="sxs-lookup"><span data-stu-id="04fbf-169">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="04fbf-170">Se terminan todas las modalidades de conferencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-170">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="04fbf-171">Todas las modalidades funcionan ahora.</span><span class="sxs-lookup"><span data-stu-id="04fbf-171">All modalities now work.</span></span> <span data-ttu-id="04fbf-172">Cada participante tiene que hacer clic para volver a unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="04fbf-172">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04fbf-173">Conferencias en curso organizadas por un usuario no afectado</span><span class="sxs-lookup"><span data-stu-id="04fbf-173">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="04fbf-174">La Conferencia sigue y el usuario afectado puede permanecer en la Conferencia y todas las modalidades funcionan.</span><span class="sxs-lookup"><span data-stu-id="04fbf-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="04fbf-175">La Conferencia sigue y el usuario afectado puede permanecer en la Conferencia y todas las modalidades funcionan.</span><span class="sxs-lookup"><span data-stu-id="04fbf-175">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04fbf-176">Todas las sesiones de punto a punto y las modalidades</span><span class="sxs-lookup"><span data-stu-id="04fbf-176">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="04fbf-177">Disponible</span><span class="sxs-lookup"><span data-stu-id="04fbf-177">Available</span></span></p></td>
<td><p><span data-ttu-id="04fbf-178">Disponible</span><span class="sxs-lookup"><span data-stu-id="04fbf-178">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

