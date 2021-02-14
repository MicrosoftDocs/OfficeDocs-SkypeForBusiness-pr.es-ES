---
title: 'Restricciones de llamadas salientes: Audioconferencia & llamadas RTC'
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
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908659"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="bb3ed-103">Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario</span><span class="sxs-lookup"><span data-stu-id="bb3ed-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="bb3ed-104">Como administrador, puede usar los controles de llamadas salientes para restringir el tipo de audioconferencias y llamadas RTC del usuario final que pueden realizar los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="bb3ed-105">Los controles de llamada saliente se pueden aplicar por usuario y proporcionar los siguientes dos controles para restringir de forma independiente cada tipo de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="bb3ed-106">De forma predeterminada, ambos controles se establecen para permitir llamadas internacionales y nacionales salientes.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="bb3ed-107">Control</span><span class="sxs-lookup"><span data-stu-id="bb3ed-107">Control</span></span>|<span data-ttu-id="bb3ed-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb3ed-108">Description</span></span>|<span data-ttu-id="bb3ed-109">Opciones de control</span><span class="sxs-lookup"><span data-stu-id="bb3ed-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bb3ed-110">Llamadas RTC de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="bb3ed-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="bb3ed-111">Restringe el tipo de salida</span><span class="sxs-lookup"><span data-stu-id="bb3ed-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="bb3ed-112">llamadas que se permiten desde dentro</span><span class="sxs-lookup"><span data-stu-id="bb3ed-112">calls that are allowed from within</span></span> </br><span data-ttu-id="bb3ed-113">reuniones organizadas por un usuario.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-113">meetings organized by a user.</span></span>|<span data-ttu-id="bb3ed-114">Cualquier destino (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="bb3ed-114">Any destination (default)</span></span></br><span data-ttu-id="bb3ed-115">En el mismo país o región que el organizador</span><span class="sxs-lookup"><span data-stu-id="bb3ed-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="bb3ed-116">[Solo países o regiones de la zona A](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="bb3ed-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="bb3ed-117">No permitir</span><span class="sxs-lookup"><span data-stu-id="bb3ed-117">Don't allow</span></span>|
|<span data-ttu-id="bb3ed-118">Llamadas RTC de usuario final</span><span class="sxs-lookup"><span data-stu-id="bb3ed-118">End user PSTN calls</span></span>|<span data-ttu-id="bb3ed-119">Restringe el tipo de llamadas</span><span class="sxs-lookup"><span data-stu-id="bb3ed-119">Restricts the type of calls</span></span> </br><span data-ttu-id="bb3ed-120">que puede realizar un usuario.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-120">that can be made by a user.</span></span>|<span data-ttu-id="bb3ed-121">Internacional y nacional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="bb3ed-121">International and Domestic (default)</span></span></br><span data-ttu-id="bb3ed-122">Nacionales</span><span class="sxs-lookup"><span data-stu-id="bb3ed-122">Domestic</span></span></br><span data-ttu-id="bb3ed-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bb3ed-123">None</span></span>|

<span data-ttu-id="bb3ed-124">Para averiguar qué países y regiones se consideran zona A, vea zonas de país y [región para Audioconferencia.](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="bb3ed-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="bb3ed-125">Una llamada se considera nacional si el número marcado se encuentra en el mismo país donde se ha configurado Microsoft 365 u Office 365 para el organizador de la reunión (en el caso de las audioconferencias) o el usuario final (en el caso de las llamadas RTC del usuario final).</span><span class="sxs-lookup"><span data-stu-id="bb3ed-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="bb3ed-126">Restringir las llamadas salientes de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="bb3ed-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="bb3ed-127">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="bb3ed-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="bb3ed-128">En el panel de navegación izquierdo, **haga** clic en Usuarios y, a continuación, haga clic en el nombre para mostrar del usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-128">In the left navigation, click **Users**, and then click the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="bb3ed-129">Junto a **Audioconferencia,** haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="bb3ed-129">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="bb3ed-130">En **Llamar desde las reuniones,** seleccione la opción de restricción de acceso telefónico que desee.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="bb3ed-131">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-131">Click **Save**.</span></span> 

<span data-ttu-id="bb3ed-132">![Icono que muestra el logotipo de Skype Empresarial](media/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="bb3ed-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="bb3ed-133">En el **Centro de administración** de Skype Empresarial, en el panel de navegación izquierdo, vaya a Usuarios de **Audioconferencia** y, a continuación, seleccione el usuario en la lista  >  de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="bb3ed-134">En el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-134">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="bb3ed-135">En **Restricciones a las llamadas desde las reuniones** de este usuario, seleccione la opción de restricción de acceso telefónico que desee.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![Las restricciones a las opciones de acceso telefónico](media/restrictions-to-dial-outs.png)
      

4. <span data-ttu-id="bb3ed-137">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-137">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="bb3ed-138">**Con PowerShell**</span><span class="sxs-lookup"><span data-stu-id="bb3ed-138">**Using PowerShell**</span></span>

<span data-ttu-id="bb3ed-139">Las restricciones de llamada saliente se controlan mediante una sola directiva denominada OnlineDialOutPolicy, que tiene un atributo de restricción para cada uno.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="bb3ed-140">La directiva no se puede personalizar, sino que hay instancias de directiva predefinidas para cada combinación de la configuración.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="bb3ed-141">Puede usar el cmdlet Get-CSOnlineDialOutPolicy para ver las directivas de llamadas salientes y asignarlas a los usuarios mediante el cmdlet Grant-CSDialOutPolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="bb3ed-142">(Tenga en cuenta que el cmdlet Grant no contiene la palabra "En línea" como lo hace el cmdlet Get).</span><span class="sxs-lookup"><span data-stu-id="bb3ed-142">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="bb3ed-143">En la tabla siguiente se proporciona información general de cada directiva.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-143">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bb3ed-144">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="bb3ed-144">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="bb3ed-145">Los usuarios de la conferencia pueden llamar a números nacionales e internacionales, y este usuario también puede realizar llamadas a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-145">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="bb3ed-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="bb3ed-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="bb3ed-147">Los usuarios de la conferencia solo pueden llamar a números nacionales y este usuario puede realizar llamadas a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-147">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="bb3ed-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="bb3ed-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="bb3ed-149">El usuario de la conferencia no puede realizar ninguna llamada. Este usuario puede realizar llamadas a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-149">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="bb3ed-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="bb3ed-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="bb3ed-151">El usuario de la conferencia puede llamar a números nacionales e internacionales, y este usuario solo puede realizar llamadas salientes a números RTC nacionales.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-151">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="bb3ed-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="bb3ed-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="bb3ed-153">El usuario de la conferencia puede llamar a números nacionales e internacionales, y este usuario no puede realizar llamadas a números RTC además de números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-153">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="bb3ed-154">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="bb3ed-154">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="bb3ed-155">Los usuarios de la conferencia solo pueden llamar a números nacionales y este usuario solo puede realizar llamadas a números RTC nacionales.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-155">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="bb3ed-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="bb3ed-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="bb3ed-157">Los usuarios de la conferencia solo pueden llamar a números nacionales y este usuario no puede realizar llamadas a números RTC además de números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-157">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="bb3ed-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="bb3ed-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="bb3ed-159">El usuario de la conferencia no puede realizar ninguna llamada, y este usuario solo puede realizar una llamada saliente a números RTC nacionales.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-159">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="bb3ed-160">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="bb3ed-160">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="bb3ed-161">El usuario de la conferencia no puede realizar ninguna llamada y este usuario no puede realizar llamadas salientes a un número RTC además de a los números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-161">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="bb3ed-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="bb3ed-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="bb3ed-163">El usuario de la conferencia solo puede llamar a países y regiones de la zona A, y este usuario puede realizar llamadas [salientes](audio-conferencing-zones.md)a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-163">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="bb3ed-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="bb3ed-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="bb3ed-165">El usuario de la conferencia solo puede llamar a países y regiones de la zona A, y este usuario solo puede realizar llamadas [salientes](audio-conferencing-zones.md)a un número RTC nacional.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-165">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="bb3ed-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="bb3ed-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="bb3ed-167">El usuario de la conferencia solo puede llamar a países y regiones de la zona A, y este usuario no puede realizar llamadas [salientes](audio-conferencing-zones.md)a números de RTC además de números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="bb3ed-167">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
