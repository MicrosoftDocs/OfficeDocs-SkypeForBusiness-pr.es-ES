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
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar las directivas de comentarios para controlar si los usuarios de equipos de su organización pueden enviar comentarios sobre los equipos a Microsoft.
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2019
ms.locfileid: "35540956"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="606da-103">Administrar directivas de comentarios en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="606da-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="606da-104">Los usuarios pueden enviar comentarios y sugerencias sobre equipos a Microsoft para **ayudarle** > a**proporcionar comentarios** en los clientes de Teams.</span><span class="sxs-lookup"><span data-stu-id="606da-104">Users can send comments and suggestions about Teams to Microsoft by going to **Help** > **Give feedback** in the Teams clients.</span></span> <span data-ttu-id="606da-105">Mejoramos continuamente la experiencia de los equipos y usamos estos comentarios para mejorar los equipos.</span><span class="sxs-lookup"><span data-stu-id="606da-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

![Captura de pantalla de la opción ofrecer comentarios en Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="606da-107">Los datos enviados a través de enviar **comentarios** se consideran "datos de soporte técnico" en el acuerdo de Office 365, incluida información que de otro modo se consideraría "datos de los clientes" o "datos personales".</span><span class="sxs-lookup"><span data-stu-id="606da-107">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="606da-108">Establecer si los usuarios pueden enviar comentarios sobre equipos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="606da-108">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="606da-109">Como administrador, puede controlar si los usuarios de su organización pueden enviar comentarios sobre los equipos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="606da-109">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft.</span></span> <span data-ttu-id="606da-110">De forma predeterminada, a todos los usuarios de la organización se les asigna automáticamente la directiva global (opción predeterminada para toda la organización) y la característica está habilitada en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="606da-110">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the feature is enabled in the policy.</span></span> <span data-ttu-id="606da-111">La excepción es equipos para el ámbito educativo, donde la característica está habilitada para los profesores y deshabilitada para los alumnos.</span><span class="sxs-lookup"><span data-stu-id="606da-111">The exception is Teams for Education, where the feature is enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="606da-112">Puede editar la directiva global o crear y asignar una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="606da-112">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="606da-113">Si un usuario tiene asignada una directiva personalizada, esa Directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="606da-113">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="606da-114">Si un usuario no tiene asignada una directiva personalizada, la política global se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="606da-114">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="606da-115">Después de modificar la directiva global o asignar una directiva, los cambios pueden tardar hasta 24 horas en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="606da-115">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="606da-116">Supongamos, por ejemplo, que desea permitir que todos los usuarios de su organización envíen comentarios, excepto para nuevos empleados en curso.</span><span class="sxs-lookup"><span data-stu-id="606da-116">Say, for example, you want to allow all users in your organization to send feedback except for new hires in training.</span></span> <span data-ttu-id="606da-117">En este escenario, puede crear una directiva personalizada para desactivar la característica y asignarla a nuevos empleados.</span><span class="sxs-lookup"><span data-stu-id="606da-117">In this scenario, you create a custom policy to turn off the feature and assign it to new hires.</span></span> <span data-ttu-id="606da-118">El resto de los usuarios de su organización obtienen la directiva global con la característica activada.</span><span class="sxs-lookup"><span data-stu-id="606da-118">All other users in your organization get the global policy with the feature turned on.</span></span>  

<span data-ttu-id="606da-119">Use el cmdlet **New-CsTeamsFeedbackPolicy** para crear una directiva personalizada y el cmdlet **Grant-CsTeamsFeedbackPolicy** para asignarla a uno o más usuarios o grupos de usuarios, como un grupo de seguridad o un grupo de distribución.</span><span class="sxs-lookup"><span data-stu-id="606da-119">You use the **New-CsTeamsFeedbackPolicy** cmdlet to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> 

<span data-ttu-id="606da-120">Establezca el parámetro **userInitiatedMode** en **habilitado** para permitir que los usuarios a los que se les asigne la Directiva puedan enviar comentarios.</span><span class="sxs-lookup"><span data-stu-id="606da-120">Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="606da-121">Establecer el parámetro en \*\*\*\* deshabilitado desactiva la característica y los usuarios a los que se les asigna la Directiva no tienen la opción de enviar comentarios.</span><span class="sxs-lookup"><span data-stu-id="606da-121">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="606da-122">Crear una directiva personalizada de comentarios</span><span class="sxs-lookup"><span data-stu-id="606da-122">Create a custom feedback policy</span></span>

<span data-ttu-id="606da-123">En este ejemplo, creamos una política de comentarios denominada nueva Directiva de comentarios para empleados y desactivamos la posibilidad de enviar comentarios.</span><span class="sxs-lookup"><span data-stu-id="606da-123">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback.</span></span>

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="606da-124">Asignar una directiva personalizada de comentarios</span><span class="sxs-lookup"><span data-stu-id="606da-124">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="606da-125">Asignar una directiva personalizada de comentarios a un usuario</span><span class="sxs-lookup"><span data-stu-id="606da-125">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="606da-126">En este ejemplo, asignamos una directiva personalizada denominada nueva Directiva de comentarios para el contrato a un usuario denominado usuario1.</span><span class="sxs-lookup"><span data-stu-id="606da-126">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="606da-127">Asignar una directiva de comentarios personalizada a los usuarios de un grupo</span><span class="sxs-lookup"><span data-stu-id="606da-127">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="606da-128">Es posible que desee asignar una directiva personalizada de comentarios a varios usuarios que ya haya identificado.</span><span class="sxs-lookup"><span data-stu-id="606da-128">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="606da-129">Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="606da-129">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="606da-130">En este ejemplo, asignamos una directiva personalizada de comentarios denominada nueva política de comentarios de la contratación a todos los usuarios del grupo contoso New contratados.</span><span class="sxs-lookup"><span data-stu-id="606da-130">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="606da-131">Obtén la GroupObjectId del grupo en particular.</span><span class="sxs-lookup"><span data-stu-id="606da-131">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="606da-132">Obtener los miembros del grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="606da-132">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="606da-133">Asignar todos los usuarios del grupo a una política de comentarios determinada.</span><span class="sxs-lookup"><span data-stu-id="606da-133">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="606da-134">En este ejemplo, se trata de una nueva política de comentarios de los empleados.</span><span class="sxs-lookup"><span data-stu-id="606da-134">In this example, it's New Hire Feedback Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="606da-135">Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="606da-135">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="606da-136">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="606da-136">Related topics</span></span>

- [<span data-ttu-id="606da-137">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="606da-137">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)