---
title: 'Actualizar a Teams desde una implementación local de Skype Empresarial: Microsoft Teams'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 'Actualizar de Skype Empresarial a Teams: herramientas para actualizar'
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 952214d615b62d0175841e2c7b24b45f1ae2d2b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533577"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="a77cb-103">Herramientas para actualizar a Teams para &mdash; administradores de TI</span><span class="sxs-lookup"><span data-stu-id="a77cb-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="a77cb-104">En este artículo se describen las herramientas para actualizar a Teams.</span><span class="sxs-lookup"><span data-stu-id="a77cb-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="a77cb-105">Este artículo es el tercero de varios que describen los conceptos de actualización y la implementación para los administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="a77cb-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="a77cb-106">Información general</span><span class="sxs-lookup"><span data-stu-id="a77cb-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="a77cb-107">Métodos de actualización</span><span class="sxs-lookup"><span data-stu-id="a77cb-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="a77cb-108">**Herramientas para administrar la actualización**   (este artículo)</span><span class="sxs-lookup"><span data-stu-id="a77cb-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="a77cb-109">Consideraciones adicionales para las organizaciones con Skype Empresarial local</span><span class="sxs-lookup"><span data-stu-id="a77cb-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="a77cb-110">Implementar la actualización</span><span class="sxs-lookup"><span data-stu-id="a77cb-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="a77cb-111">Consideraciones de la red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="a77cb-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="a77cb-112">Además, en los artículos siguientes se describen conceptos importantes de actualización y comportamientos de coexistencia:</span><span class="sxs-lookup"><span data-stu-id="a77cb-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="a77cb-113">Coexistencia de Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="a77cb-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="a77cb-114">Modos de coexistencia - Referencia</span><span class="sxs-lookup"><span data-stu-id="a77cb-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="a77cb-115">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="a77cb-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="a77cb-116">Herramientas para administrar la actualización</span><span class="sxs-lookup"><span data-stu-id="a77cb-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="a77cb-117">Independientemente del método de actualización que elija, para los usuarios que ya tienen Skype Empresarial Online, administre la transición a TeamsOnly con [TeamsUpgradePolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)que controla el modo de coexistencia de un usuario.</span><span class="sxs-lookup"><span data-stu-id="a77cb-117">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="a77cb-118">Para los usuarios con una cuenta local en Skype Empresarial Server, también puede usarlos para `Move-CsUser` [moverlos a la nube.](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="a77cb-118">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="a77cb-119">Para obtener más información sobre cada uno de los modos, vea Modos [de coexistencia.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="a77cb-119">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>  

<span data-ttu-id="a77cb-120">Tanto si realiza la transición de funciones específicas con los modos de Skype Empresarial como si simplemente actualiza al modo TeamsOnly desde la configuración predeterminada de las Islas, TeamsUpgradePolicy es la herramienta principal para los usuarios que ya tienen Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="a77cb-120">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="a77cb-121">Como cualquier otra directiva de Teams, puede asignar TeamsUpgradePolicy directamente a un usuario.</span><span class="sxs-lookup"><span data-stu-id="a77cb-121">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="a77cb-122">También puede establecer la directiva como predeterminada para todo el inquilino.</span><span class="sxs-lookup"><span data-stu-id="a77cb-122">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="a77cb-123">Cualquier asignación a un usuario tiene prioridad sobre la configuración predeterminada del inquilino.</span><span class="sxs-lookup"><span data-stu-id="a77cb-123">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="a77cb-124">Puede administrar la directiva en la Consola de administración de Teams y en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a77cb-124">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="a77cb-125">También puede asignar cualquier modo de TeamsUpgradePolicy, excepto el modo TeamsOnly, a los usuarios que están en Skype Empresarial local.</span><span class="sxs-lookup"><span data-stu-id="a77cb-125">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="a77cb-126">**El modo TeamsOnly solo puede asignarse a un usuario que ya** esté en Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="a77cb-126">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="a77cb-127">Esto se debe a que la interoperabilidad con los usuarios y la federación de Skype Empresarial y la funcionalidad del Sistema telefónico de Microsoft 365 solo son posibles si el usuario está en Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="a77cb-127">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="a77cb-128">Además, no puede asignar el modo **TeamsOnly** como el valor predeterminado de todo el espacio empresarial si tiene una implementación local de Skype Empresarial (que se detecta por la presencia de un registro DNS de lyncdiscover que apunta a una ubicación diferente a Office 365.</span><span class="sxs-lookup"><span data-stu-id="a77cb-128">In addition, **you cannot assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="a77cb-129">Los usuarios con cuentas de Skype Empresarial locales deben moverse en línea [(ya](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) sea a Skype Empresarial Online o directamente a Teams) con Move-CsUser en el conjunto de herramientas local de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="a77cb-129">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="a77cb-130">Estos usuarios se pueden mover a TeamsOnly en uno o dos pasos:</span><span class="sxs-lookup"><span data-stu-id="a77cb-130">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="a77cb-131">1 paso: Especificar el modificador -MoveToTeams en Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="a77cb-131">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="a77cb-132">Esto requiere Skype Empresarial Server 2019 o Skype Empresarial Server 2015 con CU8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="a77cb-132">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="a77cb-133">2 pasos: Después de ejecutar Move-CsUser, conceda el modo TeamsOnly al usuario mediante TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="a77cb-133">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="a77cb-134">A diferencia de otras directivas, no es posible crear nuevas instancias de TeamsUpgradePolicy en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="a77cb-134">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="a77cb-135">Todas las instancias existentes están integradas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="a77cb-135">All the existing instances are built into the service.</span></span>  <span data-ttu-id="a77cb-136">(Tenga en cuenta que el modo es una propiedad dentro de TeamsUpgradePolicy, en lugar del nombre de una instancia de directiva). En algunos casos (aunque no todos), el nombre de la instancia de directiva es el mismo que el modo.</span><span class="sxs-lookup"><span data-stu-id="a77cb-136">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="a77cb-137">En particular, para asignar el modo TeamsOnly a un usuario, concederá la instancia "UpgradeToTeams" de TeamsUpgradePolicy a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="a77cb-137">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="a77cb-138">Para ver una lista de todas las instancias, puede ejecutar el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="a77cb-138">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="a77cb-139">Para actualizar un usuario en línea al modo TeamsOnly, asigne la instancia "UpgradeToTeams":</span><span class="sxs-lookup"><span data-stu-id="a77cb-139">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="a77cb-140">Para actualizar un usuario local de Skype Empresarial al modo TeamsOnly, use Move-CsUser el conjunto de herramientas local:</span><span class="sxs-lookup"><span data-stu-id="a77cb-140">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="a77cb-141">Para cambiar el modo de todos los usuarios del espacio empresarial, excepto los que tienen una concesión explícita por usuario (que tiene prioridad), ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a77cb-141">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="a77cb-142">Si tiene usuarios con cuentas de Skype Empresarial locales, no puede asignar el modo TeamsOnly en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="a77cb-142">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="a77cb-143">Debe mover estos usuarios individualmente a la nube mediante Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="a77cb-143">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="a77cb-144">Usar notificaciones en clientes de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="a77cb-144">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="a77cb-145">Los administradores tienen la opción de proporcionar notificaciones de usuario final en el cliente de Skype Empresarial para informar a los usuarios de que pronto se actualizarán a Teams, tal como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="a77cb-145">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="a77cb-146">Por ejemplo, una semana antes de que el administrador tenga previsto actualizar un grupo de usuarios al modo TeamsOnly, es posible que el administrador quiera activar estas notificaciones para ese grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a77cb-146">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="a77cb-147">Estas notificaciones están habilitadas usando una instancia de TeamsUpgradePolicy con NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="a77cb-147">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="a77cb-148">Para todos los modos distintos de TeamsOnly, realmente hay dos instancias por modo, que corresponde a los dos valores de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="a77cb-148">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="a77cb-149">Para todos los modos distintos de TeamsOnly, realmente hay dos instancias por modo, que corresponde a los dos valores de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="a77cb-149">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagrama que muestra notificaciones](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="a77cb-151">Si los usuarios están en Skype Empresarial Online, simplemente asigne la instancia de directiva que tenga el mismo modo que el usuario, pero con NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="a77cb-151">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="a77cb-152">Si los usuarios están en Skype Empresarial Server local, necesitará usar el conjunto de herramientas local y necesitará Skype Empresarial Server 2019 o CU8 para Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a77cb-152">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="a77cb-153">Para los usuarios que están en Skype Empresarial Server local, se respeta la propiedad mode de la instancia en línea de TeamsUpgradePolicy, pero no la propiedad NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="a77cb-153">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="a77cb-154">Si quiere recibir notificaciones, debe crear una instancia local de TeamsUpgradePolicy para controlar el comportamiento del cliente.</span><span class="sxs-lookup"><span data-stu-id="a77cb-154">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="a77cb-155">En la ventana de PowerShell local, cree una nueva instancia de TeamsUpgradePolicy con NotifySfbUsers=true:</span><span class="sxs-lookup"><span data-stu-id="a77cb-155">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="a77cb-156">Después, con la misma ventana de PowerShell local, asigne esa nueva directiva a los usuarios que quiera:</span><span class="sxs-lookup"><span data-stu-id="a77cb-156">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="a77cb-157">Migración de reuniones</span><span class="sxs-lookup"><span data-stu-id="a77cb-157">Meeting migration</span></span>

<span data-ttu-id="a77cb-158">Cuando se migra un usuario al modo TeamsOnly, sus reuniones existentes de Skype Empresarial que han organizado se convierten en Teams de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a77cb-158">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="a77cb-159">Opcionalmente, puede deshabilitar el comportamiento predeterminado al asignar el modo TeamsOnly a un usuario.</span><span class="sxs-lookup"><span data-stu-id="a77cb-159">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="a77cb-160">Al mover usuarios desde local, las reuniones deben migrarse a la nube para que funcionen con la cuenta de usuario en línea, pero si no especifica -MoveToTeams, las reuniones se migrarán como reuniones de Skype Empresarial, en lugar de convertirse a Teams.</span><span class="sxs-lookup"><span data-stu-id="a77cb-160">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="a77cb-161">Al asignar el modo TeamsOnly en el nivel de inquilino, no se activa la migración de reuniones para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a77cb-161">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="a77cb-162">Si desea asignar el modo TeamsOnly en el nivel de inquilino y migrar reuniones, puede usar PowerShell para obtener una lista de usuarios en el inquilino (por ejemplo, usando Get-CsOnlineUser con los filtros que sean necesarios) y, después, recorrer cada uno de estos usuarios para desencadenar la migración de reuniones con Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="a77cb-162">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="a77cb-163">Para obtener más información, [consulte Usar el servicio de migración de reuniones (MMS).](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="a77cb-163">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="a77cb-164">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="a77cb-164">Related links</span></span>

[<span data-ttu-id="a77cb-165">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="a77cb-165">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="a77cb-166">Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="a77cb-166">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="a77cb-167">Mover usuarios entre la implementación local y la nube</span><span class="sxs-lookup"><span data-stu-id="a77cb-167">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="a77cb-168">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="a77cb-168">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="a77cb-169">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="a77cb-169">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="a77cb-170">Usar el servicio de migración de reuniones (MMS)</span><span class="sxs-lookup"><span data-stu-id="a77cb-170">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

