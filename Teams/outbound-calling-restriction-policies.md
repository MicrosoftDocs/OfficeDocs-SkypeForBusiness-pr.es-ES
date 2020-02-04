---
title: Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario
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
- NOCSH
ms.custom:
- Audio Conferencing
description: Los administradores pueden controlar el tipo de conferencias de audio y llamadas RTC de usuarios finales que pueden realizar los usuarios.
ms.openlocfilehash: b4dbaf73b34da163c731a0514a90b5a3536427fa
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708826"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="f3e95-103">Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario</span><span class="sxs-lookup"><span data-stu-id="f3e95-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="f3e95-104">Como administrador, puede usar los controles de llamadas salientes para restringir el tipo de audioconferencias y llamadas RTC del usuario final que pueden realizar los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="f3e95-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="f3e95-105">Los controles de llamadas salientes se pueden aplicar en cada usuario y proporcionan los dos controles siguientes para restringir de forma independiente cada tipo de llamada saliente.</span><span class="sxs-lookup"><span data-stu-id="f3e95-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="f3e95-106">De forma predeterminada, ambos controles se establecen para permitir llamadas salientes internacionales y nacionales.</span><span class="sxs-lookup"><span data-stu-id="f3e95-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="f3e95-107">Control</span><span class="sxs-lookup"><span data-stu-id="f3e95-107">Control</span></span>|<span data-ttu-id="f3e95-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3e95-108">Description</span></span>|<span data-ttu-id="f3e95-109">Opciones de control</span><span class="sxs-lookup"><span data-stu-id="f3e95-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f3e95-110">Llamadas RTC de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="f3e95-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="f3e95-111">Restringe el tipo de salida</span><span class="sxs-lookup"><span data-stu-id="f3e95-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="f3e95-112">llamadas permitidas desde dentro de</span><span class="sxs-lookup"><span data-stu-id="f3e95-112">calls that are allowed from within</span></span> </br><span data-ttu-id="f3e95-113">reuniones organizadas por un usuario.</span><span class="sxs-lookup"><span data-stu-id="f3e95-113">meetings organized by a user.</span></span>|<span data-ttu-id="f3e95-114">Internacional y nacional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f3e95-114">International and Domestic (default)</span></span></br><span data-ttu-id="f3e95-115">Nacionales</span><span class="sxs-lookup"><span data-stu-id="f3e95-115">Domestic</span></span></br><span data-ttu-id="f3e95-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f3e95-116">None</span></span>|
|<span data-ttu-id="f3e95-117">Llamadas RTC de usuarios finales</span><span class="sxs-lookup"><span data-stu-id="f3e95-117">End user PSTN calls</span></span>|<span data-ttu-id="f3e95-118">Restringe el tipo de llamadas</span><span class="sxs-lookup"><span data-stu-id="f3e95-118">Restricts the type of calls</span></span> </br><span data-ttu-id="f3e95-119">que puede realizar un usuario.</span><span class="sxs-lookup"><span data-stu-id="f3e95-119">that can be made by a user.</span></span>|<span data-ttu-id="f3e95-120">Internacional y nacional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f3e95-120">International and Domestic (default)</span></span></br><span data-ttu-id="f3e95-121">Nacionales</span><span class="sxs-lookup"><span data-stu-id="f3e95-121">Domestic</span></span></br><span data-ttu-id="f3e95-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f3e95-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="f3e95-123">Una llamada se considera nacional si el número marcado se encuentra en el mismo país en el que se ha configurado Office 365 para el organizador de la reunión (en el caso de las conferencias de audio) o el usuario final (en el caso de llamadas RTC de usuario final).</span><span class="sxs-lookup"><span data-stu-id="f3e95-123">A call is considered domestic if the number dialed is in the same country where Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="f3e95-124">Restringir llamadas salientes de conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="f3e95-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="f3e95-125">![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="f3e95-125">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f3e95-126">En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="f3e95-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f3e95-127">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f3e95-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="f3e95-128">Junto a **audioconferencia**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f3e95-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="f3e95-129">En **permisos de acceso telefónico de las reuniones**, seleccione la opción de restricción de llamada saliente que desee.</span><span class="sxs-lookup"><span data-stu-id="f3e95-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="f3e95-130">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="f3e95-130">Click **Save**.</span></span> 

