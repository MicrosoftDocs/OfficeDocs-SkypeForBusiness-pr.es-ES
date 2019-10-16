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
f1keywords:
- ms.teamsadmincenter.callparkpolicies.overview
ms.custom:
- Phone System
description: Use estacionamiento y recuperar para poner una llamada en espera en el servicio de Teams en la nube.
ms.openlocfilehash: ab70832cde09cf5328e6fa0743c00614c839fc8d
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "37517034"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="bed6a-103">Estacionamiento y recuperación de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bed6a-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="bed6a-104">Llamar a estacionamiento y recuperar es una característica que permite al usuario poner una llamada en espera en el servicio de Teams en la nube.</span><span class="sxs-lookup"><span data-stu-id="bed6a-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="bed6a-105">Cuando se aparca una llamada, el servicio genera un código único para la recuperación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bed6a-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="bed6a-106">El usuario que ha aparcado la llamada u otra persona puede usar ese código y una aplicación o dispositivo admitido para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="bed6a-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="bed6a-107">Algunos de los escenarios comunes para usar el parque de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="bed6a-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="bed6a-108">Un recepcionista que recepcionista una llamada a alguien que trabaja en una fábrica.</span><span class="sxs-lookup"><span data-stu-id="bed6a-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="bed6a-109">El recepcionista anuncia entonces la llamada y el número de código en el sistema de dirección pública.</span><span class="sxs-lookup"><span data-stu-id="bed6a-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="bed6a-110">El usuario al que corresponde la llamada puede recoger un teléfono del equipo en la fábrica e introducir el código para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="bed6a-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="bed6a-111">Un usuario activa una llamada en un dispositivo móvil porque la batería del dispositivo se está agotando.</span><span class="sxs-lookup"><span data-stu-id="bed6a-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="bed6a-112">Después, el usuario puede introducir el código para recuperar la llamada desde un teléfono de escritorio de Teams.</span><span class="sxs-lookup"><span data-stu-id="bed6a-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="bed6a-113">Un representante de soporte técnico se apoya una llamada de cliente y envía un anuncio en un canal de Teams para que un experto pueda recuperar la llamada y ayudar al cliente.</span><span class="sxs-lookup"><span data-stu-id="bed6a-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="bed6a-114">Un experto escribe el código de los clientes de Teams para recuperar la llamada</span><span class="sxs-lookup"><span data-stu-id="bed6a-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bed6a-115">Esta característica solo está disponible en el modo de implementación solo para equipos.</span><span class="sxs-lookup"><span data-stu-id="bed6a-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="bed6a-116">Para obtener más información sobre los modos de implementación de Teams, consulte [comprender la coexistencia y la interoperabilidad de Microsoft Teams y Skype empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="bed6a-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="bed6a-117">Licencia requerida</span><span class="sxs-lookup"><span data-stu-id="bed6a-117">License required</span></span>

<span data-ttu-id="bed6a-118">Para detener y recuperar llamadas, un usuario debe ser un usuario de telefonía empresarial y un administrador debe concederle una directiva de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bed6a-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="bed6a-119">Para obtener más información sobre el modelo de licencias, consulte [licencias de Office 365 para Microsoft Teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="bed6a-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="bed6a-120">Llamar a estacionamiento y recuperar la disponibilidad de características</span><span class="sxs-lookup"><span data-stu-id="bed6a-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="bed6a-121">En la actualidad, los siguientes clientes y dispositivos son compatibles con la función deestacionamiento y recuperar.</span><span class="sxs-lookup"><span data-stu-id="bed6a-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="bed6a-122">(Compatible con el modo solo de Teams, con o sin conectividad RTC).</span><span class="sxs-lookup"><span data-stu-id="bed6a-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="bed6a-123">Capacidades</span><span class="sxs-lookup"><span data-stu-id="bed6a-123">Capability</span></span> | <span data-ttu-id="bed6a-124">Equipo de escritorio</span><span class="sxs-lookup"><span data-stu-id="bed6a-124">Teams Desktop</span></span> | <span data-ttu-id="bed6a-125">Aplicación de equipos Mac</span><span class="sxs-lookup"><span data-stu-id="bed6a-125">Teams Mac App</span></span> | <span data-ttu-id="bed6a-126">Teams Web App (Edge)</span><span class="sxs-lookup"><span data-stu-id="bed6a-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="bed6a-127">Teams Mobile iOS/aplicación para Android</span><span class="sxs-lookup"><span data-stu-id="bed6a-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="bed6a-128">Teléfono IP de Teams</span><span class="sxs-lookup"><span data-stu-id="bed6a-128">Teams IP phone</span></span> | <span data-ttu-id="bed6a-129">Teléfono IP de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="bed6a-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="bed6a-130">Detener una llamada</span><span class="sxs-lookup"><span data-stu-id="bed6a-130">Park a call</span></span> | <span data-ttu-id="bed6a-131">Sí</span><span class="sxs-lookup"><span data-stu-id="bed6a-131">Yes</span></span> | <span data-ttu-id="bed6a-132">Sí</span><span class="sxs-lookup"><span data-stu-id="bed6a-132">Yes</span></span> | <span data-ttu-id="bed6a-133">Sí</span><span class="sxs-lookup"><span data-stu-id="bed6a-133">Yes</span></span> | <span data-ttu-id="bed6a-134">Sí</span><span class="sxs-lookup"><span data-stu-id="bed6a-134">Yes</span></span> | <span data-ttu-id="bed6a-135">Próximamente</span><span class="sxs-lookup"><span data-stu-id="bed6a-135">Coming soon</span></span>| <span data-ttu-id="bed6a-136">No</span><span class="sxs-lookup"><span data-stu-id="bed6a-136">No</span></span> |
| <span data-ttu-id="bed6a-137">Recuperar una llamada estacionada</span><span class="sxs-lookup"><span data-stu-id="bed6a-137">Retrieve a parked call</span></span> | <span data-ttu-id="bed6a-138">Sí</span><span class="sxs-lookup"><span data-stu-id="bed6a-138">Yes</span></span> | <span data-ttu-id="bed6a-139">Sí</span><span class="sxs-lookup"><span data-stu-id="bed6a-139">Yes</span></span> | <span data-ttu-id="bed6a-140">Sí</span><span class="sxs-lookup"><span data-stu-id="bed6a-140">Yes</span></span> | <span data-ttu-id="bed6a-141">Sí</span><span class="sxs-lookup"><span data-stu-id="bed6a-141">Yes</span></span> | <span data-ttu-id="bed6a-142">Próximamente</span><span class="sxs-lookup"><span data-stu-id="bed6a-142">Coming soon</span></span>| <span data-ttu-id="bed6a-143">No</span><span class="sxs-lookup"><span data-stu-id="bed6a-143">No</span></span> |
| <span data-ttu-id="bed6a-144">Timbre de llamada no recuperado</span><span class="sxs-lookup"><span data-stu-id="bed6a-144">Unretrieved call ring back</span></span> | <span data-ttu-id="bed6a-145">Sí</span><span class="sxs-lookup"><span data-stu-id="bed6a-145">Yes</span></span> | <span data-ttu-id="bed6a-146">Sí</span><span class="sxs-lookup"><span data-stu-id="bed6a-146">Yes</span></span> | <span data-ttu-id="bed6a-147">Sí</span><span class="sxs-lookup"><span data-stu-id="bed6a-147">Yes</span></span> | <span data-ttu-id="bed6a-148">Sí</span><span class="sxs-lookup"><span data-stu-id="bed6a-148">Yes</span></span> | <span data-ttu-id="bed6a-149">Próximamente</span><span class="sxs-lookup"><span data-stu-id="bed6a-149">Coming soon</span></span>| <span data-ttu-id="bed6a-150">No</span><span class="sxs-lookup"><span data-stu-id="bed6a-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="bed6a-151">Configurar el parque de llamadas y recuperar</span><span class="sxs-lookup"><span data-stu-id="bed6a-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="bed6a-152">Debe ser administrador para configurar el parque de llamadas y recuperar, y la característica está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bed6a-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="bed6a-153">Puede habilitarlo para los usuarios y crear grupos de usuarios con la Directiva de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bed6a-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="bed6a-154">Al aplicar la misma directiva a un conjunto de usuarios, pueden detenerse y recuperar llamadas entre sí.</span><span class="sxs-lookup"><span data-stu-id="bed6a-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="bed6a-155">Para configurar el parque de llamadas para los usuarios y crear grupos de usuarios de estacionamiento de llamadas, siga el procedimiento [asignar una directiva de estacionamiento de llamadas](#assign-a-call-park-policy) que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="bed6a-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="bed6a-156">Para obtener más información sobre cómo usar la característica Parque de llamadas y recuperar, consulte [detener una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="bed6a-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="bed6a-157">Habilitar una directiva de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="bed6a-157">Enable a call park policy</span></span>

<span data-ttu-id="bed6a-158">Siga estos pasos para habilitar una directiva de estacionamiento de llamadas:</span><span class="sxs-lookup"><span data-stu-id="bed6a-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="bed6a-159"> > Vaya al **centro de administración de Microsoft Team\s\*\*\**directivas de estacionamiento de llamadas**de**voz** > .</span><span class="sxs-lookup"><span data-stu-id="bed6a-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="bed6a-160">Seleccione **nueva Directiva**.</span><span class="sxs-lookup"><span data-stu-id="bed6a-160">Select **New policy**.</span></span>
3. <span data-ttu-id="bed6a-161">Asigne un nombre a la Directiva y, a continuación, cambie **permitir el aparcamiento de llamadas** a **activado**.</span><span class="sxs-lookup"><span data-stu-id="bed6a-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="bed6a-162">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bed6a-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="bed6a-163">Asignar una directiva de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="bed6a-163">Assign a call park policy</span></span>

<span data-ttu-id="bed6a-164">Siga estos pasos para asignar una directiva de estacionamiento de llamadas a uno o más usuarios:</span><span class="sxs-lookup"><span data-stu-id="bed6a-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="bed6a-165"> > Vaya al **centro de administración de Microsoft Team\s\*\*\**directivas de estacionamiento de llamadas**de**voz** > .</span><span class="sxs-lookup"><span data-stu-id="bed6a-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="bed6a-166">Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="bed6a-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="bed6a-167">Seleccione **administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="bed6a-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="bed6a-168">En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bed6a-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="bed6a-169">Repita este paso para cada usuario que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="bed6a-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="bed6a-170">Cuando haya terminado de agregar usuarios, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bed6a-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="bed6a-171">Configurar el parque de llamadas y recuperar con PowerShell</span><span class="sxs-lookup"><span data-stu-id="bed6a-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="bed6a-172">Use el cmdlet [de PowerShell New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) para crear una directiva de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bed6a-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="bed6a-173">Use el cmdlet [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) de PowerShell para conceder una directiva de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bed6a-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="bed6a-174">Puede cambiar la configuración predeterminada con [set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="bed6a-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="bed6a-175">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="bed6a-175">Troubleshooting</span></span>

<span data-ttu-id="bed6a-176">Si los usuarios no pueden ver el botón detener o recuperar:</span><span class="sxs-lookup"><span data-stu-id="bed6a-176">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="bed6a-177">Compruebe que el usuario tiene habilitada la Directiva de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bed6a-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="bed6a-178">Si un usuario intenta recuperar una llamada y no se ha realizado correctamente, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bed6a-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="bed6a-179">Comprobar que el usuario está usando el cliente de Teams o un dispositivo/teléfono habilitado para Teams</span><span class="sxs-lookup"><span data-stu-id="bed6a-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="bed6a-180">Agrupación: ¿es el usuario miembro del grupo de estacionamiento de llamadas?</span><span class="sxs-lookup"><span data-stu-id="bed6a-180">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="bed6a-181">Modo isla: la llamada de estacionamiento y recuperar no está disponible en el modo isla de Teams.</span><span class="sxs-lookup"><span data-stu-id="bed6a-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="bed6a-182">Ya se ha recuperado o finalizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="bed6a-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="bed6a-183">Más información</span><span class="sxs-lookup"><span data-stu-id="bed6a-183">More information</span></span>

<span data-ttu-id="bed6a-184">[Estacione una llamada en Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="bed6a-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>