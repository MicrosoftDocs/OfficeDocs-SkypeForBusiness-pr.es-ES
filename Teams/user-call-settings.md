---
title: Configurar las opciones de llamada para los usuarios
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
description: Obtenga información sobre cómo configurar las opciones de usuario para el desvío de llamadas y la delegación.
ms.openlocfilehash: 64907043448f44ff861ede026d0a4343899ad98b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272235"
---
# <a name="configure-call-settings-for-your-users"></a>Configurar las opciones de llamada para los usuarios

En este artículo se describe cómo el administrador puede cambiar la configuración de delegación y desvío de llamadas para los usuarios. Es posible que quiera cambiar esta configuración, por ejemplo, si:

- Un usuario está en bajas por enfermedad y necesita asegurarse de que las llamadas entrantes al usuario se desvíen a un compañero.
- Debe inspeccionar la configuración del desvío de llamadas para todos los usuarios de un departamento y posiblemente corregirlos según corresponda.
- Se ha empleado un nuevo asistente y necesita agregar al asistente como delegado de un grupo de empleados.

Puede usar el Centro de administración de Teams o los cmdlets de PowerShell de Teams para ver y cambiar la configuración de llamadas de los usuarios.

Para establecer la configuración de llamadas de un usuario, el usuario debe tener asignada una licencia de Microsoft Phone System.

## <a name="use-the-teams-admin-center"></a>Usar el Centro de administración de Teams

Puede usar el Centro de administración de Teams para configurar opciones de desvío de llamadas y sin responder, selección de llamadas grupales y delegación de llamadas para los usuarios.

Para configurar las opciones de desvío de llamadas inmediato:

1. En el Centro de administración de Teams, vaya a **Usuarios** > **Administrar usuarios** y seleccione un usuario.

2. En la página de detalles del usuario, vaya a la pestaña **Voz** .

3. En **Reglas de respuesta de llamadas**, seleccione **Desviarse inmediatamente** y seleccione el destino y el tipo de desvío de llamadas adecuados.

Para configurar la llamada simultánea, en la misma página, seleccione **Llamar a los dispositivos del usuario**. En la lista desplegable **Permitir también** , seleccione la configuración de llamada simultánea adecuada.

Para configurar opciones sin responder, en la misma página, seleccione la configuración adecuada en la lista desplegable **Si no se ha respondido** . En la lista desplegable **Llamar durante estos segundos antes de redirigir** , especifique el número de segundos que debe esperar.

La configuración de la delegación de llamadas y la recogida de llamadas de grupo se integran en el desvío de llamadas y las configuraciones no respondidas seleccionando el tipo adecuado. Por ejemplo, para configurar que las llamadas también llamen a los delegados del usuario, en la misma página seleccione **Delegación de llamadas** en **Permitir también**. A continuación, agregue los delegados adecuados seleccionando **Agregar personas** y haciendo clic en **Guardar**.

## <a name="use-powershell"></a>Usar PowerShell

Puede usar PowerShell para configurar las opciones de desvío y delegación de llamadas para los usuarios.  Usará los siguientes cmdlets, que están disponibles en la versión 4.0 o posterior del módulo PowerShell de Teams:

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings) : muestra la configuración del desvío de llamadas, los delegados y la información del delegador de un usuario.
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings) : establece la configuración del desvío de llamadas para un usuario.
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate) : agrega un nuevo delegado con permisos para un usuario.
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate) : cambia los permisos de un delegado existente.
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate) : quita un delegado de un usuario.

### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Mostrar la configuración de desvío y delegación de llamadas para un usuario

Para mostrar la configuración actual de desvío de llamadas y delegación de un usuario, use el cmdlet de Get-CsUserCallingSettings, como se muestra en el ejemplo siguiente:

```PowerShell
Get-CsUserCallingSettings -Identity user1@contoso.com
SipUri                    : sip:opr1@contoso.com
IsForwardingEnabled       : True
ForwardingType            : Simultaneous
ForwardingTarget          :
ForwardingTargetType      : MyDelegates
IsUnansweredEnabled       : True
UnansweredTarget          :
UnansweredTargetType      : Voicemail
UnansweredDelay           : 00:00:20
Delegates                 : Id:sip:user2@contoso.com
Delegators                :
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : sip:user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

La salida muestra que user1 tiene llamadas simultáneas a los delegados configurados. Las llamadas no respondidas se envían al correo de voz después de 20 segundos. User2 se define como el delegado con todos los permisos de delegado.

### <a name="set-call-forward-settings-for-a-user"></a>Establecer la configuración del desvío de llamadas para un usuario

Para desviar todas las llamadas de user1 a user2, use el cmdlet Set-CsUserCallingSettings, como se muestra en el siguiente ejemplo:

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Para llamar simultáneamente a todos los delegados para user3, use el cmdlet Set-CsUserCallingSettings, como se muestra en el ejemplo siguiente:

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

En el ejemplo siguiente se usa el cmdlet Set-CsUserCallingSettings para configurar un grupo de llamadas para user4 con user5 y user6 como miembros. Todas las llamadas a los miembros del grupo se desvían en el orden en que se definen:

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Para obtener más ejemplos, vea [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings).

### <a name="add-a-calling-delegate-for-a-user"></a>Agregar un delegado de llamada para un usuario

Para agregar user2 como delegado de usuario1 con todos los permisos permitidos, use el cmdlet de New-CsUserCallingDelegate, como se muestra en el ejemplo siguiente:

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Cambiar los permisos de los delegados de llamadas

Para cambiar los permisos de delegado (por ejemplo, para que el usuario2 no pueda realizar llamadas para usuario1), use el cmdlet Set-CsUserCallingDelegate como se muestra en el ejemplo siguiente:

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Quitar un delegado de llamadas de un usuario

Para quitar user2 como delegado de usuario1, use el cmdlet de Remove-CsUserCallingDelegate, como se muestra en el siguiente ejemplo:

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```

## <a name="related-topics"></a>Temas relacionados

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)
