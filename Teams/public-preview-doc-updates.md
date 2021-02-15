---
title: Versión preliminar pública para Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga más información sobre la versión preliminar pública en Microsoft Teams. Pruebe nuevas características y envíe sus comentarios.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 60ed1c821389fb56d6e6bfb4ab4a37e562be726a
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196224"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="5d9b3-104">Versión preliminar pública en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d9b3-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="5d9b3-p102">Es posible que las características incluidas en la versión preliminar no estén completas y experimenten cambios antes de que estén disponibles en la versión pública. Se ofrecen solo para fines de evaluación y exploración. No compatible con Office 365 Government Community Cloud (GCC).</span><span class="sxs-lookup"><span data-stu-id="5d9b3-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only. Not supported in Office 365 Government Community Cloud (GCC).</span></span>

<span data-ttu-id="5d9b3-p103">La versión preliminar pública para Microsoft Teams ofrece acceso anticipado a características no publicadas en Teams. Las versiones preliminares le permiten explorar y probar las características futuras. También agradecemos sus comentarios sobre cualquier característica de la versión preliminar pública. La versión preliminar pública está habilitada por usuario de Teams, por lo que no tiene que preocuparse por si afecta a toda la organización.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.</span></span>

<span data-ttu-id="5d9b3-112">Para consultar una lista de elementos disponibles en la versión preliminar pública de Teams, visite [Notas de la versión para el canal actual (versión preliminar) de Office](https://docs.microsoft.com/officeupdates/current-channel-preview).</span><span class="sxs-lookup"><span data-stu-id="5d9b3-112">For a list of what's available in the Teams public preview, visit [Release Notes for Office Current Channel (Preview)](https://docs.microsoft.com/officeupdates/current-channel-preview).</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="5d9b3-113">Configure la directiva de actualización</span><span class="sxs-lookup"><span data-stu-id="5d9b3-113">Set the Update policy</span></span>

<span data-ttu-id="5d9b3-114">La versión preliminar pública está habilitada de manera individual por cada usuario y la opción para activarla se controla en una directiva de administración.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-114">Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="5d9b3-115">Las directivas de actualización se utilizan para administrar a usuarios de Office y Teams que verán las funciones de prelanzamiento o de versión preliminar en la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-115">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="5d9b3-116">Puede usar la directiva global (predeterminada para toda la organización) y personalizarla, o bien crear una o varias directivas personalizadas para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-116">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="5d9b3-117">La directiva debe asignarse a usuarios específicos porque no sobrescribe la directiva global.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-117">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="5d9b3-118">Inicie sesión en el Centro de administración.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-118">Sign in to the admin center.</span></span>
2. <span data-ttu-id="5d9b3-119">Seleccione **Teams**>**Actualizar directivas**.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-119">Select **Teams**>**Update policies**.</span></span>

   ![Seleccione la opción Actualizar directivas](media/updatePolicies.png)

3. <span data-ttu-id="5d9b3-121">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-121">Select **Add**.</span></span>
4. <span data-ttu-id="5d9b3-122">Asigne un nombre a la directiva de actualización, agregue una descripción y active **Mostrar características de versión preliminar**.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-122">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="5d9b3-123">También puede establecer la directiva con PowerShell usando el cmdlet de `CsTeamsUpdateManagementPolicy`.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-123">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="5d9b3-124">Habilite la versión preliminar pública</span><span class="sxs-lookup"><span data-stu-id="5d9b3-124">Enable public preview</span></span>

<span data-ttu-id="5d9b3-125">Para habilitar la versión preliminar pública en un escritorio o cliente web, tiene que realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="5d9b3-125">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="5d9b3-126">Seleccione su perfil para mostrar el menú de Teams.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-126">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="5d9b3-127">Seleccione **Acerca de** → **Versión preliminar pública**.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-127">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="5d9b3-128">Seleccione **Cambiar a la Versión preliminar pública**.</span><span class="sxs-lookup"><span data-stu-id="5d9b3-128">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5d9b3-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5d9b3-129">Related topics</span></span>

[<span data-ttu-id="5d9b3-130">Versión preliminar pública para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="5d9b3-130">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)

