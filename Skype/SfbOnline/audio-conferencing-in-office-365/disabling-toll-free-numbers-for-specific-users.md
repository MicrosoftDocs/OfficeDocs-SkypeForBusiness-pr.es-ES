---
title: Deshabilitar los números gratuitos para usuarios específicos de Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Los administradores pueden controlar cómo los organizadores pueden usar los números gratuitos para sus reuniones.
ms.openlocfilehash: 541398a760f41effc37e802cafde1141acca2d57
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306093"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="db20d-103">Deshabilitar los números gratuitos para usuarios específicos de Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="db20d-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>
 
> [!Note]
> <span data-ttu-id="db20d-104">Para obtener información acerca de deshabilitar los números gratuitos para los usuarios de Teams, vea [Deshabilitar los números gratuitos para usuarios específicos de Teams](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="db20d-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="db20d-105">Si su organización tiene números gratuitos en su puente de Audioconferencia de Microsoft, puede permitir o impedir su uso en las reuniones de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="db20d-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="db20d-p101">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings. If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span><span class="sxs-lookup"><span data-stu-id="db20d-p101">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings. If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="db20d-108">Cuando se deshabilitan los números gratuitos para un organizador determinado:</span><span class="sxs-lookup"><span data-stu-id="db20d-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="db20d-109">Ya no se incluirá un número de teléfono gratuito en sus invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="db20d-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="db20d-110">Los números gratuitos ya no se mostrarán en la página "Encontrar un número local" a la que se hace referencia en sus invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="db20d-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="db20d-111">Los participantes no podrán unirse a la reunión del organizador determinado si llaman a cualquier número de teléfono gratuito de la organización.</span><span class="sxs-lookup"><span data-stu-id="db20d-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="db20d-112">Se volverán a programar automáticamente todas las reuniones del organizador y el número de teléfono gratuito se quitará de ellas.</span><span class="sxs-lookup"><span data-stu-id="db20d-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="db20d-113">Esto hará que se vuelvan a enviar todas las invitaciones de correo electrónico del organizador a todos los participantes de las reuniones.</span><span class="sxs-lookup"><span data-stu-id="db20d-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="db20d-114">Los participantes pueden continuar uniéndose a reuniones del organizador utilizando números de teléfono de pago.</span><span class="sxs-lookup"><span data-stu-id="db20d-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="db20d-115">Deshabilitar los números gratuitos para usuarios específicos</span><span class="sxs-lookup"><span data-stu-id="db20d-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="db20d-116">Desde el **centro de administración de Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="db20d-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="db20d-117">En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="db20d-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="db20d-118">Junto a **audioconferencia**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="db20d-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="db20d-119">Set **incluye números gratuitos en las convocatorias de reunión de este usuario** como \*\*\*\* deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="db20d-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="db20d-120">Haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="db20d-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="db20d-121">**Usar PowerShell**</span><span class="sxs-lookup"><span data-stu-id="db20d-121">**Using PowerShell**</span></span>  

<span data-ttu-id="db20d-122">Puede usar el parámetro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser para habilitar o deshabilitar este control.</span><span class="sxs-lookup"><span data-stu-id="db20d-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="db20d-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="db20d-123">For example:</span></span> 

- <span data-ttu-id="db20d-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="db20d-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
