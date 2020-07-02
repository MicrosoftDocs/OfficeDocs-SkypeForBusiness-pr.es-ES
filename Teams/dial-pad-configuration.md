---
title: Configuración del teclado de marcado de Teams
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
localization_priority: Normal
f1.keywords:
- NOCSH
description: Obtenga más información sobre cómo configurar el teclado de marcado en el cliente de Teams para que los usuarios puedan acceder a la funcionalidad de red telefónica conmutada (RTC).
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012425"
---
# <a name="dial-pad-configuration"></a>Configuración del teclado de marcado

En el cliente de Teams, el teclado de marcado permite a los usuarios acceder a la funcionalidad de red telefónica conmutada (RTC). El teclado de marcado está disponible para los usuarios con una licencia de sistema telefónico, siempre que estén configurados correctamente. Los siguientes criterios son necesarios para que el teclado de marcado se muestre:

- El usuario tiene una licencia de sistema telefónico habilitado ("MCOEV")
- El usuario tiene el plan de llamadas de Microsoft o está habilitado para enrutamiento directo
- El usuario tiene habilitada la telefonía IP empresarial
- El usuario está conectado en línea y no en Skype empresarial local
- El usuario tiene habilitada la Directiva de llamadas de Teams

En las siguientes secciones se describe cómo usar PowerShell para comprobar los criterios. En la mayoría de los casos, tendrá que mirar varias propiedades en el resultado del cmdlet Get-CsOnlineUser. Algunos ejemplos suponen que $user es la dirección de UPN o SIP del usuario.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>El usuario tiene una licencia de sistema telefónico habilitado ("MCOEV")

Debe asegurarse de que el plan asignado para el usuario muestre el **atributo CapabilityStatus establecido en habilitado** y el **plan de capacidades establecido en MCOEV** (licencia de sistema telefónico). Es posible que vea MCOEV, MCOEV1, etc. Todas son aceptables, siempre y cuando el plan de capacidades comience con MCOEV.

Para comprobar que los atributos se han establecido correctamente, use el siguiente comando:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

El resultado tendrá un aspecto similar al siguiente. Solo tiene que comprobar los atributos de **CapabilityStatus** y **plan de capacidad** :

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>El usuario tiene el plan de llamadas de Microsoft o está habilitado para enrutamiento directo

**Si el usuario tiene un plan de llamadas de Microsoft**, debe asegurarse de que el **atributo CapabilityStatus se establece en habilitado**y de que el **plan de capacidad está establecido en MCOPSTN**. Es posible que vea MCOPSTN1, MCOPSTN2, etc. Todas son aceptables, siempre y cuando el plan de capacidades comience con MCOPSTN.

Para comprobar los atributos, use el siguiente comando:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

El resultado tendrá un aspecto similar al siguiente. Solo tiene que comprobar los atributos de **CapabilityStatus** y **plan de capacidad** :

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

**Si el usuario está habilitado para el enrutamiento directo**, el usuario debe tener asignado un valor no nulo para OnlineVoiceRoutingPolicy. Para comprobar el atributo, use el siguiente comando:
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

La salida debe tener un valor no nulo, por ejemplo:

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>El usuario tiene habilitada la telefonía IP empresarial

Para comprobar si el usuario tiene habilitada la telefonía IP empresarial, use el siguiente comando:

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

El resultado debería tener el siguiente aspecto:

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>El usuario está conectado en línea y no en Skype empresarial local

Para garantizar que el usuario está conectado y no en Skype para empresas, la RegistrarPool debe ser nula y Hostingprovider manda debe contener un valor que empiece por "sipfed. online".  Para comprobar los valores, use el siguiente comando:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

El resultado debería ser similar a:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>El usuario tiene habilitada la Directiva de llamadas de Teams

La TeamsCallingPolicy vigente del usuario debe tener AllowPrivateCalling establecido en true.  De forma predeterminada, los usuarios heredan la directiva global, que tiene AllowPrivateCallingPolicy establecido en true de forma predeterminada.

Para obtener el TeamsCallingPolicy para un usuario y comprobar que AllowPrivateCalling está establecido en true, use el siguiente comando:

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

El resultado debería tener el siguiente aspecto:

```
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

-   Es posible que tenga que reiniciar el cliente de Teams después de realizar cualquiera de estos cambios de configuración.

-   Si ha actualizado recientemente alguno de los criterios anteriores, es posible que tenga que esperar unas pocas horas para que el cliente reciba la nueva configuración.

-   Si sigue sin ver el teclado de marcado, compruebe si hay un error de aprovisionamiento con el siguiente comando:

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    Si ha transcurrido más de 24 horas y sigues teniendo problemas, ponte en contacto con el soporte técnico.


