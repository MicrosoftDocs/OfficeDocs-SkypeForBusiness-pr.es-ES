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
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533597"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="ce49c-103">Consideraciones de actualización para organizaciones con Skype Empresarial Server local &mdash; para administradores de TI</span><span class="sxs-lookup"><span data-stu-id="ce49c-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="ce49c-104">En este artículo se describen consideraciones adicionales para las organizaciones con Skype Empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="ce49c-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="ce49c-105">Este artículo es el cuarto de varios que describen los conceptos de actualización y la implementación para los administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="ce49c-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="ce49c-106">Información general</span><span class="sxs-lookup"><span data-stu-id="ce49c-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="ce49c-107">Métodos de actualización</span><span class="sxs-lookup"><span data-stu-id="ce49c-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="ce49c-108">Herramientas para administrar la actualización</span><span class="sxs-lookup"><span data-stu-id="ce49c-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="ce49c-109">**Consideraciones adicionales para las organizaciones con Skype Empresarial local** (este artículo)</span><span class="sxs-lookup"><span data-stu-id="ce49c-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="ce49c-110">Implementación de la actualización</span><span class="sxs-lookup"><span data-stu-id="ce49c-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="ce49c-111">Consideraciones de la red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="ce49c-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="ce49c-112">Además, en los artículos siguientes se describen conceptos importantes de actualización y comportamientos de coexistencia:</span><span class="sxs-lookup"><span data-stu-id="ce49c-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="ce49c-113">Coexistencia de Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="ce49c-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="ce49c-114">Modos de coexistencia - Referencia</span><span class="sxs-lookup"><span data-stu-id="ce49c-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="ce49c-115">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="ce49c-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="ce49c-116">Consideraciones para las organizaciones con Skype Empresarial Server local</span><span class="sxs-lookup"><span data-stu-id="ce49c-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="ce49c-117">Configurar la implementación híbrida de Skype Empresarial es un requisito previo para migrar al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ce49c-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="ce49c-118">Aunque es posible usar Teams en modo de islas sin híbrido, no se puede realizar la transición al modo TeamsOnly hasta que el usuario se mueve de Skype Empresarial local a Skype Empresarial Online (mediante [Move-CsUser).](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="ce49c-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="ce49c-119">Para obtener más información, vea [Configurar conectividad híbrida.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="ce49c-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="ce49c-120">Si su organización tiene Skype Empresarial Server y no ha configurado la conectividad híbrida, pero desea seguir utilizando Teams, para administrar la funcionalidad de Teams, debe usar una cuenta administrativa que tenga un dominio .onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="ce49c-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="ce49c-121">Los usuarios de Teams que tienen una cuenta de Skype Empresarial local (es decir, aún no se han movido a la nube mediante Move-CsUser) no pueden interactuar con ningún usuario de Skype Empresarial, ni pueden federar con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="ce49c-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="ce49c-122">Esta funcionalidad solo está disponible una vez que los usuarios se mueven a la nube (ya sea en modo islas o como usuarios de TeamsOnly).</span><span class="sxs-lookup"><span data-stu-id="ce49c-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="ce49c-123">Si tiene usuarios con cuentas de Skype Empresarial locales, no puede asignar el modo TeamsOnly en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="ce49c-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="ce49c-124">Primero debe mover todos los usuarios con cuentas locales de Skype Empresarial a la nube y, después, deshabilitar la implementación híbrida para completar la `Move-CsUser` [migración a la nube.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)</span><span class="sxs-lookup"><span data-stu-id="ce49c-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="ce49c-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` no funcionará en el nivel de inquilino si se detecta un registro DNS de lyncdiscover que apunta a una ubicación que no sea Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce49c-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="ce49c-126">Debe asegurarse de que los usuarios están sincronizados correctamente en Azure AD con los atributos correctos de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ce49c-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="ce49c-127">Estos atributos son todos prefijos con "msRTCSIP-".</span><span class="sxs-lookup"><span data-stu-id="ce49c-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="ce49c-128">Si los usuarios no están sincronizados correctamente con Azure AD, las herramientas de administración de Teams no podrán administrarlos.</span><span class="sxs-lookup"><span data-stu-id="ce49c-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="ce49c-129">(Por ejemplo, no podrá asignar directivas de Teams a los usuarios locales a menos que sincronice correctamente estos atributos). Para obtener más información, [consulte Configurar Azure AD Connect para Teams y Skype Empresarial.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)</span><span class="sxs-lookup"><span data-stu-id="ce49c-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="ce49c-130">Para crear un nuevo usuario de TeamsOnly o Skype Empresarial Online en una organización híbrida, primero debe habilitar el usuario en Skype Empresarial *Server* local y, a continuación, mover el usuario de local a la nube mediante Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="ce49c-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="ce49c-131">Al crear el usuario local, primero se garantiza que el resto de usuarios locales de Skype Empresarial puedan enrutar al usuario recién creado.</span><span class="sxs-lookup"><span data-stu-id="ce49c-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="ce49c-132">Una vez que todos los usuarios se han movido en línea, ya no es necesario habilitar primero los usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="ce49c-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="ce49c-133">Cuando se mueve un usuario de un sitio a la nube, las reuniones organizadas por ese usuario se migran a Skype Empresarial Online o Teams, dependiendo de si se especifica el modificador -MoveToTeams.</span><span class="sxs-lookup"><span data-stu-id="ce49c-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="ce49c-134">Si desea mostrar las notificaciones en el cliente de Skype Empresarial para los usuarios locales, debe usar TeamsUpgradePolicy en el conjunto de herramientas local.</span><span class="sxs-lookup"><span data-stu-id="ce49c-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="ce49c-135">Solo el parámetro NotifySfbUsers es relevante para los usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="ce49c-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="ce49c-136">Los usuarios locales reciben su modo de las instancias en línea de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="ce49c-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="ce49c-137">Vea las notas en [Grant-CsTeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ce49c-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="ce49c-138">Los nuevos inquilinos creados después del 3 de septiembre de 2019 se crean como inquilinos de TeamsOnly a menos que la organización ya tenga una implementación local de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ce49c-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="ce49c-139">Microsoft usa los registros DNS para identificar las organizaciones locales de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ce49c-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="ce49c-140">Si su organización tiene Skype Empresarial Server local sin entradas DNS públicas, deberá llamar al soporte técnico de Microsoft para que su nuevo inquilino se haya degradado.</span><span class="sxs-lookup"><span data-stu-id="ce49c-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="ce49c-141">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="ce49c-141">Related links</span></span>

[<span data-ttu-id="ce49c-142">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="ce49c-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="ce49c-143">Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="ce49c-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="ce49c-144">Mover usuarios entre la implementación local y la nube</span><span class="sxs-lookup"><span data-stu-id="ce49c-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="ce49c-145">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="ce49c-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="ce49c-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="ce49c-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="ce49c-147">Usar el servicio de migración de reuniones (MMS)</span><span class="sxs-lookup"><span data-stu-id="ce49c-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

