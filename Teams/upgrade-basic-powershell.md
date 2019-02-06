---
title: PowerShell actualización básica | Los equipos de Microsoft | Directiva de interoperabilidad de actualización de GRANT
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Provisional para la actualización a los equipos si todavía no iluminada el centro de administración en el inquilino
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f0d76ffb4f2564a09ea3a4418f9baf7e53e8446
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754386"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="8f9cc-103">Actualizar a los usuarios de Skype para empresarial en línea para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8f9cc-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="8f9cc-104">Los comandos que se describen en este artículo están diseñados para usarse como parte de la lista de comprobación [De actualización básica](https://aka.ms/UpgradeBasic) .</span><span class="sxs-lookup"><span data-stu-id="8f9cc-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="8f9cc-105">Los aspectos técnicos de migración de la actualización implican notificar a los usuarios que se actualización a los equipos y, a continuación, moverlos a un modo de **equipos sólo** Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="8f9cc-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="8f9cc-106">Estos pasos pueden realizarse a través de un Skype para la sesión remota de Windows PowerShell de negocio o a través del centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8f9cc-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="8f9cc-107">Nos estamos implantar activamente actualización herramientas en el [Centro de administración de equipos de Microsoft](manage-teams-skypeforbusiness-admin-center.md), y debe estar disponible pronto en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="8f9cc-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="8f9cc-108">Tan pronto como está disponible, puede encontrar información sobre la migración de los usuarios en el [establecimiento de la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="8f9cc-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="8f9cc-109">Si está listo para la actualización de hoy en día, puede usar los comandos de [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) enumerados en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="8f9cc-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="8f9cc-110">Actualización paso básico #</span><span class="sxs-lookup"><span data-stu-id="8f9cc-110">Upgrade Basic step #</span></span> | <span data-ttu-id="8f9cc-111">Modo</span><span class="sxs-lookup"><span data-stu-id="8f9cc-111">Mode</span></span> | <span data-ttu-id="8f9cc-112">Comando de PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f9cc-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="8f9cc-113">5</span><span class="sxs-lookup"><span data-stu-id="8f9cc-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="8f9cc-114">Islas + notificar la Skype para usuarios de empresa</span><span class="sxs-lookup"><span data-stu-id="8f9cc-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="8f9cc-115">(Utilice este comando si los usuarios están actualmente en modo de **Islas** (valor predeterminado))</span><span class="sxs-lookup"><span data-stu-id="8f9cc-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="8f9cc-116">*(por ejemplo, $SipAddress = 'TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="8f9cc-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="8f9cc-117">5</span><span class="sxs-lookup"><span data-stu-id="8f9cc-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="8f9cc-118">Skype para la empresa sólo + notificar la Skype para usuarios de empresa</span><span class="sxs-lookup"><span data-stu-id="8f9cc-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="8f9cc-119">(Utilice este comando si los usuarios están actualmente en modo de **Skype para la empresa sólo** )</span><span class="sxs-lookup"><span data-stu-id="8f9cc-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="8f9cc-120">7</span><span class="sxs-lookup"><span data-stu-id="8f9cc-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="8f9cc-121">Sólo los equipos</span><span class="sxs-lookup"><span data-stu-id="8f9cc-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |