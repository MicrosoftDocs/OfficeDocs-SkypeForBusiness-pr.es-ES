---
title: Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Los administradores pueden controlar el tipo de audioconferencias llamadas de RTC de conferencia y el usuario final que pueden realizar los usuarios.
ms.openlocfilehash: 473baddce6ddac5fa523f02477cd89f6a2c4f4a2
ms.sourcegitcommit: 905ba61de9622dd485ff375fa75bb0d76bac0b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "22193017"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="2119e-103">Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario</span><span class="sxs-lookup"><span data-stu-id="2119e-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="2119e-104">Como administrador, puede usar los controles de llamada saliente para restringir el tipo de audioconferencias llamadas de RTC de conferencia y el usuario final que pueden realizar los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="2119e-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="2119e-105">Controles de llamada saliente se pueden aplicar por usuario y proporcionan los siguientes dos controles para restringir cada tipo de llamadas salientes de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="2119e-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="2119e-106">De forma predeterminada, ambos controles están configurados para permitir llamadas salientes nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="2119e-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="2119e-107">Control</span><span class="sxs-lookup"><span data-stu-id="2119e-107">Control</span></span>|<span data-ttu-id="2119e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2119e-108">Description</span></span>|<span data-ttu-id="2119e-109">Opciones de control</span><span class="sxs-lookup"><span data-stu-id="2119e-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2119e-110">Llamadas de audio de conferencia RTC</span><span class="sxs-lookup"><span data-stu-id="2119e-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="2119e-111">Restringe el tipo de salida</span><span class="sxs-lookup"><span data-stu-id="2119e-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="2119e-112">llamadas que se permiten desde dentro</span><span class="sxs-lookup"><span data-stu-id="2119e-112">calls that are allowed from within</span></span> </br><span data-ttu-id="2119e-113">reuniones organizadas por un usuario.</span><span class="sxs-lookup"><span data-stu-id="2119e-113">meetings organized by a user.</span></span>|<span data-ttu-id="2119e-114">Internacionales y nacionales (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="2119e-114">International and Domestic (default)</span></span></br><span data-ttu-id="2119e-115">Nacionales</span><span class="sxs-lookup"><span data-stu-id="2119e-115">Domestic</span></span></br><span data-ttu-id="2119e-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="2119e-116">None</span></span>|
|<span data-ttu-id="2119e-117">Llamadas de RTC del usuario final</span><span class="sxs-lookup"><span data-stu-id="2119e-117">End user PSTN calls</span></span>|<span data-ttu-id="2119e-118">Restringe el tipo de llamadas</span><span class="sxs-lookup"><span data-stu-id="2119e-118">Restricts the type of calls</span></span> </br><span data-ttu-id="2119e-119">que puede ser realizados por un usuario.</span><span class="sxs-lookup"><span data-stu-id="2119e-119">that can be made by a user.</span></span>|<span data-ttu-id="2119e-120">Internacionales y nacionales (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="2119e-120">International and Domestic (default)</span></span></br><span data-ttu-id="2119e-121">Nacionales</span><span class="sxs-lookup"><span data-stu-id="2119e-121">Domestic</span></span></br><span data-ttu-id="2119e-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="2119e-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="2119e-123">Una llamada se determina como nacionales si el número de teléfono llamada se encuentra en el mismo país como el país en el que se ha establecido en Office 365 para el organizador de la reunión (en el caso de conferencias de audio) o el usuario final (en el caso de las llamadas de RTC de usuario final).</span><span class="sxs-lookup"><span data-stu-id="2119e-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="2119e-124">Restringir las llamadas salientes de conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="2119e-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="2119e-125">![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="2119e-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="2119e-126">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="2119e-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="2119e-127">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2119e-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="2119e-128">Haga clic en el menú situado junto a **Puentes de conferencia**y, a continuación, haga clic en **Editar** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2119e-128">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="2119e-129">En el panel de **proveedor de puente de conferencia** , bajo **restricciones de marcado-outs de reuniones de este usuario**, seleccione la opción de salida de la restricción que desee.</span><span class="sxs-lookup"><span data-stu-id="2119e-129">In the **Conference bridge provider** pane, under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="2119e-130">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2119e-130">Click **Apply**.</span></span> 

<span data-ttu-id="2119e-131">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="2119e-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="2119e-132">En el **Skype para el centro de administración de negocio**, en el panel de navegación izquierdo, vaya a la **conferencia de Audio** > **a los usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="2119e-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="2119e-133">En el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2119e-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="2119e-134">En **las restricciones de marcado-outs de reuniones de este usuario**, seleccione la opción de salida de la restricción que desee.</span><span class="sxs-lookup"><span data-stu-id="2119e-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Las restricciones a las opciones de marcado-outs](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="2119e-136">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2119e-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="2119e-137">**Uso de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2119e-137">**Using PowerShell**</span></span>

<span data-ttu-id="2119e-138">Restricciones de llamadas salientes se controlan mediante una sola directiva denominada OnlineDialOutPolicy que tiene un atributo de restricción para cada uno.</span><span class="sxs-lookup"><span data-stu-id="2119e-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="2119e-139">No se puede personalizar la directiva, en su lugar hay instancias de directiva predefinidas para cada combinación de la configuración.</span><span class="sxs-lookup"><span data-stu-id="2119e-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="2119e-140">Puede usar el cmdlet Get-CSOnlineDialOutPolicy para ver las directivas llamadas salientes y asignar a los usuarios mediante el cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="2119e-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="2119e-141">(Tenga en cuenta que el cmdlet Grant no contiene la palabra "En línea" al igual que el cmdlet Get.)</span><span class="sxs-lookup"><span data-stu-id="2119e-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="2119e-142">En la siguiente tabla proporciona una visión general de cada directiva.</span><span class="sxs-lookup"><span data-stu-id="2119e-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2119e-143">Identidad = 'etiqueta: DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="2119e-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="2119e-144">Números internacionales y nacionales puede marcar un usuario en la conferencia, y este usuario también puede efectuar llamadas salientes a números internacionales y nacionales.</span><span class="sxs-lookup"><span data-stu-id="2119e-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="2119e-145">Identidad = 'etiqueta: DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="2119e-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="2119e-146">Usuario en la conferencia puede marcar un sólo a los números nacionales, y este usuario puede realizar llamadas a números internacionales y nacionales.</span><span class="sxs-lookup"><span data-stu-id="2119e-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="2119e-147">Identidad = 'etiqueta: DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="2119e-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="2119e-148">Usuario en la conferencia no puede realizar cualquier marcado. Este usuario puede realizar llamadas a números internacionales y nacionales.</span><span class="sxs-lookup"><span data-stu-id="2119e-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="2119e-149">Identidad = 'etiqueta: DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="2119e-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="2119e-150">Números internacionales y nacionales puede marcar un usuario en la conferencia, y este usuario solo puede realizar llamadas salientes a número nacional de RTC.</span><span class="sxs-lookup"><span data-stu-id="2119e-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="2119e-151">Identidad = 'etiqueta: DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="2119e-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="2119e-152">Números internacionales y nacionales puede marcar un usuario en la conferencia, y este usuario no puede realizar llamadas salientes al número de RTC además de los números de emergencias.</span><span class="sxs-lookup"><span data-stu-id="2119e-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="2119e-153">Identidad = 'etiqueta: DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="2119e-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="2119e-154">Usuario en la conferencia puede marcar un sólo a los números nacionales, y este usuario solo puede realizar llamadas salientes a los números de RTC nacionales.</span><span class="sxs-lookup"><span data-stu-id="2119e-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="2119e-155">Identidad = 'etiqueta: DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="2119e-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="2119e-156">Usuario en la conferencia puede marcar un sólo a los números nacionales, y este usuario no puede realizar llamadas salientes al número de RTC además de los números de emergencias.</span><span class="sxs-lookup"><span data-stu-id="2119e-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="2119e-157">Identidad = 'etiqueta: DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="2119e-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="2119e-158">Usuario en la conferencia no puede realizar cualquier llamadas salientes, y este usuario solo puede realizar llamadas salientes a los números de RTC nacionales.</span><span class="sxs-lookup"><span data-stu-id="2119e-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="2119e-159">Identidad = 'etiqueta: DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="2119e-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="2119e-160">Usuario en la conferencia no puede realizar cualquier llamadas salientes, y este usuario no puede realizar llamadas salientes al número de RTC además de los números de emergencias.</span><span class="sxs-lookup"><span data-stu-id="2119e-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
