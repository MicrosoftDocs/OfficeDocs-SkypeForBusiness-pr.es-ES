---
title: Directivas de restricción de llamada saliente para conferencias de Audio y usuario llamadas PSTN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 2/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Los administradores pueden controlar el tipo de audio llamadas PSTN conferencias y el usuario final que se pueden realizar los usuarios.
ms.openlocfilehash: ab6f34e46ceb6a9811830ba1444278db667de73c
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="ae724-103">Directivas de restricción de llamada saliente para conferencias de Audio y usuario llamadas PSTN</span><span class="sxs-lookup"><span data-stu-id="ae724-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="ae724-104">Como administrador, puede utilizar controles de llamada saliente para restringir el tipo de usuario final y conferencias PSTN llamadas de audio de que se pueden realizar los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="ae724-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="ae724-105">Controles de llamada saliente pueden aplicarse a cada usuario y proporcionan los siguientes dos controles para restringir de forma independiente cada tipo de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="ae724-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="ae724-106">De forma predeterminada, ambos controles están configurados para permitir llamadas salientes nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="ae724-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="ae724-107">Control</span><span class="sxs-lookup"><span data-stu-id="ae724-107">Control</span></span>|<span data-ttu-id="ae724-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae724-108">Description</span></span>|<span data-ttu-id="ae724-109">Opciones de control</span><span class="sxs-lookup"><span data-stu-id="ae724-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ae724-110">Llamadas de audio de conferencias PSTN</span><span class="sxs-lookup"><span data-stu-id="ae724-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="ae724-111">Restringe el tipo de salida</span><span class="sxs-lookup"><span data-stu-id="ae724-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="ae724-112">llamadas que se permiten desde dentro</span><span class="sxs-lookup"><span data-stu-id="ae724-112">calls that are allowed from within</span></span> </br><span data-ttu-id="ae724-113">reuniones organizadas por un usuario.</span><span class="sxs-lookup"><span data-stu-id="ae724-113">meetings organized by a user.</span></span>|<span data-ttu-id="ae724-114">Internacional y nacional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="ae724-114">International and Domestic (default)</span></span></br><span data-ttu-id="ae724-115">Nacionales</span><span class="sxs-lookup"><span data-stu-id="ae724-115">Domestic</span></span></br><span data-ttu-id="ae724-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="ae724-116">None</span></span>|
|<span data-ttu-id="ae724-117">Usuario final las llamadas PSTN</span><span class="sxs-lookup"><span data-stu-id="ae724-117">End user PSTN calls</span></span>|<span data-ttu-id="ae724-118">Restringe el tipo de llamadas</span><span class="sxs-lookup"><span data-stu-id="ae724-118">Restricts the type of calls</span></span> </br><span data-ttu-id="ae724-119">que puede ser realizado por un usuario.</span><span class="sxs-lookup"><span data-stu-id="ae724-119">that can be made by a user.</span></span>|<span data-ttu-id="ae724-120">Internacional y nacional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="ae724-120">International and Domestic (default)</span></span></br><span data-ttu-id="ae724-121">Nacionales</span><span class="sxs-lookup"><span data-stu-id="ae724-121">Domestic</span></span></br><span data-ttu-id="ae724-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="ae724-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="ae724-123">Una llamada se determina como doméstica Si el número de teléfono al que llame se encuentra en el mismo país como el país en el que se ha establecido en Office 365 para el organizador de la reunión (en el caso de conferencias de audio) o el usuario final (en el caso de las llamadas PSTN usuario final).</span><span class="sxs-lookup"><span data-stu-id="ae724-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 


## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="ae724-124">Restringir las llamadas salientes de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="ae724-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="ae724-125">**Utilizando los equipos de Microsoft y Skype para el centro de administración de negocios**</span><span class="sxs-lookup"><span data-stu-id="ae724-125">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="ae724-126">En la exploración de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="ae724-126">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="ae724-127">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ae724-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="ae724-128">Haga clic en el menú situado junto a **Los puentes de conferencia**y, a continuación, haga clic en **Editar** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ae724-128">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="ae724-129">En el panel de **proveedor de puente de conferencia** , en **restricciones de marcado de salida de las reuniones de este usuario**, seleccione la opción de restricción de acceso telefónico de salida que desee.</span><span class="sxs-lookup"><span data-stu-id="ae724-129">In the **Conference bridge provider** pane, under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="ae724-130">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="ae724-130">Click **Apply**.</span></span> 

