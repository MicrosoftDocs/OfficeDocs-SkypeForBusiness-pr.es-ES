---
title: Usar PowerShell para controlar el acceso de invitado a un equipo
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Use PowerShell para permitir el acceso de invitado a los equipos de Microsoft Teams o bloquearlo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3bcf91bc6f78951439b051f3cc2d3e827210a9f
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706254"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="a2191-103">Usar PowerShell para controlar el acceso de invitado a un equipo</span><span class="sxs-lookup"><span data-stu-id="a2191-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="a2191-104">Además de usar el Centro de administración de Office 365 y el portal de Azure Active Directory, puede usar Windows PowerShell para controlar el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="a2191-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="a2191-105">Con PowerShell, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2191-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="a2191-106">Permitir o bloquear el acceso de invitado a todos los equipos y grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="a2191-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
- <span data-ttu-id="a2191-107">Permitir que se puedan agregar invitados a todos los equipos y grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="a2191-107">Allow guests to be added to all teams and Office 365 groups</span></span>
      
- <span data-ttu-id="a2191-108">Permitir o bloquear a usuarios invitados en un equipo o grupo específico de Office 365</span><span class="sxs-lookup"><span data-stu-id="a2191-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
<span data-ttu-id="a2191-109">Para obtener información detallada, vea la sección "Uso de PowerShell para controlar el acceso de invitado" en la ficha administrar de [acceso como invitado en grupos de Office 365](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="a2191-109">For details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="a2191-110">También se puede usar PowerShell para permitir o bloquear un usuario invitado en función de su dominio.</span><span class="sxs-lookup"><span data-stu-id="a2191-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="a2191-111">Por ejemplo, vamos a imaginar que su negocio (Contoso) tiene una asociación con otra empresa (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="a2191-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="a2191-112">Fabrikam se puede agregar a su lista de permitidos de manera que sus usuarios puedan agregar a esos invitados a sus grupos.</span><span class="sxs-lookup"><span data-stu-id="a2191-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="a2191-113">Para obtener más información, vea [Permitir o bloquear el acceso de invitado a los grupos de Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="a2191-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="a2191-114">Si desea bloquear a invitados en los equipos y seguir permitiendo que los invitados tengan acceso a sitios de SharePoint, puede usar los cmdlets de Azure Active Directory PowerShell para deshabilitar el parámetro AllowGuestAccessToGroups en el objeto de empresa, siempre que el uso compartido externo esté activado para los sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2191-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="a2191-115">Acceso de invitado frente a acceso externo</span><span class="sxs-lookup"><span data-stu-id="a2191-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]