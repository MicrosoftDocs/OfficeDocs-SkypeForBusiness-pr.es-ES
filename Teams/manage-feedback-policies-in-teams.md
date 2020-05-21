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
ms.openlocfilehash: b016a1d566f15cdabea55913b7fe107d86dee358
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326687"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="294cb-103">Administrar directivas de comentarios en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="294cb-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="294cb-104">Los usuarios de su organización pueden enviar comentarios acerca de Teams a Microsoft para saber cómo estamos haciendo, directamente desde el escritorio de Teams y los clientes Web.</span><span class="sxs-lookup"><span data-stu-id="294cb-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="294cb-105">Mejoramos continuamente la experiencia de los equipos y usamos estos comentarios para mejorar los equipos.</span><span class="sxs-lookup"><span data-stu-id="294cb-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

<span data-ttu-id="294cb-106">**La característica proporcionar comentarios**</span><span class="sxs-lookup"><span data-stu-id="294cb-106">**The Give feedback feature**</span></span>

<span data-ttu-id="294cb-107">Los usuarios pueden enviar comentarios y sugerencias sobre los equipos para que nos **ayuden**a  >  **proporcionar comentarios** en Teams.</span><span class="sxs-lookup"><span data-stu-id="294cb-107">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="294cb-108">Los datos enviados a través de enviar **comentarios** se consideran "datos de soporte técnico" en el acuerdo de Office 365, incluida información que de otro modo se consideraría "datos de los clientes" o "datos personales".</span><span class="sxs-lookup"><span data-stu-id="294cb-108">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Captura de pantalla de la opción ofrecer comentarios en Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="294cb-110">**Inspeccion**</span><span class="sxs-lookup"><span data-stu-id="294cb-110">**Surveys**</span></span>

