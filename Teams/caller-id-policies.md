---
title: Administrar directivas de identificación de llamadas en Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Aprenda a usar y administrar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear la identificación de llamadas de los usuarios de su organización.
ms.openlocfilehash: 41466640f33769a64ce14d5d3dc47959c876a5bc
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938469"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="a2f4b-103">Administrar directivas de identificación de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a2f4b-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="a2f4b-104">Como administrador, puede usar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear la identificación de llamadas (también conocida como identificador de línea de llamada).</span><span class="sxs-lookup"><span data-stu-id="a2f4b-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="a2f4b-105">De forma predeterminada, se puede ver el número de teléfono de los usuarios de Teams cuando hacen una llamada a un teléfono PSTN y el número de teléfono de los autores de llamadas RTC se puede ver al llamar a un usuario de Teams.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="a2f4b-106">Puede usar las directivas de identificación de llamadas para mostrar un número de teléfono alternativo para los usuarios de equipos de su organización o impedir que se muestre un número entrante.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="a2f4b-107">Por ejemplo, cuando los usuarios hacen una llamada, puede cambiar la identificación de llamadas para mostrar el número de teléfono principal de su organización en lugar de los números de teléfono de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="a2f4b-108">Para administrar las directivas de identificación de llamadas, **Voice**vaya a  >  **directivas de identificación de llamadas** de voz en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="a2f4b-109">Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="a2f4b-110">Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="a2f4b-111">Crear una directiva de identificación de llamadas personalizada</span><span class="sxs-lookup"><span data-stu-id="a2f4b-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="a2f4b-112">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de identificación de llamadas**de voz.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="a2f4b-113">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-113">Click **Add**.</span></span> <br>
<span data-ttu-id="a2f4b-114">![Captura de pantalla de la nueva página de la Directiva de identificación de llamadas en el centro de administración](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="a2f4b-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="a2f4b-115">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="a2f4b-116">Desde aquí, elija la configuración que desee:</span><span class="sxs-lookup"><span data-stu-id="a2f4b-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="a2f4b-117">**Bloquear la identificación de llamadas entrantes**: activa esta configuración para bloquear la identificación de llamadas entrantes de llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="a2f4b-118">**Invalidar la Directiva de identificación de llamadas**: activa esta configuración para permitir a los usuarios invalidar la configuración de la Directiva relativa a la presentación de su número a destinatarios o no.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="a2f4b-119">Esto significa que los usuarios pueden elegir si deseas Mostrar la identificación de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="a2f4b-120">Para obtener más información, consulte [control del usuario final de la identificación de llamadas salientes](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span><span class="sxs-lookup"><span data-stu-id="a2f4b-120">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="a2f4b-121">**Cambie la identificación de llamadas por**: establezca la identificación de llamadas que se va a mostrar para los usuarios seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a2f4b-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="a2f4b-122">**Número de usuario**: muestra el número de usuario.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="a2f4b-123">**Número de servicio**: te permite establecer un número de teléfono de servicio para que se muestre como la identificación de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="a2f4b-124">**Anonymous**: muestra la identificación de llamadas como anónima.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="a2f4b-125">**Reemplazar la identificación de llamadas por este número de servicio**: elige un número de servicio para reemplazar la identificación de llamadas de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="a2f4b-126">Esta opción está disponible si seleccionaste **número de servicio** en **reemplazar la identificación de llamadas por**.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="a2f4b-127">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="a2f4b-128">Editar una directiva de identificación de llamadas</span><span class="sxs-lookup"><span data-stu-id="a2f4b-128">Edit a caller ID policy</span></span>

<span data-ttu-id="a2f4b-129">Puede editar la directiva global o cualquier directiva personalizada que cree.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="a2f4b-130">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de identificación de llamadas**de voz.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="a2f4b-131">Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="a2f4b-132">Cambie la configuración que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a2f4b-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="a2f4b-133">Asignar una directiva de identificación de llamadas personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="a2f4b-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="a2f4b-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a2f4b-134">Related topics</span></span>

[<span data-ttu-id="a2f4b-135">Nuevo: CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="a2f4b-135">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="a2f4b-136">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="a2f4b-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
