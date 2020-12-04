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
ms.openlocfilehash: ab48796f877f6af33b8a3c1b2bc5a3cc56e7bd1e
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530987"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="eee96-104">Versión preliminar pública en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eee96-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="eee96-p102">Es posible que las características incluidas en la versión preliminar no estén completas y experimenten cambios antes de que estén disponibles en la versión pública. Se ofrecen solo para fines de evaluación y exploración.</span><span class="sxs-lookup"><span data-stu-id="eee96-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="eee96-p103">La versión preliminar pública para Microsoft Teams ofrece acceso anticipado a características no publicadas en Teams. Las versiones preliminares le permiten explorar y probar las características futuras. También agradecemos sus comentarios sobre cualquier característica de la versión preliminar pública. La versión preliminar pública está habilitada para todos los usuarios de Teams, por lo que no tiene que preocuparse por afectar a toda la organización.</span><span class="sxs-lookup"><span data-stu-id="eee96-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled each Teams user, so you don't need to worry about affecting your entire organization.</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="eee96-111">Configure la directiva de actualización</span><span class="sxs-lookup"><span data-stu-id="eee96-111">Set the Update policy</span></span>

 <span data-ttu-id="eee96-112">La versión preliminar pública está habilitada para cada usuario y la opción para activarla se controla en una directiva de administración.</span><span class="sxs-lookup"><span data-stu-id="eee96-112">Public preview is enabled for each user, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="eee96-113">Las directivas de actualización se utilizan para administrar a usuarios de Office y Teams que verán las funciones de prelanzamiento o de versión preliminar en la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="eee96-113">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="eee96-114">Puede usar la directiva global (predeterminada para toda la organización) y personalizarla, o bien crear una o varias directivas personalizadas para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="eee96-114">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="eee96-115">La directiva debe asignarse a usuarios específicos porque no sobrescribe la directiva global.</span><span class="sxs-lookup"><span data-stu-id="eee96-115">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="eee96-116">Inicie sesión en el Centro de administración.</span><span class="sxs-lookup"><span data-stu-id="eee96-116">Sign in to the admin center.</span></span>
2. <span data-ttu-id="eee96-117">Seleccione **Teams**>**Actualizar directivas**.</span><span class="sxs-lookup"><span data-stu-id="eee96-117">Select **Teams**>**Update policies**.</span></span>

   ![Seleccione la opción Actualizar directivas](media/updatePolicies.png)

3. <span data-ttu-id="eee96-119">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="eee96-119">Select **Add**.</span></span>
4. <span data-ttu-id="eee96-120">Asigne un nombre a la directiva de actualización, agregue una descripción y active **Mostrar características de versión preliminar**.</span><span class="sxs-lookup"><span data-stu-id="eee96-120">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="eee96-121">También puede establecer la directiva con PowerShell usando el cmdlet de `CsTeamsUpdateManagementPolicy`.</span><span class="sxs-lookup"><span data-stu-id="eee96-121">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="eee96-122">Habilite la versión preliminar pública</span><span class="sxs-lookup"><span data-stu-id="eee96-122">Enable public preview</span></span>

<span data-ttu-id="eee96-123">Para habilitar la versión preliminar pública en un escritorio o cliente web, tiene que realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="eee96-123">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="eee96-124">Seleccione su perfil para mostrar el menú de Teams.</span><span class="sxs-lookup"><span data-stu-id="eee96-124">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="eee96-125">Seleccione **Acerca de** → **Versión preliminar pública**.</span><span class="sxs-lookup"><span data-stu-id="eee96-125">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="eee96-126">Seleccione **Cambiar a la Versión preliminar pública**.</span><span class="sxs-lookup"><span data-stu-id="eee96-126">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eee96-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="eee96-127">Related topics</span></span>

[<span data-ttu-id="eee96-128">Versión preliminar pública para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="eee96-128">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
