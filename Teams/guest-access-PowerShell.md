---
title: Usar PowerShell para controlar el acceso de invitado a un equipo
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: Use PowerShell para permitir el acceso de invitado a los equipos de Microsoft Teams o bloquearlo.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 0e087aadced6980db80890f423e3e6e3c4b7a701
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="deb21-103">Usar PowerShell para controlar el acceso de invitado a un equipo</span><span class="sxs-lookup"><span data-stu-id="deb21-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="deb21-104">Además de usar el Centro de administración de Office 365 y el portal de Azure Active Directory, puede usar Windows PowerShell para controlar el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="deb21-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="deb21-105">Con PowerShell, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="deb21-105">With PowerShell, you can do the following:</span></span>
  
  
   

- <span data-ttu-id="deb21-106">Permitir o bloquear el acceso de invitado a todos los equipos y grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="deb21-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="deb21-107">Permitir que se puedan agregar invitados a todos los equipos y grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="deb21-107">Allow guests to be added to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="deb21-108">Permitir o bloquear a usuarios invitados en un equipo o grupo específico de Office 365</span><span class="sxs-lookup"><span data-stu-id="deb21-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
  
<span data-ttu-id="deb21-109">Para obtener más información, consulte la sección "Usar PowerShell para controlar el acceso de invitado" en la ficha Administrar de [Acceso de invitado en Office 365 Groups](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="deb21-109">For more details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
    
    
<span data-ttu-id="deb21-110">También se puede usar PowerShell para permitir o bloquear un usuario invitado en función de su dominio.</span><span class="sxs-lookup"><span data-stu-id="deb21-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="deb21-111">Por ejemplo, vamos a imaginar que su negocio (Contoso) tiene una asociación con otra empresa (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="deb21-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="deb21-112">Fabrikam se puede agregar a su lista de permitidos de manera que sus usuarios puedan agregar a esos invitados a sus grupos.</span><span class="sxs-lookup"><span data-stu-id="deb21-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="deb21-113">Para obtener más información, vea [Permitir o bloquear el acceso de invitado a los grupos de Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="deb21-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
 
<span data-ttu-id="deb21-114">Si desea bloquear a invitados en los equipos y seguir permitiendo que los invitados tengan acceso a sitios de SharePoint, puede usar los cmdlets de Azure Active Directory PowerShell para deshabilitar el parámetro AllowGuestAccessToGroups en el objeto de empresa, siempre que el uso compartido externo esté activado para los sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="deb21-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

