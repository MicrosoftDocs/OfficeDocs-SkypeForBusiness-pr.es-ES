---
title: Actualización básica de PowerShell| Microsoft Teams| Conceder directiva de interoperabilidad de actualización
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre un stopgap para actualizar a Microsoft Teams si el Centro de administración no se ha iluminado en su inquilino.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef164ee5d93cb5491923ef3b319ae51134924cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120550"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="e29c9-103">Actualizar los usuarios de Skype Empresarial Online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e29c9-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="e29c9-104">Los comandos descritos en este artículo están diseñados para usarse como parte de la lista de comprobación [Actualizar básico.](./upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="e29c9-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](./upgrade-start-here.md) checklist.</span></span>

<span data-ttu-id="e29c9-105">Los aspectos de migración técnica de la actualización implican notificar a los usuarios que Skype Empresarial actualizará a Teams y, después, los trasladará a un modo **solo de Teams.**</span><span class="sxs-lookup"><span data-stu-id="e29c9-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="e29c9-106">Estos pasos se pueden realizar a través de una sesión remota de Skype Empresarial Windows PowerShell sesión o a través del Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e29c9-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="e29c9-107">Estamos implementando activamente las herramientas de actualización en el Centro de administración de [Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)y debería estar disponible próximamente en su inquilino.</span><span class="sxs-lookup"><span data-stu-id="e29c9-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="e29c9-108">Tan pronto como esté disponible, encontrará información sobre cómo migrar los usuarios en Establecer la configuración de [coexistencia y actualización.](./setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e29c9-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="e29c9-109">Si está listo para actualizar hoy, puede usar los comandos [de PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) enumerados en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e29c9-109">If you're ready to upgrade today, you can use the [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="e29c9-110">Paso Básico de actualización #</span><span class="sxs-lookup"><span data-stu-id="e29c9-110">Upgrade Basic step #</span></span> | <span data-ttu-id="e29c9-111">Modo</span><span class="sxs-lookup"><span data-stu-id="e29c9-111">Mode</span></span> | <span data-ttu-id="e29c9-112">Comando de PowerShell</span><span class="sxs-lookup"><span data-stu-id="e29c9-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="e29c9-113">5</span><span class="sxs-lookup"><span data-stu-id="e29c9-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="e29c9-114">Islas + Notificar al usuario de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e29c9-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="e29c9-115">(Use este comando si los usuarios están actualmente en **modo Islas** (predeterminado))</span><span class="sxs-lookup"><span data-stu-id="e29c9-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="e29c9-116">*(por ejemplo, $SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="e29c9-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="e29c9-117">5</span><span class="sxs-lookup"><span data-stu-id="e29c9-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="e29c9-118">Skype Empresarial Solo + Notificar al usuario de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e29c9-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="e29c9-119">(Use este comando si los usuarios están actualmente en el **modo solo para Skype** Empresarial)</span><span class="sxs-lookup"><span data-stu-id="e29c9-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="e29c9-120">7</span><span class="sxs-lookup"><span data-stu-id="e29c9-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="e29c9-121">Solo en Teams</span><span class="sxs-lookup"><span data-stu-id="e29c9-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |