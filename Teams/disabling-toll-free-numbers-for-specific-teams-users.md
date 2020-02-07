---
title: Deshabilitar los números gratuitos para usuarios específicos de Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: Los administradores pueden controlar la forma en la que los organizadores pueden usar los números gratuitos para sus reuniones.
ms.openlocfilehash: 7bc830529fc24a61be914998e923ad2d5288b7c5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837270"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="2b206-103">Deshabilitar los números gratuitos para usuarios específicos de Teams</span><span class="sxs-lookup"><span data-stu-id="2b206-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="2b206-104">Si su organización tiene números gratuitos en su puente de Audioconferencia de Microsoft, puede permitir o impedir su uso en las reuniones de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="2b206-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="2b206-105">De forma predeterminada, todos los usuarios de su organización están habilitados para el uso de los números gratuitos, lo que significa que dichos números, si están disponible, se pueden usar por los participantes para unirse a sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="2b206-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="2b206-106">Si no es el comportamiento deseado para algunos usuarios de su organización, puede restringir a usuarios específicos el uso de dichos números en sus reuniones a través de un control de habilitación de los números gratuitos.</span><span class="sxs-lookup"><span data-stu-id="2b206-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="2b206-107">Cuando se deshabilitan los números gratuitos para un organizador determinado:</span><span class="sxs-lookup"><span data-stu-id="2b206-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="2b206-108">Ya no se incluirá un número de teléfono gratuito en sus invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="2b206-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="2b206-109">Los números gratuitos ya no se mostrarán en la página "Encontrar un número local" a la que se hace referencia en sus invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="2b206-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="2b206-110">Los participantes no podrán unirse a la reunión del organizador determinado si llaman a cualquier número de teléfono gratuito de la organización.</span><span class="sxs-lookup"><span data-stu-id="2b206-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="2b206-111">Se volverán a programar automáticamente todas las reuniones del organizador y el número de teléfono gratuito se quitará de ellas.</span><span class="sxs-lookup"><span data-stu-id="2b206-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="2b206-112">Esto hará que se vuelvan a enviar todas las invitaciones de correo electrónico del organizador a todos los participantes de las reuniones.</span><span class="sxs-lookup"><span data-stu-id="2b206-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="2b206-113">Los participantes pueden continuar uniéndose a reuniones del organizador utilizando números de teléfono de pago.</span><span class="sxs-lookup"><span data-stu-id="2b206-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="2b206-114">Deshabilitar los números gratuitos para usuarios específicos</span><span class="sxs-lookup"><span data-stu-id="2b206-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="2b206-115">Desde el **centro de administración de Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="2b206-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="2b206-116">En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="2b206-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="2b206-117">Junto a **Audioconferencia**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2b206-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="2b206-118">Set **incluye números gratuitos en las convocatorias de reunión de este usuario** como **deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="2b206-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="2b206-119">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b206-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="2b206-120">**Uso de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2b206-120">**Using PowerShell**</span></span>  

<span data-ttu-id="2b206-121">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2b206-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
