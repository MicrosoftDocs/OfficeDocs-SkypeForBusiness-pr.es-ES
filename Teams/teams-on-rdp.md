---
title: Usar Teams con servicios de escritorio remoto
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar Microsoft Teams con servicios de escritorio remoto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7090aac3c5e7ff724a079e7f9d9ffe9d712cd447
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119099"
---
# <a name="teams-in-remote-desktop-services"></a><span data-ttu-id="780ae-103">Teams en Servicios de escritorio remoto</span><span class="sxs-lookup"><span data-stu-id="780ae-103">Teams in Remote Desktop Services</span></span>

<span data-ttu-id="780ae-104">En este artículo se describen los requisitos y limitaciones para usar Microsoft Teams en un entorno de servicios de escritorio remoto (RDS).</span><span class="sxs-lookup"><span data-stu-id="780ae-104">This article describes the requirements and limitations for using Microsoft Teams in a remote desktop services (RDS) environment.</span></span>

## <a name="what-is-rds"></a><span data-ttu-id="780ae-105">¿Qué es RDS?</span><span class="sxs-lookup"><span data-stu-id="780ae-105">What is RDS?</span></span>

<span data-ttu-id="780ae-106">Servicios de escritorio remoto (RDS) es la plataforma de elección para crear soluciones de virtualización para cada necesidad del cliente final.</span><span class="sxs-lookup"><span data-stu-id="780ae-106">Remote Desktop Services (RDS) is the platform of choice for building virtualization solutions for every end customer need.</span></span> <span data-ttu-id="780ae-107">RDS le permite ofrecer aplicaciones virtualizadas individuales, proporcionar acceso de escritorio remoto y móvil seguro y proporcionar a los usuarios finales la capacidad de ejecutar sus aplicaciones y escritorios desde la nube.</span><span class="sxs-lookup"><span data-stu-id="780ae-107">RDS lets you deliver individual virtualized applications, provide secure mobile and remote desktop access, and provide end users the ability to run their applications and desktops from the cloud.</span></span>

<span data-ttu-id="780ae-108">RDS ofrece flexibilidad de implementación, eficiencia de costos y extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="780ae-108">RDS offers deployment flexibility, cost efficiency, and extensibility.</span></span> <span data-ttu-id="780ae-109">RDS se entrega a través de una variedad de opciones de implementación, como Windows Server 2016 para implementaciones locales, Microsoft Azure para implementaciones en la nube y una sólida matriz de soluciones de partners.</span><span class="sxs-lookup"><span data-stu-id="780ae-109">RDS is delivered through a variety of deployment options, including Windows Server 2016 for on-premises deployments, Microsoft Azure for cloud deployments, and a robust array of partner solutions.</span></span>
<span data-ttu-id="780ae-110">Según su entorno y preferencias, puede configurar la solución RDS para la virtualización basada en sesión, como una infraestructura de escritorio virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="780ae-110">Depending on your environment and preferences, you can set up the RDS solution for session-based virtualization, as a virtual desktop infrastructure (VDI)</span></span>

<span data-ttu-id="780ae-111">Actualmente, Teams en un entorno de servicios de escritorio remoto está disponible con soporte para la colaboración y la funcionalidad de chat.</span><span class="sxs-lookup"><span data-stu-id="780ae-111">Currently, Teams in a remote desktop services environment is available with support for collaboration and chat functionality.</span></span> <span data-ttu-id="780ae-112">Para garantizar una experiencia de usuario óptima, siga las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="780ae-112">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-rds-with-chat-and-collaboration"></a><span data-ttu-id="780ae-113">Teams en RDS con chat y colaboración</span><span class="sxs-lookup"><span data-stu-id="780ae-113">Teams on RDS with chat and collaboration</span></span>

