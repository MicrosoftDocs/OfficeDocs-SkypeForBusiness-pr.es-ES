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
ms.openlocfilehash: 1a18a954e40ba7a0c72e4d87b4b3c943e827f2a1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049142"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Uso de la funcionalidad SEFAUtil a través de PowerShell en Skype empresarial Server 2019

SEFAUtil (la activación de características de extensión secundaria) permite a los administradores de Skype empresarial Server y a los agentes de asistencia técnica configurar la llamada delegada, el desvío de llamadas y la configuración de remisión de grupo en nombre de un usuario de Skype empresarial Server. Esta herramienta también permite a los administradores consultar la configuración de enrutamiento de llamadas publicada para un usuario en particular. Después de instalar la actualización acumulativa de Skype empresarial Server 2019 de julio, la siguiente funcionalidad que actualmente se puede administrar a través de SEFAUtil también será administrable a través de PowerShell:

- [Configuración de desvío de llamadas](#call-forwarding-settings)
- [Configuración de delegación](#delegation-settings)
- [Miembros del equipo y configuración relacionada](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Configuración de desvío de llamadas

Los administradores pueden cambiar la configuración de desvío de llamadas mediante el siguiente cmdlet en PowerShell:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Este cmdlet devuelve la configuración de desvío de llamadas del usuario especificada como un objeto y muestra la misma en la pantalla.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Este cmdlet modifica la configuración de desvío de llamadas del usuario especificado. Este cmdlet devuelve la configuración de desvío de llamadas del usuario especificada como un objeto y muestra lo mismo en la pantalla, en caso de éxito. En caso de error, se mostrará un mensaje de error apropiado.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Este cmdlet deshabilita la configuración de desvío de llamadas del usuario (aquí se muestran dos ejemplos de parámetros distintos).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Este cmdlet modifica la configuración de desvío de llamadas del usuario.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Este cmdlet modifica la configuración de situaciones (de nuevo, con dos ejemplos de parámetros, uno para no tener respuesta al correo de voz y el segundo que no responde a otros).

## <a name="delegation-settings"></a>Configuración de delegación

Los administradores pueden cambiar la configuración de delegación mediante el siguiente cmdlet en PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Este cmdlet devuelve una lista de objetos delegados y muestra la lista de delegados del usuario especificado, en caso de éxito. En caso de error, se mostrará un mensaje de error apropiado.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Este cmdlet modifica la configuración de delegación del usuario especificada, devuelve una lista de objetos delegados y muestra la lista de delegados en caso de éxito. En caso de error, se mostrará un mensaje de error apropiado. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Este cmdlet agrega o quita un delegado.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Este cmdlet establece una lista de delegados en delegados específicos.

## <a name="team-members-and-related-settings"></a>Miembros del equipo y configuración relacionada

Los administradores pueden cambiar los miembros del equipo y la configuración relacionada mediante el siguiente cmdlet en PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Este cmdlet devuelve un objeto que contiene una lista de miembros del equipo y muestra el objeto en la pantalla, en caso de que se haya realizado correctamente. En caso de error, se mostrará un mensaje de error apropiado.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Este cmdlet modifica la lista de miembros del equipo del usuario especificado, devuelve un objeto que contiene la lista de miembros del equipo y muestra el objeto en la pantalla, en caso de que se haya realizado correctamente. En caso de error, se mostrará un mensaje de error apropiado.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Este cmdlet agrega o quita miembros del equipo.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Este cmdlet establece una lista de equipos en miembros específicos.

## <a name="more-information"></a>Más información

En el caso de las implementaciones locales, los cmdlets que se presentaron en esta característica solo los pueden ejecutar los miembros de los siguientes grupos, según el nivel de acceso especificado a continuación:

- CsAdministrator – get y set para todos los cmdlets
- CsVoiceAdministrator-get y set para todos los cmdlets
- CsHelpDesk: obtener para todos los cmdlets

Para obtener más información sobre estos roles de administrador, consulte [crear administradores del panel de control de Skype empresarial Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). El administrador puede tener acceso a estos cmdlets al iniciar sesión de forma directa o remota en un equipo servidor.
Para una implementación híbrida, los administradores de Skype empresarial deben poder llamar a get y set para todos los cmdlets. Para obtener más información acerca de la lista completa de funciones, consulte Acerca de los [roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)

> [!NOTE]
> La detección automática de servidores debe estar habilitada. No se presentarán requisitos de licencia adicionales para el uso de los cmdlets.
