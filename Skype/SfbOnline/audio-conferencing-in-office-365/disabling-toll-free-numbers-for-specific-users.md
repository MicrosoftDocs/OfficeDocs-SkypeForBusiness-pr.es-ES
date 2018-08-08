---
title: Deshabilitar a los números gratuitos para usuarios específicos
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Los administradores pueden controlar cómo los organizadores pueden usar los números gratuitos para sus reuniones.
ms.openlocfilehash: 4bee4449dd8e21ded52f40cc04832bd40b15c139
ms.sourcegitcommit: 905ba61de9622dd485ff375fa75bb0d76bac0b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "22193048"
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="ce479-103">Deshabilitar a los números gratuitos para usuarios específicos</span><span class="sxs-lookup"><span data-stu-id="ce479-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="ce479-104">Si su organización tiene los números gratuitos en su Bridge Conferencing de Audio de Microsoft, puede permitir o impedir su uso en las reuniones de los organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="ce479-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="ce479-105">De forma predeterminada, todos los usuarios de su organización están habilitados para el uso de los números gratuitos, lo que significa que dichos números, si está disponible, se pueden usar por los participantes para unirse a sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="ce479-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="ce479-106">Si no es el comportamiento deseado para algunos usuarios de su organización, puede restringir usuarios específicos de uso de dichos números en sus reuniones a través de un control de habilitación de número gratuito.</span><span class="sxs-lookup"><span data-stu-id="ce479-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="ce479-107">Cuando se deshabilitan los números gratuitos para el organizador de una determinada:</span><span class="sxs-lookup"><span data-stu-id="ce479-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="ce479-108">Un número de teléfono gratuito ya no se incluirá en su o invita su reunión.</span><span class="sxs-lookup"><span data-stu-id="ce479-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="ce479-109">Los números gratuitos ya no se mostrarán en la página "Encontrar un número local" en el que se hace referencia en su o invita su reunión.</span><span class="sxs-lookup"><span data-stu-id="ce479-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="ce479-110">Los participantes no puedan unirse a la reunión del organizador determinado si marcado de cualquier número de teléfono gratuito de la organización.</span><span class="sxs-lookup"><span data-stu-id="ce479-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="ce479-111">Se volverá a programar automáticamente todas las reuniones del organizador de la, y el número de teléfono gratuito se quitará de ellos.</span><span class="sxs-lookup"><span data-stu-id="ce479-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="ce479-112">Esto volverá a enviar todas las invitaciones de correo electrónico del organizador a todos los participantes de las reuniones.</span><span class="sxs-lookup"><span data-stu-id="ce479-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="ce479-113">Los participantes pueden continuar unirse a reuniones del organizador utilizando números de teléfono de pago.</span><span class="sxs-lookup"><span data-stu-id="ce479-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="ce479-114">Deshabilitar a los números gratuitos para usuarios específicos</span><span class="sxs-lookup"><span data-stu-id="ce479-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="ce479-115">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="ce479-115">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="ce479-116">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="ce479-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ce479-117">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ce479-117">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="ce479-118">Haga clic en el menú situado junto a **Puentes de conferencia**y, a continuación, haga clic en **Editar** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ce479-118">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="ce479-119">En el panel de **proveedor de puente de conferencia** , desactive **Permitir utilizando los números gratuitos en el puente de conferencia de su organización para unirse a las reuniones de este usuario**.</span><span class="sxs-lookup"><span data-stu-id="ce479-119">In the **Conference bridge provider** pane, turn off **Allow using toll-free numbers in the Conferencing bridge of your organization to join the meetings of this user**.</span></span> 

5. <span data-ttu-id="ce479-120">Haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="ce479-120">Click **Apply.**</span></span> 

<span data-ttu-id="ce479-121">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="ce479-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="ce479-122">En el **Skype para el centro de administración de negocio**, en el panel de navegación izquierdo, vaya a la **conferencia de Audio** > **a los usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="ce479-122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="ce479-123">En el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ce479-123">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="ce479-124">Desactive **Permitir el uso de los números gratuitos para unirse a las reuniones de este usuario**.</span><span class="sxs-lookup"><span data-stu-id="ce479-124">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="ce479-125">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ce479-125">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="ce479-126">**Uso de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ce479-126">**Using PowerShell**</span></span>  

<span data-ttu-id="ce479-127">Puede usar el parámetro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser para habilitar o deshabilitar este control.</span><span class="sxs-lookup"><span data-stu-id="ce479-127">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="ce479-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ce479-128">For example:</span></span> 

 - <span data-ttu-id="ce479-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="ce479-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
