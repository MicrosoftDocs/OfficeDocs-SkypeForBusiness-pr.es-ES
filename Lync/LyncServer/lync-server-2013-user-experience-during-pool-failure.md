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
ms.openlocfilehash: 65d33dad39527f64ba7b96ae6d75f8d6e11a2f04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="fb5ad-102">Experiencia del usuario durante un error de grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb5ad-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb5ad-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="fb5ad-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="fb5ad-104">Si un grupo se conmuta por error, se fuerza a todos los usuarios del grupo afectado a cerrar sesión y, a continuación, iniciar sesión en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="fb5ad-105">Durante un breve período, los usuarios que inicien sesión en el grupo de copia de seguridad pueden estar en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="fb5ad-106">En el modo de resistencia, los usuarios no pueden realizar tareas que provocarían un cambio persistente en Lync Server, como agregar un contacto.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="fb5ad-107">Una vez completada la conmutación por error, todos los usuarios pueden obtener todos los servicios del grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="fb5ad-108">Las sesiones que tiene un usuario cuando se produce un error en el grupo de servidores se interrumpen y el usuario debe volver a establecer esas sesiones después de la conmutación por error para continuar.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="fb5ad-109">Los usuarios no se reubican durante la conmutación por error o conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-109">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="fb5ad-110">Los usuarios hospedados en un grupo en el que se produce un error se darán de forma temporal a través del grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-110">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="fb5ad-111">Cuando se restaura el grupo de servidores principales, el administrador puede conmutar por recuperación a estos usuarios para que los dé servicio de su grupo de servidores principal original.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-111">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="fb5ad-112">Nota en Lync 2013, la base de datos del servidor de información de ubicación no se replica en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="fb5ad-113">Para un procedimiento recomendado, el administrador debe hacer una copia de seguridad de la base de datos de LIS y usar la copia de seguridad más reciente para restaurar la base de datos LIS en el grupo de copia de seguridad después de la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="fb5ad-114">Experiencia de usuario durante la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="fb5ad-114">User Experience During Failover</span></span>

<span data-ttu-id="fb5ad-115">Cuando un usuario se encuentra en un grupo de servidores que genera un error, el usuario ha cerrado la sesión. Se finalizan todas las sesiones punto a punto en las que participe el usuario, como las conferencias organizadas por dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-115">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="fb5ad-116">El usuario no puede volver a iniciar sesión hasta que expire el temporizador de resistencia del registrador o el administrador inicie los procedimientos de conmutación por error, lo que suceda primero.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-116">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="fb5ad-117">Cuando el usuario vuelva a iniciar sesión, iniciará sesión en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-117">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="fb5ad-118">Si inician sesión antes de que se complete la conmutación por error, estarán en modo de resistencia hasta que se complete la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-118">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="fb5ad-119">Solo entonces el usuario puede establecer nuevas sesiones o restablecer sesiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-119">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="fb5ad-120">Experiencia de usuario durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="fb5ad-120">User Experience During Failback</span></span>

