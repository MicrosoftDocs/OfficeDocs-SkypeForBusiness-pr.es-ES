---
title: Estacionamiento y recuperación de llamadas en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar el parque de llamadas y recuperar para poner una llamada en espera en Microsoft Teams.
ms.openlocfilehash: 11c0abc5c9cd49a524417ce9706129cea9ccae1e
ms.sourcegitcommit: 84d99b266dea2a972774d781b92eccc67d6c197a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197585"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="273c0-103">Estacionamiento y recuperación de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="273c0-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="273c0-104">Parque de llamadas y recuperación es una característica que permite a un usuario realizar una llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="273c0-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="273c0-105">Cuando una llamada está estacionada, el servicio genera un código único para la recuperación de llamadas.</span><span class="sxs-lookup"><span data-stu-id="273c0-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="273c0-106">El usuario que estacionó la llamada u otra persona puede usar ese código con una aplicación o dispositivo compatible para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="273c0-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="273c0-107">(Vea [Estacionar una llamada en Teams para](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) obtener más información).</span><span class="sxs-lookup"><span data-stu-id="273c0-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="273c0-108">Algunos de los escenarios comunes para usar el parque de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="273c0-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="273c0-109">Un recepcionista aparca una llamada para alguien que trabaja en una fábrica.</span><span class="sxs-lookup"><span data-stu-id="273c0-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="273c0-110">A continuación, el recepcionista anunciará la llamada y el número de código a través del sistema de direcciones públicas.</span><span class="sxs-lookup"><span data-stu-id="273c0-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="273c0-111">A continuación, el usuario para el que se llama puede recoger un teléfono de Teams en el piso de fábrica y escribir el código para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="273c0-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="273c0-112">Un usuario aparca una llamada en un dispositivo móvil porque la batería del dispositivo se está quedando sin energía.</span><span class="sxs-lookup"><span data-stu-id="273c0-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="273c0-113">A continuación, el usuario puede escribir el código para recuperar la llamada desde un teléfono de escritorio de Teams.</span><span class="sxs-lookup"><span data-stu-id="273c0-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="273c0-114">Un representante de soporte técnico aparca una llamada de cliente y envía un anuncio en un canal de Teams para que un experto recupere la llamada y ayude al cliente.</span><span class="sxs-lookup"><span data-stu-id="273c0-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="273c0-115">Un experto escribe el código en los clientes de Teams para recuperar la llamada</span><span class="sxs-lookup"><span data-stu-id="273c0-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="273c0-116">Para estacionar y recuperar llamadas, un usuario debe ser Telefonía IP empresarial usuario y debe incluirse en una directiva de parque de llamadas.</span><span class="sxs-lookup"><span data-stu-id="273c0-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="273c0-117">El parque de llamadas y la recuperación solo está disponible en el modo de implementación solo de [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y no es compatible con los teléfonos IP de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="273c0-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="273c0-118">Configurar el parque de llamadas y recuperar</span><span class="sxs-lookup"><span data-stu-id="273c0-118">Configure call park and retrieve</span></span>

<span data-ttu-id="273c0-119">Debe ser administrador de Teams para configurar el parque de llamadas y recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="273c0-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="273c0-120">Está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="273c0-120">It is disabled by default.</span></span> <span data-ttu-id="273c0-121">Puede habilitarlo para los usuarios y crear grupos de usuarios con la directiva de parque de llamadas.</span><span class="sxs-lookup"><span data-stu-id="273c0-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="273c0-122">Al aplicar la misma directiva a un conjunto de usuarios, pueden estacionar y recuperar llamadas entre ellos.</span><span class="sxs-lookup"><span data-stu-id="273c0-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="273c0-123">Para habilitar una directiva de parque de llamadas</span><span class="sxs-lookup"><span data-stu-id="273c0-123">To enable a call park policy</span></span>

1. <span data-ttu-id="273c0-124">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de **parque**  >  **de llamadas de voz.**</span><span class="sxs-lookup"><span data-stu-id="273c0-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="273c0-125">En la **pestaña Administrar directivas,** haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="273c0-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="273c0-126">Asigne un nombre a la directiva y, a continuación, cambie **Permitir parque de llamadas** a **Activar**.</span><span class="sxs-lookup"><span data-stu-id="273c0-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Captura de pantalla de la configuración de directiva de parque de llamadas](media/call-park-add-policy.png)

4. <span data-ttu-id="273c0-128">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="273c0-128">Select **Save**.</span></span>

<span data-ttu-id="273c0-129">Para editar la directiva, selecciónelo en la lista y haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="273c0-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="273c0-130">Para que la directiva funcione, debe asignarse a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="273c0-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="273c0-131">Puede asignar [la directiva a los usuarios individualmente](assign-policies.md) o asignarla a un grupo.</span><span class="sxs-lookup"><span data-stu-id="273c0-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="273c0-132">Para asignar una directiva de parque de llamadas a un grupo</span><span class="sxs-lookup"><span data-stu-id="273c0-132">To assign a call park policy to a group</span></span>

1. <span data-ttu-id="273c0-133">En la página **Directivas de parque de** llamadas, en la pestaña **Asignación de** directivas de grupo, haga clic en Agregar **grupo.**</span><span class="sxs-lookup"><span data-stu-id="273c0-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="273c0-134">Busque el grupo que desea usar y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="273c0-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="273c0-135">Elija una clasificación en comparación con otras asignaciones de grupo.</span><span class="sxs-lookup"><span data-stu-id="273c0-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="273c0-136">En **Seleccionar una directiva,** elija la directiva a la que desea asignar este grupo.</span><span class="sxs-lookup"><span data-stu-id="273c0-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![imagen de directivas de parque](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="273c0-138">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="273c0-138">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="273c0-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="273c0-139">Related topics</span></span>

[<span data-ttu-id="273c0-140">Estacionar una llamada en Teams</span><span class="sxs-lookup"><span data-stu-id="273c0-140">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="273c0-141">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="273c0-141">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="273c0-142">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="273c0-142">New-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="273c0-143">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="273c0-143">Set-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="273c0-144">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="273c0-144">Grant-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)