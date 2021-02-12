---
title: 'Actualizar a Teams desde una implementación local de Skype Empresarial: Microsoft Teams'
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Actualización de Skype Empresarial a Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578403"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="bfeb3-103">Actualizar de Skype Empresarial a Teams para &mdash; administradores de TI</span><span class="sxs-lookup"><span data-stu-id="bfeb3-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="bfeb3-104">Información general</span><span class="sxs-lookup"><span data-stu-id="bfeb3-104">Overview</span></span>

<span data-ttu-id="bfeb3-105">Al actualizar de Skype Empresarial a Teams, algunas organizaciones requieren una implementación progresiva que sea planeada y administrada por sus departamentos de TI.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="bfeb3-106">Los artículos de esta sección se aplican principalmente a los administradores de TI de grandes organizaciones.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="bfeb3-107">Normalmente, estas organizaciones son locales, pero también pueden ser grandes organizaciones de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="bfeb3-108">Antes de leer estos artículos, asegúrese de leer [Introducción a](upgrade-start-here.md) la actualización de Teams y al marco de trabajo de [actualización.](upgrade-framework.md)</span><span class="sxs-lookup"><span data-stu-id="bfeb3-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="bfeb3-109">En los artículos siguientes se le guiará por el proceso de actualización para su organización:</span><span class="sxs-lookup"><span data-stu-id="bfeb3-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="bfeb3-110">Métodos de actualización</span><span class="sxs-lookup"><span data-stu-id="bfeb3-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="bfeb3-111">Herramientas para administrar la actualización</span><span class="sxs-lookup"><span data-stu-id="bfeb3-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="bfeb3-112">Consideraciones adicionales para las organizaciones con Skype Empresarial local</span><span class="sxs-lookup"><span data-stu-id="bfeb3-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="bfeb3-113">Implementar la actualización</span><span class="sxs-lookup"><span data-stu-id="bfeb3-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="bfeb3-114">Consideraciones de la red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="bfeb3-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="bfeb3-115">Además, en los artículos siguientes se describen conceptos importantes de actualización y comportamientos de coexistencia:</span><span class="sxs-lookup"><span data-stu-id="bfeb3-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="bfeb3-116">Coexistencia de Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="bfeb3-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="bfeb3-117">Modos de coexistencia - Referencia</span><span class="sxs-lookup"><span data-stu-id="bfeb3-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="bfeb3-118">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="bfeb3-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="bfeb3-119">En estos artículos se usan los términos Skype Empresarial Online, Skype Empresarial Server local y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="bfeb3-120">El último término hace referencia a las versiones en línea y local.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="bfeb3-121">Antes de empezar, tenga en cuenta que un usuario que se ha migrado a Teams ya no usa un cliente de Skype Empresarial, excepto para unirse a una reunión hospedada en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="bfeb3-122">Todos los chats y llamadas pasan al cliente de Teams del usuario, independientemente de si el remitente utiliza Teams o Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="bfeb3-123">Las nuevas reuniones organizadas por el usuario migrado se programarán como reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="bfeb3-124">Si el usuario intenta usar el cliente de Skype Empresarial, se bloquea el inicio de chats y llamadas.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="bfeb3-125">Sin embargo, el usuario puede (y debe) seguir utilizando el cliente de Skype Empresarial para unirse a las reuniones de Skype Empresarial a las que está invitado.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="bfeb3-126">(Los clientes antiguos de Skype Empresarial que se enviaron antes de 2017 no respetan TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="bfeb3-127">Asegúrese de que está usando el cliente más reciente de Skype Empresarial).</span><span class="sxs-lookup"><span data-stu-id="bfeb3-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="bfeb3-128">Usted administra la transición de los usuarios a Teams usando el concepto de [modo,](migration-interop-guidance-for-teams-with-skype.md)que es una propiedad de [TeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="bfeb3-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="bfeb3-129">Un usuario que se ha migrado a Teams como se describe anteriormente se encuentra en el modo "TeamsOnly".</span><span class="sxs-lookup"><span data-stu-id="bfeb3-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="bfeb3-130">En el caso de una organización que va a migrar a Teams, el objetivo final es pasar a todos los usuarios al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

>[!NOTE]
><span data-ttu-id="bfeb3-131">Los usuarios que tienen una cuenta de Skype Empresarial local no pueden ser TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-131">Users who have a Skype for Business on-premises account cannot be TeamsOnly.</span></span> <span data-ttu-id="bfeb3-132">Aunque estos usuarios pueden [usar Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)en modo Islas, esto no proporciona el conjunto completo de funciones de Teams que están disponibles en el modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-132">Although these users can [use Teams in Islands mode](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), this does not provide the full set of Teams functionality that is available in TeamsOnly mode.</span></span> <span data-ttu-id="bfeb3-133">Para que estos usuarios se puedan usar TeamsOnly, deben moverse a la nube con las herramientas locales `Move-CsUser` de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-133">To make these users TeamsOnly, they must be moved to the cloud using `Move-CsUser` in the on-premises Skype for Business Server tools.</span></span>

<span data-ttu-id="bfeb3-134">De acuerdo.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-134">OK.</span></span> <span data-ttu-id="bfeb3-135">Empecemos.</span><span class="sxs-lookup"><span data-stu-id="bfeb3-135">Let's get started.</span></span>  <span data-ttu-id="bfeb3-136">El primer paso es conocer los [métodos de actualización disponibles.](upgrade-to-teams-on-prem-upgrade-methods.md)</span><span class="sxs-lookup"><span data-stu-id="bfeb3-136">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="bfeb3-137">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="bfeb3-137">Related links</span></span>

[<span data-ttu-id="bfeb3-138">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="bfeb3-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="bfeb3-139">Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="bfeb3-139">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="bfeb3-140">Mover usuarios entre la implementación local y la nube</span><span class="sxs-lookup"><span data-stu-id="bfeb3-140">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="bfeb3-141">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="bfeb3-141">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="bfeb3-142">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="bfeb3-142">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="bfeb3-143">Usar el servicio de migración de reuniones (MMS)</span><span class="sxs-lookup"><span data-stu-id="bfeb3-143">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