<span data-ttu-id="fb5ad-121">La conmutación por recuperación de un grupo de servidores puede ocurrir mientras un usuario afectado inicia sesión en el grupo de copia de seguridad y el usuario permanece conectado y en funcionamiento durante la conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-121">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="fb5ad-122">Tenga en cuenta que el proceso de conmutación por error tarda en completarse.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-122">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="fb5ad-123">Como referencia, un grupo de 20.000  usuarios suele tardar 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-123">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="fb5ad-124">En las siguientes tablas se muestran más detalles sobre cómo un usuario con un cliente de Lync 2013 o un cliente de Microsoft Lync 2010 se ve afectado durante y después de la conmutación por recuperación, así como la forma en que los usuarios de otros grupos de servidores ven e interactúan con un usuario de un grupo de servidores que se está recuperando tras error.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="fb5ad-125">Los usuarios con los clientes de Microsoft Office Communicator 2007 R2 no pueden iniciar sesión hasta que el grupo de servidores front-end no pueda realizar una copia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="fb5ad-126">El término *usuario afectado* se refiere a cualquier usuario que haya realizado una conmutación por error en el grupo de servidores principales y que esté siendo el servicio del grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-126">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="fb5ad-127">Por definición, cualquier usuario hospedado originalmente en el grupo de copia de seguridad no es un usuario afectado.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-127">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="fb5ad-128">Experiencia del usuario para un usuario afectado en un grupo de servidores en failback</span><span class="sxs-lookup"><span data-stu-id="fb5ad-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb5ad-129">Tarea o estado de usuario</span><span class="sxs-lookup"><span data-stu-id="fb5ad-129">User state or task</span></span></th>
<th><span data-ttu-id="fb5ad-130">Durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="fb5ad-130">During failback</span></span></th>
<th><span data-ttu-id="fb5ad-131">Después de completar la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="fb5ad-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb5ad-132">Estado del usuario que ya ha iniciado sesión</span><span class="sxs-lookup"><span data-stu-id="fb5ad-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-133">El usuario mantiene la sesión iniciada y conectada al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-133">User stays signed in and connected to backup pool.</span></span> <span data-ttu-id="fb5ad-134">En algún momento, el usuario se cerrará y volverá a iniciar sesión en el grupo principal original, en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-134">At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-135">El usuario mantiene la sesión iniciada y entra en el modo normal.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5ad-136">Nuevo inicio de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="fb5ad-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-137">El usuario puede iniciar sesión en el grupo principal en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-138">El usuario puede iniciar sesión en el grupo principal original en modo normal.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb5ad-139">Conferencias en curso organizadas por el usuario afectado</span><span class="sxs-lookup"><span data-stu-id="fb5ad-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-140">Se terminan todas las modalidades de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-140">All modalities of conference are terminated.</span></span> <span data-ttu-id="fb5ad-141">Aparecerá el botón volver a unir, pero ningún usuario podrá volver a unirse mientras el usuario afectado esté en modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-141">Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-142">Todas las modalidades funcionan ahora.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-142">All modalities now work.</span></span> <span data-ttu-id="fb5ad-143">Cada participante tiene que hacer clic para volver a unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-143">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5ad-144">Conferencias en curso organizadas por un usuario no afectado</span><span class="sxs-lookup"><span data-stu-id="fb5ad-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-145">La Conferencia sigue y el usuario afectado puede permanecer en la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-145">Conference continues and affected user can stay in the conference.</span></span> <span data-ttu-id="fb5ad-146">El usuario afectado está restringido a lo que puede hacer en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-146">Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-147">La Conferencia sigue y el usuario afectado puede permanecer en la Conferencia y todas las modalidades funcionan después de que el usuario salga del modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb5ad-148">Programación o modificación de reuniones programadas, creación de conferencias ad-hoc</span><span class="sxs-lookup"><span data-stu-id="fb5ad-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-149">No es posible mientras el usuario está en modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-150">Disponible para todas las modalidades.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5ad-151">Presencia según lo ven otros usuarios en el mismo grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="fb5ad-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-152">Presencia desconocida mientras el usuario inició sesión en el grupo de servidores de reserva durante el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-153">Muestra el último estado de presencia establecido por el usuario, y los cambios de presencia ahora se reflejarán.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb5ad-154">Disponibilidad del servicio de libreta de direcciones y lista de contactos</span><span class="sxs-lookup"><span data-stu-id="fb5ad-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-155">No disponible</span><span class="sxs-lookup"><span data-stu-id="fb5ad-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-156">Disponible</span><span class="sxs-lookup"><span data-stu-id="fb5ad-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5ad-157">Todas las sesiones de punto a punto y las modalidades</span><span class="sxs-lookup"><span data-stu-id="fb5ad-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-158">Disponible</span><span class="sxs-lookup"><span data-stu-id="fb5ad-158">Available</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-159">Disponible</span><span class="sxs-lookup"><span data-stu-id="fb5ad-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="fb5ad-160">Experiencia del usuario para un usuario hospedado en un grupo de servidores no afectado durante la conmutación por recuperación de otro grupo</span><span class="sxs-lookup"><span data-stu-id="fb5ad-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb5ad-161">Tarea de usuario</span><span class="sxs-lookup"><span data-stu-id="fb5ad-161">User task</span></span></th>
<th><span data-ttu-id="fb5ad-162">Durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="fb5ad-162">During failback</span></span></th>
<th><span data-ttu-id="fb5ad-163">Después de completar la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="fb5ad-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb5ad-164">Visualización de la presencia del usuario afectado</span><span class="sxs-lookup"><span data-stu-id="fb5ad-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-165">Muestra el último estado de presencia establecido por el usuario afectado.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-166">Trabaje.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-166">Working.</span></span> <span data-ttu-id="fb5ad-167">Los usuarios no afectados ven las actualizaciones realizadas por los usuarios afectados.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-167">Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5ad-168">Conferencias en curso organizadas por el usuario afectado</span><span class="sxs-lookup"><span data-stu-id="fb5ad-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-169">Se terminan todas las modalidades de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-170">Todas las modalidades funcionan ahora.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-170">All modalities now work.</span></span> <span data-ttu-id="fb5ad-171">Cada participante tiene que hacer clic para volver a unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-171">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb5ad-172">Conferencias en curso organizadas por un usuario no afectado</span><span class="sxs-lookup"><span data-stu-id="fb5ad-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-173">La Conferencia sigue y el usuario afectado puede permanecer en la Conferencia y todas las modalidades funcionan.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-174">La Conferencia sigue y el usuario afectado puede permanecer en la Conferencia y todas las modalidades funcionan.</span><span class="sxs-lookup"><span data-stu-id="fb5ad-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5ad-175">Todas las sesiones de punto a punto y las modalidades</span><span class="sxs-lookup"><span data-stu-id="fb5ad-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-176">Disponible</span><span class="sxs-lookup"><span data-stu-id="fb5ad-176">Available</span></span></p></td>
<td><p><span data-ttu-id="fb5ad-177">Disponible</span><span class="sxs-lookup"><span data-stu-id="fb5ad-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

