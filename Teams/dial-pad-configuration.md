---
title: configuración del teclado de marcado Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar el teclado de marcado en el cliente de Teams para que los usuarios puedan acceder a la funcionalidad de la red telefónica conmutada (RTC).
ms.openlocfilehash: 6aa5edf8f57574fa08a224541772c1f9e662f9ca
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676162"
---
# <a name="dial-pad-configuration"></a>Configuración del teclado de marcado

En el cliente Teams, el teclado de marcado permite a los usuarios acceder a la funcionalidad de la red telefónica conmutada (RTC). El teclado de marcado está disponible para los usuarios con una licencia de Sistema telefónico, siempre que estén configurados correctamente. Los siguientes criterios son necesarios para que el teclado de marcado muestre:

- El usuario tiene una licencia de Sistema telefónico ("MCOEV") habilitada
- El usuario tiene un plan de llamadas de Microsoft, Conexión con operador o está habilitado para enrutamiento directo
- El usuario tiene Telefonía IP empresarial habilitado
- El usuario está alojado en línea y no en Skype Empresarial local
- El usuario tiene habilitada Teams directiva de llamadas

En las siguientes secciones se describe cómo usar PowerShell para comprobar los criterios. En la mayoría de los casos, necesita ver varias propiedades en el resultado del cmdlet de Get-CsOnlineUser. Los ejemplos asumen $user es la dirección UPN o sip del usuario.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>El usuario tiene una licencia de Sistema telefónico ("MCOEV") habilitada

Asegúrese de que el plan asignado para el usuario muestra el **atributo CapabilityStatus establecido en Enabled** y el **capability establecido en MCOEV** (Sistema telefónico licencia). Es posible que vea MCOEV, MCOEV1, etc. Todos son aceptables, siempre y cuando la funcionalidad comience con MCOEV.

Para comprobar que los atributos están establecidos correctamente, use el siguiente comando:

```PowerShell
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

El resultado será similar al siguiente. Solo necesita comprobar los atributos **CapabilityStatus** y **Capability** :

```PowerShell
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-...
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-...
```

## <a name="user-has-microsoft-calling-plan-operator-connect-or-is-enabled-for-direct-routing"></a>El usuario tiene el plan de llamadas de Microsoft, Conexión con operador O está habilitado para el enrutamiento directo

**Si el usuario tiene Microsoft Calling Plan**, asegúrese de que el **atributo CapabilityStatus se establece en Enabled** y que **capability se establece en MCOPSTN**. Es posible que vea MCOPSTN1, MCOPSTN2, etc. Todos son aceptables, siempre y cuando la funcionalidad comience con MCOPSTN.

Para comprobar los atributos, use el siguiente comando:

```PowerShell
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

El resultado será similar al siguiente. Solo necesita comprobar los atributos **CapabilityStatus** y **Capability** :

```PowerShell
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-...
07-02-2020 12:28:48 MCOPSTN2        Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 5a10155d-f5c1-411a-a8ec-...
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-...
```

**Si el usuario está habilitado para Conexión con operador**, el usuario debe tener un valor no nulo para TeamsCarrierEmergencyCallRoutingPolicy. Para comprobar el atributo, use el siguiente comando:

```PowerShell
Get-CsOnlineUser -Identity $user|Select TeamsCarrierEmergencyCallRoutingPolicy
```

El resultado debe tener un valor no nulo, por ejemplo:

```PowerShell
TeamsCarrierEmergencyCallRoutingPolicy
--------------------------------------
Synergy_98d1a5cb-d3e6-4306-885e-69a95f2da5c3
```

**Si el usuario está habilitado para Direct Routing**, se debe asignar al usuario un valor no nulo para OnlineVoiceRoutingPolicy. Para comprobar el atributo, use el siguiente comando:

```PowerShell
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy
```

El resultado debe tener un valor no nulo, por ejemplo:

```PowerShell
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>El usuario tiene Telefonía IP empresarial habilitado

Para comprobar si el usuario tiene Telefonía IP empresarial habilitado, use el siguiente comando:

```PowerShell
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

La salida debe tener el siguiente aspecto:

```PowerShell
EnterpriseVoiceEnabled
----------------------
                  True
```

## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>El usuario está alojado en línea y no en Skype Empresarial local

Para asegurarse de que el usuario está alojado en línea y no en Skype Empresarial local, el RegistrarPool no debe ser null y HostingProvider debe contener un valor que empiece por "sipfed.online".  Para comprobar los valores, use el siguiente comando:

```PowerShell
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

La salida debe ser similar a:

```PowerShell
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>El usuario tiene habilitada Teams directiva de llamadas

TeamsCallingPolicy eficaz del usuario debe tener AllowPrivateCalling establecido en true.  De forma predeterminada, los usuarios heredan la directiva global, que tiene AllowPrivateCallingPolicy establecido en true de forma predeterminada.

Para obtener TeamsCallingPolicy para un usuario y comprobar que AllowPrivateCalling está establecido en true, use el siguiente comando:

```PowerShell
if (($p=Get-CsUserPolicyAssignment -Identity $user -PolicyType TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity Global} else {Get-CsTeamsCallingPolicy -Identity $p.PolicyName}
```

La salida debe tener el siguiente aspecto:

```PowerShell
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
```

## <a name="additional-notes"></a>Notas adicionales

- Es posible que tenga que reiniciar el cliente de Teams después de realizar cualquiera de estos cambios de configuración.

- Si ha actualizado recientemente cualquiera de los criterios anteriores, es posible que tenga que esperar unas horas hasta que el cliente reciba la nueva configuración.

- Si sigue sin ver el teclado de marcado, compruebe si hay un error de aprovisionamiento mediante el siguiente comando:

  ```PowerShell
  Get-CsOnlineUser -Identity $user|Select UserValidationErrors
  ```

- Si han transcurrido más de 24 horas y sigues viendo problemas, ponte en contacto con soporte técnico.
