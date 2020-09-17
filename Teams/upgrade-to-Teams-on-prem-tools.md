---
title: Actualizar a teams desde una implementación local de Skype empresarial-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Actualización de Skype Empresarial a Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf51019aad5b2deb6239c698623475263241b3f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940737"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="160d6-103">Herramientas para actualizar a teams &mdash; para administradores de ti</span><span class="sxs-lookup"><span data-stu-id="160d6-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="160d6-104">En este artículo se describen las herramientas para actualizar a teams.</span><span class="sxs-lookup"><span data-stu-id="160d6-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="160d6-105">Este artículo es el tercero de varios que describen los conceptos de actualización y la implementación para administradores de ti.</span><span class="sxs-lookup"><span data-stu-id="160d6-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="160d6-106">Información general</span><span class="sxs-lookup"><span data-stu-id="160d6-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="160d6-107">Métodos de actualización</span><span class="sxs-lookup"><span data-stu-id="160d6-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="160d6-108">**Herramientas para administrar la actualización**   (este artículo)</span><span class="sxs-lookup"><span data-stu-id="160d6-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="160d6-109">Consideraciones adicionales para las organizaciones con Skype empresarial local</span><span class="sxs-lookup"><span data-stu-id="160d6-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="160d6-110">Implementar la actualización</span><span class="sxs-lookup"><span data-stu-id="160d6-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="160d6-111">Consideraciones sobre la red telefónica pública conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="160d6-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="160d6-112">Además, los artículos siguientes describen los conceptos de actualización importantes y los comportamientos de coexistencia:</span><span class="sxs-lookup"><span data-stu-id="160d6-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="160d6-113">Coexistencia de Teams y Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="160d6-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="160d6-114">Modos de coexistencia: referencia</span><span class="sxs-lookup"><span data-stu-id="160d6-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="160d6-115">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="160d6-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="160d6-116">Herramientas para administrar la actualización</span><span class="sxs-lookup"><span data-stu-id="160d6-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="160d6-117">Independientemente del método de actualización que elija, administra la transición a TeamsOnly con [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), que controla el modo de coexistencia de un usuario.</span><span class="sxs-lookup"><span data-stu-id="160d6-117">Whichever upgrade method you choose, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="160d6-118">Para obtener más información sobre cada uno de los modos, vea [modos de coexistencia](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="160d6-118">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="160d6-119">Tanto si realiza una transición de funciones seleccionadas con los modos de Skype empresarial o simplemente si actualiza el modo TeamsOnly desde la configuración de islas predeterminadas, TeamsUpgradePolicy es la herramienta principal.</span><span class="sxs-lookup"><span data-stu-id="160d6-119">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.</span></span> <span data-ttu-id="160d6-120">Como cualquier otra directiva de Teams, puede asignar TeamsUpgradePolicy directamente a un usuario.</span><span class="sxs-lookup"><span data-stu-id="160d6-120">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="160d6-121">También puede establecer la Directiva como el valor predeterminado para todo el inquilino.</span><span class="sxs-lookup"><span data-stu-id="160d6-121">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="160d6-122">Cualquier asignación a un usuario tiene prioridad sobre la configuración predeterminada de inquilino.</span><span class="sxs-lookup"><span data-stu-id="160d6-122">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="160d6-123">Puede administrar la Directiva en la consola de administración de Teams y en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="160d6-123">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="160d6-124">Puede asignar cualquier modo de TeamsUpgradePolicy a los usuarios, independientemente de si el usuario está alojado en Skype empresarial online o en un entorno local, **excepto que el modo TeamsOnly solo se puede asignar a un usuario que ya esté alojado en Skype empresarial online**.</span><span class="sxs-lookup"><span data-stu-id="160d6-124">You can assign any mode of TeamsUpgradePolicy to users whether the user is homed in Skype for Business Online or on-premises, **except that TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="160d6-125">Esto se debe a que la interoperabilidad con usuarios y Federación de Skype empresarial, así como con la funcionalidad del sistema telefónico de Microsoft 365 solo es posible si el usuario se ha alojado en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="160d6-125">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>

