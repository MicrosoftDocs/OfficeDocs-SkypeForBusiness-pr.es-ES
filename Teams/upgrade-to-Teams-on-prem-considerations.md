---
title: Actualizar a teams desde una implementación local de Skype empresarial-Microsoft Teams
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
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="1c3a5-103">Consideraciones de actualización para organizaciones con Skype empresarial Server local &mdash; para administradores de ti</span><span class="sxs-lookup"><span data-stu-id="1c3a5-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="1c3a5-104">En este artículo se describen algunas consideraciones adicionales para las organizaciones con Skype empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="1c3a5-105">Este artículo es el cuarto de varios que describen los conceptos de actualización y la implementación para administradores de ti.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="1c3a5-106">Información general</span><span class="sxs-lookup"><span data-stu-id="1c3a5-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="1c3a5-107">Métodos de actualización</span><span class="sxs-lookup"><span data-stu-id="1c3a5-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="1c3a5-108">Herramientas para administrar la actualización</span><span class="sxs-lookup"><span data-stu-id="1c3a5-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="1c3a5-109">**Consideraciones adicionales para las organizaciones con Skype empresarial local** (este artículo)</span><span class="sxs-lookup"><span data-stu-id="1c3a5-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="1c3a5-110">Implementación de la actualización</span><span class="sxs-lookup"><span data-stu-id="1c3a5-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="1c3a5-111">Consideraciones sobre la red telefónica pública conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="1c3a5-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="1c3a5-112">Además, los artículos siguientes describen los conceptos de actualización importantes y los comportamientos de coexistencia:</span><span class="sxs-lookup"><span data-stu-id="1c3a5-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="1c3a5-113">Coexistencia de Teams y Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="1c3a5-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="1c3a5-114">Modos de coexistencia: referencia</span><span class="sxs-lookup"><span data-stu-id="1c3a5-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="1c3a5-115">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="1c3a5-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="1c3a5-116">Consideraciones para las organizaciones con Skype empresarial Server local</span><span class="sxs-lookup"><span data-stu-id="1c3a5-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="1c3a5-117">La configuración del entorno híbrido de Skype empresarial es un requisito previo para migrar al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="1c3a5-118">Aunque es posible usar equipos en el modo islas sin entornos híbridos, no se puede realizar la transición al modo TeamsOnly hasta que el usuario pase de Skype empresarial local a Skype empresarial online (mediante [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span><span class="sxs-lookup"><span data-stu-id="1c3a5-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="1c3a5-119">Para obtener más información, vea [configurar la conectividad híbrida](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="1c3a5-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="1c3a5-120">Si su organización tiene Skype empresarial Server y no ha configurado la conectividad híbrida, pero aún desea usar Teams para administrar la funcionalidad de Teams, debe usar una cuenta administrativa que tenga un dominio. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="1c3a5-121">Los usuarios de equipos que tienen una cuenta de Skype empresarial local (es decir, que aún no se han movido a la nube mediante Move-CsUser) no pueden interoperar con ningún usuario de Skype empresarial ni pueden federarse a usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="1c3a5-122">Esta función solo está disponible cuando los usuarios se mueven a la nube (ya sea en modo islas o como usuarios de TeamsOnly).</span><span class="sxs-lookup"><span data-stu-id="1c3a5-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="1c3a5-123">Si tiene usuarios con cuentas de Skype empresarial en local, no puede asignar el modo TeamsOnly en el nivel de espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="1c3a5-124">Primero debe mover a la nube todos los usuarios que tengan cuentas locales de Skype empresarial `Move-CsUser` y, a continuación, [deshabilitar la implementación híbrida para completar la migración a la nube](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span><span class="sxs-lookup"><span data-stu-id="1c3a5-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="1c3a5-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` no funcionará en el nivel de inquilino si se detecta un registro DNS lyncdiscover que señala a una ubicación distinta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="1c3a5-126">Debe asegurarse de que los usuarios estén sincronizados correctamente en Azure AD con los atributos correctos de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="1c3a5-127">Estos atributos son todos los prefijos con "msRTCSIP-".</span><span class="sxs-lookup"><span data-stu-id="1c3a5-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="1c3a5-128">Si los usuarios no se sincronizan correctamente con Azure AD, las herramientas de administración de Teams no podrán administrar estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="1c3a5-129">(Por ejemplo, no podrá asignar directivas de Teams a usuarios locales, a menos que esté sincronizando estos atributos correctamente). Para obtener más información, vea [configurar Azure ad Connect para Teams y Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="1c3a5-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="1c3a5-130">Para crear un nuevo usuario de TeamsOnly o de Skype empresarial online en una organización híbrida, *primero debe habilitar el usuario en Skype empresarial Server local*y, después, mover el usuario de local a la nube con Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="1c3a5-131">La creación del usuario en local primero garantiza que todos los demás usuarios locales de Skype empresarial podrán enrutar al usuario recién creado.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="1c3a5-132">Una vez que todos los usuarios se han movido a Internet, ya no es necesario que habilite primero los usuarios en local.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="1c3a5-133">Cuando un usuario se mueve de local a la nube, las reuniones organizadas por ese usuario se migran a Skype empresarial online o Teams, en función de si se especifica o no el modificador-MoveToTeams.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="1c3a5-134">Si desea mostrar las notificaciones en el cliente de Skype empresarial para los usuarios locales, debe usar TeamsUpgradePolicy en el conjunto de herramientas local.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="1c3a5-135">Solo el parámetro NotifySfbUsers es relevante para los usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="1c3a5-136">Los usuarios locales obtienen su modo de las instancias en línea de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="1c3a5-137">Consulte las notas en [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1c3a5-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="1c3a5-138">Los nuevos inquilinos creados después del 3 de septiembre de 2019 se crean como inquilinos de TeamsOnly, a menos que la organización ya tenga una implementación local de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="1c3a5-139">Microsoft usa los registros DNS para identificar las organizaciones locales de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="1c3a5-140">Si su organización tiene Skype empresarial Server local sin entradas DNS públicas, tendrá que llamar al servicio de soporte técnico de Microsoft para descalificar el nuevo inquilino.</span><span class="sxs-lookup"><span data-stu-id="1c3a5-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="1c3a5-141">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="1c3a5-141">Related links</span></span>

[<span data-ttu-id="1c3a5-142">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="1c3a5-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="1c3a5-143">Configurar la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="1c3a5-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="1c3a5-144">Mover usuarios entre la implementación local y la nube</span><span class="sxs-lookup"><span data-stu-id="1c3a5-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="1c3a5-145">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="1c3a5-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="1c3a5-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="1c3a5-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="1c3a5-147">Usar el servicio de migración de reuniones (MMS)</span><span class="sxs-lookup"><span data-stu-id="1c3a5-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

