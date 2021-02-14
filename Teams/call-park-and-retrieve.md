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
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424600"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="0770c-103">Estacionamiento y recuperación de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0770c-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="0770c-104">La característica de estacionar y recuperar llamadas es una característica que permite a un usuario poner una llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="0770c-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="0770c-105">Cuando una llamada está estacionada, el servicio genera un código único para la recuperación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0770c-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="0770c-106">El usuario que estacionó la llamada o cualquier otra persona puede usar ese código con una aplicación o dispositivo compatible para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="0770c-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="0770c-107">(Consulte [Estacione una llamada en Teams para](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) obtener más información).</span><span class="sxs-lookup"><span data-stu-id="0770c-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="0770c-108">Algunos de los escenarios comunes para usar el parque de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="0770c-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="0770c-109">Un parque de recepciones es una llamada para alguien que trabaja en una fábrica.</span><span class="sxs-lookup"><span data-stu-id="0770c-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="0770c-110">El recepcionista anunciará entonces la llamada y el número de código en el sistema de direcciones públicas.</span><span class="sxs-lookup"><span data-stu-id="0770c-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="0770c-111">El usuario para el que se llama puede elegir un teléfono de Teams en la planta de fábrica y escribir el código para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="0770c-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="0770c-112">Un parque de usuarios es una llamada en un dispositivo móvil porque la batería del dispositivo se está quedando sin energía.</span><span class="sxs-lookup"><span data-stu-id="0770c-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="0770c-113">Después, el usuario puede escribir el código para recuperar la llamada desde un teléfono de escritorio de Teams.</span><span class="sxs-lookup"><span data-stu-id="0770c-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="0770c-114">Un representante de soporte técnico llama a un cliente y envía un anuncio en un canal de Teams para que un experto recupere la llamada y ayude al cliente.</span><span class="sxs-lookup"><span data-stu-id="0770c-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="0770c-115">Un experto escribe el código en los clientes de Teams para recuperar la llamada</span><span class="sxs-lookup"><span data-stu-id="0770c-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="0770c-116">Para estacionar y recuperar llamadas, un usuario debe ser Telefonía IP empresarial usuario y debe incluirse en una directiva de parque de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0770c-116">To park and retrieve calls, a user must be an Enterprise Voice user and and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="0770c-117">El parque de llamadas y la recuperación solo está disponible en el modo de implementación [de Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y no es compatible con los teléfonos IP de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0770c-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="0770c-118">Configurar el parque de llamadas y recuperar</span><span class="sxs-lookup"><span data-stu-id="0770c-118">Configure call park and retrieve</span></span>

<span data-ttu-id="0770c-119">Debe ser administrador de Teams para configurar el parque de llamadas y recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="0770c-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="0770c-120">Está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0770c-120">It is disabled by default.</span></span> <span data-ttu-id="0770c-121">Puede habilitarlo para los usuarios y crear grupos de usuarios con la directiva de parque de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0770c-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="0770c-122">Cuando aplica la misma directiva a un conjunto de usuarios, estos pueden estacionar y recuperar llamadas entre ellos.</span><span class="sxs-lookup"><span data-stu-id="0770c-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="0770c-123">Para habilitar una directiva de parque de llamadas</span><span class="sxs-lookup"><span data-stu-id="0770c-123">To enable a call park policy</span></span>

1. <span data-ttu-id="0770c-124">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las directivas **del parque de** llamadas de  >  **voz.**</span><span class="sxs-lookup"><span data-stu-id="0770c-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="0770c-125">En la pestaña **Administrar directivas,** haga clic **en Agregar.**</span><span class="sxs-lookup"><span data-stu-id="0770c-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="0770c-126">Asigne un nombre a la directiva y, a continuación, cambie Permitir el **parque de llamadas** a **Activar.**</span><span class="sxs-lookup"><span data-stu-id="0770c-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Captura de pantalla de la configuración de directiva de parque de llamadas](media/call-park-add-policy.png)

4. <span data-ttu-id="0770c-128">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0770c-128">Select **Save**.</span></span>

<span data-ttu-id="0770c-129">Puede editar la directiva seleccionándosela en la lista y haciendo clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="0770c-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="0770c-130">Para que la directiva funcione, debe asignarse a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0770c-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="0770c-131">Puede asignar [la directiva a los usuarios individualmente](assign-policies.md) o asignarlos a un grupo.</span><span class="sxs-lookup"><span data-stu-id="0770c-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="0770c-132">Para asignar una directiva de elemento de llamada a un grupo</span><span class="sxs-lookup"><span data-stu-id="0770c-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="0770c-133">En la página **Directivas de parque de** llamadas, en la pestaña **Asignación de** directivas de grupo, haga clic en Agregar **grupo.**</span><span class="sxs-lookup"><span data-stu-id="0770c-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="0770c-134">Busque el grupo que desea usar y, a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="0770c-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="0770c-135">Elija una clasificación en comparación con otras tareas de grupo.</span><span class="sxs-lookup"><span data-stu-id="0770c-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="0770c-136">En **Seleccionar una directiva,** elija la directiva a la que desea asignar este grupo.</span><span class="sxs-lookup"><span data-stu-id="0770c-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="0770c-137">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="0770c-137">Click **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0770c-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0770c-138">Related topics</span></span>

[<span data-ttu-id="0770c-139">Estacionar una llamada en Teams</span><span class="sxs-lookup"><span data-stu-id="0770c-139">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="0770c-140">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="0770c-140">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="0770c-141">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="0770c-141">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="0770c-142">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="0770c-142">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="0770c-143">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="0770c-143">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)