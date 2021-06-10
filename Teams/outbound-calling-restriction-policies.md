---
title: 'Restricciones de llamadas salientes: conferencias de audio & llamadas RTC'
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Los administradores pueden controlar el tipo de audioconferencia y las llamadas RTC de usuario final que pueden realizar los usuarios.
ms.openlocfilehash: 86622b493fbb8d31f98f600acb7158afc82e15e5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526733"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="a2e1d-103">Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario</span><span class="sxs-lookup"><span data-stu-id="a2e1d-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="a2e1d-104">Como administrador, puede usar controles de llamadas salientes para restringir el tipo de audioconferencia y las llamadas de red telefónica conmutada (RTC) de usuario final que pueden realizar los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end-user Public Switched Telephone Network (PSTN) calls that can be made by users in your organization.</span></span>

<span data-ttu-id="a2e1d-105">Los controles de llamadas salientes se pueden aplicar por usuario o por inquilino y proporcionan los dos controles siguientes para restringir de forma independiente cada tipo de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-105">Outbound call controls can be applied on a per-user basis or on a tenant basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="a2e1d-106">De forma predeterminada, ambos controles están configurados para permitir llamadas salientes internacionales y nacionales.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-106">By default, both controls are set to allow international and domestic outbound calls.</span></span>