<span data-ttu-id="ae724-131">Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ae724-131">**Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="ae724-132">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="ae724-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="ae724-133">En el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ae724-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="ae724-134">En **restricciones de marcado de salida de las reuniones de este usuario**, seleccione la opción de restricción de acceso telefónico de salida que desee.</span><span class="sxs-lookup"><span data-stu-id="ae724-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Las restricciones a las opciones de acceso telefónico de salida](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="ae724-136">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ae724-136">Click **Save**.</span></span>

<span data-ttu-id="ae724-137">**Uso de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ae724-137">**Using PowerShell**</span></span>

<span data-ttu-id="ae724-138">Restricciones de llamadas salientes están controladas por una directiva única denominada OnlineDialOutPolicy que tiene un atributo de restricción para cada uno.</span><span class="sxs-lookup"><span data-stu-id="ae724-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="ae724-139">No se puede personalizar la directiva, en su lugar, existen instancias de directivas predefinidas para cada combinación de la configuración.</span><span class="sxs-lookup"><span data-stu-id="ae724-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="ae724-140">Puede utilizar el cmdlet Get-CSOnlineDialOutPolicy para ver las directivas llamadas salientes y asignarlos a los usuarios mediante el cmdlet de concesión CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="ae724-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="ae724-141">(Tenga en cuenta que el cmdlet de concesión no contiene la palabra "En línea" igual que el cmdlet Get.)</span><span class="sxs-lookup"><span data-stu-id="ae724-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="ae724-142">En la siguiente tabla proporciona una visión general de cada directiva.</span><span class="sxs-lookup"><span data-stu-id="ae724-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ae724-143">Identidad = 'etiqueta: DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="ae724-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="ae724-144">Usuario en la conferencia puede marcar a números nacionales e internacionales, y este usuario puede realizar también llamadas salientes a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="ae724-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="ae724-145">Identidad = 'etiqueta: DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="ae724-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="ae724-146">Sólo puede marcar el usuario en la conferencia a números nacionales, y este usuario puede realizar llamadas salientes a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="ae724-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="ae724-147">Identidad = 'etiqueta: DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="ae724-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="ae724-148">Usuario de la conferencia no puede divisar cualquier marcado. Este usuario puede realizar llamadas salientes a números nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="ae724-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="ae724-149">Identidad = 'etiqueta: DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="ae724-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="ae724-150">Usuario en la conferencia puede marcar a números nacionales e internacionales, y este usuario sólo puede realizar llamadas salientes a número nacional de RTC.</span><span class="sxs-lookup"><span data-stu-id="ae724-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="ae724-151">Identidad = 'etiqueta: DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="ae724-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="ae724-152">Usuario en la conferencia puede marcar a números nacionales e internacionales, y este usuario no puede realizar llamadas salientes a número de RTC además de números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ae724-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="ae724-153">Identidad = 'etiqueta: DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="ae724-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="ae724-154">Sólo puede marcar el usuario en la conferencia a números nacionales, y este usuario sólo puede realizar llamadas salientes a números nacionales de RTC.</span><span class="sxs-lookup"><span data-stu-id="ae724-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="ae724-155">Identidad = 'etiqueta: DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="ae724-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="ae724-156">Sólo puede marcar el usuario en la conferencia a números nacionales, y este usuario no puede realizar llamadas salientes a número de RTC además de números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ae724-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="ae724-157">Identidad = 'etiqueta: DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="ae724-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="ae724-158">Usuario en la conferencia no puede realizar ninguna llamada de salida, y este usuario sólo puede realizar llamadas salientes a números nacionales de RTC.</span><span class="sxs-lookup"><span data-stu-id="ae724-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="ae724-159">Identidad = 'etiqueta: DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="ae724-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="ae724-160">Usuario en la conferencia no puede realizar ninguna llamada de salida, y este usuario no puede realizar llamadas salientes a número de RTC además de números de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ae724-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
