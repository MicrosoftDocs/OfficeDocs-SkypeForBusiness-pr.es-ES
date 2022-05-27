---
title: Compatibilidad con el uso de la funcionalidad SEFAUtil en Skype PowerShell en Skype Empresarial Server 2019
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Resumen: aprenda a usar PowerShell para obtener la funcionalidad SEFAUtil en Skype Empresarial Server 2019 después de instalar la actualización acumulativa 1.'
ms.openlocfilehash: 07d05ef1687fa9ca14f7e90108ae8b5c0e7e3bb9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676542"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Uso de la funcionalidad SEFAUtil mediante PowerShell en Skype Empresarial Server 2019

SEFAUtil (activación de características de extensión secundaria) permite a los administradores de Skype Empresarial Server y a los agentes del departamento de soporte técnico configurar la configuración de llamadas de delegado, reenvío de llamadas y recogida de llamadas en grupo en nombre de Skype Empresarial Server usuarios. SEFAUtil también permite a los administradores consultar la configuración de enrutamiento de llamadas para un usuario determinado.

Después de instalar la actualización acumulativa de julio de Skype Empresarial Server 2019, la siguiente funcionalidad que solo estaba disponible a través de SEFAUtil también estará disponible en Skype PowerShell:

- [Configuración del reenvío de llamadas](#call-forwarding-settings)
- [Configuración de delegación](#delegation-settings)
- [Miembros del equipo y configuración relacionada](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Configuración del reenvío de llamadas

Los administradores pueden cambiar la configuración del reenvío de llamadas mediante los siguientes comandos en PowerShell:

```powershell
Get-CsUserCallForwardingSettings -Identity <UserIdParameter>
```

Este comando devuelve la configuración de reenvío de llamadas del usuario especificado como un objeto y muestra lo mismo en la pantalla.

```powershell
Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]...
```

Este comando modifica la configuración de reenvío de llamadas del usuario especificado. Este comando devuelve la configuración de reenvío de llamadas del usuario especificado como un objeto y muestra lo mismo en la pantalla. Si el comando no se ejecuta correctamente, se mostrará un mensaje de error adecuado.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

Este comando deshabilita la configuración de reenvío de llamadas del usuario (aquí se muestran dos ejemplos de parámetros diferentes).

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

Este comando modifica la configuración de reenvío de llamadas del usuario.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]
```

Este comando modifica la configuración del anillo simultáneo (de nuevo, con dos ejemplos de parámetros, uno para el correo de voz sin respuesta y el segundo sin respuesta a otro).

## <a name="delegation-settings"></a>Configuración de delegación

Los administradores pueden cambiar la configuración de delegación mediante el siguiente comando en PowerShell:

```powershell
Get-CsuserDelegates -Identity <UserIdParameter>
```

Este comando devuelve un objeto de lista de delegados y muestra la lista de delegados del usuario especificado. Si el comando no se ejecuta correctamente, se mostrará un mensaje de error adecuado.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]
```

Este comando modifica la configuración de delegación del usuario especificado, devuelve un objeto de lista de delegados y muestra la lista de delegados. Si el comando no se ejecuta correctamente, se mostrará un mensaje de error adecuado.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]
```

Este comando agrega o quita un delegado.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]
```

Este comando establece una lista de delegados en delegados específicos.

## <a name="team-members-and-related-settings"></a>Miembros del equipo y configuración relacionada

Los administradores pueden cambiar los miembros del equipo y la configuración relacionada mediante el siguiente comando en PowerShell:

```powershell
Get-CsUserTeamMembers -Identity <UserIdParameter>
```

Este comando devuelve un objeto que contiene la lista de miembros del equipo y muestra el objeto en pantalla. Si el comando no se ejecuta correctamente, se mostrará un mensaje de error adecuado.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]
```

Este comando modifica la lista de miembros del equipo del usuario especificado, devuelve un objeto que contiene la lista de miembros del equipo y muestra el objeto en la pantalla. Si el comando no se ejecuta correctamente, se mostrará un mensaje de error adecuado.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]
```

Este comando agrega o quita miembros del equipo.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]
```

Este comando establece una lista de equipos en miembros específicos.

## <a name="more-information"></a>Más información

En el caso de las implementaciones locales, los cmdlets introducidos en esta característica solo los pueden ejecutar los miembros de los siguientes grupos, según el nivel de acceso especificado a continuación:

- CsAdministrator: obtener y establecer para todos los cmdlets
- CsVoiceAdministrator: Obtener y establecer para todos los cmdlets
- CsHelpDesk: obtención de todos los cmdlets

Para obtener más información sobre estos roles de administrador, consulte [Creación de administradores de Skype Empresarial Server Panel de control](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). El administrador puede acceder a estos cmdlets iniciando sesión directamente o de forma remota en un equipo servidor.
En el caso de una implementación híbrida, los administradores de Skype Empresarial deben poder llamar a Get y Set para todos los cmdlets. Para obtener más información sobre la lista completa de roles, consulte [Acerca de los roles de administrador](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> La detección automática del servidor debe estar habilitada. No se introducirán requisitos de licencia adicionales para el uso de los cmdlets.