<span data-ttu-id="780ae-114">Si su organización solo quiere usar las características de chat y colaboración en Teams, puede establecer directivas de nivel de usuario para desactivar la funcionalidad de llamadas y reuniones en Teams.</span><span class="sxs-lookup"><span data-stu-id="780ae-114">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="780ae-115">Establecer directivas para desactivar la funcionalidad de llamadas y reuniones</span><span class="sxs-lookup"><span data-stu-id="780ae-115">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="780ae-116">Puede establecer directivas mediante el Centro de administración de Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="780ae-116">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="780ae-117">Los cambios de directiva pueden tardar algún tiempo (unas horas) en propagarse.</span><span class="sxs-lookup"><span data-stu-id="780ae-117">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="780ae-118">Si no ve cambios para una cuenta determinada inmediatamente, inténtelo de nuevo en unas horas.</span><span class="sxs-lookup"><span data-stu-id="780ae-118">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="780ae-119">[**Directivas de llamadas:**](teams-calling-policy.md)Teams incluye la directiva de llamadas Desautorizado integrada, en la que todas las características de llamadas están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="780ae-119">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="780ae-120">Asigne la directiva DisallowCalling a todos los usuarios de su organización que usen Teams en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="780ae-120">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="780ae-121">[**Directivas de reunión:**](meeting-policies-in-teams.md)Teams incluye la directiva de reunión de AllOff integrada, en la que todas las características de la reunión están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="780ae-121">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="780ae-122">Asigne la directiva AllOff a todos los usuarios de su organización que usen Teams en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="780ae-122">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="780ae-123">Asignar directivas con el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="780ae-123">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="780ae-124">Para asignar la directiva de llamadas Desautorizado y la directiva de reunión AllOff a un usuario:</span><span class="sxs-lookup"><span data-stu-id="780ae-124">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="780ae-125">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios.**</span><span class="sxs-lookup"><span data-stu-id="780ae-125">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="780ae-126">Seleccione el usuario seleccionando a la izquierda del nombre de usuario y, a continuación, **seleccione Editar configuración.**</span><span class="sxs-lookup"><span data-stu-id="780ae-126">Select the user by selecting to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="780ae-127">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="780ae-127">Do the following steps:</span></span>

    <span data-ttu-id="780ae-128">a.</span><span class="sxs-lookup"><span data-stu-id="780ae-128">a.</span></span>  <span data-ttu-id="780ae-129">En **Directiva de llamadas,** seleccione **No permitir La llamada**.</span><span class="sxs-lookup"><span data-stu-id="780ae-129">Under **Calling policy**, select **DisallowCalling**.</span></span>

    <span data-ttu-id="780ae-130">b.</span><span class="sxs-lookup"><span data-stu-id="780ae-130">b.</span></span>  <span data-ttu-id="780ae-131">En **Directiva de reunión,** seleccione **AllOff**.</span><span class="sxs-lookup"><span data-stu-id="780ae-131">Under **Meeting policy**, select **AllOff**.</span></span>

4. <span data-ttu-id="780ae-132">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="780ae-132">Select **Apply**.</span></span>

<span data-ttu-id="780ae-133">Para asignar una directiva a varios usuarios a la vez:</span><span class="sxs-lookup"><span data-stu-id="780ae-133">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="780ae-134">En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Usuarios**, después, busque los usuarios o filtre la vista para mostrar los usuarios que desee.</span><span class="sxs-lookup"><span data-stu-id="780ae-134">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="780ae-135">En la columna **&#x2713;** (marca de verificación), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="780ae-135">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="780ae-136">Para seleccionar todos los usuarios, seleccione &#x2713; (marca de verificación) en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="780ae-136">To select all users, select the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="780ae-137">Seleccione **Editar configuración,** realice los cambios que desee y, a continuación, **seleccione Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="780ae-137">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="780ae-138">O bien, también puede realizar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="780ae-138">Or, you can also do the following steps:</span></span>

1. <span data-ttu-id="780ae-139">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="780ae-139">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="780ae-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="780ae-140">For example:</span></span>

    - <span data-ttu-id="780ae-141">Vaya a **Directivas de**  >  **llamadas de** voz y, a continuación, seleccione No permitir la **llamada.**</span><span class="sxs-lookup"><span data-stu-id="780ae-141">Go to **Voice** > **Calling policies**, and then select **DisallowCalling**.</span></span>
    - <span data-ttu-id="780ae-142">Vaya a **Directivas de reunión** de  >  **reuniones** y, a continuación, seleccione **AllOff**.</span><span class="sxs-lookup"><span data-stu-id="780ae-142">Go to **Meetings** > **Meeting policies**, and then select **AllOff**.</span></span>

2. <span data-ttu-id="780ae-143">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="780ae-143">Select **Manage users**.</span></span>
3. <span data-ttu-id="780ae-144">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="780ae-144">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="780ae-145">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="780ae-145">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="780ae-146">Cuando haya terminado de agregar usuarios, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="780ae-146">When you're finished adding users, select **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="780ae-147">Asignar directivas con PowerShell</span><span class="sxs-lookup"><span data-stu-id="780ae-147">Assign policies using PowerShell</span></span>

<span data-ttu-id="780ae-148">En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para asignar la directiva de llamadas Desautor a un usuario.</span><span class="sxs-lookup"><span data-stu-id="780ae-148">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="780ae-149">Para obtener más información sobre el uso de PowerShell para administrar directivas de llamadas, vea [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="780ae-149">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="780ae-150">En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para asignar la directiva de reunión AllOff a un usuario.</span><span class="sxs-lookup"><span data-stu-id="780ae-150">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="780ae-151">Para obtener más información sobre el uso de PowerShell para administrar directivas de reunión, vea [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="780ae-151">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>