---
title: Deshabilitar a los números gratuitos para Skype específico para los usuarios empresariales en línea
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Los administradores pueden controlar cómo los organizadores pueden usar los números gratuitos para sus reuniones.
ms.openlocfilehash: 1cd144af4f57b3c4ecb19de6c4aeea36f5d2baed
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490549"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="fe63e-103">Deshabilitar a los números gratuitos para Skype específico para los usuarios empresariales en línea</span><span class="sxs-lookup"><span data-stu-id="fe63e-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

> [!Note]
> <span data-ttu-id="fe63e-104">Para obtener información acerca de los números deshabilitar libre de herramienta para los usuarios de los equipos, vea [Deshabilitar los números gratuitos para usuarios de equipos específicos](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="fe63e-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="fe63e-105">Si su organización tiene los números gratuitos en su Bridge Conferencing de Audio de Microsoft, puede permitir o impedir su uso en las reuniones de los organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="fe63e-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="fe63e-106">De forma predeterminada, todos los usuarios de su organización están habilitados para el uso de los números gratuitos, lo que significa que dichos números, si está disponible, se pueden usar por los participantes para unirse a sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="fe63e-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="fe63e-107">Si no es el comportamiento deseado para algunos usuarios de su organización, puede restringir usuarios específicos de uso de dichos números en sus reuniones a través de un control de habilitación de número gratuito.</span><span class="sxs-lookup"><span data-stu-id="fe63e-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="fe63e-108">Cuando se deshabilitan los números gratuitos para el organizador de una determinada:</span><span class="sxs-lookup"><span data-stu-id="fe63e-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="fe63e-109">Un número de teléfono gratuito ya no se incluirá en su o invita su reunión.</span><span class="sxs-lookup"><span data-stu-id="fe63e-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="fe63e-110">Los números gratuitos ya no se mostrarán en la página "Encontrar un número local" en el que se hace referencia en su o invita su reunión.</span><span class="sxs-lookup"><span data-stu-id="fe63e-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="fe63e-111">Los participantes no puedan unirse a la reunión del organizador determinado si marcado de cualquier número de teléfono gratuito de la organización.</span><span class="sxs-lookup"><span data-stu-id="fe63e-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="fe63e-112">Se volverá a programar automáticamente todas las reuniones del organizador de la, y el número de teléfono gratuito se quitará de ellos.</span><span class="sxs-lookup"><span data-stu-id="fe63e-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="fe63e-113">Esto volverá a enviar todas las invitaciones de correo electrónico del organizador a todos los participantes de las reuniones.</span><span class="sxs-lookup"><span data-stu-id="fe63e-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="fe63e-114">Los participantes pueden continuar unirse a reuniones del organizador utilizando números de teléfono de pago.</span><span class="sxs-lookup"><span data-stu-id="fe63e-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="fe63e-115">Deshabilitar a los números gratuitos para usuarios específicos</span><span class="sxs-lookup"><span data-stu-id="fe63e-115">Disabling toll-free numbers for specific users</span></span> 


1. <span data-ttu-id="fe63e-116">En el **Skype para el centro de administración de negocio**, en el panel de navegación izquierdo, vaya a la **conferencia de Audio** > **a los usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="fe63e-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="fe63e-117">En el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fe63e-117">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="fe63e-118">Desactive **Permitir el uso de los números gratuitos para unirse a las reuniones de este usuario**.</span><span class="sxs-lookup"><span data-stu-id="fe63e-118">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="fe63e-119">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fe63e-119">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="fe63e-120">**Uso de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fe63e-120">**Using PowerShell**</span></span>  

<span data-ttu-id="fe63e-121">Puede usar el parámetro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser para habilitar o deshabilitar este control.</span><span class="sxs-lookup"><span data-stu-id="fe63e-121">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="fe63e-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fe63e-122">For example:</span></span> 

 - <span data-ttu-id="fe63e-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="fe63e-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
