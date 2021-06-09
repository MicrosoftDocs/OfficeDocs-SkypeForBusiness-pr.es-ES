---
title: Consideraciones RTC al actualizar a Teams desde Skype Empresarial
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Consideraciones de voz para actualizar de Skype Empresarial a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4024e62c90ef99f3280d5aec15cd718b3d2b6de
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796824"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Consideraciones RTC para actualizar a Teams desde Skype Empresarial local

En este artículo se describen las consideraciones de red telefónica conmutada (RTC) al actualizar a Teams.

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

Además, en los artículos siguientes se describen conceptos de actualización importantes y comportamientos de coexistencia:

- [Coexistencia de Teams y Skype Empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - Usar Sistema telefónico con Teams solo es compatible cuando se asigna a la cuenta del usuario una Teams de actualización con Teams solo.  
 > - Usar Sistema telefónico con Skype Empresarial solo es compatible cuando se asigna a la cuenta del usuario una Teams de actualización con un modo SfB. 
 > - Sistema telefónico no se admite cuando se asigna a la cuenta del usuario una directiva de Teams de actualización con el modo Islas.
 > - Cualquier configuración de reenvío de llamadas, grupo de llamada de equipo y delegación de Skype Empresarial no se migra y tendrá que volver a crearse para Teams.
 > - Para obtener información general sobre Microsoft Teams de voz en la nube y ayudar a decidir qué solución de voz de Microsoft es adecuada para su organización, vea Planear su solución de voz Teams [de voz.](cloud-voice-landing-page.md)


## <a name="pstn-calling-scenarios"></a>Escenarios de llamadas RTC

Hay cuatro escenarios de llamadas posibles al pasar al modo TeamsOnly:

- [Un usuario en Skype Empresarial online, con un plan de llamadas de Microsoft](#from-skype-for-business-online-with-microsoft-calling-plans). Tras la actualización, este usuario seguirá teniendo un plan de Llamadas de Microsoft.

- [Un usuario en Skype Empresarial Online,](#from-skype-for-business-online-with-on-premises-voice) con funcionalidad de voz local a través Skype Empresarial local o Cloud Connector Edition. La actualización del usuario a Teams debe coordinarse con la migración del usuario a Enrutamiento directo para asegurarse de que el usuario de TeamsOnly tiene funcionalidad RTC.

- [Un usuario de Skype Empresarial local](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)con Telefonía IP empresarial , que se trasladará a internet y mantendrá la conectividad RTC local.  Migrar este usuario Teams requiere mover la cuenta de Skype Empresarial local del usuario Skype Empresarial la nube y coordinar ese movimiento con la migración del usuario a Enrutamiento directo. 

- [Un usuario de Skype Empresarial local](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)con Telefonía IP empresarial , que se trasladará a internet y usará un plan de Microsoft Calling.  Migrar este usuario a Teams requiere mover la cuenta de Skype Empresarial local del usuario Skype Empresarial la nube y coordinar que se muevan con cualquiera de las dos A) el puerto del número de teléfono de ese usuario a un Plan de llamadas de Microsoft o B) asignando un nuevo número de suscriptor de las regiones disponibles.

En este artículo solo se proporciona información general de alto nivel. Para obtener más información, [vea Sistema telefónico planes](direct-routing-landing-page.md) de enrutamiento directo y [llamadas.](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Desde Skype Empresarial online con planes de llamadas de Microsoft 

Este es el escenario de actualización más sencillo que implica voz. 

1. Asegúrese de que a los usuarios se les haya asignado una Teams licencia. De forma predeterminada, al asignar una licencia Microsoft 365 o Office 365, Teams está habilitada, por lo que, a menos que haya deshabilitado previamente la licencia de Teams, no debe ser necesario realizar ninguna acción.

2.  Si los usuarios ya tienen un plan de llamadas de Microsoft con un número de teléfono, el único cambio necesario es asignar el modo TeamsOnly del usuario en TeamsUpgradePolicy.  Antes de asignar el modo TeamsOnly, las llamadas RTC entrantes llegarán al cliente Skype Empresarial usuario. Después de la actualización al modo TeamsOnly, las llamadas RTC entrantes llegarán al cliente Teams usuario.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Desde Skype Empresarial online con voz local

En este escenario, el usuario ya está en Skype Empresarial Online, pero su conectividad RTC es local, ya sea usando Skype Empresarial Server en modo híbrido o Cloud Connector Edition. Migrar estos usuarios al modo TeamsOnly con la funcionalidad RTC significa habilitarlos para enrutamiento directo, en el que los troncos RTC se conectan directamente al servicio de enrutamiento directo en la nube, a través de su controlador de borde de sesión (SBC) local.

A continuación se muestran los pasos básicos.  Los pasos 1 a 4 se muestran en la secuencia sugerida, pero se pueden realizar en cualquier orden. La clave es que todos estos deben completarse antes del paso 5.

1. Si va a establecer la directiva de todo el espacio empresarial en uno de los modos Skype Empresarial, asegúrese de asignar explícitamente el modo Islas a los usuarios existentes de las Islas, como se describe anteriormente.

2. Configure el espacio empresarial para enrutamiento directo. Vea [Resumen de la configuración por inquilino de Enrutamiento directo.](#summary-of-per-tenant-configuration-of-direct-routing)

3. Si lo desea, configure varias Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Esto se puede hacer en cualquier momento, pero si desea asegurarse de que los usuarios tienen la configuración correcta cuando se actualizan, es mejor hacerlo antes de que el usuario se actualice al modo TeamsOnly.

4. Preparar usuarios seleccionados para la migración de voz: 
   - Si es necesario, asigne la Teams licencia.  Suponiendo que el usuario ya funciona en Skype Empresarial voz local en línea, el usuario ya tiene Skype Empresarial plan 2, así como Teléfono Microsoft sistema. Deje ambos planes habilitados, incluida Skype Empresarial licencia de Plan 2 en línea.  
   - Asigne el OnlineVoiceRoutingPolicy deseado. 

5. Actualizar al usuario: estos pasos deben coordinarse. 

   - En Microsoft 365 o Office 365, actualice el usuario al modo TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - En el SBC, configure el enrutamiento de voz para habilitar las llamadas entrantes enviando llamadas a Enrutamiento directo en lugar de al servidor de mediación local.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Desde Skype Empresarial Server local, con Telefonía IP empresarial, hasta Enrutamiento directo

En este escenario, el usuario todavía se encuentra en Skype Empresarial local y su conectividad RTC también es local. Migrar estos usuarios al modo TeamsOnly con la funcionalidad RTC significa habilitarlos para enrutamiento directo y, a continuación, mover el usuario a la nube. 
 
A continuación se muestran los pasos básicos.  Los pasos 1 a 5 se muestran en la secuencia sugerida, pero se pueden realizar en cualquier orden. La clave es que todos estos deben completarse antes del paso 6.

1. Si va a establecer la directiva de todo el espacio empresarial en uno de los modos Skype Empresarial, asegúrese de que los usuarios existentes de islas ya existentes se asignen explícitamente el modo Islas, como se describe anteriormente.

2. Si aún no lo ha hecho, configure la organización para Skype Empresarial [híbrida.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. Configure el espacio empresarial para enrutamiento directo. Vea [Resumen de la configuración por inquilino de Enrutamiento directo.](#summary-of-per-tenant-configuration-of-direct-routing)

4. Si lo desea, configure Teams directivas para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Esto se puede hacer en cualquier momento, pero si desea asegurarse de que los usuarios tienen la configuración correcta cuando se actualizan, es mejor hacerlo antes de que el usuario se actualice a TeamsOnly.

5. Asigne las Microsoft 365 o Office 365 licencias si es necesario.  El usuario debe tener Teams y Skype Empresarial plan en línea 2, así como Sistema telefónico. Si el Skype Empresarial Online Plan 2 está deshabilitado, vuelva a habilitarlo.  

6. Actualizar al usuario: estos pasos deben coordinarse. 

   - Con las herramientas de Skype Empresarial locales, ejecute Move-CsUser con el modificador -MoveToTeams. Si usa una versión de Skype Empresarial Server que no admite el modificador -MoveToTeams, primero ejecute Move-CsUser y, después, asigne el modo TeamsOnly en PowerShell remoto de inquilino o Teams consola de administración.

   - En el SBC, configure el enrutamiento de voz para habilitar las llamadas entrantes enviando llamadas a Enrutamiento directo en lugar de al servidor de mediación local. 

   - En Microsoft 365 o Office 365: Asigne el OnlineVoiceRoutingPolicy correspondiente para habilitar las llamadas salientes. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Desde Skype Empresarial Server local, con Telefonía IP empresarial, hasta Microsoft Calling Plan

En este escenario, el usuario todavía se encuentra en Skype Empresarial local y su conectividad RTC también es local. Migrar estos usuarios al modo TeamsOnly con la funcionalidad RTC significa mover el usuario a la nube y porte su número del operador antiguo a un plan de Llamadas de Microsoft o asignar al usuario un nuevo número. 

A continuación se muestran los pasos básicos.Los pasos 1 a 5 se muestran en la secuencia sugerida, pero se pueden realizar en cualquier orden. La clave es que todos estos deben completarse antes del paso 6. 

1. Si va a establecer la directiva de todo el espacio empresarial en uno de los modos Skype Empresarial, asegúrese de que los usuarios existentes de islas ya existentes se asignen explícitamente el modo Islas, como se describe anteriormente. 

2. Si aún no lo ha hecho, configure la organización para Skype Empresarial [híbrida.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. Si lo desea, configure varias Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Esto se puede hacer en cualquier momento, pero si desea asegurarse de que los usuarios tienen la configuración correcta cuando se actualizan, es mejor hacerlo antes de que el usuario se actualice a TeamsOnly. 

4. Asigne las Microsoft 365 o Office 365 licencias si es necesario.El usuario debe tener Teams y Skype Empresarial plan en línea 2, así como Sistema telefónico. Si el Skype Empresarial Online Plan 2 está deshabilitado, vuelva a habilitarlo.  

5. Obtener números de teléfono para los usuarios. (Para obtener más información, vea [Administrar números de teléfono para su organización).](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

   - Si va a volver a usar los números, envíe una solicitud de porte a su operador.  
   - Como alternativa, puede adquirir nuevos números directamente desde Microsoft. 

6. Actualice el usuario y, si es necesario, asigne LineUri. Con las herramientas de Skype Empresarial locales, ejecute Move-CsUser con el modificador -MoveToTeams.  

    - Si va a portabilidad de números a Microsoft, debe coordinar los intervalos de esta operación para que se produzcan cuando se produzca el puerto. 

    - Si usa números nuevos de Microsoft, tendrá que cambiar el LineUri para el usuario. Esto debe hacerse después de que el usuario se mueve en línea con Set-CsOnlineVoiceUser.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Resumen de la configuración por inquilino de Enrutamiento directo 

1. Asegúrese de que el controlador de borde de sesión (SBC) es compatible con enrutamiento directo revisando [esta lista.](direct-routing-border-controllers.md) También debe asegurarse de que tiene la versión correcta del firmware.  

2. Emparejar su SBC local con el Teams de enrutamiento directo. Para obtener más información, [vea Emparejar el SBC con el servicio de](direct-routing-configure.md)enrutamiento directo de Sistema telefónico . 

3. Esta configuración es esencialmente un reflejo de la configuración local. La configuración en línea consta de: 
   - OnlineVoiceRoutingPolicy (basado en voiceRoutingPolicy local si se migran usuarios desde Skype Empresarial Online y en función de VoicePolicy si se migran usuarios desde locales con Telefonía IP empresarial).
   - OnlinePSTNUsage objetos (basados en el uso de RTC local). 
   - Objetos de OnlineVoiceRoute (basados en VoiceRoute local). 

Para obtener más información, vea [Configurar enrutamiento directo.](direct-routing-configure.md) 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Administrar la propiedad EnterpriseVoiceEnabled durante la migración 

Tanto si usa enrutamiento directo como un plan de Microsoft Calling, un usuario debe tener EnterpriseVoiceEnabled=true en Azure AD para que el usuario tenga funcionalidad RTC.  EnterpriseVoiceEnabled ("habilitado para EV") es una propiedad (no una directiva) que existe tanto en un directorio local como en la nube. El valor de la nube es lo importante para Teams.  La lógica exacta de cómo se establece la opción EV habilitada en true depende del siguiente escenario: 

- Si el usuario está habilitado para EV en Skype Empresarial Server local y se asigna una licencia de Sistema telefónico al usuario antes de mover el usuario a la nube con Move-CsUser, el usuario en línea se aprovisionará con EV-enabled=true. 

- Si a un usuario de TeamsOnly o Skype Empresarial Online se le asigna una licencia de Sistema telefónico, la opción habilitada para EV no se establece en true de forma predeterminada.  Este también es el caso si un usuario local se mueve a la nube antes de asignar la Sistema telefónico licencia. En cualquier caso, el administrador debe especificar el siguiente cmdlet: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Vínculos relacionados

[Planear su Teams de voz](cloud-voice-landing-page.md)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
