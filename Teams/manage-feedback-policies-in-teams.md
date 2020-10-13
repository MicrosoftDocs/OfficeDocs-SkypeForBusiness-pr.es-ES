---
title: Administrar directivas de comentarios en Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Aprenda a usar las directivas de comentarios para controlar si los usuarios de equipos de su organización pueden enviar comentarios sobre los equipos a Microsoft.
ms.openlocfilehash: 0bece4515825a0d7ddf7e547f1607fbd6cf205cc
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433043"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="aca34-103">Administrar directivas de comentarios en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aca34-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="aca34-104">Los usuarios de su organización pueden enviar comentarios acerca de Teams a Microsoft para saber cómo estamos haciendo, directamente desde el escritorio de Teams y los clientes Web.</span><span class="sxs-lookup"><span data-stu-id="aca34-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="aca34-105">Mejoramos continuamente la experiencia de los equipos y usamos estos comentarios para mejorar los equipos.</span><span class="sxs-lookup"><span data-stu-id="aca34-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="aca34-106">Las directivas de comentarios no están disponibles en las implementaciones GCC, GCC High o DOD.</span><span class="sxs-lookup"><span data-stu-id="aca34-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="aca34-107">**La característica proporcionar comentarios**</span><span class="sxs-lookup"><span data-stu-id="aca34-107">**The Give feedback feature**</span></span>

<span data-ttu-id="aca34-108">Los usuarios pueden enviar comentarios y sugerencias sobre los equipos para que nos **ayuden**a  >  **proporcionar comentarios** en Teams.</span><span class="sxs-lookup"><span data-stu-id="aca34-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="aca34-109">Los datos enviados a través de enviar **comentarios** se consideran "datos de soporte técnico" en el contrato de Microsoft 365 u Office 365, incluyendo información que de otro modo se consideraría "datos de los clientes" o "datos personales".</span><span class="sxs-lookup"><span data-stu-id="aca34-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Captura de pantalla de la opción ofrecer comentarios en Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="aca34-111">**Inspeccion**</span><span class="sxs-lookup"><span data-stu-id="aca34-111">**Surveys**</span></span>

<span data-ttu-id="aca34-112">Los usuarios también pueden calificar su experiencia con Teams y enviarnos detalles sobre la clasificación que ofrecen.</span><span class="sxs-lookup"><span data-stu-id="aca34-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="aca34-113">Esta encuesta emergente se muestra a los usuarios de vez en cuando en Teams.</span><span class="sxs-lookup"><span data-stu-id="aca34-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="aca34-114">Cuando un usuario hace clic en **proporcionar comentarios** en la notificación, la encuesta se muestra para que se complete.</span><span class="sxs-lookup"><span data-stu-id="aca34-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Captura de pantalla de la notificación de encuesta y el formulario en Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="aca34-116">Establecer si los usuarios pueden enviar comentarios sobre equipos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="aca34-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="aca34-117">Como administrador, puede controlar si los usuarios de su organización pueden enviar comentarios sobre equipos a Microsoft mediante **comentarios** y si reciben la encuesta.</span><span class="sxs-lookup"><span data-stu-id="aca34-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="aca34-118">De forma predeterminada, a todos los usuarios de la organización se les asigna automáticamente la directiva global (opción predeterminada para toda la organización) y la característica **proporcionar comentarios** y la encuesta están habilitadas en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="aca34-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="aca34-119">La excepción es equipos para el ámbito educativo, donde las características están habilitadas para los profesores y deshabilitadas para los alumnos.</span><span class="sxs-lookup"><span data-stu-id="aca34-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="aca34-120">Puede editar la directiva global o crear y asignar una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="aca34-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="aca34-121">Después de modificar la directiva global o asignar una directiva personalizada, los cambios pueden demorar algunas horas en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="aca34-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="aca34-122">Supongamos, por ejemplo, que desea permitir que todos los usuarios de su organización envíen **comentarios y** reciban encuestas, excepto para los nuevos empleados en curso.</span><span class="sxs-lookup"><span data-stu-id="aca34-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="aca34-123">En este escenario, puede crear una directiva personalizada para desactivar ambas características y asignarla a nuevos empleados.</span><span class="sxs-lookup"><span data-stu-id="aca34-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="aca34-124">El resto de los usuarios de su organización obtienen la directiva global con las características activadas.</span><span class="sxs-lookup"><span data-stu-id="aca34-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="aca34-125">Las directivas de comentarios se administran mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aca34-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="aca34-126">Use el cmdlet **New-CsTeamsFeedbackPolicy** , *que se puede [encontrar aquí](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, para crear una directiva personalizada y el cmdlet **Grant-CsTeamsFeedbackPolicy** para asignarla a uno o más usuarios o grupos de usuarios, como un grupo de seguridad o un grupo de distribución.</span><span class="sxs-lookup"><span data-stu-id="aca34-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="aca34-127">Para desactivar y activar las características, establezca los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="aca34-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="aca34-128">**Enviar comentarios**: establezca el parámetro **userInitiatedMode** en **habilitado** para permitir a los usuarios a quienes les asignan Comentarios.</span><span class="sxs-lookup"><span data-stu-id="aca34-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="aca34-129">Establecer el parámetro en **deshabilitado** desactiva la característica y los usuarios a los que se les asigna la Directiva no tienen la opción de enviar comentarios.</span><span class="sxs-lookup"><span data-stu-id="aca34-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="aca34-130">**Encuestas**: establezca el parámetro **receiveSurveysMode** en **habilitado** para permitir que los usuarios a los que se les asigne la Directiva reciban la encuesta.</span><span class="sxs-lookup"><span data-stu-id="aca34-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="aca34-131">Para que los usuarios reciban la encuesta y les permita su cancelación, establezca el parámetro en **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="aca34-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="aca34-132">En Teams, los usuarios pueden ir a la **configuración**  >  **privacidad** y elegir si desean participar en encuestas.</span><span class="sxs-lookup"><span data-stu-id="aca34-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="aca34-133">Establecer el parámetro en **deshabilitado** desactiva la característica y los usuarios que tienen asignada la Directiva no recibirán la encuesta.</span><span class="sxs-lookup"><span data-stu-id="aca34-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="aca34-134">Crear una directiva personalizada de comentarios</span><span class="sxs-lookup"><span data-stu-id="aca34-134">Create a custom feedback policy</span></span>

<span data-ttu-id="aca34-135">En este ejemplo, creamos una política de comentarios denominada nueva Directiva de comentarios para empleados y desactivamos la posibilidad de enviar comentarios mediante **comentarios** y la encuesta.</span><span class="sxs-lookup"><span data-stu-id="aca34-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="aca34-136">Asignar una directiva personalizada de comentarios a los usuarios</span><span class="sxs-lookup"><span data-stu-id="aca34-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="aca34-137">En este ejemplo, asignamos una directiva personalizada denominada nueva Directiva de comentarios para el contrato a un usuario denominado usuario1.</span><span class="sxs-lookup"><span data-stu-id="aca34-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="aca34-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aca34-138">Related topics</span></span>

- [<span data-ttu-id="aca34-139">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="aca34-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="aca34-140">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="aca34-140">Assign policies to your users in Teams</span></span>](assign-policies.md)