|<span data-ttu-id="a2e1d-107">Control</span><span class="sxs-lookup"><span data-stu-id="a2e1d-107">Control</span></span>|<span data-ttu-id="a2e1d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2e1d-108">Description</span></span>|<span data-ttu-id="a2e1d-109">Opciones de control</span><span class="sxs-lookup"><span data-stu-id="a2e1d-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2e1d-110">Llamadas RTC de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="a2e1d-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="a2e1d-111">Restringe el tipo de salida</span><span class="sxs-lookup"><span data-stu-id="a2e1d-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="a2e1d-112">llamadas que se permiten desde dentro</span><span class="sxs-lookup"><span data-stu-id="a2e1d-112">calls that are allowed from within</span></span> </br><span data-ttu-id="a2e1d-113">reuniones organizadas por un usuario.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-113">meetings organized by a user.</span></span>|<span data-ttu-id="a2e1d-114">Cualquier destino (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="a2e1d-114">Any destination (default)</span></span></br><span data-ttu-id="a2e1d-115">En el mismo país o región que el organizador</span><span class="sxs-lookup"><span data-stu-id="a2e1d-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="a2e1d-116">[Solo países o regiones de zona A](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="a2e1d-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="a2e1d-117">No permitir</span><span class="sxs-lookup"><span data-stu-id="a2e1d-117">Don't allow</span></span>|
|<span data-ttu-id="a2e1d-118">Llamadas RTC de usuario final</span><span class="sxs-lookup"><span data-stu-id="a2e1d-118">End-user PSTN calls</span></span>|<span data-ttu-id="a2e1d-119">Restringe el tipo de llamadas</span><span class="sxs-lookup"><span data-stu-id="a2e1d-119">Restricts the type of calls</span></span> </br><span data-ttu-id="a2e1d-120">que puede realizar un usuario.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-120">that can be made by a user.</span></span>|<span data-ttu-id="a2e1d-121">Internacional y Nacional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="a2e1d-121">International and Domestic (default)</span></span></br><span data-ttu-id="a2e1d-122">Nacionales</span><span class="sxs-lookup"><span data-stu-id="a2e1d-122">Domestic</span></span></br><span data-ttu-id="a2e1d-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a2e1d-123">None</span></span>|

<span data-ttu-id="a2e1d-124">Para saber qué países y regiones se consideran zona A, vea Zonas de país y [región para audioconferencias.](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="a2e1d-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="a2e1d-125">Una llamada se considera nacional si el número marcado se encuentra en el mismo país donde se ha configurado Microsoft 365 o Office 365 para el organizador de la reunión (en el caso de las audioconferencias) o el usuario final (en el caso de las llamadas RTC del usuario final).</span><span class="sxs-lookup"><span data-stu-id="a2e1d-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="a2e1d-126">Restringir las llamadas salientes de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="a2e1d-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="a2e1d-127">![el Microsoft Teams con ](media/teams-logo-30x30.png) **el centro Microsoft Teams administración**</span><span class="sxs-lookup"><span data-stu-id="a2e1d-127">![the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a2e1d-128">En el panel de navegación izquierdo, seleccione **Usuarios** y, a continuación, seleccione el nombre para mostrar del usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-128">In the left navigation, select **Users**, and then select the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="a2e1d-129">Junto a **Audioconferencia,** seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-129">Next to **Audio Conferencing**, select **Edit**.</span></span>

4. <span data-ttu-id="a2e1d-130">En **Llamar desde reuniones,** seleccione la opción de restricción de acceso telefónico que desee.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="a2e1d-131">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-131">Select **Save**.</span></span>

<span data-ttu-id="a2e1d-132">![Icono que muestra el logotipo de Skype Empresarial](media/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="a2e1d-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="a2e1d-133">En el **Skype Empresarial** de administración , en el panel de navegación izquierdo, vaya a **Usuarios** de audioconferencia y, a continuación, seleccione el usuario de la lista de  >  usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a2e1d-134">En el panel de acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-134">In the Action pane, select **Edit**.</span></span>

3.  <span data-ttu-id="a2e1d-135">En **Restricciones a las salidas** de acceso telefónico de las reuniones de este usuario, seleccione la opción de restricción de acceso telefónico que desee.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![Las opciones restricciones de acceso telefónico](media/restrictions-to-dial-outs.png)

4. <span data-ttu-id="a2e1d-137">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-137">Select **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="a2e1d-138">**Con PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a2e1d-138">**Using PowerShell**</span></span>

<span data-ttu-id="a2e1d-139">Las restricciones de llamadas salientes se controlan mediante una única directiva denominada OnlineDialOutPolicy, que tiene un atributo de restricción para cada una.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy, which has a restriction attribute for each.</span></span> <span data-ttu-id="a2e1d-140">La directiva no se puede personalizar, sino que hay instancias de directiva predefinidas para cada combinación de la configuración.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span>

<span data-ttu-id="a2e1d-141">Puede usar el cmdlet Get-CSOnlineDialOutPolicy para ver las directivas de llamadas salientes y usar el siguiente comando para la configuración.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and use the following command for the setup.</span></span>

<span data-ttu-id="a2e1d-142">**Establezca la directiva en un nivel por usuario con el siguiente cmdlet.**</span><span class="sxs-lookup"><span data-stu-id="a2e1d-142">**Set the policy on a per-user level with the following cmdlet**.</span></span> <span data-ttu-id="a2e1d-143">(El cmdlet Grant no contiene la palabra "En línea" como lo hace el cmdlet Get).</span><span class="sxs-lookup"><span data-stu-id="a2e1d-143">(The Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span>

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

<span data-ttu-id="a2e1d-144">**Establezca la directiva en el nivel de inquilino con el cmdlet siguiente.**</span><span class="sxs-lookup"><span data-stu-id="a2e1d-144">**Set the policy on the tenant level with the following cmdlet**.</span></span>

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

<span data-ttu-id="a2e1d-145">Todos los usuarios del inquilino que no tengan asignada ninguna directiva de marcado recibirán esta directiva.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-145">All users of the tenant who don't have any dialout policy assigned will get this policy.</span></span> <span data-ttu-id="a2e1d-146">Otros usuarios permanecen con su directiva actual.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-146">Other users remain with their current policy.</span></span>

<span data-ttu-id="a2e1d-147">En la tabla siguiente se proporciona información general sobre cada directiva.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-147">The following table provides an overview of each policy.</span></span>

|<span data-ttu-id="a2e1d-148">Cmdlet de PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2e1d-148">PowerShell cmdlet</span></span>|<span data-ttu-id="a2e1d-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2e1d-149">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="a2e1d-150">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="a2e1d-150">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="a2e1d-151">El usuario de la conferencia puede llamar a números nacionales e internacionales, y este usuario también puede realizar llamadas salientes a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-151">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="a2e1d-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="a2e1d-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="a2e1d-153">El usuario de la conferencia solo puede llamar a números nacionales y este usuario puede realizar llamadas salientes a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-153">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="a2e1d-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="a2e1d-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="a2e1d-155">El usuario de la conferencia no puede marcar hacia fuera. Este usuario puede realizar llamadas salientes a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-155">User in the conference can't dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="a2e1d-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="a2e1d-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="a2e1d-157">El usuario de la conferencia puede llamar a números nacionales e internacionales, y este usuario solo puede realizar llamadas salientes a números RTC nacionales.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-157">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="a2e1d-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="a2e1d-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="a2e1d-159">El usuario de la conferencia puede llamar a números nacionales e internacionales, y este usuario no puede realizar llamadas salientes a números RTC además de números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-159">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="a2e1d-160">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="a2e1d-160">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="a2e1d-161">El usuario de la conferencia solo puede llamar a números nacionales y este usuario solo puede realizar llamadas salientes a números RTC nacionales.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-161">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="a2e1d-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="a2e1d-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="a2e1d-163">El usuario de la conferencia solo puede llamar a números nacionales y este usuario no puede realizar llamadas salientes a números RTC además de números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-163">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="a2e1d-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="a2e1d-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="a2e1d-165">El usuario de la conferencia no puede marcar y este usuario solo puede realizar llamadas salientes a números RTC nacionales.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-165">User in the conference can't dial out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="a2e1d-166">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="a2e1d-166">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="a2e1d-167">El usuario de la conferencia no puede marcar y este usuario no puede realizar llamadas salientes al número RTC además de los números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-167">User in the conference can't dial out, and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="a2e1d-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="a2e1d-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="a2e1d-169">El usuario de la conferencia solo puede llamar a países y regiones de zona A y este usuario puede realizar llamadas [salientes](audio-conferencing-zones.md)a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-169">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="a2e1d-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="a2e1d-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="a2e1d-171">El usuario de la conferencia solo puede llamar a países y regiones de zona A y este usuario solo puede realizar llamadas [salientes](audio-conferencing-zones.md)al número RTC nacional.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-171">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="a2e1d-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="a2e1d-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="a2e1d-173">El usuario de la conferencia solo puede llamar a países y regiones de la zona A y este usuario no puede realizar llamadas [salientes](audio-conferencing-zones.md)a números RTC además de números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="a2e1d-173">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
