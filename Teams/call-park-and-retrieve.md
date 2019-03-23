---
title: Estacionamiento y recuperación de llamadas en Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 01/16/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Use estacionamiento y recuperación para realizar una llamada en espera en el servicio de los equipos en la nube.
ms.openlocfilehash: 416458b1f7c134fca3294107bd82bbd0f2300abc
ms.sourcegitcommit: 5ed00e911a151d3ab834528f121db8653c25dc12
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747657"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="2c1fc-103">Estacionamiento y recuperación de llamadas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2c1fc-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="2c1fc-104">Estacionamiento y recuperación es una característica que permite a un usuario realizar una llamada en espera en el servicio de los equipos en la nube.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="2c1fc-105">Cuando una llamada está estacionada, el servicio genera un código único para la recuperación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="2c1fc-106">El usuario que estacionar la llamada o a otro usuario, a continuación, puede utilizar ese código y aplicaciones compatibles o dispositivo para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="2c1fc-107">Algunos de los escenarios comunes para el uso de estacionamiento de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="2c1fc-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="2c1fc-108">Un recepcionista aparca una llamada de alguien que trabaje en una fábrica.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="2c1fc-109">La recepcionista anuncia a continuación, la llamada y el número de código a través del sistema de dirección pública.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="2c1fc-110">El usuario que la llamada es para, a continuación, puede elegir un teléfono de los equipos en la fábrica y escriba el código para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="2c1fc-111">Un usuario aparca una llamada en un dispositivo móvil debido a que la batería del dispositivo se está quedando sin energía.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="2c1fc-112">El usuario puede, a continuación, escriba, a continuación, el código para recuperar la llamada desde un teléfono de escritorio de los equipos.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-112">The user can then enter then code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="2c1fc-113">Un parques representante de soporte técnico un cliente de llamadas y envía un anuncio en un canal de los equipos de con un experto recuperar la llamada y ayudar al cliente.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="2c1fc-114">Con un experto entra en el código en los clientes de equipos para recuperar la llamada</span><span class="sxs-lookup"><span data-stu-id="2c1fc-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c1fc-115">Esta característica solo está disponible en el modo de implementación sólo de los equipos.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="2c1fc-116">Para obtener más detalles sobre los modos de implementación de los equipos, vea [Descripción de los equipos de Microsoft y Skype para la interoperabilidad y coexistencia de negocio](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="2c1fc-116">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="2c1fc-117">Se requiere una licencia</span><span class="sxs-lookup"><span data-stu-id="2c1fc-117">License required</span></span>