<span data-ttu-id="f3e95-131">![Un icono que muestra el logotipo](media/sfb-logo-30x30.png) de Skype empresarial **con el centro de administración de Skype empresarial**</span><span class="sxs-lookup"><span data-stu-id="f3e95-131">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="f3e95-132">En el **centro de administración de Skype empresarial**, en el navegación de la izquierda, vaya a**usuarios**de **conferencias** > de audio y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="f3e95-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="f3e95-133">En el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f3e95-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="f3e95-134">En **restricciones para las llamadas realizadas desde las reuniones de este usuario**, seleccione la opción de restricción de acceso telefónico que desee.</span><span class="sxs-lookup"><span data-stu-id="f3e95-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Las restricciones de las opciones de marcado](media/restrictions-to-dial-outs.png)

5. <span data-ttu-id="f3e95-136">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="f3e95-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="f3e95-137">**Usar PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f3e95-137">**Using PowerShell**</span></span>

<span data-ttu-id="f3e95-138">Las restricciones de llamadas salientes se controlan mediante una única directiva denominada OnlineDialOutPolicy que tiene un atributo de restricción para cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="f3e95-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="f3e95-139">La Directiva no se puede personalizar, en lugar de que haya instancias de directiva predefinidas para cada combinación de configuración.</span><span class="sxs-lookup"><span data-stu-id="f3e95-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="f3e95-140">Puede usar el cmdlet Get-CSOnlineDialOutPolicy para ver las directivas de llamadas salientes y asignarlas a los usuarios mediante el cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="f3e95-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="f3e95-141">(Tenga en cuenta que el cmdlet Grant no contiene la palabra "conectado" como lo hace el cmdlet Get).</span><span class="sxs-lookup"><span data-stu-id="f3e95-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="f3e95-142">En la tabla siguiente se proporciona una descripción general de cada Directiva.</span><span class="sxs-lookup"><span data-stu-id="f3e95-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f3e95-143">Identity = ' etiqueta: DialoutCPCandPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="f3e95-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="f3e95-144">El usuario de la Conferencia puede llamar a números nacionales y internacionales, y este usuario también puede hacer llamadas salientes a números nacionales y internacionales.</span><span class="sxs-lookup"><span data-stu-id="f3e95-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="f3e95-145">Identity = ' etiqueta: DialoutCPCDomesticPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="f3e95-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="f3e95-146">El usuario de la Conferencia solo puede llamar a números nacionales y este usuario puede hacer llamadas salientes a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="f3e95-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="f3e95-147">Identity = ' etiqueta: DialoutCPCDisabledPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="f3e95-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="f3e95-148">El usuario de la Conferencia no puede hacer llamadas. Este usuario puede hacer llamadas salientes a números internacionales y nacionales.</span><span class="sxs-lookup"><span data-stu-id="f3e95-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="f3e95-149">Identity = ' etiqueta: DialoutCPCInternationalPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="f3e95-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="f3e95-150">El usuario de la Conferencia puede llamar a números nacionales y internacionales, y este usuario solo puede hacer llamadas salientes a un número de RTC nacional.</span><span class="sxs-lookup"><span data-stu-id="f3e95-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="f3e95-151">Identity = ' etiqueta: DialoutCPCInternationalPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="f3e95-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="f3e95-152">El usuario de la Conferencia puede llamar a números nacionales y internacionales, y este usuario no puede hacer llamadas salientes a un número RTC además de números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="f3e95-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="f3e95-153">Identity = ' etiqueta: DialoutCPCandPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="f3e95-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="f3e95-154">El usuario de la Conferencia solo puede llamar a números nacionales y este usuario solo puede hacer llamadas salientes a números de RTC nacionales.</span><span class="sxs-lookup"><span data-stu-id="f3e95-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="f3e95-155">Identity = ' etiqueta: DialoutCPCDomesticPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="f3e95-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="f3e95-156">El usuario de la Conferencia solo puede llamar a números nacionales y este usuario no puede realizar llamadas salientes a números de RTC además de números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="f3e95-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="f3e95-157">Identity = ' etiqueta: DialoutCPCDisabledPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="f3e95-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="f3e95-158">El usuario de la Conferencia no puede hacer llamadas, y este usuario solo puede hacer llamadas salientes a números RTC nacionales.</span><span class="sxs-lookup"><span data-stu-id="f3e95-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="f3e95-159">Identity = ' etiqueta: DialoutCPCandPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="f3e95-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="f3e95-160">El usuario de la Conferencia no puede hacer llamadas, y este usuario no puede hacer llamadas salientes a un número de RTC además de números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="f3e95-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
