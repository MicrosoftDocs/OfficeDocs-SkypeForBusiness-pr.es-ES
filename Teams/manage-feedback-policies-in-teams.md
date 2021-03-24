---
title: Administrar directivas de comentarios en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar directivas de comentarios para controlar si los usuarios de Teams de su organización pueden enviar comentarios sobre Teams a Microsoft.
ms.openlocfilehash: bc925320959c55b2fa06c8480f1011aab81aae9c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094270"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="2cc9a-103">Administrar directivas de comentarios en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2cc9a-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="2cc9a-104">Los usuarios de su organización pueden enviar comentarios sobre Teams a Microsoft para que sepamos cómo estamos, directamente desde los clientes de escritorio y web de Teams.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="2cc9a-105">Estamos mejorando continuamente la experiencia de Teams y usamos estos comentarios para mejorar Teams.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="2cc9a-106">Las directivas de comentarios no están disponibles en implementaciones de GCC, GCC High o DOD.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="2cc9a-107">**La característica Enviar comentarios**</span><span class="sxs-lookup"><span data-stu-id="2cc9a-107">**The Give feedback feature**</span></span>

<span data-ttu-id="2cc9a-108">Los usuarios pueden enviarnos comentarios y sugerencias sobre Teams yendo a **Ayuda**  >  **para enviar comentarios** en Teams.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="2cc9a-109">Los datos  enviados a través de Enviar comentarios se consideran "Datos de soporte técnico" en virtud de su contrato de Microsoft 365 u Office 365, incluida la información que de otro modo se consideraría "Datos del cliente" o "Datos personales".</span><span class="sxs-lookup"><span data-stu-id="2cc9a-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Captura de pantalla de la opción Enviar comentarios en Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="2cc9a-111">**Encuestas**</span><span class="sxs-lookup"><span data-stu-id="2cc9a-111">**Surveys**</span></span>

<span data-ttu-id="2cc9a-112">Los usuarios también pueden calificar su experiencia con Teams y enviarnos detalles sobre la clasificación que dan.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="2cc9a-113">Esta encuesta emergente se muestra a los usuarios de vez en cuando en Teams.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="2cc9a-114">Cuando un usuario hace clic **en Proporcionar comentarios** en la notificación, se muestra la encuesta para que se complete.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Captura de pantalla de la notificación y el formulario de la encuesta en Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="2cc9a-116">Establecer si los usuarios pueden enviar comentarios sobre Teams a Microsoft</span><span class="sxs-lookup"><span data-stu-id="2cc9a-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="2cc9a-117">Como administrador, puede controlar si los usuarios de su organización pueden enviar comentarios sobre Teams a Microsoft a través de **Enviar** comentarios y si reciben la encuesta.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="2cc9a-118">De forma predeterminada, a todos los usuarios de su organización se  les asigna automáticamente la directiva global (predeterminada para toda la organización) y la característica y la encuesta Enviar comentarios están habilitadas en la directiva.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="2cc9a-119">La excepción es Teams for Education, donde las características están habilitadas para los profesores y deshabilitadas para los alumnos.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="2cc9a-120">Puede editar la directiva global o crear y asignar una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="2cc9a-121">Después de editar la directiva global o asignar una directiva personalizada, los cambios pueden tardar unas horas en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="2cc9a-122">Por ejemplo, quiere permitir que todos los usuarios de  su organización envíen comentarios a través de Enviar comentarios y recibir encuestas, excepto los nuevos empleados en formación.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="2cc9a-123">En este escenario, creará una directiva personalizada para desactivar ambas características y asignarla a nuevos empleados.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="2cc9a-124">Todos los demás usuarios de su organización obtienen la directiva global con las características activadas.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="2cc9a-125">Puede administrar directivas de comentarios con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="2cc9a-126">Use el cmdlet **New-CsTeamsFeedbackPolicy,** que se puede encontrar *aquí, [](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* para crear una directiva personalizada y el cmdlet **Grant-CsTeamsFeedbackPolicy** para asignarlo a uno o varios usuarios o grupos de usuarios, como un grupo de seguridad o un grupo de distribución.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="2cc9a-127">Para desactivar y activar las características, establezca los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="2cc9a-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="2cc9a-128">**Enviar comentarios:** Establezca el **parámetro userInitiatedMode** en **habilitado** para permitir que los usuarios a los que se les asigne la directiva puedan enviar comentarios.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="2cc9a-129">Al establecer el parámetro en **deshabilitado** se desactiva la característica y los usuarios a los que se les asigna la directiva no tienen la opción de enviar comentarios.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="2cc9a-130">**Encuestas:** establezca el **parámetro receiveSurveysMode** en **habilitado** para permitir que los usuarios a los que se les asigne la directiva reciban la encuesta.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="2cc9a-131">Para que los usuarios reciban la encuesta y les permitan optar por no participar, establezca el parámetro en **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="2cc9a-132">En Teams, los usuarios pueden ir a **Configuración**  >  **privacidad** y elegir si quieren participar en encuestas.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="2cc9a-133">Al establecer el parámetro en **deshabilitado,** se desactiva la característica y los usuarios a los que se les asigna la directiva no recibirán la encuesta.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="2cc9a-134">Crear una directiva de comentarios personalizada</span><span class="sxs-lookup"><span data-stu-id="2cc9a-134">Create a custom feedback policy</span></span>

<span data-ttu-id="2cc9a-135">En este ejemplo, creamos una directiva de comentarios denominada Nueva directiva de comentarios de contratación y desactivamos la capacidad de enviar comentarios a través de **Enviar** comentarios y la encuesta.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="2cc9a-136">Asignar una directiva de comentarios personalizados a los usuarios</span><span class="sxs-lookup"><span data-stu-id="2cc9a-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="2cc9a-137">En este ejemplo, asignamos una directiva personalizada denominada Nueva directiva de comentarios de contratación a un usuario denominado usuario1.</span><span class="sxs-lookup"><span data-stu-id="2cc9a-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="2cc9a-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2cc9a-138">Related topics</span></span>

- [<span data-ttu-id="2cc9a-139">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="2cc9a-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="2cc9a-140">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="2cc9a-140">Assign policies to your users in Teams</span></span>](assign-policies.md)