---
title: Configurar la configuración de llamadas para los usuarios
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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Obtenga información sobre cómo configurar la configuración de usuario para el reenvío de llamadas y la delegación.
ms.openlocfilehash: 5443ad958d23753b1d67d42782ddab41d9d6d080
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2022
ms.locfileid: "63689174"
---
# <a name="configure-call-settings-for-your-users"></a>Configurar la configuración de llamadas para los usuarios

En este artículo se describe cómo usted, el administrador, puede cambiar la configuración de reenvío de llamadas y delegación para los usuarios. Es posible que quiera cambiar esta configuración, por ejemplo, si:

- Un usuario está de baja por enfermedad y debe asegurarse de que las llamadas entrantes al usuario se reenvía a un compañero.

- Debe inspeccionar la configuración de reenvío de llamadas para todos los usuarios de un departamento y, posiblemente, corregirlas según corresponda.

- Se ha empleado un nuevo asistente y debe agregar el asistente como delegado para un grupo de empleados.

Puede usar el Teams de administración o Teams cmdlets de PowerShell para ver y cambiar la configuración de llamadas para los usuarios.

Para establecer la configuración de llamada de un usuario, el usuario debe tener una licencia Teléfono Microsoft sistema.

## <a name="use-the-teams-admin-center"></a>Usar el Teams de administración

Puede usar el centro de Teams para configurar la recogida de llamadas grupales y la delegación de llamadas para los usuarios. 

> [!NOTE]
> La opción para configurar la configuración de reenvío de llamadas no está disponible actualmente en el centro Teams administración.

Para configurar la recogida de llamadas grupales:

1. En el Teams de administración, vaya a **UsuariosAdministrador**  >  de usuarios y seleccione un usuario.

2. En la página de detalles del usuario, vaya a la **pestaña** Voz.

3. En **Recogida de llamadas grupales**, seleccione **Agregar personas**. 

4. Especifique la configuración del **retraso de la llamada y el pedido**.

Para configurar la delegación, en la misma página vaya a **Delegación de llamadas** y seleccione **Agregar personas**.

## <a name="use-powershell"></a>Usar PowerShell

Puede usar PowerShell para configurar la configuración de reenvío de llamadas y delegación para los usuarios.  Usará los cmdlets siguientes, que están disponibles en Teams módulo de PowerShell versión 4.0 o posterior:

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) : muestra la configuración de reenvío de llamadas, los delegados y la información del delegado para un usuario.

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) : establece la configuración de reenvío de llamadas para un usuario.

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) : agrega un nuevo delegado con permisos para un usuario.

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) : cambia los permisos de un delegado existente.

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) : quita un delegado de un usuario.


### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Mostrar la configuración de reenvío de llamadas y delegación para un usuario

Para mostrar la configuración actual de reenvío de llamadas y delegación para un usuario, use el cmdlet Get-CsUserCallingSettings, como se muestra en el ejemplo siguiente:

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
Delegates                 : Id:user2@contoso.com
Delegators                : 
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

El resultado muestra que usuario1 tiene llamadas simultáneas a los delegados configurados. Las llamadas sin responder se envían al correo de voz después de 20 segundos. User2 se define como el delegado con todos los permisos de delegado.


### <a name="set-call-forward-settings-for-a-user"></a>Establecer la configuración de reenvío de llamadas para un usuario

Para reenviar todas las llamadas de usuario1 al usuario2, use el cmdlet Set-CsUserCallingSettings, como se muestra en el siguiente ejemplo: 

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Para llamar simultáneamente a todos los delegados para user3, use el cmdlet Set-CsUserCallingSettings, como se muestra en el siguiente ejemplo: 

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

En el ejemplo siguiente se usa el cmdlet Set-CsUserCallingSettings para configurar un grupo de llamadas para user4 con user5 y user6 como miembros. Todas las llamadas a los miembros del grupo se reenvía en el orden en que se definen: 

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Para obtener más ejemplos, [vea Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps).

### <a name="add-a-calling-delegate-for-a-user"></a>Agregar un delegado de llamada para un usuario

Para agregar user2 como delegado para user1 con todos los permisos permitidos, use el cmdlet New-CsUserCallingDelegate, como se muestra en el ejemplo siguiente: 

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Cambiar permisos de delegado de llamadas

Para cambiar los permisos delegados (por ejemplo, para no permitir que el usuario2 realice llamadas para el usuario1), use el cmdlet Set-CsUserCallingDelegate como se muestra en el ejemplo siguiente: 

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Quitar un delegado de llamadas para un usuario

Para quitar user2 como delegado para user1, use el cmdlet Remove-CsUserCallingDelegate, como se muestra en el siguiente ejemplo: 

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```


## <a name="related-topics"></a>Temas relacionados

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) 

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) 

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) 

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) 

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) 
