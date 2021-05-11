---
title: Administrar directivas del id. de llamada en Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar directivas de identificador de llamadas en Microsoft Teams para cambiar o bloquear el identificador de llamada de Teams usuarios de su organización.
ms.openlocfilehash: cd928af5213a1e6fa927662adaba0fefecb687d5
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308379"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="24925-103">Administrar directivas del id. de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24925-103">Manage caller ID policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="24925-104">Para establecer el identificador de llamada en un número de teléfono de cuenta de recurso y establecer el nombre de la parte que llama, use los cmdlets de PowerShell New-CsCallingLineIdentity o Set-CsCallingLineIdentity en el módulo de PowerShell de Teams 2.3.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="24925-104">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="24925-105">(Estas opciones no están disponibles actualmente en el centro Microsoft Teams administración).</span><span class="sxs-lookup"><span data-stu-id="24925-105">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="24925-106">De forma predeterminada, cuando un Teams realiza una llamada a un teléfono RTC, el número de teléfono del Teams usuario está visible.</span><span class="sxs-lookup"><span data-stu-id="24925-106">By default, when a Teams user makes a call to a PSTN phone, the phone number of the Teams user is visible.</span></span> <span data-ttu-id="24925-107">Del mismo modo, cuando un autor de la llamada RTC realiza una llamada a un Teams, el número de teléfono del autor de la llamada RTC está visible.</span><span class="sxs-lookup"><span data-stu-id="24925-107">Likewise, when a PSTN caller makes a call to a Teams user, the PSTN caller's phone number is visible.</span></span>

<span data-ttu-id="24925-108">Como administrador, puede usar directivas de identificación de llamadas para cambiar o bloquear el identificador de llamada (también conocido como identificador de línea de llamada).</span><span class="sxs-lookup"><span data-stu-id="24925-108">As an administrator, you can use caller ID policies to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="24925-109">Puede usar directivas de identificación de llamadas para mostrar un número de teléfono alternativo para los usuarios de Teams de su organización, bloquear el número de teléfono saliente, bloquear la visualización de un número entrante o establecer el nombre de la parte que llama (CNAM).</span><span class="sxs-lookup"><span data-stu-id="24925-109">You can use caller ID policies to display an alternate phone number for Teams users in your organization, block the outbound phone number, block an incoming number from being displayed, or set the Calling Party Name (CNAM).</span></span> <span data-ttu-id="24925-110">Por ejemplo, cuando un usuario realiza una llamada, puede cambiar el identificador de llamada para mostrar el número de teléfono principal y el nombre de la empresa de su organización en lugar del número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="24925-110">For example, when a user makes a call, you can change the caller ID to display your organization's main phone number and company name instead of the user's phone number.</span></span>

<span data-ttu-id="24925-111">Para administrar las directivas de identificación de llamadas, vaya **a** Directivas de identificador de llamadas de voz en el centro de Microsoft Teams de  >   llamadas.</span><span class="sxs-lookup"><span data-stu-id="24925-111">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="24925-112">Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="24925-112">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="24925-113">Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="24925-113">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="24925-114">Crear una directiva de identificación de llamadas personalizada</span><span class="sxs-lookup"><span data-stu-id="24925-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="24925-115">En el panel de navegación izquierdo del Microsoft Teams de administración, vaya **a** Directivas de identificación de llamadas  >  **de voz.**</span><span class="sxs-lookup"><span data-stu-id="24925-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="24925-116">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="24925-116">Click **Add**.</span></span> <br>
<span data-ttu-id="24925-117">![Captura de pantalla de la nueva página de directiva de identificación de llamadas en el Centro de administración](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="24925-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="24925-118">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="24925-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="24925-119">Desde aquí, elija la configuración que desee:</span><span class="sxs-lookup"><span data-stu-id="24925-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="24925-120">**Bloquear el identificador de llamada entrante:** active esta configuración para bloquear la visualización del identificador de llamada de las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="24925-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="24925-121">**Invalidar la directiva de identificador de** llamada: active esta configuración para permitir que los usuarios invaliden la configuración de la directiva en relación con la visualización de su número en callees o no.</span><span class="sxs-lookup"><span data-stu-id="24925-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="24925-122">Esto significa que los usuarios pueden elegir si desea mostrar su identificador de llamada.</span><span class="sxs-lookup"><span data-stu-id="24925-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="24925-123">Para obtener más información, vea [Control de usuario final del identificador de llamada saliente.](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)</span><span class="sxs-lookup"><span data-stu-id="24925-123">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="24925-124">**Reemplace el identificador de llamada por:** Establezca el id. de autor de la llamada para que se muestre para los usuarios seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="24925-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="24925-125">**Número de usuario:** muestra el número del usuario.</span><span class="sxs-lookup"><span data-stu-id="24925-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="24925-126">**Número de servicio:** le permite establecer un número de teléfono de servicio para que se muestre como el identificador de llamada.</span><span class="sxs-lookup"><span data-stu-id="24925-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="24925-127">**Anónimo:** muestra el identificador de llamada como Anónimo.</span><span class="sxs-lookup"><span data-stu-id="24925-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="24925-128">**Reemplace el identificador de llamada por este número de servicio:** elija un número de servicio para reemplazar el id. de autor de la llamada de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="24925-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="24925-129">Esta opción está disponible si ha seleccionado Número **de servicio en** Reemplazar el identificador de llamada **con**.</span><span class="sxs-lookup"><span data-stu-id="24925-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="24925-130">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="24925-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="24925-131">Editar una directiva de identificador de llamada</span><span class="sxs-lookup"><span data-stu-id="24925-131">Edit a caller ID policy</span></span>

<span data-ttu-id="24925-132">Puede editar la directiva global o las directivas personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="24925-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="24925-133">En el panel de navegación izquierdo del Microsoft Teams de administración, vaya **a** Directivas de identificación de llamadas  >  **de voz.**</span><span class="sxs-lookup"><span data-stu-id="24925-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="24925-134">Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="24925-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="24925-135">Cambie la configuración que desee y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="24925-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="24925-136">Asignar una directiva de identificador de llamada personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="24925-136">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="24925-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="24925-137">Related topics</span></span>

[<span data-ttu-id="24925-138">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="24925-138">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="24925-139">Set-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="24925-139">Set-CsCallingLineIdentity</span></span>](/powershell/module/skype/set-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="24925-140">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="24925-140">Assign policies to your users in Teams</span></span>](assign-policies.md)