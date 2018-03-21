---
title: "Desactivación de números de teléfono gratuitos para usuarios específicos"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 02/23/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Los administradores pueden controlar cómo los organizadores pueden usar números de teléfono gratuitos para sus reuniones."
ms.openlocfilehash: fb4b0f8725608928e686307845871b4f5c1976d9
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="d9549-103">Desactivación de números de teléfono gratuitos para usuarios específicos</span><span class="sxs-lookup"><span data-stu-id="d9549-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="d9549-104">Si su organización tiene números gratuitos en su Microsoft Audio Conferencing Bridge, puede permitir o impedir su uso en las reuniones de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="d9549-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="d9549-105">De forma predeterminada, todos los usuarios de su organización están habilitados para el uso de números de teléfono gratuitos, lo que significa que esos números, si está disponible, pueden utilizarse por los participantes para unirse a sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="d9549-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="d9549-106">Si no es el comportamiento deseado de algunos usuarios de su organización, puede evitar que usuarios específicos utilizando esos números en sus reuniones a través de un control de habilitación número gratuito.</span><span class="sxs-lookup"><span data-stu-id="d9549-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="d9549-107">Cuando los números gratuitos están deshabilitados para el organizador de una determinada:</span><span class="sxs-lookup"><span data-stu-id="d9549-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="d9549-108">Ya no se incluirán un número gratuito en su o invita su reunión.</span><span class="sxs-lookup"><span data-stu-id="d9549-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="d9549-109">Ya no se mostrarán en la página "Buscar un número local" que se hace referencia en su números gratuitos o invita su reunión.</span><span class="sxs-lookup"><span data-stu-id="d9549-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="d9549-110">Los participantes no pueden participar en la reunión del organizador determinado si marcar cualquier número gratuito de la organización.</span><span class="sxs-lookup"><span data-stu-id="d9549-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="d9549-111">Se programará automáticamente todas las reuniones del organizador y se quitará el número gratuito de ellos.</span><span class="sxs-lookup"><span data-stu-id="d9549-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="d9549-112">Esto volverá a enviar todas las invitaciones de correo electrónico del organizador a todos los participantes de las reuniones.</span><span class="sxs-lookup"><span data-stu-id="d9549-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="d9549-113">Los participantes pueden continuar unirse a reuniones del organizador con números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="d9549-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users-using-the-skype-for-business-admin-center"></a><span data-ttu-id="d9549-114">Desactivación de números de teléfono gratuitos para usuarios específicos mediante el Skype para el centro de administración de negocios</span><span class="sxs-lookup"><span data-stu-id="d9549-114">Disabling toll-free numbers for specific users using the Skype for Business admin center</span></span> 
 1. <span data-ttu-id="d9549-115">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="d9549-115">Go to the **Office 365 admin center** > **Skype for Business**.</span></span> 
 2. <span data-ttu-id="d9549-116">En el Skype para el centro de administración de negocios, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="d9549-116">In the Skype for Business admin center, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 
 3. <span data-ttu-id="d9549-117">En el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d9549-117">In the Action pane, click **Edit**.</span></span> 
 4. <span data-ttu-id="d9549-118">Active o desactive **Permitir mediante números de teléfono gratuitos para unirse a las reuniones de este usuario**.</span><span class="sxs-lookup"><span data-stu-id="d9549-118">Check or clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 5. <span data-ttu-id="d9549-119">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d9549-119">Click **Save**.</span></span> 
 
## <a name="disabling-toll-free-numbers-for-specific-users-using-powershell"></a><span data-ttu-id="d9549-120">Desactivación de números de teléfono gratuitos para usuarios específicos mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9549-120">Disabling toll-free numbers for specific users using PowerShell</span></span>  

<span data-ttu-id="d9549-121">Puede utilizar el parámetro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser para habilitar o deshabilitar este control.</span><span class="sxs-lookup"><span data-stu-id="d9549-121">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="d9549-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d9549-122">For example:</span></span> 

 - <span data-ttu-id="d9549-123">Conjunto CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="d9549-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
