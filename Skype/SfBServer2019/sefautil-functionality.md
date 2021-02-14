---
title: Compatibilidad con el uso de la funcionalidad SEFAUtil en PowerShell en Skype Empresarial Server 2019
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
description: 'Resumen: obtenga información sobre cómo usar PowerShell para obtener la funcionalidad SEFAUtil en Skype Empresarial Server 2019 después de instalar la actualización acumulativa 1.'
ms.openlocfilehash: 19c3ba1124bbc1f32f301096036404f8bd101fe9
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868557"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="fdec8-103">Uso de la funcionalidad SEFAUtil a través de PowerShell en Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="fdec8-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="fdec8-104">SEFAUtil (activación de características de extensión secundaria) permite a los administradores de Skype Empresarial Server y a los agentes del departamento de soporte técnico configurar las opciones de llamadas delegadas, reenvío de llamadas y atención de llamadas grupales en nombre de un usuario de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fdec8-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="fdec8-105">Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas que se publica para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="fdec8-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="fdec8-106">Después de instalar la actualización acumulativa de julio de Skype Empresarial Server 2019, la siguiente funcionalidad que actualmente solo se puede administrar a través de SEFAUtil también se podrá administrar a través de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fdec8-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="fdec8-107">Configuración de reenvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="fdec8-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="fdec8-108">Configuración de delegación</span><span class="sxs-lookup"><span data-stu-id="fdec8-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="fdec8-109">Miembros del equipo y configuración relacionada</span><span class="sxs-lookup"><span data-stu-id="fdec8-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="fdec8-110">Configuración de reenvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="fdec8-110">Call forwarding settings</span></span>

<span data-ttu-id="fdec8-111">Los administradores pueden cambiar la configuración de reenvío de llamadas mediante el siguiente cmdlet en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fdec8-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="fdec8-112">Este cmdlet devuelve la configuración de reenvío de llamadas del usuario especificado como un objeto y muestra lo mismo en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="fdec8-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="fdec8-113">Este cmdlet modifica la configuración de reenvío de llamadas del usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="fdec8-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="fdec8-114">Este cmdlet devuelve la configuración de reenvío de llamadas del usuario especificado como un objeto y muestra lo mismo en la pantalla, en caso de éxito.</span><span class="sxs-lookup"><span data-stu-id="fdec8-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="fdec8-115">En caso de error, se mostrará un mensaje de error adecuado.</span><span class="sxs-lookup"><span data-stu-id="fdec8-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="fdec8-116">Este cmdlet deshabilita la configuración de reenvío de llamadas del usuario (aquí se muestran dos ejemplos de parámetros diferentes).</span><span class="sxs-lookup"><span data-stu-id="fdec8-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="fdec8-117">Este cmdlet modifica la configuración de reenvío de llamadas del usuario.</span><span class="sxs-lookup"><span data-stu-id="fdec8-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="fdec8-118">Este cmdlet modifica la configuración de SimulRing (de nuevo, con dos ejemplos de parámetros, uno para no responder al correo de voz y el otro sin responder a otro).</span><span class="sxs-lookup"><span data-stu-id="fdec8-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="fdec8-119">Configuración de delegación</span><span class="sxs-lookup"><span data-stu-id="fdec8-119">Delegation settings</span></span>

<span data-ttu-id="fdec8-120">Los administradores pueden cambiar la configuración de delegación mediante el siguiente cmdlet en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fdec8-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="fdec8-121">Este cmdlet devuelve un objeto de lista de delegados y muestra la lista de delegados del usuario especificado, en caso de éxito.</span><span class="sxs-lookup"><span data-stu-id="fdec8-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="fdec8-122">En caso de error, se mostrará un mensaje de error adecuado.</span><span class="sxs-lookup"><span data-stu-id="fdec8-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="fdec8-123">Este cmdlet modifica la configuración de delegación del usuario especificado, devuelve un objeto de lista de delegados y muestra la lista de delegados, en caso de éxito.</span><span class="sxs-lookup"><span data-stu-id="fdec8-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="fdec8-124">En caso de error, se mostrará un mensaje de error adecuado.</span><span class="sxs-lookup"><span data-stu-id="fdec8-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="fdec8-125">Este cmdlet agrega o quita un delegado.</span><span class="sxs-lookup"><span data-stu-id="fdec8-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="fdec8-126">Este cmdlet establece una lista de delegados para delegados específicos.</span><span class="sxs-lookup"><span data-stu-id="fdec8-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="fdec8-127">Miembros del equipo y configuración relacionada</span><span class="sxs-lookup"><span data-stu-id="fdec8-127">Team members and related settings</span></span>

<span data-ttu-id="fdec8-128">Los administradores pueden cambiar los miembros del equipo y la configuración relacionada mediante el siguiente cmdlet en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fdec8-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="fdec8-129">Este cmdlet devuelve un objeto que contiene una lista de miembros del equipo y muestra el objeto en pantalla, en caso de éxito.</span><span class="sxs-lookup"><span data-stu-id="fdec8-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="fdec8-130">En caso de error, se mostrará un mensaje de error adecuado.</span><span class="sxs-lookup"><span data-stu-id="fdec8-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="fdec8-131">Este cmdlet modifica la lista de miembros del equipo del usuario especificado, devuelve un objeto que contiene la lista de miembros del equipo y muestra el objeto en pantalla, en caso de éxito.</span><span class="sxs-lookup"><span data-stu-id="fdec8-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="fdec8-132">En caso de error, se mostrará un mensaje de error adecuado.</span><span class="sxs-lookup"><span data-stu-id="fdec8-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="fdec8-133">Este cmdlet agrega o quita miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="fdec8-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="fdec8-134">Este cmdlet establece una lista de equipos para miembros específicos.</span><span class="sxs-lookup"><span data-stu-id="fdec8-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="fdec8-135">Más información</span><span class="sxs-lookup"><span data-stu-id="fdec8-135">More information</span></span>

<span data-ttu-id="fdec8-136">Para las implementaciones locales, los cmdlets introducidos en esta característica solo pueden ejecutar los miembros de los siguientes grupos, según el nivel de acceso especificado a continuación:</span><span class="sxs-lookup"><span data-stu-id="fdec8-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="fdec8-137">CsAdministrator: Obtener y establecer para todos los cmdlets</span><span class="sxs-lookup"><span data-stu-id="fdec8-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="fdec8-138">CsVoiceAdministrator: Obtener y establecer para todos los cmdlets</span><span class="sxs-lookup"><span data-stu-id="fdec8-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="fdec8-139">CsHelpDesk: obtener para todos los cmdlets</span><span class="sxs-lookup"><span data-stu-id="fdec8-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="fdec8-140">Para obtener más información sobre estos roles de administrador, consulte Crear administradores del Panel de [control de Skype Empresarial Server.](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)</span><span class="sxs-lookup"><span data-stu-id="fdec8-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="fdec8-141">El administrador puede obtener acceso a estos cmdlets iniciando sesión de forma directa o remota en un equipo servidor.</span><span class="sxs-lookup"><span data-stu-id="fdec8-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="fdec8-142">Para una implementación híbrida, los administradores de Skype Empresarial deben poder llamar a Get y Set para todos los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fdec8-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="fdec8-143">Para obtener más información acerca de la lista completa de roles, vea [Acerca de los roles de administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="fdec8-143">For more information about the full list of roles, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

> [!NOTE]
> <span data-ttu-id="fdec8-144">La detección automática del servidor debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="fdec8-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="fdec8-145">No se introducirán requisitos de licencia adicionales para el uso de los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fdec8-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
