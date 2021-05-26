---
title: Actualizaciones asistidos | Skype Business Online para Teams actualización
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Información general sobre las actualizaciones asistidos de Skype Empresarial Online a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2e445fd6c5d26a64005ff1c285d8e9d843ca0211
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656063"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="81939-103">Actualizaciones asistidos de Skype Empresarial Online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81939-103">Assisted upgrades from Skype for Business Online to Microsoft Teams</span></span>

<span data-ttu-id="81939-104">Microsoft ofrece actualizaciones asistidos a Teams ayudar a las organizaciones a realizar una transición correcta desde Skype Empresarial Online cuando el servicio se retire el 31 de julio de 2021.</span><span class="sxs-lookup"><span data-stu-id="81939-104">Microsoft offers assisted upgrades to Teams to help organizations make a successful transition from Skype for Business Online as the service retires July 31, 2021.</span></span> <span data-ttu-id="81939-105">Tanto si su organización está actualizando desde un entorno *Skype Empresarial Online* o *Skype Empresarial Online* con entorno híbrido (usuarios en Skype Empresarial **Online** y Skype Empresarial Server), las actualizaciones asistidos reducen el número de tareas técnicas que necesita realizar y permiten centrarse más en la preparación de la organización, el conocimiento de los usuarios y el aprendizaje Teams.</span><span class="sxs-lookup"><span data-stu-id="81939-105">Whether your organization is upgrading from a *Skype for Business Online* or *Skype for Business Online with hybrid* (users in both Skype for Business Online **and** Skype for Business Server) environment, assisted upgrades reduce the number of technical tasks you need to do and allow for greater focus on organizational preparedness, user awareness, and Teams training.</span></span>

<span data-ttu-id="81939-106">Le recomendamos que revise nuestras instrucciones [de actualización antes](https://aka.ms/SkypeToTeams) de la actualización.</span><span class="sxs-lookup"><span data-stu-id="81939-106">We recommend that you review our [upgrade guidance](https://aka.ms/SkypeToTeams) before your upgrade.</span></span> <span data-ttu-id="81939-107">Nuestras instrucciones de actualización incluyen actividades recomendadas y recursos útiles para completar una actualización de Skype Empresarial Online a Teams.</span><span class="sxs-lookup"><span data-stu-id="81939-107">Our upgrade guidance includes recommended activities and helpful resources for completing an upgrade from Skype for Business Online to Teams.</span></span> <span data-ttu-id="81939-108">Esta guía se aplica a cualquier organización que planee una actualización a Teams, ya sea que administren todos los aspectos de la actualización o usen el proceso asistido.</span><span class="sxs-lookup"><span data-stu-id="81939-108">This guidance applies to any organization planning an upgrade to Teams, whether they manage all aspects of the upgrade or use the assisted process.</span></span>

> [!NOTE]
> <span data-ttu-id="81939-109">Si está programado para que una actualización asistido Teams, puede realizar su propia actualización desde Skype Empresarial Online antes de la fecha de actualización programada.</span><span class="sxs-lookup"><span data-stu-id="81939-109">If you're scheduled for an assisted upgrade to Teams, you can perform your own upgrade from Skype for Business Online before your scheduled upgrade date.</span></span> <span data-ttu-id="81939-110">Para obtener más información sobre cómo actualizar manualmente a Teams, consulte nuestras instrucciones [de actualización.](https://aka.ms/SkypeToTeams)</span><span class="sxs-lookup"><span data-stu-id="81939-110">For more information about how to manually upgrade to Teams, see our [upgrade guidance](https://aka.ms/SkypeToTeams).</span></span>
>
> <span data-ttu-id="81939-111">Las actualizaciones asistidos no están disponibles para implementaciones locales de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="81939-111">Assisted upgrades are not available for on-premises deployments of Skype for Business Server.</span></span>

## <a name="notifications-for-scheduled-customers"></a><span data-ttu-id="81939-112">Notificaciones para clientes programados</span><span class="sxs-lookup"><span data-stu-id="81939-112">Notifications for scheduled customers</span></span>

<span data-ttu-id="81939-113">Skype Empresarial Los clientes en línea que están programados para las actualizaciones asistidos Teams recibirán una serie de notificaciones de actualización.</span><span class="sxs-lookup"><span data-stu-id="81939-113">Skype for Business Online customers that are scheduled for assisted upgrades to Teams will receive a series of upgrade notifications.</span></span> <span data-ttu-id="81939-114">Estas notificaciones comenzarán 90 días antes de la fecha de actualización programada.</span><span class="sxs-lookup"><span data-stu-id="81939-114">These notifications will begin 90 days before the scheduled upgrade date.</span></span> <span data-ttu-id="81939-115">Estas notificaciones se entregarán como publicaciones de *Plan de* cambio en el Centro de mensajes de Microsoft 365, notificaciones de panel de actualización en el centro de administración de Teams y marcas desde la aplicación a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="81939-115">These notifications will be delivered as *Plan for Change* posts in the Microsoft 365 Message Center, upgrade dashboard notifications in Teams admin center, and in-app flags to end users.</span></span>

<span data-ttu-id="81939-116">Las notificaciones de actualización incluirán la fecha programada de la actualización asistida y se vincularán a recursos de actualización y aprendizaje para ayudar a impulsar la adopción y el uso de Teams.</span><span class="sxs-lookup"><span data-stu-id="81939-116">Upgrade notifications will include the scheduled date of the assisted upgrade, and will link to upgrade resources and training to help drive adoption and usage of Teams.</span></span>

## <a name="the-assisted-upgrade-experience"></a><span data-ttu-id="81939-117">La experiencia de actualización asistida</span><span class="sxs-lookup"><span data-stu-id="81939-117">The assisted upgrade experience</span></span>

<span data-ttu-id="81939-118">Las actualizaciones asistidos comenzarán en agosto de 2021 con fechas específicas del inquilino compartidas en las notificaciones de programación mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="81939-118">Assisted upgrades will begin in August 2021 with tenant-specific dates shared in the scheduling notifications mentioned above.</span></span>

<span data-ttu-id="81939-119">La experiencia de actualización asistido variará ligeramente dependiendo de si tiene un Skype Empresarial solo en línea o un Skype Empresarial Online con entorno híbrido:</span><span class="sxs-lookup"><span data-stu-id="81939-119">Your assisted upgrade experience will differ slightly depending on whether you have a Skype for Business Online-only or a Skype for Business Online with hybrid environment:</span></span>

- <span data-ttu-id="81939-120">**Skype Empresarial solo en línea** El proceso de actualización asistida aplicará la `TeamsUpgradeOverridePolicy` directiva a su organización.</span><span class="sxs-lookup"><span data-stu-id="81939-120">**Skype for Business Online-only** The assisted upgrade process will apply the `TeamsUpgradeOverridePolicy` policy to your organization.</span></span> <span data-ttu-id="81939-121">Cuando se aplique esta directiva, todos los usuarios Skype Empresarial online se colocarán en Teams solo.</span><span class="sxs-lookup"><span data-stu-id="81939-121">When this policy is applied, all your Skype for Business Online users will be placed in Teams Only mode.</span></span>
- <span data-ttu-id="81939-122">**Skype Empresarial Online con híbrido** Los entornos híbridos pueden tener usuarios que están en una de las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="81939-122">**Skype for Business Online with hybrid** Hybrid environments may have users that fall into one of the following categories:</span></span>

  - <span data-ttu-id="81939-123">Los usuarios locales se alocuban en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="81939-123">On-premises users homed on Skype for Business Server</span></span>
  - <span data-ttu-id="81939-124">Skype Empresarial Usuarios en línea que están en Teams modo solo para usuarios</span><span class="sxs-lookup"><span data-stu-id="81939-124">Skype for Business Online users that are in Teams Only mode</span></span>
  - <span data-ttu-id="81939-125">Skype Empresarial Usuarios en línea que **no están** en Teams modo Solo para usuarios</span><span class="sxs-lookup"><span data-stu-id="81939-125">Skype for Business Online users that are **not** in Teams Only mode</span></span>

  <span data-ttu-id="81939-126">Si tiene una combinación de usuarios en cada una de las categorías enumeradas anteriormente, el proceso de actualización asistida solo cambiará Skype Empresarial los usuarios en línea Teams modo solo si aún no están en ese modo.</span><span class="sxs-lookup"><span data-stu-id="81939-126">If you have a mixture of users in each of the categories listed above, the assisted upgrade process will only switch Skype for Business Online users to Teams Only mode if they're not already in that mode.</span></span> <span data-ttu-id="81939-127">Los usuarios Skype Empresarial local no se verán afectados por el proceso de actualización asistida.</span><span class="sxs-lookup"><span data-stu-id="81939-127">On-premises Skype for Business users won't be impacted by the assisted upgrade process.</span></span>

> [!NOTE]
> <span data-ttu-id="81939-128">No se preocupe si la actualización asistido está programada para una fecha posterior al 31 de julio de 2021.</span><span class="sxs-lookup"><span data-stu-id="81939-128">Don't worry if your assisted upgrade is scheduled for a date after July 31, 2021.</span></span> <span data-ttu-id="81939-129">Su organización podrá usar Skype Empresarial Online hasta que se complete la actualización.</span><span class="sxs-lookup"><span data-stu-id="81939-129">Your organization will be able to use Skype for Business Online until your upgrade is complete.</span></span>

<span data-ttu-id="81939-130">La duración de la actualización variará según el volumen de usuarios y las características de la implementación.</span><span class="sxs-lookup"><span data-stu-id="81939-130">The duration of the upgrade will vary by volume of users and the characteristics of the deployment.</span></span> <span data-ttu-id="81939-131">En la mayoría de los casos, los usuarios de un espacio empresarial se actualizarán dentro de las 24 horas siguientes al inicio de la actualización.</span><span class="sxs-lookup"><span data-stu-id="81939-131">In most cases, users within a tenant will be upgraded within 24 hours of the start of the upgrade.</span></span> <span data-ttu-id="81939-132">Durante este tiempo, los usuarios finales seguirán teniendo acceso a Skype Empresarial en línea.</span><span class="sxs-lookup"><span data-stu-id="81939-132">During this time, end users will still have access to Skype for Business Online functionality.</span></span> <span data-ttu-id="81939-133">Una vez completada la actualización y los usuarios cerrarán sesión en Skype Empresarial Online, empezarán a usar Teams para mensajería, reuniones y llamadas.</span><span class="sxs-lookup"><span data-stu-id="81939-133">Once the upgrade has completed and users sign out of Skype for Business Online, they'll start using Teams for messaging, meetings, and calling.</span></span>

## <a name="the-post-upgrade-experience"></a><span data-ttu-id="81939-134">La experiencia posterior a la actualización</span><span class="sxs-lookup"><span data-stu-id="81939-134">The post-upgrade experience</span></span>

<span data-ttu-id="81939-135">Cuando se complete la actualización asistido, el modo **de coexistencia** para los usuarios actualizados se establece en Teams solo.</span><span class="sxs-lookup"><span data-stu-id="81939-135">When the assisted upgrade completes, the **Coexistence Mode** for upgraded users is set to Teams Only.</span></span> <span data-ttu-id="81939-136">Le recomendamos que revise las [Teams de modo solo antes](teams-only-mode-considerations.md) de la actualización.</span><span class="sxs-lookup"><span data-stu-id="81939-136">We recommend that you review [Teams Only mode considerations](teams-only-mode-considerations.md) before your upgrade.</span></span> <span data-ttu-id="81939-137">En la tabla siguiente se proporciona información general de alto nivel sobre la Teams solo para el usuario.</span><span class="sxs-lookup"><span data-stu-id="81939-137">The table below provides a high-level overview of the Teams Only user experience.</span></span>

:::row:::
    :::column span="1":::
        <span data-ttu-id="81939-138">**Chat y llamadas**</span><span class="sxs-lookup"><span data-stu-id="81939-138">**Chat and Calling**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="81939-139">Todas las llamadas y chats se inician y se reciben en Teams</span><span class="sxs-lookup"><span data-stu-id="81939-139">All calls and chats are started and received in Teams</span></span>
        - <span data-ttu-id="81939-140">Los usuarios pueden comunicarse (chat o llamada) con cualquier Skype Empresarial usuario</span><span class="sxs-lookup"><span data-stu-id="81939-140">Users can communicate (chat/call) with any Skype for Business user</span></span>
        - <span data-ttu-id="81939-141">Las organizaciones pueden permitir que Teams usuarios se comuniquen con los usuarios del Skype de [consumidores](manage-external-access.md) mediante la administración de permisos de acceso externo</span><span class="sxs-lookup"><span data-stu-id="81939-141">Organizations can enable Teams users to communicate with users of the Skype consumer service by managing [external access permissions](manage-external-access.md)</span></span>
        - <span data-ttu-id="81939-142">Teams usuarios que intentan iniciar sesión en Skype Empresarial Online se redirigen a Teams</span><span class="sxs-lookup"><span data-stu-id="81939-142">Teams users who attempt to sign in to Skype for Business Online are redirected to Teams</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="81939-143">**Reuniones**</span><span class="sxs-lookup"><span data-stu-id="81939-143">**Meetings**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="81939-144">Los usuarios programan todas las reuniones nuevas en Teams (complemento reemplazado)</span><span class="sxs-lookup"><span data-stu-id="81939-144">Users schedule all new meetings in Teams (plugin replaced)</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="81939-145">**Datos migrados**</span><span class="sxs-lookup"><span data-stu-id="81939-145">**Migrated Data**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="81939-146">Contactos existentes desde Skype Empresarial Online, incluidos federados (pero sin listas de distribución)</span><span class="sxs-lookup"><span data-stu-id="81939-146">Existing contacts from Skype for Business Online including federated (but no distribution lists)</span></span>
        - <span data-ttu-id="81939-147">Los contactos se migran cuando los usuarios inician sesión Teams por primera vez.</span><span class="sxs-lookup"><span data-stu-id="81939-147">Contacts are migrated when users log into Teams for the first time.</span></span>
            > [!IMPORTANT]
            ><span data-ttu-id="81939-148">Los contactos deben migrarse dentro de los 90 días posteriores a la finalización de la actualización.</span><span class="sxs-lookup"><span data-stu-id="81939-148">Contacts must be migrated within 90 days of the completion of your upgrade.</span></span>
        - <span data-ttu-id="81939-149">Las Skype Empresarial en línea existentes se convierten en Teams reuniones</span><span class="sxs-lookup"><span data-stu-id="81939-149">Existing Skype for Business Online meetings are converted to Teams meetings</span></span>
            > [!IMPORTANT]
            > <span data-ttu-id="81939-150">Los clientes con configuraciones Skype Empresarial Online necesitan usar el Servicio de migración de reuniones (MMS) para migrar las reuniones Skype Empresarial online existentes a Teams reuniones.</span><span class="sxs-lookup"><span data-stu-id="81939-150">Customers with pure Skype for Business Online configurations need to use the Meeting Migration Service (MMS) to migrate existing Skype for Business Online meetings to Teams meetings.</span></span> <span data-ttu-id="81939-151">Se recomienda usar MMS antes de la fecha de actualización asistida.</span><span class="sxs-lookup"><span data-stu-id="81939-151">We recommend using MMS prior to the assisted upgrade date.</span></span> <span data-ttu-id="81939-152">Para obtener más información sobre MMS, vea [Usar el servicio de migración de reuniones (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="81939-152">For more information about MMS, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span></span>
    :::column-end:::
:::row-end:::

<span data-ttu-id="81939-153">Una vez completada la actualización, las organizaciones con implementaciones híbridas pueden mover usuarios de local a Teams o movidos de Teams a locales.</span><span class="sxs-lookup"><span data-stu-id="81939-153">After your upgrade is complete, organizations with hybrid deployments may move users from on-premises to Teams or moved from Teams to on-premises.</span></span>  

## <a name="related-content"></a><span data-ttu-id="81939-154">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="81939-154">Related content</span></span>

- [<span data-ttu-id="81939-155">Introducción a su actualización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81939-155">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="81939-156">Retirada de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="81939-156">Skype for Business Online retirement</span></span>](skype-for-business-online-retirement.md)
- [<span data-ttu-id="81939-157">Get-CsTeamsUpgradeStatus</span><span class="sxs-lookup"><span data-stu-id="81939-157">Get-CsTeamsUpgradeStatus</span></span>](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [<span data-ttu-id="81939-158">Consideraciones del modo Teams solo</span><span class="sxs-lookup"><span data-stu-id="81939-158">Teams Only mode considerations</span></span>](teams-only-mode-considerations.md)
