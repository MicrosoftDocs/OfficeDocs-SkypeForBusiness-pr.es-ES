---
title: Estacionamiento y recuperación en Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/17/2018
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Use estacionamiento y recuperación para realizar una llamada en espera en el servicio de los equipos en la nube.
ms.openlocfilehash: 004a5b12e178a6460ef05f7c6f5c5738c8ced042
ms.sourcegitcommit: 0e671e6e6fdd25227068c7e3a3a5509b6536d2b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2018
ms.locfileid: "27294191"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="79acd-103">Estacionamiento y recuperación en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79acd-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="79acd-104">Estacionamiento y recuperación es una característica que permite a un usuario realizar una llamada en espera en el servicio de los equipos en la nube.</span><span class="sxs-lookup"><span data-stu-id="79acd-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="79acd-105">Cuando una llamada está estacionada, el servicio genera un código único para la recuperación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="79acd-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="79acd-106">El usuario que estacionar la llamada o a otro usuario, a continuación, puede utilizar ese código y aplicaciones compatibles o dispositivo para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="79acd-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="79acd-107">Algunos de los escenarios comunes para el uso de estacionamiento de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="79acd-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="79acd-108">Un recepcionista aparca una llamada de alguien que trabaje en una fábrica.</span><span class="sxs-lookup"><span data-stu-id="79acd-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="79acd-109">La recepcionista anuncia a continuación, la llamada y el número de código a través del sistema de dirección pública.</span><span class="sxs-lookup"><span data-stu-id="79acd-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="79acd-110">El usuario que la llamada es para, a continuación, puede elegir un teléfono de los equipos en la fábrica y escriba el código para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="79acd-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="79acd-111">Un usuario aparca una llamada en un dispositivo móvil debido a que la batería del dispositivo se está quedando sin energía.</span><span class="sxs-lookup"><span data-stu-id="79acd-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="79acd-112">El usuario puede, a continuación, escriba, a continuación, el código para recuperar la llamada desde un teléfono de escritorio de los equipos.</span><span class="sxs-lookup"><span data-stu-id="79acd-112">The user can then enter then code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="79acd-113">Un parques representante de soporte técnico un cliente de llamadas y envía un anuncio en un canal de los equipos de con un experto recuperar la llamada y ayudar al cliente.</span><span class="sxs-lookup"><span data-stu-id="79acd-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="79acd-114">Con un experto entra en el código en los clientes de equipos para recuperar la llamada</span><span class="sxs-lookup"><span data-stu-id="79acd-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79acd-115">Esta característica solo está disponible en el modo de implementación sólo de los equipos.</span><span class="sxs-lookup"><span data-stu-id="79acd-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="79acd-116">Para obtener más detalles sobre los modos de implementación de los equipos, vea [Descripción de los equipos de Microsoft y Skype para la interoperabilidad y coexistencia de negocio](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="79acd-116">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="79acd-117">Se requiere una licencia</span><span class="sxs-lookup"><span data-stu-id="79acd-117">License required</span></span>

<span data-ttu-id="79acd-118">Para estacionar y recuperar las llamadas, un usuario debe ser un usuario de Enterprise Voice y un administrador debe conceder al usuario una directiva de estacionamiento de llamada.</span><span class="sxs-lookup"><span data-stu-id="79acd-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="79acd-119">Para obtener más información sobre el modelo de licencias, vea [licencias de Office 365 para equipos de Microsoft](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="79acd-119">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="79acd-120">Estacionamiento y recuperación de disponibilidad de la característica</span><span class="sxs-lookup"><span data-stu-id="79acd-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="79acd-121">Estacionamiento y recuperación es compatible actualmente con los siguientes clientes y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="79acd-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="79acd-122">(Admite en el modo de sólo los equipos, con o sin conectividad RTC).</span><span class="sxs-lookup"><span data-stu-id="79acd-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="79acd-123">Capacidad</span><span class="sxs-lookup"><span data-stu-id="79acd-123">Capability</span></span> | <span data-ttu-id="79acd-124">Escritorio de los equipos</span><span class="sxs-lookup"><span data-stu-id="79acd-124">Teams Desktop</span></span> | <span data-ttu-id="79acd-125">Aplicación de Mac de los equipos</span><span class="sxs-lookup"><span data-stu-id="79acd-125">Teams Mac App</span></span> | <span data-ttu-id="79acd-126">Los equipos Web App (borde)</span><span class="sxs-lookup"><span data-stu-id="79acd-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="79acd-127">Los equipos móviles iOS y Android aplicación</span><span class="sxs-lookup"><span data-stu-id="79acd-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="79acd-128">Teléfono IP de los equipos</span><span class="sxs-lookup"><span data-stu-id="79acd-128">Teams IP phone</span></span> | <span data-ttu-id="79acd-129">Skype para teléfono IP empresarial</span><span class="sxs-lookup"><span data-stu-id="79acd-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="79acd-130">Estacionar una llamada</span><span class="sxs-lookup"><span data-stu-id="79acd-130">Park a call</span></span> | <span data-ttu-id="79acd-131">Sí</span><span class="sxs-lookup"><span data-stu-id="79acd-131">Yes</span></span> | <span data-ttu-id="79acd-132">Sí</span><span class="sxs-lookup"><span data-stu-id="79acd-132">Yes</span></span> | <span data-ttu-id="79acd-133">Sí</span><span class="sxs-lookup"><span data-stu-id="79acd-133">Yes</span></span> | <span data-ttu-id="79acd-134">Próximamente</span><span class="sxs-lookup"><span data-stu-id="79acd-134">Coming soon</span></span> | <span data-ttu-id="79acd-135">Próximamente</span><span class="sxs-lookup"><span data-stu-id="79acd-135">Coming soon</span></span>| <span data-ttu-id="79acd-136">No</span><span class="sxs-lookup"><span data-stu-id="79acd-136">No</span></span> |
| <span data-ttu-id="79acd-137">Recuperar una llamada estacionada</span><span class="sxs-lookup"><span data-stu-id="79acd-137">Retrieve a parked call</span></span> | <span data-ttu-id="79acd-138">Sí</span><span class="sxs-lookup"><span data-stu-id="79acd-138">Yes</span></span> | <span data-ttu-id="79acd-139">Sí</span><span class="sxs-lookup"><span data-stu-id="79acd-139">Yes</span></span> | <span data-ttu-id="79acd-140">Sí</span><span class="sxs-lookup"><span data-stu-id="79acd-140">Yes</span></span> | <span data-ttu-id="79acd-141">Próximamente</span><span class="sxs-lookup"><span data-stu-id="79acd-141">Coming soon</span></span> | <span data-ttu-id="79acd-142">Próximamente</span><span class="sxs-lookup"><span data-stu-id="79acd-142">Coming soon</span></span>| <span data-ttu-id="79acd-143">No</span><span class="sxs-lookup"><span data-stu-id="79acd-143">No</span></span> |
| <span data-ttu-id="79acd-144">Timbre de llamada reactivar recuperado atrás</span><span class="sxs-lookup"><span data-stu-id="79acd-144">Un-retrieved call ring back</span></span> | <span data-ttu-id="79acd-145">Sí</span><span class="sxs-lookup"><span data-stu-id="79acd-145">Yes</span></span> | <span data-ttu-id="79acd-146">Sí</span><span class="sxs-lookup"><span data-stu-id="79acd-146">Yes</span></span> | <span data-ttu-id="79acd-147">Sí</span><span class="sxs-lookup"><span data-stu-id="79acd-147">Yes</span></span> | <span data-ttu-id="79acd-148">Próximamente</span><span class="sxs-lookup"><span data-stu-id="79acd-148">Coming soon</span></span> | <span data-ttu-id="79acd-149">Próximamente</span><span class="sxs-lookup"><span data-stu-id="79acd-149">Coming soon</span></span>| <span data-ttu-id="79acd-150">No</span><span class="sxs-lookup"><span data-stu-id="79acd-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="79acd-151">Configuración de estacionamiento y recuperación</span><span class="sxs-lookup"><span data-stu-id="79acd-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="79acd-152">Debe ser un administrador para configurar estacionamiento y recuperación, y la característica está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="79acd-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="79acd-153">Puede habilitar para los usuarios y crear grupos de usuarios mediante la directiva de estacionamiento de llamada.</span><span class="sxs-lookup"><span data-stu-id="79acd-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="79acd-154">Cuando se aplica la misma directiva a un conjunto de usuarios, podrán estacionar y recuperar las llamadas entre sí.</span><span class="sxs-lookup"><span data-stu-id="79acd-154">When you apply the same policy to a set of users, they will be able to park and retrieve calls among themselves.</span></span> <span data-ttu-id="79acd-155">Para configurar el estacionamiento de llamadas para los usuarios y crear grupos de usuarios de estacionamiento de llamada, siga el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="79acd-155">To configure call park for users and create call park user groups, follow the procedure below.</span></span>

<span data-ttu-id="79acd-156">Para obtener información acerca de cómo usar el estacionamiento de llamadas y recuperar característica, vea [estacionamiento una llamada en los equipos](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="79acd-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="79acd-157">Configurar el estacionamiento de llamadas y recuperar con PowerShell</span><span class="sxs-lookup"><span data-stu-id="79acd-157">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="79acd-158">Use el cmdlet de PowerShell [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) para crear una directiva de estacionamiento de llamada.</span><span class="sxs-lookup"><span data-stu-id="79acd-158">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="79acd-159">Use el cmdlet de PowerShell [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) para conceder una directiva de estacionamiento de llamada.</span><span class="sxs-lookup"><span data-stu-id="79acd-159">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="79acd-160">Puede cambiar la configuración predeterminada mediante el uso [Conjunto CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="79acd-160">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="79acd-161">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="79acd-161">Troubleshooting</span></span>

<span data-ttu-id="79acd-162">Si los usuarios no pueden ver el estacionamiento de o recuperar botón:</span><span class="sxs-lookup"><span data-stu-id="79acd-162">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="79acd-163">Compruebe que el usuario tiene la directiva de estacionamiento de llamadas habilitada.</span><span class="sxs-lookup"><span data-stu-id="79acd-163">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="79acd-164">Si un usuario intenta recuperar una llamada y no tiene éxito, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="79acd-164">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="79acd-165">Compruebe que el usuario está utilizando el cliente de los equipos o un teléfono o dispositivo habilitado para los equipos</span><span class="sxs-lookup"><span data-stu-id="79acd-165">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="79acd-166">¿Agrupación: es el usuario miembro del grupo de estacionamiento de llamada?</span><span class="sxs-lookup"><span data-stu-id="79acd-166">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="79acd-167">Modo de isla – estacionamiento y recuperación no está disponible en el modo de la isla de los equipos.</span><span class="sxs-lookup"><span data-stu-id="79acd-167">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="79acd-168">La llamada ya se ha recuperado o terminada.</span><span class="sxs-lookup"><span data-stu-id="79acd-168">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="79acd-169">Más información</span><span class="sxs-lookup"><span data-stu-id="79acd-169">More information</span></span>

<span data-ttu-id="79acd-170">[Estacionamiento una llamada en los equipos](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="79acd-170">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>