---
title: Usar PowerShell para controlar el acceso de invitado a un equipo
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Use PowerShell para permitir el acceso de invitado a los equipos de Microsoft Teams o bloquearlo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b429d4e2411e697c4e3357ebd7b5fc66ab27376
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "35220889"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="8adcf-103">Usar PowerShell para controlar el acceso de invitado a un equipo</span><span class="sxs-lookup"><span data-stu-id="8adcf-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="8adcf-104">Además de usar el centro de administración de Microsoft 365 y el portal de Azure Active Directory (Azure AD), puede usar Windows PowerShell para controlar el acceso de invitados.</span><span class="sxs-lookup"><span data-stu-id="8adcf-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="8adcf-105">Con PowerShell, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8adcf-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="8adcf-106">Permitir o bloquear el acceso de invitados a todos los grupos de Teams y Office 365</span><span class="sxs-lookup"><span data-stu-id="8adcf-106">Allow or block guest access to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="8adcf-107">Permitir que los invitados se agreguen a todos los grupos de equipos y de Office 365</span><span class="sxs-lookup"><span data-stu-id="8adcf-107">Allow guests to be added to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="8adcf-108">Permitir o bloquear a usuarios invitados en un equipo o grupo específico de Office 365</span><span class="sxs-lookup"><span data-stu-id="8adcf-108">Allow or block guest users from a specific team or Office 365 group</span></span>

<span data-ttu-id="8adcf-109">Para obtener más información, vea "usar PowerShell para controlar el acceso de invitados" en [administrar el acceso de invitados en los grupos de Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span><span class="sxs-lookup"><span data-stu-id="8adcf-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>
  
<span data-ttu-id="8adcf-110">También se puede usar PowerShell para permitir o bloquear un usuario invitado en función de su dominio.</span><span class="sxs-lookup"><span data-stu-id="8adcf-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="8adcf-111">Por ejemplo, vamos a imaginar que su negocio (Contoso) tiene una asociación con otra empresa (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="8adcf-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="8adcf-112">Fabrikam se puede agregar a su lista de permitidos de manera que sus usuarios puedan agregar a esos invitados a sus grupos.</span><span class="sxs-lookup"><span data-stu-id="8adcf-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="8adcf-113">Para obtener más información, consulte [permitir o bloquear el acceso de invitados a grupos de Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="8adcf-113">For more information, see [Allow/Block guest access to Office 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="8adcf-114">Si desea bloquear invitados en Teams y aún desea permitirles el acceso a sitios de SharePoint, puede usar los cmdlets de PowerShell de Azure AD para deshabilitar el parámetro AllowGuestsToAccessGroups en el objeto de la compañía, suponiendo que el uso compartido externo esté activado para los sitios de SharePoint .</span><span class="sxs-lookup"><span data-stu-id="8adcf-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="8adcf-115">Acceso de invitado frente a acceso externo</span><span class="sxs-lookup"><span data-stu-id="8adcf-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