<span data-ttu-id="160d6-126">Los usuarios con cuentas de Skype empresarial domésticas locales [deben moverse por Internet](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (ya sea a Skype empresarial online o directamente a teams) mediante Move-CsUser en el conjunto de herramientas de Skype empresarial local.</span><span class="sxs-lookup"><span data-stu-id="160d6-126">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="160d6-127">Estos usuarios se pueden mover a TeamsOnly en 1 o 2 pasos:</span><span class="sxs-lookup"><span data-stu-id="160d6-127">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="160d6-128">1 paso: especificar el modificador-MoveToTeams en Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="160d6-128">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="160d6-129">Para ello, necesita Skype empresarial Server 2019 o Skype empresarial Server 2015 con CU8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="160d6-129">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="160d6-130">2 pasos: después de ejecutar Move-CsUser, conceda el modo TeamsOnly al usuario mediante TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="160d6-130">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="160d6-131">A diferencia de otras directivas, no es posible crear nuevas instancias de TeamsUpgradePolicy en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="160d6-131">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="160d6-132">Todas las instancias existentes están integradas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="160d6-132">All the existing instances are built into the service.</span></span>  <span data-ttu-id="160d6-133">(Tenga en cuenta que el modo es una propiedad dentro de TeamsUpgradePolicy, en lugar del nombre de una instancia de directiva). En algunos, pero no en todos los casos, el nombre de la instancia de directiva es el mismo que el modo.</span><span class="sxs-lookup"><span data-stu-id="160d6-133">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="160d6-134">En concreto, para asignar el modo de TeamsOnly a un usuario, conceda la instancia "UpgradeToTeams" de TeamsUpgradePolicy a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="160d6-134">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="160d6-135">Para ver una lista de todas las instancias, puede ejecutar el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="160d6-135">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="160d6-136">Para actualizar un usuario en línea al modo TeamsOnly, asigne la instancia "UpgradeToTeams":</span><span class="sxs-lookup"><span data-stu-id="160d6-136">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="160d6-137">Para actualizar un usuario local de Skype empresarial al modo TeamsOnly, use Move-CsUser en el conjunto de herramientas local:</span><span class="sxs-lookup"><span data-stu-id="160d6-137">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="160d6-138">Para cambiar el modo para todos los usuarios del espacio empresarial, excepto aquellos que tienen una concesión de conceder por usuario explícita (que tiene prioridad), ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="160d6-138">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="160d6-139">Si tiene usuarios de Skype empresarial locales, no debe asignar el modo TeamsOnly en el nivel del espacio empresarial, a menos que asigne de forma explícita algún otro modo a todos los usuarios con cuentas locales de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="160d6-139">If you have any users with Skype for Business accounts on-premises, you must not assign TeamsOnly mode at the tenant level, unless you explicitly assign some other mode to all users with on-premises Skype for Business accounts.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="160d6-140">Uso de notificaciones en clientes de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="160d6-140">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="160d6-141">Los administradores tienen la opción de proporcionar notificaciones de usuario final en el cliente de Skype empresarial para informar a los usuarios de que pronto se actualizarán a Teams, tal y como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="160d6-141">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="160d6-142">Por ejemplo, una semana antes de que el administrador planea actualizar un grupo de usuarios al modo TeamsOnly, es posible que el administrador desee activar estas notificaciones para ese grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="160d6-142">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="160d6-143">Estas notificaciones se habilitan mediante una instancia de TeamsUpgradePolicy con NotifySfbUsers = true.</span><span class="sxs-lookup"><span data-stu-id="160d6-143">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="160d6-144">Para todos los modos distintos de TeamsOnly, en realidad existen dos instancias por modo, que corresponden a los dos valores de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="160d6-144">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="160d6-145">Para todos los modos distintos de TeamsOnly, en realidad existen dos instancias por modo, que corresponden a los dos valores de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="160d6-145">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagrama que muestra las notificaciones](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="160d6-147">Si los usuarios están alojados en Skype empresarial online, simplemente asigne la instancia de directiva que tiene el mismo modo que el usuario, pero con NotifySfbUsers = true.</span><span class="sxs-lookup"><span data-stu-id="160d6-147">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="160d6-148">Si los usuarios están alojados en Skype empresarial Server local, tendrá que usar el conjunto de herramientas local y necesitará Skype empresarial Server 2019 o CU8 para Skype empresarial Server 2015...</span><span class="sxs-lookup"><span data-stu-id="160d6-148">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="160d6-149">Para los usuarios alojados en Skype empresarial Server local, se admite la propiedad Mode de la instancia de TeamsUpgradePolicy, pero no la propiedad NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="160d6-149">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="160d6-150">Si deseas recibir notificaciones, deberás crear una instancia local de TeamsUpgradePolicy para controlar el comportamiento de los clientes.</span><span class="sxs-lookup"><span data-stu-id="160d6-150">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="160d6-151">En la ventana de PowerShell local, cree una nueva instancia de TeamsUpgradePolicy con NotifySfbUsers = true:</span><span class="sxs-lookup"><span data-stu-id="160d6-151">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="160d6-152">Después, con la misma ventana de PowerShell local, asigne esa nueva Directiva a los usuarios que desee:</span><span class="sxs-lookup"><span data-stu-id="160d6-152">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="160d6-153">Migración de reuniones</span><span class="sxs-lookup"><span data-stu-id="160d6-153">Meeting migration</span></span>

<span data-ttu-id="160d6-154">Cuando se migra un usuario al modo TeamsOnly, las reuniones de Skype empresarial existentes que organizó se convertirán en Teams de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="160d6-154">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="160d6-155">Si lo desea, puede deshabilitar el comportamiento predeterminado al asignar el modo de TeamsOnly a un usuario.</span><span class="sxs-lookup"><span data-stu-id="160d6-155">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="160d6-156">Al mover usuarios de forma local, las reuniones se deben migrar a la nube para que funcione con la cuenta de usuario en línea, pero si no especifica-MoveToTeams, las reuniones se migrarán como reuniones de Skype empresarial, en lugar de convertirlas a teams.</span><span class="sxs-lookup"><span data-stu-id="160d6-156">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="160d6-157">Al asignar el modo de TeamsOnly en el nivel de espacio empresarial, la migración de reuniones no se desencadena para ningún usuario.</span><span class="sxs-lookup"><span data-stu-id="160d6-157">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="160d6-158">Si desea asignar el modo de TeamsOnly en el nivel de inquilino y migrar reuniones, puede usar PowerShell para obtener una lista de los usuarios en el espacio empresarial (por ejemplo, usar Get-CsOnlineUser con los filtros necesarios) y, a continuación, recorra cada uno de estos usuarios para desencadenar la migración de reuniones con Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="160d6-158">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="160d6-159">Para obtener más información, vea [usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="160d6-159">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="160d6-160">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="160d6-160">Related links</span></span>

[<span data-ttu-id="160d6-161">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="160d6-161">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="160d6-162">Configurar la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="160d6-162">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="160d6-163">Mover usuarios entre la implementación local y la nube</span><span class="sxs-lookup"><span data-stu-id="160d6-163">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="160d6-164">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="160d6-164">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="160d6-165">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="160d6-165">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="160d6-166">Usar el servicio de migración de reuniones (MMS)</span><span class="sxs-lookup"><span data-stu-id="160d6-166">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

