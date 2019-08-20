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
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: Aprenda a usar PowerShell para obtener la funcionalidad de SEFAUtil en Skype empresarial Server 2019 después de instalar la actualización acumulativa 1.'
ms.openlocfilehash: 6e0f7fc8e4bbb25564faa8107dec81ae3887b360
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464559"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Usar la funcionalidad de SEFAUtil a través de PowerShell en Skype empresarial Server 2019

SEFAUtil (la activación de características de extensión secundaria) permite a los administradores de Skype para empresas y a los agentes del Departamento de soporte técnico configurar llamadas delegadas, el desvío de llamadas y la recopilación de llamadas grupales en nombre de un usuario de Skype empresarial Server. Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas que se haya publicado para un usuario concreto. Después de instalar la actualización acumulativa de Skype empresarial Server 2019 de julio, la siguiente funcionalidad que actualmente se puede administrar a través de SEFAUtil también se podrá administrar a través de PowerShell:

- [Configuración de desvío de llamadas](#call-forwarding-settings)
- [Configuración de delegación](#delegation-settings)
- [Miembros del equipo y configuración relacionada](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Configuración de desvío de llamadas

Los administradores pueden cambiar la configuración del desvío de llamadas con el siguiente cmdlet de PowerShell:

- `Get-CsUserForwardingSettings -Identity <UserIdParameter>`

Este cmdlet devuelve la configuración de desvío de llamadas del usuario especificada como un objeto y muestra lo mismo en la pantalla.

- `Set-CsUserForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Este cmdlet modifica la configuración de desvío de llamadas del usuario especificado. Este cmdlet devuelve la configuración de desvío de llamadas del usuario especificado como un objeto, y muestra lo mismo en la pantalla, en caso de que se haya realizado correctamente. En caso de error, se mostrará un mensaje de error adecuado.

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Este cmdlet deshabilita la configuración de desvío de llamadas del usuario (aquí se muestran dos ejemplos de parámetros diferentes).

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Este cmdlet modifica la configuración del desvío de llamadas del usuario.

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Este cmdlet modifica la configuración de SimulRing (de nuevo, con dos ejemplos de parámetros, uno para no contestar al buzón de voz y el segundo no responde a otros).

## <a name="delegation-settings"></a>Configuración de delegación

Los administradores pueden cambiar la configuración de delegación mediante el siguiente cmdlet de PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Este cmdlet devuelve un objeto de la lista de delegados y muestra la lista de delegados del usuario especificado, en caso de éxito. En caso de error, se mostrará un mensaje de error adecuado.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Este cmdlet modifica la configuración de delegación del usuario especificado, devuelve un objeto de lista de delegados y muestra la lista de delegados, en caso de éxito. En caso de error, se mostrará un mensaje de error adecuado. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Este cmdlet agrega o quita un delegado.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Este cmdlet establece una lista de delegados en delegados específicos.

## <a name="team-members-and-related-settings"></a>Miembros del equipo y configuración relacionada

Los administradores pueden cambiar los miembros del equipo y la configuración relacionada con el siguiente cmdlet de PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Este cmdlet devuelve un objeto que contiene una lista de miembros del equipo y muestra el objeto en la pantalla, en caso de que se haya realizado correctamente. En caso de error, se mostrará un mensaje de error adecuado.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Este cmdlet modifica la lista de miembros del equipo del usuario especificado, devuelve un objeto que contiene la lista de miembros del equipo y muestra el objeto en la pantalla, en caso de éxito. En caso de error, se mostrará un mensaje de error adecuado.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Este cmdlet agrega o quita miembros del equipo.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Este cmdlet establece una lista de equipos en miembros específicos.

## <a name="more-information"></a>Más información

En el caso de las implementaciones locales, los cmdlets introducidos en esta característica solo los pueden ejecutar los miembros de los siguientes grupos, según el nivel de acceso especificado a continuación:

- CsAdministrator: obtener y establecer para todos los cmdlets
- CsVoiceAdministrator: obtener y establecer para todos los cmdlets
- CsHelpDesk: obtener para todos los cmdlets

Para obtener más información sobre estos roles de administrador, consulte [crear administradores del panel de control de Skype empresarial Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). El administrador puede acceder a estos cmdlets, iniciando sesión en un equipo servidor de forma directa o remota.
Para una implementación híbrida, los administradores de Skype empresarial deben poder llamar a get y set para todos los cmdlets. Para obtener más información sobre la lista completa de roles, consulte Acerca de los [roles de administrador de Office 365](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)

> [!NOTE]
> La detección automática del servidor debe estar habilitada. No se introducirán requisitos de licencia adicionales para el uso de los cmdlets.
