---
title: Actualización de los comandos de PowerShell básica - Microsoft Teams
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Provisional para la actualización a los equipos si todavía no iluminada el centro de administración en el inquilino
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf44cbca9c6836c462802293f37ef6b916566520
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860586"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="e7dc7-103">Actualizar a los usuarios de Skype para empresarial en línea para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e7dc7-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="e7dc7-104">Los comandos que se describen en este artículo están diseñados para usarse como parte de la lista de comprobación [De actualización básica](https://aka.ms/UpgradeBasic) .</span><span class="sxs-lookup"><span data-stu-id="e7dc7-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="e7dc7-105">Los aspectos técnicos de migración de la actualización implican notificar a los usuarios que se actualización a los equipos y, a continuación, moverlos a un modo de **equipos sólo** Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="e7dc7-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="e7dc7-106">Estos pasos pueden realizarse a través de un Skype para la sesión remota de Windows PowerShell de negocio o a través de la Microsoft Teams & Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="e7dc7-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams & Skype for Business Admin Center.</span></span> 
 
<span data-ttu-id="e7dc7-107">Nos estamos implantar activamente en [los equipos de Microsoft & Skype para el centro de administración de negocio](manage-teams-skypeforbusiness-admin-center.md)de herramientas de actualización y debe estar disponible pronto en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="e7dc7-107">We're actively rolling out upgrade tooling in the [Microsoft Teams & Skype for Business Admin Center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="e7dc7-108">Tan pronto como está disponible, puede encontrar información sobre la migración de los usuarios en el [establecimiento de la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="e7dc7-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span> 
 
<span data-ttu-id="e7dc7-109">Si está listo para la actualización de hoy en día, puede usar los comandos de [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) enumerados en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="e7dc7-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span> 
 
 |<span data-ttu-id="e7dc7-110">Actualización paso básico #</span><span class="sxs-lookup"><span data-stu-id="e7dc7-110">Upgrade Basic step #</span></span> | <span data-ttu-id="e7dc7-111">Modo</span><span class="sxs-lookup"><span data-stu-id="e7dc7-111">Mode</span></span> | <span data-ttu-id="e7dc7-112">Comando de PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7dc7-112">PowerShell command</span></span> |
|-------|--------|------|
| [<span data-ttu-id="e7dc7-113">5</span><span class="sxs-lookup"><span data-stu-id="e7dc7-113">5</span></span>](upgrade-basic.md#step-5) |<span data-ttu-id="e7dc7-114">Islas + notificar la Skype para usuarios de empresa</span><span class="sxs-lookup"><span data-stu-id="e7dc7-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="e7dc7-115">(Utilice este comando si los usuarios están actualmente en modo de **Islas** (valor predeterminado))</span><span class="sxs-lookup"><span data-stu-id="e7dc7-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="e7dc7-116">_(por ejemplo, $SipAddress = 'TestUser@contoso.com')_</span><span class="sxs-lookup"><span data-stu-id="e7dc7-116">_(for example, $SipAddress='TestUser@contoso.com')_</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="e7dc7-117">5</span><span class="sxs-lookup"><span data-stu-id="e7dc7-117">5</span></span>](upgrade-basic.md#step-5)  | <span data-ttu-id="e7dc7-118">Skype para la empresa sólo + notificar la Skype para usuarios de empresa</span><span class="sxs-lookup"><span data-stu-id="e7dc7-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="e7dc7-119">(Utilice este comando si los usuarios están actualmente en modo de **Skype para la empresa sólo** )</span><span class="sxs-lookup"><span data-stu-id="e7dc7-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="e7dc7-120">7</span><span class="sxs-lookup"><span data-stu-id="e7dc7-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="e7dc7-121">Sólo los equipos</span><span class="sxs-lookup"><span data-stu-id="e7dc7-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |


