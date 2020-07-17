---
title: Estacionamiento y recuperación de llamadas en Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
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
description: Obtenga más información sobre cómo usar el servicio de atención telefónica y recuperar para poner una llamada en espera en el servicio de Teams en la nube.
ms.openlocfilehash: a9518705cd5edff3834be21732f78dd47352cd63
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938539"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="97e5a-103">Estacionamiento y recuperación de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="97e5a-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="97e5a-104">Llamar a estacionamiento y recuperar es una característica que permite al usuario poner una llamada en espera en el servicio de Teams en la nube.</span><span class="sxs-lookup"><span data-stu-id="97e5a-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="97e5a-105">Cuando se aparca una llamada, el servicio genera un código único para la recuperación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="97e5a-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="97e5a-106">El usuario que ha aparcado la llamada u otra persona puede usar ese código y una aplicación o dispositivo admitido para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="97e5a-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="97e5a-107">Algunos de los escenarios comunes para usar el parque de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="97e5a-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="97e5a-108">Un recepcionista que recepcionista una llamada a alguien que trabaja en una fábrica.</span><span class="sxs-lookup"><span data-stu-id="97e5a-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="97e5a-109">El recepcionista anuncia entonces la llamada y el número de código en el sistema de dirección pública.</span><span class="sxs-lookup"><span data-stu-id="97e5a-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="97e5a-110">El usuario al que corresponde la llamada puede recoger un teléfono del equipo en la fábrica e introducir el código para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="97e5a-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="97e5a-111">Un usuario activa una llamada en un dispositivo móvil porque la batería del dispositivo se está agotando.</span><span class="sxs-lookup"><span data-stu-id="97e5a-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="97e5a-112">Después, el usuario puede introducir el código para recuperar la llamada desde un teléfono de escritorio de Teams.</span><span class="sxs-lookup"><span data-stu-id="97e5a-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="97e5a-113">Un representante de soporte técnico se apoya una llamada de cliente y envía un anuncio en un canal de Teams para que un experto pueda recuperar la llamada y ayudar al cliente.</span><span class="sxs-lookup"><span data-stu-id="97e5a-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="97e5a-114">Un experto escribe el código de los clientes de Teams para recuperar la llamada</span><span class="sxs-lookup"><span data-stu-id="97e5a-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97e5a-115">Esta característica solo está disponible en el modo de implementación solo para equipos.</span><span class="sxs-lookup"><span data-stu-id="97e5a-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="97e5a-116">Para obtener más información sobre los modos de implementación de Teams, consulte [comprender la coexistencia y la interoperabilidad de Microsoft Teams y Skype empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="97e5a-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="97e5a-117">Licencia requerida</span><span class="sxs-lookup"><span data-stu-id="97e5a-117">License required</span></span>

<span data-ttu-id="97e5a-118">Para detener y recuperar llamadas, un usuario debe ser un usuario de telefonía empresarial y un administrador debe concederle una directiva de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="97e5a-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="97e5a-119">Para obtener más información sobre el modelo de licencias, vea [Descripción del servicio Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="97e5a-119">For more information about the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="97e5a-120">Llamar a estacionamiento y recuperar la disponibilidad de características</span><span class="sxs-lookup"><span data-stu-id="97e5a-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="97e5a-121">En la actualidad, los siguientes clientes y dispositivos son compatibles con la función deestacionamiento y recuperar.</span><span class="sxs-lookup"><span data-stu-id="97e5a-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="97e5a-122">(Compatible con el modo solo de Teams, con o sin conectividad RTC).</span><span class="sxs-lookup"><span data-stu-id="97e5a-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="97e5a-123">Función</span><span class="sxs-lookup"><span data-stu-id="97e5a-123">Capability</span></span> | <span data-ttu-id="97e5a-124">Equipo de escritorio</span><span class="sxs-lookup"><span data-stu-id="97e5a-124">Teams Desktop</span></span> | <span data-ttu-id="97e5a-125">Aplicación de equipos Mac</span><span class="sxs-lookup"><span data-stu-id="97e5a-125">Teams Mac App</span></span> | <span data-ttu-id="97e5a-126">Teams Web App (Edge)</span><span class="sxs-lookup"><span data-stu-id="97e5a-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="97e5a-127">Teams Mobile iOS/aplicación para Android</span><span class="sxs-lookup"><span data-stu-id="97e5a-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="97e5a-128">Teléfono IP de Teams</span><span class="sxs-lookup"><span data-stu-id="97e5a-128">Teams IP phone</span></span> | <span data-ttu-id="97e5a-129">Teléfono IP de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="97e5a-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="97e5a-130">Detener una llamada</span><span class="sxs-lookup"><span data-stu-id="97e5a-130">Park a call</span></span> | <span data-ttu-id="97e5a-131">Sí </span><span class="sxs-lookup"><span data-stu-id="97e5a-131">Yes</span></span> | <span data-ttu-id="97e5a-132">Sí </span><span class="sxs-lookup"><span data-stu-id="97e5a-132">Yes</span></span> | <span data-ttu-id="97e5a-133">Sí </span><span class="sxs-lookup"><span data-stu-id="97e5a-133">Yes</span></span> | <span data-ttu-id="97e5a-134">Sí </span><span class="sxs-lookup"><span data-stu-id="97e5a-134">Yes</span></span> | <span data-ttu-id="97e5a-135">Sí</span><span class="sxs-lookup"><span data-stu-id="97e5a-135">Yes</span></span> | <span data-ttu-id="97e5a-136">No</span><span class="sxs-lookup"><span data-stu-id="97e5a-136">No</span></span> |
| <span data-ttu-id="97e5a-137">Recuperar una llamada estacionada</span><span class="sxs-lookup"><span data-stu-id="97e5a-137">Retrieve a parked call</span></span> | <span data-ttu-id="97e5a-138">Sí </span><span class="sxs-lookup"><span data-stu-id="97e5a-138">Yes</span></span> | <span data-ttu-id="97e5a-139">Sí </span><span class="sxs-lookup"><span data-stu-id="97e5a-139">Yes</span></span> | <span data-ttu-id="97e5a-140">Sí </span><span class="sxs-lookup"><span data-stu-id="97e5a-140">Yes</span></span> | <span data-ttu-id="97e5a-141">Sí </span><span class="sxs-lookup"><span data-stu-id="97e5a-141">Yes</span></span> | <span data-ttu-id="97e5a-142">Sí</span><span class="sxs-lookup"><span data-stu-id="97e5a-142">Yes</span></span> | <span data-ttu-id="97e5a-143">No</span><span class="sxs-lookup"><span data-stu-id="97e5a-143">No</span></span> |
| <span data-ttu-id="97e5a-144">Timbre de llamada no recuperado</span><span class="sxs-lookup"><span data-stu-id="97e5a-144">Unretrieved call ring back</span></span> | <span data-ttu-id="97e5a-145">Sí </span><span class="sxs-lookup"><span data-stu-id="97e5a-145">Yes</span></span> | <span data-ttu-id="97e5a-146">Sí </span><span class="sxs-lookup"><span data-stu-id="97e5a-146">Yes</span></span> | <span data-ttu-id="97e5a-147">Sí </span><span class="sxs-lookup"><span data-stu-id="97e5a-147">Yes</span></span> | <span data-ttu-id="97e5a-148">Sí </span><span class="sxs-lookup"><span data-stu-id="97e5a-148">Yes</span></span> | <span data-ttu-id="97e5a-149">Sí</span><span class="sxs-lookup"><span data-stu-id="97e5a-149">Yes</span></span> | <span data-ttu-id="97e5a-150">No</span><span class="sxs-lookup"><span data-stu-id="97e5a-150">No</span></span> |

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="97e5a-151">Configurar el parque de llamadas y recuperar</span><span class="sxs-lookup"><span data-stu-id="97e5a-151">Configure call park and retrieve</span></span>

<span data-ttu-id="97e5a-152">Debe ser administrador para configurar el parque de llamadas y recuperar, y la característica está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="97e5a-152">You must be an admin to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="97e5a-153">Puede habilitarlo para los usuarios y crear grupos de usuarios con la Directiva de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="97e5a-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="97e5a-154">Al aplicar la misma directiva a un conjunto de usuarios, pueden detenerse y recuperar llamadas entre sí.</span><span class="sxs-lookup"><span data-stu-id="97e5a-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="97e5a-155">Para configurar el parque de llamadas para los usuarios y crear grupos de usuarios de estacionamiento de llamadas, siga el procedimiento [asignar una directiva de estacionamiento de llamadas](#assign-a-call-park-policy) que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="97e5a-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="97e5a-156">Para obtener más información sobre cómo usar la característica Parque de llamadas y recuperar, consulte [detener una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="97e5a-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="97e5a-157">Habilitar una directiva de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="97e5a-157">Enable a call park policy</span></span>

1. <span data-ttu-id="97e5a-158">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de estacionamiento de llamadas**de voz.</span><span class="sxs-lookup"><span data-stu-id="97e5a-158">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="97e5a-159">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="97e5a-159">Select **Add**.</span></span>
3. <span data-ttu-id="97e5a-160">Asigne un nombre a la Directiva y, a continuación, cambie **permitir el aparcamiento de llamadas** a **activado**.</span><span class="sxs-lookup"><span data-stu-id="97e5a-160">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>
4. <span data-ttu-id="97e5a-161">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="97e5a-161">Select **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="97e5a-162">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="97e5a-162">Using PowerShell</span></span>

<span data-ttu-id="97e5a-163">Vea [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="97e5a-163">See [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span></span>

### <a name="edit-a-call-park-policy"></a><span data-ttu-id="97e5a-164">Editar una directiva de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="97e5a-164">Edit a call park policy</span></span>

1. <span data-ttu-id="97e5a-165">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de estacionamiento de llamadas**de voz.</span><span class="sxs-lookup"><span data-stu-id="97e5a-165">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="97e5a-166">Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="97e5a-166">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="97e5a-167">Cambie **permitir** que el parque de llamadas esté **desactivado** o **activado**.</span><span class="sxs-lookup"><span data-stu-id="97e5a-167">Switch **Allow call park** to **Off** or **On**.</span></span>
4. <span data-ttu-id="97e5a-168">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="97e5a-168">Click **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="97e5a-169">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="97e5a-169">Using PowerShell</span></span>

<span data-ttu-id="97e5a-170">Consulte [set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="97e5a-170">See [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span></span> <span data-ttu-id="97e5a-171">Por ejemplo, para cambiar la configuración predeterminada, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="97e5a-171">For example, to change the default setting, run the following:</span></span>

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="97e5a-172">Asignar una directiva de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="97e5a-172">Assign a call park policy</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
<span data-ttu-id="97e5a-173">Consulte también [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="97e5a-173">See also [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="97e5a-174">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="97e5a-174">Troubleshooting</span></span>

<span data-ttu-id="97e5a-175">Si los usuarios no pueden ver el botón detener o recuperar:</span><span class="sxs-lookup"><span data-stu-id="97e5a-175">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="97e5a-176">Compruebe que el usuario tiene habilitada la Directiva de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="97e5a-176">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="97e5a-177">Si un usuario intenta recuperar una llamada y no se ha realizado correctamente, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="97e5a-177">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="97e5a-178">Comprobar que el usuario está usando el cliente de Teams o un dispositivo/teléfono habilitado para Teams</span><span class="sxs-lookup"><span data-stu-id="97e5a-178">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="97e5a-179">Agrupación: el usuario es miembro del grupo de estacionamiento de llamada, que se basa en que los mismos equipos tienen asignada la política de estacionamiento.</span><span class="sxs-lookup"><span data-stu-id="97e5a-179">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="97e5a-180">Modo isla: la llamada de estacionamiento y recuperar no está disponible en el modo isla de Teams.</span><span class="sxs-lookup"><span data-stu-id="97e5a-180">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="97e5a-181">Ya se ha recuperado o finalizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="97e5a-181">The call has already been retrieved or terminated.</span></span>

## <a name="related-topics"></a><span data-ttu-id="97e5a-182">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="97e5a-182">Related topics</span></span>

[<span data-ttu-id="97e5a-183">Detener una llamada en Teams</span><span class="sxs-lookup"><span data-stu-id="97e5a-183">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="97e5a-184">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="97e5a-184">Assign policies to your users in Teams</span></span>](assign-policies.md)
