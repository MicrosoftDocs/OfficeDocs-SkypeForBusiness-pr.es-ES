---
title: Compatibilidad con el uso de la funcionalidad de SEFAUtil en PowerShell en Skype empresarial Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: Obtenga información sobre cómo usar PowerShell para obtener la funcionalidad de SEFAUtil en Skype empresarial Server 2019 después de instalar la actualización acumulativa 1.'
ms.openlocfilehash: 19c3ba1124bbc1f32f301096036404f8bd101fe9
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868557"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="328fe-103">Uso de la funcionalidad SEFAUtil a través de PowerShell en Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="328fe-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="328fe-104">SEFAUtil (la activación de características de extensión secundaria) permite a los administradores de Skype empresarial Server y a los agentes de asistencia técnica configurar la llamada delegada, el desvío de llamadas y la configuración de remisión de grupo en nombre de un usuario de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="328fe-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="328fe-105">Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas publicada para un usuario en particular.</span><span class="sxs-lookup"><span data-stu-id="328fe-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="328fe-106">Después de instalar la actualización acumulativa de Skype empresarial Server 2019 de julio, la siguiente funcionalidad que actualmente se puede administrar a través de SEFAUtil también será administrable a través de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="328fe-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="328fe-107">Configuración de desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="328fe-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="328fe-108">Configuración de delegación</span><span class="sxs-lookup"><span data-stu-id="328fe-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="328fe-109">Miembros del equipo y configuración relacionada</span><span class="sxs-lookup"><span data-stu-id="328fe-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="328fe-110">Configuración de desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="328fe-110">Call forwarding settings</span></span>

<span data-ttu-id="328fe-111">Los administradores pueden cambiar la configuración de desvío de llamadas mediante el siguiente cmdlet en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="328fe-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="328fe-112">Este cmdlet devuelve la configuración de desvío de llamadas del usuario especificada como un objeto y muestra la misma en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="328fe-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="328fe-113">Este cmdlet modifica la configuración de desvío de llamadas del usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="328fe-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="328fe-114">Este cmdlet devuelve la configuración de desvío de llamadas del usuario especificada como un objeto y muestra lo mismo en la pantalla, en caso de éxito.</span><span class="sxs-lookup"><span data-stu-id="328fe-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="328fe-115">En caso de error, se mostrará un mensaje de error apropiado.</span><span class="sxs-lookup"><span data-stu-id="328fe-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="328fe-116">Este cmdlet deshabilita la configuración de desvío de llamadas del usuario (aquí se muestran dos ejemplos de parámetros distintos).</span><span class="sxs-lookup"><span data-stu-id="328fe-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="328fe-117">Este cmdlet modifica la configuración de desvío de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="328fe-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="328fe-118">Este cmdlet modifica la configuración de situaciones (de nuevo, con dos ejemplos de parámetros, uno para no tener respuesta al correo de voz y el segundo que no responde a otros).</span><span class="sxs-lookup"><span data-stu-id="328fe-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="328fe-119">Configuración de delegación</span><span class="sxs-lookup"><span data-stu-id="328fe-119">Delegation settings</span></span>

<span data-ttu-id="328fe-120">Los administradores pueden cambiar la configuración de delegación mediante el siguiente cmdlet en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="328fe-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="328fe-121">Este cmdlet devuelve una lista de objetos delegados y muestra la lista de delegados del usuario especificado, en caso de éxito.</span><span class="sxs-lookup"><span data-stu-id="328fe-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="328fe-122">En caso de error, se mostrará un mensaje de error apropiado.</span><span class="sxs-lookup"><span data-stu-id="328fe-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="328fe-123">Este cmdlet modifica la configuración de delegación del usuario especificada, devuelve una lista de objetos delegados y muestra la lista de delegados en caso de éxito.</span><span class="sxs-lookup"><span data-stu-id="328fe-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="328fe-124">En caso de error, se mostrará un mensaje de error apropiado.</span><span class="sxs-lookup"><span data-stu-id="328fe-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="328fe-125">Este cmdlet agrega o quita un delegado.</span><span class="sxs-lookup"><span data-stu-id="328fe-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="328fe-126">Este cmdlet establece una lista de delegados en delegados específicos.</span><span class="sxs-lookup"><span data-stu-id="328fe-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="328fe-127">Miembros del equipo y configuración relacionada</span><span class="sxs-lookup"><span data-stu-id="328fe-127">Team members and related settings</span></span>

<span data-ttu-id="328fe-128">Los administradores pueden cambiar los miembros del equipo y la configuración relacionada mediante el siguiente cmdlet en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="328fe-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="328fe-129">Este cmdlet devuelve un objeto que contiene una lista de miembros del equipo y muestra el objeto en la pantalla, en caso de que se haya realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="328fe-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="328fe-130">En caso de error, se mostrará un mensaje de error apropiado.</span><span class="sxs-lookup"><span data-stu-id="328fe-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="328fe-131">Este cmdlet modifica la lista de miembros del equipo del usuario especificado, devuelve un objeto que contiene la lista de miembros del equipo y muestra el objeto en la pantalla, en caso de que se haya realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="328fe-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="328fe-132">En caso de error, se mostrará un mensaje de error apropiado.</span><span class="sxs-lookup"><span data-stu-id="328fe-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="328fe-133">Este cmdlet agrega o quita miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="328fe-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="328fe-134">Este cmdlet establece una lista de equipos en miembros específicos.</span><span class="sxs-lookup"><span data-stu-id="328fe-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="328fe-135">Más información</span><span class="sxs-lookup"><span data-stu-id="328fe-135">More information</span></span>

<span data-ttu-id="328fe-136">En el caso de las implementaciones locales, los cmdlets que se presentaron en esta característica solo los pueden ejecutar los miembros de los siguientes grupos, según el nivel de acceso especificado a continuación:</span><span class="sxs-lookup"><span data-stu-id="328fe-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="328fe-137">CsAdministrator – get y set para todos los cmdlets</span><span class="sxs-lookup"><span data-stu-id="328fe-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="328fe-138">CsVoiceAdministrator-get y set para todos los cmdlets</span><span class="sxs-lookup"><span data-stu-id="328fe-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="328fe-139">CsHelpDesk: obtener para todos los cmdlets</span><span class="sxs-lookup"><span data-stu-id="328fe-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="328fe-140">Para obtener más información sobre estos roles de administrador, consulte [crear administradores del panel de control de Skype empresarial Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="328fe-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="328fe-141">El administrador puede tener acceso a estos cmdlets al iniciar sesión de forma directa o remota en un equipo servidor.</span><span class="sxs-lookup"><span data-stu-id="328fe-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="328fe-142">Para una implementación híbrida, los administradores de Skype empresarial deben poder llamar a get y set para todos los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="328fe-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="328fe-143">Para obtener más información acerca de la lista completa de roles, consulte Acerca de los [roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="328fe-143">For more information about the full list of roles, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

> [!NOTE]
> <span data-ttu-id="328fe-144">La detección automática de servidores debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="328fe-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="328fe-145">No se presentarán requisitos de licencia adicionales para el uso de los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="328fe-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
