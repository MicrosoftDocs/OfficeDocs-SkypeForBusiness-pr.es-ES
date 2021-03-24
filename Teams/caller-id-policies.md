---
title: Administrar directivas del id. de llamada en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
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
description: Obtenga información sobre cómo usar y administrar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear el identificador de llamada de los usuarios de Teams de su organización.
ms.openlocfilehash: cd15245523cdc3f5fb3625a2b4cfdae4deebb7d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102786"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="65683-103">Administrar directivas del id. de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65683-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="65683-104">Como administrador, puede usar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear el identificador de llamada (también conocido como identificador de línea de llamada).</span><span class="sxs-lookup"><span data-stu-id="65683-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="65683-105">De forma predeterminada, el número de teléfono de los usuarios de Teams se puede ver cuando hacen una llamada a un teléfono RTC y el número de teléfono de las llamadas RTC se puede ver cuando llaman a un usuario de Teams.</span><span class="sxs-lookup"><span data-stu-id="65683-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="65683-106">Puede usar directivas de identificación de llamadas para mostrar un número de teléfono alternativo para los usuarios de Teams de su organización o bloquear la visualización de un número entrante.</span><span class="sxs-lookup"><span data-stu-id="65683-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="65683-107">Por ejemplo, cuando los usuarios hacen una llamada, puede cambiar el identificador de llamada para mostrar el número de teléfono principal de su organización en lugar de los números de teléfono de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="65683-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="65683-108">Para administrar las directivas de identificador de llamadas, vaya **a** Directivas de identificación de llamadas  >  **de** voz en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="65683-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="65683-109">Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="65683-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="65683-110">Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="65683-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="65683-111">Crear una directiva de identificación de llamadas personalizada</span><span class="sxs-lookup"><span data-stu-id="65683-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="65683-112">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya **a** Directivas de identificación de llamadas  >  **de voz.**</span><span class="sxs-lookup"><span data-stu-id="65683-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="65683-113">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="65683-113">Click **Add**.</span></span> <br>
<span data-ttu-id="65683-114">![Captura de pantalla de la nueva página de directiva de identificación de llamadas en el Centro de administración](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="65683-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="65683-115">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="65683-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="65683-116">Desde aquí, elija la configuración que desee:</span><span class="sxs-lookup"><span data-stu-id="65683-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="65683-117">**Bloquear el identificador de llamada entrante:** active esta configuración para bloquear la visualización del identificador de llamada de las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="65683-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="65683-118">**Invalidar la directiva de identificador de** llamada: active esta configuración para permitir que los usuarios invaliden la configuración de la directiva en relación con la visualización de su número en callees o no.</span><span class="sxs-lookup"><span data-stu-id="65683-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="65683-119">Esto significa que los usuarios pueden elegir si desea mostrar su identificador de llamada.</span><span class="sxs-lookup"><span data-stu-id="65683-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="65683-120">Para obtener más información, vea [Control de usuario final del identificador de llamada saliente.](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)</span><span class="sxs-lookup"><span data-stu-id="65683-120">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="65683-121">**Reemplace el identificador de llamada por:** Establezca el id. de autor de la llamada para que se muestre para los usuarios seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="65683-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="65683-122">**Número de usuario:** muestra el número del usuario.</span><span class="sxs-lookup"><span data-stu-id="65683-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="65683-123">**Número de servicio:** le permite establecer un número de teléfono de servicio para que se muestre como el identificador de llamada.</span><span class="sxs-lookup"><span data-stu-id="65683-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="65683-124">**Anónimo:** muestra el identificador de llamada como Anónimo.</span><span class="sxs-lookup"><span data-stu-id="65683-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="65683-125">**Reemplace el identificador de llamada por este número de servicio:** elija un número de servicio para reemplazar el id. de autor de la llamada de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="65683-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="65683-126">Esta opción está disponible si ha seleccionado Número **de servicio en** Reemplazar el identificador de llamada **con**.</span><span class="sxs-lookup"><span data-stu-id="65683-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="65683-127">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="65683-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="65683-128">Editar una directiva de identificador de llamada</span><span class="sxs-lookup"><span data-stu-id="65683-128">Edit a caller ID policy</span></span>

<span data-ttu-id="65683-129">Puede editar la directiva global o las directivas personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="65683-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="65683-130">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya **a** Directivas de identificación de llamadas  >  **de voz.**</span><span class="sxs-lookup"><span data-stu-id="65683-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="65683-131">Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="65683-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="65683-132">Cambie la configuración que desee y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="65683-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="65683-133">Asignar una directiva de identificador de llamada personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="65683-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="65683-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="65683-134">Related topics</span></span>

[<span data-ttu-id="65683-135">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="65683-135">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="65683-136">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="65683-136">Assign policies to your users in Teams</span></span>](assign-policies.md)