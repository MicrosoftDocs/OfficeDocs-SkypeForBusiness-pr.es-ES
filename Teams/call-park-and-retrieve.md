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
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="f06be-103">Estacionamiento y recuperación de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f06be-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="f06be-104">Llamar a estacionamiento y recuperar es una característica que permite al usuario poner una llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="f06be-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="f06be-105">Cuando se aparca una llamada, el servicio genera un código único para la recuperación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f06be-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="f06be-106">El usuario que ha aparcado la llamada u otra persona puede usar ese código con una aplicación o dispositivo admitido para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="f06be-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="f06be-107">(Consulte [detener una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="f06be-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="f06be-108">Algunos de los escenarios comunes para usar el parque de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="f06be-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="f06be-109">Un recepcionista que recepcionista una llamada a alguien que trabaja en una fábrica.</span><span class="sxs-lookup"><span data-stu-id="f06be-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="f06be-110">El recepcionista anuncia entonces la llamada y el número de código en el sistema de dirección pública.</span><span class="sxs-lookup"><span data-stu-id="f06be-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="f06be-111">El usuario al que corresponde la llamada puede recoger un teléfono del equipo en la fábrica e introducir el código para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="f06be-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="f06be-112">Un usuario activa una llamada en un dispositivo móvil porque la batería del dispositivo se está agotando.</span><span class="sxs-lookup"><span data-stu-id="f06be-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="f06be-113">Después, el usuario puede introducir el código para recuperar la llamada desde un teléfono de escritorio de Teams.</span><span class="sxs-lookup"><span data-stu-id="f06be-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="f06be-114">Un representante de soporte técnico se apoya una llamada de cliente y envía un anuncio en un canal de Teams para que un experto pueda recuperar la llamada y ayudar al cliente.</span><span class="sxs-lookup"><span data-stu-id="f06be-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="f06be-115">Un experto escribe el código de los clientes de Teams para recuperar la llamada</span><span class="sxs-lookup"><span data-stu-id="f06be-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="f06be-116">Para detener y recuperar llamadas, un usuario debe ser un usuario de voz de empresa y debe estar incluido en una directiva de Parque de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f06be-116">To park and retrieve calls, a user must be an Enterprise Voice user and and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="f06be-117">La llamada en estacionamiento y recuperar solo está disponible en el [modo de implementación solo de Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y no es compatible con los teléfonos IP de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="f06be-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="f06be-118">Configurar el parque de llamadas y recuperar</span><span class="sxs-lookup"><span data-stu-id="f06be-118">Configure call park and retrieve</span></span>

<span data-ttu-id="f06be-119">Debe ser un administrador de equipo para configurar el parque de llamadas y recuperar.</span><span class="sxs-lookup"><span data-stu-id="f06be-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="f06be-120">Está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f06be-120">It is disabled by default.</span></span> <span data-ttu-id="f06be-121">Puede habilitarlo para los usuarios y crear grupos de usuarios con la Directiva de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f06be-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="f06be-122">Al aplicar la misma directiva a un conjunto de usuarios, pueden detenerse y recuperar llamadas entre sí.</span><span class="sxs-lookup"><span data-stu-id="f06be-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="f06be-123">Para habilitar una directiva de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="f06be-123">To enable a call park policy</span></span>

1. <span data-ttu-id="f06be-124">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de estacionamiento de llamadas**de voz.</span><span class="sxs-lookup"><span data-stu-id="f06be-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="f06be-125">En la pestaña **Administrar directivas** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f06be-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="f06be-126">Asigne un nombre a la Directiva y, a continuación, cambie **permitir el aparcamiento de llamadas** a **activado**.</span><span class="sxs-lookup"><span data-stu-id="f06be-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![Captura de pantalla de la configuración de directiva de estacionamiento de llamadas](media/call-park-add-policy.png)

4. <span data-ttu-id="f06be-128">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f06be-128">Select **Save**.</span></span>

<span data-ttu-id="f06be-129">Para editar la Directiva, selecciónela en la lista y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f06be-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="f06be-130">Para que la Directiva funcione, debe estar asignada a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f06be-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="f06be-131">Puede [asignar la Directiva a los usuarios individualmente](assign-policies.md) o asignarlos a un grupo.</span><span class="sxs-lookup"><span data-stu-id="f06be-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="f06be-132">Para asignar una directiva de papel de llamada a un grupo</span><span class="sxs-lookup"><span data-stu-id="f06be-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="f06be-133">En la página **directivas de estacionamiento** , en la pestaña asignación de directivas de **Grupo** , haga clic en **Agregar grupo**.</span><span class="sxs-lookup"><span data-stu-id="f06be-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="f06be-134">Busque el grupo que desea usar y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f06be-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="f06be-135">Elija un rango comparado con otras asignaciones de grupo.</span><span class="sxs-lookup"><span data-stu-id="f06be-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="f06be-136">En **seleccionar una directiva**, elija la Directiva a la que desea asignar este grupo.</span><span class="sxs-lookup"><span data-stu-id="f06be-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="f06be-137">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f06be-137">Click **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f06be-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f06be-138">Related topics</span></span>

[<span data-ttu-id="f06be-139">Detener una llamada en Teams</span><span class="sxs-lookup"><span data-stu-id="f06be-139">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="f06be-140">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="f06be-140">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="f06be-141">Nuevo: CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="f06be-141">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="f06be-142">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="f06be-142">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="f06be-143">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="f06be-143">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)