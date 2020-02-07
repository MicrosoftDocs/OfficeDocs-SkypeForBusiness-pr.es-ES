---
title: Actualización básica PowerShell | Microsoft Teams | Conceder actualización de directiva de interoperabilidad
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Descontinuación de la actualización a teams si el centro de administración no se ha iluminado en su espacio empresarial
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
ms.openlocfilehash: 20864b6b0a4be8cf9a0a88c6f3ce63c18687f2af
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837240"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="b071f-103">Actualización de los usuarios de Skype empresarial online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b071f-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="b071f-104">Los comandos que se describen en este artículo están diseñados para usarse como parte de la actualización de la lista de comprobación [básica](https://aka.ms/UpgradeBasic) .</span><span class="sxs-lookup"><span data-stu-id="b071f-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="b071f-105">Los aspectos técnicos de la migración de su actualización implican notificar a los usuarios que Skype empresarial se va a actualizar a teams y, a continuación, moverlos a un modo de **solo equipos** .</span><span class="sxs-lookup"><span data-stu-id="b071f-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="b071f-106">Estos pasos se pueden realizar mediante una sesión de Windows PowerShell remota de Skype empresarial o a través del centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b071f-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="b071f-107">Estamos implementando de forma activa las herramientas de actualización en el [centro de administración de Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)y debería estar disponible muy pronto en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="b071f-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="b071f-108">Tan pronto como esté disponible, puede encontrar información sobre cómo migrar los usuarios con [la configuración de la coexistencia y la actualización](https://aka.ms/SkypeToTeams-SetCoexistence)de la configuración.</span><span class="sxs-lookup"><span data-stu-id="b071f-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="b071f-109">Si está listo para actualizar hoy, puede usar los comandos de [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b071f-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="b071f-110">Paso básico de actualización #</span><span class="sxs-lookup"><span data-stu-id="b071f-110">Upgrade Basic step #</span></span> | <span data-ttu-id="b071f-111">Modo</span><span class="sxs-lookup"><span data-stu-id="b071f-111">Mode</span></span> | <span data-ttu-id="b071f-112">Comando de PowerShell</span><span class="sxs-lookup"><span data-stu-id="b071f-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="b071f-113">5</span><span class="sxs-lookup"><span data-stu-id="b071f-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="b071f-114">Islas + notificar al usuario de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="b071f-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="b071f-115">(Use este comando si los usuarios están actualmente en modo **islas** (predeterminado))</span><span class="sxs-lookup"><span data-stu-id="b071f-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="b071f-116">*(por ejemplo, $SipAddress = ' TestUser@contoso.com ')*</span><span class="sxs-lookup"><span data-stu-id="b071f-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="b071f-117">5</span><span class="sxs-lookup"><span data-stu-id="b071f-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="b071f-118">Solo para Skype empresarial + notificar al usuario de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="b071f-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="b071f-119">(Use este comando si los usuarios se encuentran actualmente en modo de **solo Skype para empresas** ).</span><span class="sxs-lookup"><span data-stu-id="b071f-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="b071f-120">7</span><span class="sxs-lookup"><span data-stu-id="b071f-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="b071f-121">Solo equipos</span><span class="sxs-lookup"><span data-stu-id="b071f-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
