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
description: 'Summary: Learn how to use PowerShell to obtain SEFAUtil functionality in Skype Empresarial Server 2019 after installing Cumulative Update 1.'
ms.openlocfilehash: afb0c34afedde91bac40ee90b155809ed3c2b557d88608028b77e0835eb9661d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277625"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Uso de la funcionalidad SEFAUtil a través de PowerShell en Skype Empresarial Server 2019

SEFAUtil (activación de características de extensión secundaria) permite Skype Empresarial Server administradores y agentes de soporte técnico configurar las opciones de delegación, reenvío de llamadas y recogida de llamadas en grupo en nombre de un Skype Empresarial Server usuario. Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas que se publica para un usuario determinado. Después de instalar la actualización acumulativa de Skype Empresarial Server de julio de 2019, las siguientes funciones que actualmente solo se pueden administrar a través de SEFAUtil también se podrán administrar a través de PowerShell:

- [Configuración de reenvío de llamadas](#call-forwarding-settings)
- [Configuración de delegación](#delegation-settings)
- [Miembros del equipo y configuración relacionada](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Configuración de reenvío de llamadas

Los administradores pueden cambiar la configuración de reenvío de llamadas mediante el siguiente cmdlet en PowerShell:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Este cmdlet devuelve la configuración de reenvío de llamadas del usuario especificado como un objeto y muestra lo mismo en la pantalla.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Este cmdlet modifica la configuración de reenvío de llamadas del usuario especificado. Este cmdlet devuelve la configuración de reenvío de llamadas del usuario especificado como un objeto y muestra lo mismo en la pantalla, en caso de éxito. En caso de error, se mostrará un mensaje de error adecuado.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Este cmdlet deshabilita la configuración de reenvío de llamadas del usuario (aquí se muestran dos ejemplos de parámetros diferentes).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Este cmdlet modifica la configuración de reenvío de llamadas del usuario.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Este cmdlet modifica la configuración de anillo simultánea (de nuevo, con dos ejemplos de parámetros, uno para no responder al correo de voz y el segundo sin responder a otro).

## <a name="delegation-settings"></a>Configuración de delegación

Los administradores pueden cambiar la configuración de delegación mediante el siguiente cmdlet en PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Este cmdlet devuelve un objeto de lista de delegados y muestra la lista de delegados del usuario especificado, en caso de éxito. En caso de error, se mostrará un mensaje de error adecuado.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Este cmdlet modifica la configuración de delegación del usuario especificado, devuelve un objeto de lista de delegados y muestra la lista de delegados, en caso de éxito. En caso de error, se mostrará un mensaje de error adecuado. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Este cmdlet agrega o quita un delegado.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Este cmdlet establece una lista de delegados en delegados específicos.

## <a name="team-members-and-related-settings"></a>Miembros del equipo y configuración relacionada

Los administradores pueden cambiar los miembros del equipo y la configuración relacionada mediante el siguiente cmdlet en PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Este cmdlet devuelve un objeto que contiene una lista de miembros del equipo y muestra el objeto en pantalla, en caso de éxito. En caso de error, se mostrará un mensaje de error adecuado.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Este cmdlet modifica la lista de miembros del equipo del usuario especificado, devuelve un objeto que contiene la lista de miembros del equipo y muestra el objeto en la pantalla, en caso de éxito. En caso de error, se mostrará un mensaje de error adecuado.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Este cmdlet agrega o quita miembros del equipo.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Este cmdlet establece una lista de equipos en miembros específicos.

## <a name="more-information"></a>Más información

Para las implementaciones locales, los cmdlets introducidos en esta característica solo los pueden ejecutar los miembros de los siguientes grupos, según el nivel de acceso especificado a continuación:

- CsAdministrator: Obtener y establecer para todos los cmdlets
- CsVoiceAdministrator: Obtener y establecer para todos los cmdlets
- CsHelpDesk: Obtener para todos los cmdlets

Para obtener más información sobre estos roles de administrador, [vea Create Skype Empresarial Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). El administrador puede tener acceso a estos cmdlets iniciando sesión de forma directa o remota en un equipo servidor.
Para una implementación híbrida, Skype Empresarial administradores deben poder llamar a Get y Set para todos los cmdlets. Para obtener más información acerca de la lista completa de roles, vea [About admin roles](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> La detección automática del servidor debe estar habilitada. No se introducirán requisitos de licencia adicionales para el uso de los cmdlets.