<span data-ttu-id="294cb-111">Los usuarios también pueden calificar su experiencia con Teams y enviarnos detalles sobre la clasificación que ofrecen.</span><span class="sxs-lookup"><span data-stu-id="294cb-111">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="294cb-112">Esta encuesta emergente se muestra a los usuarios de vez en cuando en Teams.</span><span class="sxs-lookup"><span data-stu-id="294cb-112">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="294cb-113">Cuando un usuario hace clic en **proporcionar comentarios** en la notificación, la encuesta se muestra para que se complete.</span><span class="sxs-lookup"><span data-stu-id="294cb-113">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Captura de pantalla de la notificación de encuesta y el formulario en Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="294cb-115">Establecer si los usuarios pueden enviar comentarios sobre equipos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="294cb-115">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="294cb-116">Como administrador, puede controlar si los usuarios de su organización pueden enviar comentarios sobre equipos a Microsoft mediante **comentarios** y si reciben la encuesta.</span><span class="sxs-lookup"><span data-stu-id="294cb-116">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="294cb-117">De forma predeterminada, a todos los usuarios de la organización se les asigna automáticamente la directiva global (opción predeterminada para toda la organización) y la característica **proporcionar comentarios** y la encuesta están habilitadas en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="294cb-117">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="294cb-118">La excepción es equipos para el ámbito educativo, donde las características están habilitadas para los profesores y deshabilitadas para los alumnos.</span><span class="sxs-lookup"><span data-stu-id="294cb-118">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="294cb-119">Puede editar la directiva global o crear y asignar una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="294cb-119">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="294cb-120">Si un usuario tiene asignada una directiva personalizada, esa Directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="294cb-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="294cb-121">Si un usuario no tiene asignada una directiva personalizada, la política global se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="294cb-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="294cb-122">Después de modificar la directiva global o asignar una directiva, los cambios pueden demorar algunas horas en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="294cb-122">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="294cb-123">Supongamos, por ejemplo, que desea permitir que todos los usuarios de su organización envíen **comentarios y** reciban encuestas, excepto para los nuevos empleados en curso.</span><span class="sxs-lookup"><span data-stu-id="294cb-123">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="294cb-124">En este escenario, puede crear una directiva personalizada para desactivar ambas características y asignarla a nuevos empleados.</span><span class="sxs-lookup"><span data-stu-id="294cb-124">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="294cb-125">El resto de los usuarios de su organización obtienen la directiva global con las características activadas.</span><span class="sxs-lookup"><span data-stu-id="294cb-125">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="294cb-126">Use el cmdlet **New-CsTeamsFeedbackPolicy** , *que se puede [encontrar aquí](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, para crear una directiva personalizada y el cmdlet **Grant-CsTeamsFeedbackPolicy** para asignarla a uno o más usuarios o grupos de usuarios, como un grupo de seguridad o un grupo de distribución.</span><span class="sxs-lookup"><span data-stu-id="294cb-126">You use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="294cb-127">Para desactivar y activar las características, establezca los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="294cb-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="294cb-128">**Enviar comentarios**: establezca el parámetro **userInitiatedMode** en **habilitado** para permitir a los usuarios a quienes les asignan Comentarios.</span><span class="sxs-lookup"><span data-stu-id="294cb-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="294cb-129">Establecer el parámetro en **deshabilitado** desactiva la característica y los usuarios a los que se les asigna la Directiva no tienen la opción de enviar comentarios.</span><span class="sxs-lookup"><span data-stu-id="294cb-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="294cb-130">**Encuestas**: establezca el parámetro **receiveSurveysMode** en **habilitado** para permitir que los usuarios a los que se les asigne la Directiva reciban la encuesta.</span><span class="sxs-lookup"><span data-stu-id="294cb-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="294cb-131">Para que los usuarios reciban la encuesta y les permita su cancelación, establezca el parámetro en **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="294cb-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="294cb-132">En Teams, los usuarios pueden ir a la **configuración**  >  **privacidad** y elegir si desean participar en encuestas.</span><span class="sxs-lookup"><span data-stu-id="294cb-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="294cb-133">Establecer el parámetro en **deshabilitado** desactiva la característica y los usuarios que tienen asignada la Directiva no recibirán la encuesta.</span><span class="sxs-lookup"><span data-stu-id="294cb-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="294cb-134">Crear una directiva personalizada de comentarios</span><span class="sxs-lookup"><span data-stu-id="294cb-134">Create a custom feedback policy</span></span>

<span data-ttu-id="294cb-135">En este ejemplo, creamos una política de comentarios denominada nueva Directiva de comentarios para empleados y desactivamos la posibilidad de enviar comentarios mediante **comentarios** y la encuesta.</span><span class="sxs-lookup"><span data-stu-id="294cb-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="294cb-136">Asignar una directiva personalizada de comentarios</span><span class="sxs-lookup"><span data-stu-id="294cb-136">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="294cb-137">Asignar una directiva personalizada de comentarios a un usuario</span><span class="sxs-lookup"><span data-stu-id="294cb-137">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="294cb-138">En este ejemplo, asignamos una directiva personalizada denominada nueva Directiva de comentarios para el contrato a un usuario denominado usuario1.</span><span class="sxs-lookup"><span data-stu-id="294cb-138">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="294cb-139">Asignar una directiva de comentarios personalizada a los usuarios de un grupo</span><span class="sxs-lookup"><span data-stu-id="294cb-139">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="294cb-140">Es posible que desee asignar una directiva personalizada de comentarios a varios usuarios que ya haya identificado.</span><span class="sxs-lookup"><span data-stu-id="294cb-140">You may want to assign a custom feedback policy to multiple users that you've already identified.</span></span> <span data-ttu-id="294cb-141">Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="294cb-141">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="294cb-142">En este ejemplo, asignamos una directiva personalizada de comentarios denominada nueva política de comentarios de la contratación a todos los usuarios del grupo contoso New contratados.</span><span class="sxs-lookup"><span data-stu-id="294cb-142">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="294cb-143">Obtén la GroupObjectId del grupo en particular.</span><span class="sxs-lookup"><span data-stu-id="294cb-143">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="294cb-144">Obtener los miembros del grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="294cb-144">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="294cb-145">Asignar todos los usuarios del grupo a una política de comentarios determinada.</span><span class="sxs-lookup"><span data-stu-id="294cb-145">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="294cb-146">En este ejemplo, se trata de una nueva política de comentarios de los empleados.</span><span class="sxs-lookup"><span data-stu-id="294cb-146">In this example, it's New Hire Feedback Policy.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="294cb-147">Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="294cb-147">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="294cb-148">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="294cb-148">Related topics</span></span>

- [<span data-ttu-id="294cb-149">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="294cb-149">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
