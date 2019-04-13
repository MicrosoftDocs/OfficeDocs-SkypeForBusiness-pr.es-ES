---
title: Directiva de llamada en Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/12/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Obtenga información acerca de la configuración de la directiva de llamada en Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c97fd5ff9228d0761f55f2f56b9a908cc3861c29
ms.sourcegitcommit: 82490c2ef74900c348c14968b605a313b5bf3078
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2019
ms.locfileid: "31860268"
---
<a name="calling-policy-in-microsoft-teams"></a><span data-ttu-id="4f392-103">Directiva de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f392-103">Calling policy in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="4f392-104">En Microsoft Teams, llamar al control de las directivas que la llamada a y las características de desvío de llamadas están disponibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4f392-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="4f392-105">Las directivas de la llamada a determinan si un usuario puede realizar llamadas privadas, use el desvío de llamadas o llamadas a otros usuarios o números de teléfono externos simultáneas, enrutar las llamadas al correo de voz, enviar las llamadas a grupos de llamadas, delegación para las llamadas entrantes y salientes, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="4f392-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="4f392-106">Una directiva global predeterminada se crea automáticamente, pero los administradores también pueden crear y asignar directivas de llamada personalizadas.</span><span class="sxs-lookup"><span data-stu-id="4f392-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="4f392-107">Configuración de la directiva de llamada</span><span class="sxs-lookup"><span data-stu-id="4f392-107">Calling policy settings</span></span>

|<span data-ttu-id="4f392-108">Configuración de directiva de llamada</span><span class="sxs-lookup"><span data-stu-id="4f392-108">Calling policy setting</span></span> | <span data-ttu-id="4f392-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f392-109">Description</span></span> |
|-----------------------|-------------|
|<span data-ttu-id="4f392-110">Usuario puede realizar llamadas privadas</span><span class="sxs-lookup"><span data-stu-id="4f392-110">User can make private calls</span></span> | <span data-ttu-id="4f392-111">Controla todas las capacidades de llamada en los equipos.</span><span class="sxs-lookup"><span data-stu-id="4f392-111">Controls all calling capabilities in Teams.</span></span> <span data-ttu-id="4f392-112">Desactivación de esto va a desactivar toda la funcionalidad de llamada en los equipos.</span><span class="sxs-lookup"><span data-stu-id="4f392-112">Turning this off will turn off all calling functionality in Teams.</span></span>|
|<span data-ttu-id="4f392-113">Desvío de llamadas y las llamadas simultáneas a otros usuarios</span><span class="sxs-lookup"><span data-stu-id="4f392-113">Call forwarding and simultaneous ringing to other users</span></span> | <span data-ttu-id="4f392-114">Controla si las llamadas entrantes pueden transferirse a otros usuarios o pueden llamar a otra persona al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="4f392-114">Controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> |
|<span data-ttu-id="4f392-115">Desvío de llamadas y las llamadas simultáneas a números de teléfono externos</span><span class="sxs-lookup"><span data-stu-id="4f392-115">Call forwarding and simultaneous ringing to external phone numbers</span></span> | <span data-ttu-id="4f392-116">Controla si las llamadas entrantes se pueden reenviar a un número externo o pueden llamar a un número externo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="4f392-116">Controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>|
|<span data-ttu-id="4f392-117">Correo de voz está disponible para enrutar las llamadas entrantes a los usuarios</span><span class="sxs-lookup"><span data-stu-id="4f392-117">Voicemail is available for routing inbound calls to users</span></span> | <span data-ttu-id="4f392-118">Permite las llamadas entrantes que se envíen al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="4f392-118">Enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="4f392-119">Las opciones válidas son **siempre activado**, **siempre deshabilitado**o **controlado de usuario**.</span><span class="sxs-lookup"><span data-stu-id="4f392-119">Valid options are **Always enabled**, **Always disabled**, or **User controlled**.</span></span> |
|<span data-ttu-id="4f392-120">Se pueden redirigir las llamadas entrantes para llamar a grupos</span><span class="sxs-lookup"><span data-stu-id="4f392-120">Inbound calls can be routed to call groups</span></span> | <span data-ttu-id="4f392-121">Controla si se pueden reenviar las llamadas entrantes a un grupo de llamada.</span><span class="sxs-lookup"><span data-stu-id="4f392-121">Controls whether incoming calls can be forwarded to a call group.</span></span>  |
|<span data-ttu-id="4f392-122">Permitir la delegación de las llamadas entrantes y salientes</span><span class="sxs-lookup"><span data-stu-id="4f392-122">Allow delegation for inbound and outbound calls</span></span> | <span data-ttu-id="4f392-123">Permite las llamadas entrantes deben enrutarse a delegados; permite a los delegados realizar llamadas salientes en nombre de los usuarios para quienes se delega permisos.</span><span class="sxs-lookup"><span data-stu-id="4f392-123">Enables inbound calls to be routed to delegates; allows delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> |
|<span data-ttu-id="4f392-124">Evitar el desvío de pago y enviar las llamadas a través de la RTC</span><span class="sxs-lookup"><span data-stu-id="4f392-124">Prevent toll bypass and send calls through the PSTN</span></span> | <span data-ttu-id="4f392-125">Si se establece en \*\*\*\* va a enviar las llamadas a través de RTC e incurrir en los cargos en lugar de pasar por la red y omitir el cuotas.</span><span class="sxs-lookup"><span data-stu-id="4f392-125">Setting this to **On** will send calls through PSTN and incur charges rather than going through the network and bypassing the tolls.</span></span> |
|<span data-ttu-id="4f392-126">No disponible en no disponible está disponible mientras se encuentre en una llamada.</span><span class="sxs-lookup"><span data-stu-id="4f392-126">Busy on Busy is available while in a call.</span></span>| <span data-ttu-id="4f392-127">Configura las llamadas entrantes cómo se controlan cuando un usuario ya está en una llamada o conferencia.</span><span class="sxs-lookup"><span data-stu-id="4f392-127">Configures how incoming calls are handled when a user is already in a call or conference.</span></span> <span data-ttu-id="4f392-128">Se pueden rechazar las llamadas entrantes o nuevo con una señal de ocupado.</span><span class="sxs-lookup"><span data-stu-id="4f392-128">New or incoming calls can be rejected with a busy signal.</span></span> |

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="4f392-129">Crear una directiva llamada personalizada</span><span class="sxs-lookup"><span data-stu-id="4f392-129">Create a custom calling policy</span></span>

<span data-ttu-id="4f392-130">Siga estos pasos para crear una nueva directiva llamada personalizada.</span><span class="sxs-lookup"><span data-stu-id="4f392-130">Follow these steps to create a new custom calling policy.</span></span>

1. <span data-ttu-id="4f392-131">En el centro de administración de Microsoft Teams, seleccione **voz** > **Directiva de llamada**.</span><span class="sxs-lookup"><span data-stu-id="4f392-131">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="4f392-132">Seleccione **nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="4f392-132">Select **New policy**.</span></span>
3. <span data-ttu-id="4f392-133">Activar las características que desea usar en la directiva de llamada.</span><span class="sxs-lookup"><span data-stu-id="4f392-133">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="4f392-134">Todas las selecciones están **desactivadas** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4f392-134">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="4f392-135">Para controlar si los usuarios pueden enrutar las llamadas entrantes al correo de voz, seleccione **siempre habilitado** o **bajo control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="4f392-135">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="4f392-136">Para evitar que el enrutamiento al correo de voz, seleccione **siempre deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="4f392-136">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="4f392-137">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4f392-137">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="4f392-138">Modificar una directiva de llamada existente</span><span class="sxs-lookup"><span data-stu-id="4f392-138">Modify an existing calling policy</span></span>

<span data-ttu-id="4f392-139">Siga estos pasos para modificar una directiva de llamada existente.</span><span class="sxs-lookup"><span data-stu-id="4f392-139">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="4f392-140">En el centro de administración de Microsoft Teams, seleccione **voz** > **Directiva de llamada**.</span><span class="sxs-lookup"><span data-stu-id="4f392-140">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="4f392-141">Haga clic en junto a la directiva que desea modificar y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4f392-141">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="4f392-142">Activar las características que desea usar en la directiva de llamada.</span><span class="sxs-lookup"><span data-stu-id="4f392-142">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="4f392-143">Todas las selecciones están **desactivadas** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4f392-143">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="4f392-144">Para controlar si los usuarios pueden enrutar las llamadas entrantes al correo de voz, seleccione **siempre habilitado** o **bajo control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="4f392-144">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="4f392-145">Para evitar que el enrutamiento al correo de voz, seleccione **siempre deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="4f392-145">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="4f392-146">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4f392-146">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="4f392-147">Asignar una directiva de llamada a un usuario</span><span class="sxs-lookup"><span data-stu-id="4f392-147">Assign a calling policy to a user</span></span>

<span data-ttu-id="4f392-148">Siga estos pasos para asignar una directiva personalizada que llama a un usuario.</span><span class="sxs-lookup"><span data-stu-id="4f392-148">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="4f392-149">En el centro de administración de Microsoft Teams, seleccione **voz** > **Directiva de llamada**.</span><span class="sxs-lookup"><span data-stu-id="4f392-149">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="4f392-150">Haga clic en junto al nombre de directiva para seleccionarlo y, a continuación, seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="4f392-150">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="4f392-151">En el panel **Administrar usuarios** , buscar el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="4f392-151">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="4f392-152">(Debe escribir al menos tres caracteres).</span><span class="sxs-lookup"><span data-stu-id="4f392-152">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="4f392-153">Seleccione el nombre del usuario y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4f392-153">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="4f392-154">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4f392-154">Select **Save**.</span></span>