<span data-ttu-id="2c1fc-118">Para estacionar y recuperar las llamadas, un usuario debe ser un usuario de Enterprise Voice y un administrador debe conceder al usuario una directiva de estacionamiento de llamada.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="2c1fc-119">Para obtener más información sobre el modelo de licencias, vea [licencias de Office 365 para equipos de Microsoft](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="2c1fc-119">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="2c1fc-120">Estacionamiento y recuperación de disponibilidad de la característica</span><span class="sxs-lookup"><span data-stu-id="2c1fc-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="2c1fc-121">Estacionamiento y recuperación es compatible actualmente con los siguientes clientes y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="2c1fc-122">(Admite en el modo de sólo los equipos, con o sin conectividad RTC).</span><span class="sxs-lookup"><span data-stu-id="2c1fc-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="2c1fc-123">Capacidad</span><span class="sxs-lookup"><span data-stu-id="2c1fc-123">Capability</span></span> | <span data-ttu-id="2c1fc-124">Escritorio de los equipos</span><span class="sxs-lookup"><span data-stu-id="2c1fc-124">Teams Desktop</span></span> | <span data-ttu-id="2c1fc-125">Aplicación de Mac de los equipos</span><span class="sxs-lookup"><span data-stu-id="2c1fc-125">Teams Mac App</span></span> | <span data-ttu-id="2c1fc-126">Los equipos Web App (borde)</span><span class="sxs-lookup"><span data-stu-id="2c1fc-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="2c1fc-127">Los equipos móviles iOS y Android aplicación</span><span class="sxs-lookup"><span data-stu-id="2c1fc-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="2c1fc-128">Teléfono IP de los equipos</span><span class="sxs-lookup"><span data-stu-id="2c1fc-128">Teams IP phone</span></span> | <span data-ttu-id="2c1fc-129">Skype para teléfono IP empresarial</span><span class="sxs-lookup"><span data-stu-id="2c1fc-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="2c1fc-130">Estacionar una llamada</span><span class="sxs-lookup"><span data-stu-id="2c1fc-130">Park a call</span></span> | <span data-ttu-id="2c1fc-131">Sí</span><span class="sxs-lookup"><span data-stu-id="2c1fc-131">Yes</span></span> | <span data-ttu-id="2c1fc-132">Sí</span><span class="sxs-lookup"><span data-stu-id="2c1fc-132">Yes</span></span> | <span data-ttu-id="2c1fc-133">Sí</span><span class="sxs-lookup"><span data-stu-id="2c1fc-133">Yes</span></span> | <span data-ttu-id="2c1fc-134">Sí</span><span class="sxs-lookup"><span data-stu-id="2c1fc-134">Yes</span></span> | <span data-ttu-id="2c1fc-135">Próximamente</span><span class="sxs-lookup"><span data-stu-id="2c1fc-135">Coming soon</span></span>| <span data-ttu-id="2c1fc-136">No</span><span class="sxs-lookup"><span data-stu-id="2c1fc-136">No</span></span> |
| <span data-ttu-id="2c1fc-137">Recuperar una llamada estacionada</span><span class="sxs-lookup"><span data-stu-id="2c1fc-137">Retrieve a parked call</span></span> | <span data-ttu-id="2c1fc-138">Sí</span><span class="sxs-lookup"><span data-stu-id="2c1fc-138">Yes</span></span> | <span data-ttu-id="2c1fc-139">Sí</span><span class="sxs-lookup"><span data-stu-id="2c1fc-139">Yes</span></span> | <span data-ttu-id="2c1fc-140">Sí</span><span class="sxs-lookup"><span data-stu-id="2c1fc-140">Yes</span></span> | <span data-ttu-id="2c1fc-141">Sí</span><span class="sxs-lookup"><span data-stu-id="2c1fc-141">Yes</span></span> | <span data-ttu-id="2c1fc-142">Próximamente</span><span class="sxs-lookup"><span data-stu-id="2c1fc-142">Coming soon</span></span>| <span data-ttu-id="2c1fc-143">No</span><span class="sxs-lookup"><span data-stu-id="2c1fc-143">No</span></span> |
| <span data-ttu-id="2c1fc-144">Timbre de llamada reactivar recuperado atrás</span><span class="sxs-lookup"><span data-stu-id="2c1fc-144">Un-retrieved call ring back</span></span> | <span data-ttu-id="2c1fc-145">Sí</span><span class="sxs-lookup"><span data-stu-id="2c1fc-145">Yes</span></span> | <span data-ttu-id="2c1fc-146">Sí</span><span class="sxs-lookup"><span data-stu-id="2c1fc-146">Yes</span></span> | <span data-ttu-id="2c1fc-147">Sí</span><span class="sxs-lookup"><span data-stu-id="2c1fc-147">Yes</span></span> | <span data-ttu-id="2c1fc-148">Sí</span><span class="sxs-lookup"><span data-stu-id="2c1fc-148">Yes</span></span> | <span data-ttu-id="2c1fc-149">Próximamente</span><span class="sxs-lookup"><span data-stu-id="2c1fc-149">Coming soon</span></span>| <span data-ttu-id="2c1fc-150">No</span><span class="sxs-lookup"><span data-stu-id="2c1fc-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="2c1fc-151">Configuración de estacionamiento y recuperación</span><span class="sxs-lookup"><span data-stu-id="2c1fc-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="2c1fc-152">Debe ser un administrador para configurar estacionamiento y recuperación, y la característica está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="2c1fc-153">Puede habilitar para los usuarios y crear grupos de usuarios mediante la directiva de estacionamiento de llamada.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="2c1fc-154">Cuando se aplica la misma directiva a un conjunto de usuarios, podrán estacionar y recuperar las llamadas entre sí.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-154">When you apply the same policy to a set of users, they will be able to park and retrieve calls among themselves.</span></span> <span data-ttu-id="2c1fc-155">Para configurar el estacionamiento de llamadas para los usuarios y crear grupos de usuarios de estacionamiento de llamada, siga el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-155">To configure call park for users and create call park user groups, follow the procedure below.</span></span>

<span data-ttu-id="2c1fc-156">Para obtener información acerca de cómo usar el estacionamiento de llamadas y recuperar característica, vea [estacionamiento una llamada en los equipos](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="2c1fc-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="2c1fc-157">Asignar una directiva de estacionamiento de llamada</span><span class="sxs-lookup"><span data-stu-id="2c1fc-157">Assign a call park policy</span></span>

<span data-ttu-id="2c1fc-158">Siga estos pasos para asignar una directiva de estacionamiento de llamada a uno o varios usuarios:</span><span class="sxs-lookup"><span data-stu-id="2c1fc-158">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="2c1fc-159">Vaya al **Centro de administración de equipos de Microsoft** > **voz** > **las directivas de estacionamiento de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="2c1fc-160">Seleccione la directiva, haga clic en a la izquierda del nombre de la directiva.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-160">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="2c1fc-161">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-161">Select **Manage users**.</span></span>
4. <span data-ttu-id="2c1fc-162">En el panel **Administrar usuarios** , buscar el usuario por nombre para mostrar o por su nombre de usuario, seleccione el nombre y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-162">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="2c1fc-163">Repita este paso para cada usuario que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-163">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="2c1fc-164">Cuando haya terminado de agregar usuarios, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-164">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="2c1fc-165">Configurar el estacionamiento de llamadas y recuperar con PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c1fc-165">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="2c1fc-166">Use el cmdlet de PowerShell [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) para crear una directiva de estacionamiento de llamada.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-166">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="2c1fc-167">Use el cmdlet de PowerShell [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) para conceder una directiva de estacionamiento de llamada.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-167">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="2c1fc-168">Puede cambiar la configuración predeterminada mediante el uso [Conjunto CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="2c1fc-168">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="2c1fc-169">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="2c1fc-169">Troubleshooting</span></span>

<span data-ttu-id="2c1fc-170">Si los usuarios no pueden ver el estacionamiento de o recuperar botón:</span><span class="sxs-lookup"><span data-stu-id="2c1fc-170">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="2c1fc-171">Compruebe que el usuario tiene la directiva de estacionamiento de llamadas habilitada.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-171">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="2c1fc-172">Si un usuario intenta recuperar una llamada y no tiene éxito, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c1fc-172">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="2c1fc-173">Compruebe que el usuario está utilizando el cliente de los equipos o un teléfono o dispositivo habilitado para los equipos</span><span class="sxs-lookup"><span data-stu-id="2c1fc-173">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="2c1fc-174">¿Agrupación: es el usuario miembro del grupo de estacionamiento de llamada?</span><span class="sxs-lookup"><span data-stu-id="2c1fc-174">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="2c1fc-175">Modo de isla – estacionamiento y recuperación no está disponible en el modo de la isla de los equipos.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-175">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="2c1fc-176">La llamada ya se ha recuperado o terminada.</span><span class="sxs-lookup"><span data-stu-id="2c1fc-176">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="2c1fc-177">Más información</span><span class="sxs-lookup"><span data-stu-id="2c1fc-177">More information</span></span>

<span data-ttu-id="2c1fc-178">[Estacionamiento una llamada en los equipos](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="2c1fc-178">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>