---
title: Consideraciones de RTC al actualizar a Teams desde una implementación local de Skype Empresarial
author: msdmaguire
ms.author: dmaguire
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
ms.openlocfilehash: 8a9783f5d60e5a595d548bbfc83ee013500934ed
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686436"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Consideraciones de RTC para actualizar a Teams desde Skype Empresarial local

En este artículo se describen las consideraciones sobre la red telefónica conmutada (RTC) al actualizar a Teams.   


Además, en los artículos siguientes se describen conceptos importantes de actualización y comportamientos de coexistencia:

- [Coexistencia de Teams y Skype Empresarial](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistencia - Referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - Usar Sistema telefónico con Teams solo es compatible cuando el usuario está en modo TeamsOnly.  Si el usuario se encuentra en modo Islas, Sistema telefónico solo es compatible con Skype Empresarial. 
 > - No se migra ningún cambio de configuración de reenvío de llamadas, grupo de llamada de equipo y delegación de Skype Empresarial y deberá volver a crearse para Teams.
 > - Para obtener información general sobre las características de voz en la nube de Microsoft Teams y ayudar a decidir qué solución de voz de Microsoft es la adecuada para su organización, consulte Planear la solución [de voz de Teams.](cloud-voice-landing-page.md)


## <a name="pstn-calling-scenarios"></a>Escenarios de llamadas RTC

Hay cuatro escenarios de llamadas posibles al pasar al modo TeamsOnly:

- [Un usuario de Skype Empresarial Online con un plan de llamadas de Microsoft.](#from-skype-for-business-online-with-microsoft-calling-plans) Tras la actualización, este usuario seguirá teniendo un plan de Llamadas de Microsoft.

- [Un usuario de Skype Empresarial Online,](#from-skype-for-business-online-with-on-premises-voice) con funcionalidad de voz local a través de Skype Empresarial local o Cloud Connector Edition. La actualización del usuario a Teams debe coordinarse con la migración del usuario a Enrutamiento directo para asegurarse de que el usuario de TeamsOnly tiene funcionalidad RTC.

- [Un usuario de Skype Empresarial local](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)con Telefonía IP empresarial que pasará a estar conectado y mantendrá la conectividad con RTC local.  Migrar este usuario a Teams requiere mover la cuenta de Skype Empresarial local a la nube y coordinar ese movimiento con la migración del usuario a Enrutamiento directo. 

- [Un usuario de Skype Empresarial local](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)con Telefonía IP empresarial que se trasladará a Internet y que utiliza un plan de llamadas de Microsoft.  Migrar este usuario a Teams requiere mover la cuenta local de Skype Empresarial a la nube y coordinar que mueva con A el puerto del número de teléfono de ese usuario a un plan de llamadas de Microsoft o B) asignando un nuevo número de suscriptor desde las regiones disponibles.

En este artículo solo se ofrece información general de alto nivel. Para obtener más información, vea [Planes de enrutamiento directo y](direct-routing-landing-page.md) llamadas de sistema [telefónico.](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Desde Skype Empresarial Online con planes de llamadas de Microsoft 

Este es el escenario de actualización más sencillo que implica voz. 

1. Asegúrese de que a los usuarios se les ha asignado una licencia de Teams. De forma predeterminada, al asignar una licencia de Microsoft 365 u Office 365, Teams está habilitado, por lo que, a menos que haya deshabilitado previamente la licencia de Teams, no es necesario realizar ninguna acción.

2.  Si los usuarios ya tienen un plan de llamadas de Microsoft con un número de teléfono, el único cambio necesario es asignar el modo TeamsOnly del usuario en TeamsUpgradePolicy.  Antes de asignar el modo TeamsOnly, las llamadas RTC entrantes llegarán al cliente de Skype Empresarial del usuario. Después de la actualización al modo TeamsOnly, las llamadas RTC entrantes llegarán al cliente de Teams del usuario.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Desde Skype Empresarial Online con voz local

En este escenario, el usuario ya está en Skype Empresarial Online, pero su conectividad con RTC es local, ya sea usando Skype Empresarial Server en modo híbrido o Cloud Connector Edition. Migrar estos usuarios al modo TeamsOnly con la funcionalidad RTC implica habilitarles para enrutamiento directo, en el que los troncos RTC se conectan directamente al servicio de enrutamiento directo en la nube, a través del controlador de borde de sesión local (SBC).

A continuación se muestran los pasos básicos.  Los pasos del 1 al 4 se muestran en la secuencia sugerida, pero se pueden realizar en cualquier orden. La clave es que todos estos deben completarse antes del paso 5.

1. Si va a establecer la directiva de todo el inquilino en uno de los modos de Skype Empresarial, asegúrese de evitar cualquier usuario existente de las Islas asignándolos explícitamente el modo Islas, como se describió anteriormente.

2. Configure su espacio empresarial para enrutamiento directo. Vea [resumen de la configuración de enrutamiento directo por espacio empresarial.](#summary-of-per-tenant-configuration-of-direct-routing)

3. Si lo desea, configure varias directivas de Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Esto puede hacerse en cualquier momento, pero si desea asegurarse de que los usuarios tienen la configuración correcta cuando se actualizan, es mejor hacerlo antes de que el usuario se actualice al modo TeamsOnly.

4. Preparar a los usuarios seleccionados para la migración de voz: 
   - Si es necesario, asigne la licencia de Teams.  Suponiendo que el usuario ya sea funcional en la voz local de Skype Empresarial Online, el usuario ya tiene Skype Empresarial Plan 2, así como Microsoft Phone System. Deje ambos planes habilitados, incluida la licencia del Plan 2 de Skype Empresarial Online.  
   - Assign the desired OnlineVoiceRoutingPolicy. 

5. Actualizar el usuario: estos pasos deben coordinarse. 

   - En Microsoft 365 u Office 365, actualice el usuario al modo TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - En SBC, configure el enrutamiento de voz para habilitar las llamadas entrantes enviando llamadas a enrutamiento directo en lugar de al servidor de mediación local.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>De Skype Empresarial Server local, con Telefonía IP empresarial, a enrutamiento directo

En este escenario, el usuario sigue estando en la implementación local de Skype Empresarial y su conectividad con RTC también es local. Migrar estos usuarios al modo TeamsOnly con la funcionalidad RTC implica habilitarlos para enrutamiento directo y, a continuación, mover el usuario a la nube. 
 
A continuación se muestran los pasos básicos.  Los pasos del 1 al 5 se muestran en la secuencia sugerida, pero se pueden realizar en cualquier orden. La clave es que todos estos deben completarse antes del paso 6.

1. Si va a establecer la directiva de todo el inquilino en uno de los modos de Skype Empresarial, asegúrese de convertir a los usuarios existentes en islas mediante la asignación explícita del modo Islas, como se describió anteriormente.

2. Si aún no lo ha hecho, configure la organización para la implementación híbrida [de Skype Empresarial.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. Configure su espacio empresarial para enrutamiento directo. Vea [resumen de la configuración de enrutamiento directo por espacio empresarial.](#summary-of-per-tenant-configuration-of-direct-routing)

4. Si lo desea, configure varias directivas de Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Esto puede hacerse en cualquier momento, pero si desea asegurarse de que los usuarios tienen la configuración correcta cuando se actualizan, es mejor hacerlo antes de que el usuario se actualice a TeamsOnly.

5. Asigne las licencias de Microsoft 365 u Office 365 si es necesario.  El usuario debe tener Teams y Skype Empresarial Online Plan 2, así como Sistema telefónico. Si el Plan 2 de Skype Empresarial Online está deshabilitado, vuelva a activarlo.  

6. Actualizar el usuario: estos pasos deben coordinarse. 

   - Con las herramientas locales de Skype Empresarial, ejecute Move-CsUser con el modificador -MoveToTeams. Si usa una versión de Skype Empresarial Server que no admite el modificador -MoveToTeams, ejecute primero Move-CsUser y, después, asigne El modo TeamsOnly en el PowerShell remoto del espacio empresarial o en la consola de administración de Teams.

   - En SBC, configure el enrutamiento de voz para habilitar las llamadas entrantes enviando llamadas a enrutamiento directo en lugar de al servidor de mediación local. 

   - En Microsoft 365 u Office 365: asigne el Mensaje OnlineVoiceRoutingPolicy correspondiente para habilitar las llamadas salientes. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Desde Skype Empresarial Server local, con Telefonía IP empresarial, hasta Microsoft Calling Plan

En este escenario, el usuario sigue estando en la implementación local de Skype Empresarial y su conectividad con RTC también es local. Migrar estos usuarios al modo TeamsOnly con la funcionalidad RTC implica mover el usuario a la nube y por su número del antiguo operador a un plan de Llamadas de Microsoft o asignar un nuevo número al usuario. 

A continuación se muestran los pasos básicos.Los pasos del 1 al 5 se muestran en la secuencia sugerida, pero se pueden realizar en cualquier orden. La clave es que todos estos deben completarse antes del paso 6. 

1. Si va a establecer la directiva de todo el inquilino en uno de los modos de Skype Empresarial, asegúrese de convertir a los usuarios existentes en islas mediante la asignación explícita del modo Islas, como se describió anteriormente. 

2. Si aún no lo ha hecho, configure la organización para la implementación híbrida [de Skype Empresarial.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. Si lo desea, configure varias directivas de Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Esto puede hacerse en cualquier momento, pero si desea asegurarse de que los usuarios tienen la configuración correcta cuando se actualizan, es mejor hacerlo antes de que el usuario se actualice a TeamsOnly. 

4. Asigne las licencias de Microsoft 365 u Office 365 si es necesario.El usuario debe tener Teams y Skype Empresarial Online Plan 2, así como Sistema telefónico. Si el Plan 2 de Skype Empresarial Online está deshabilitado, vuelva a activarlo.  

5. Obtenga números de teléfono para los usuarios. (Para obtener más información, [consulte Administrar números de teléfono de su organización).](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

   - Si va a volver a usar los números, envíe una solicitud de pornografía a su operador.  
   - Como alternativa, puede adquirir números nuevos directamente desde Microsoft. 

6. Actualice el usuario y, si es necesario, asigne LineUri. Con las herramientas locales de Skype Empresarial, ejecute Move-CsUser con el modificador -MoveToTeams.  

    - Si está portabilidad de números a Microsoft, debe coordinar los intervalos de esta operación para que se produzcan cuando se produzca el puerto. 

    - Si usa números nuevos de Microsoft, tendrá que cambiar el LineUri para el usuario. Esto debe hacerse después de mover el usuario en línea con Set-CsOnlineVoiceUser.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Resumen de la configuración de enrutamiento directo por espacio empresarial 

1. Revise esta lista para asegurarse de que el controlador de borde de sesión (SBC) es compatible con enrutamiento [directo.](direct-routing-border-controllers.md) También debe asegurarse de que tiene la versión correcta del firmware.  

2. Emparejar su SBC local con el servicio de enrutamiento directo de Teams. Para obtener más información, [consulte Emparejar el SBC con el servicio de enrutamiento directo de Sistema telefónico.](direct-routing-configure.md) 

3. Esta configuración es básicamente un reflejo de la configuración local. La configuración en línea consiste en: 
   - OnlineVoiceRoutingPolicy (basado en voiceRoutingPolicy local si se migran usuarios desde Skype Empresarial Online y basado en VoicePolicy si se migran usuarios desde un entorno local con Telefonía IP empresarial).
   - Objetos OnlinePSTNUsage (en función del uso de RTC local). 
   - Objetos de OnlineVoiceRoute (basados en voiceRoute local). 

Para obtener más información, vea [Configurar enrutamiento directo.](direct-routing-configure.md) 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Administrar la propiedad EnterpriseVoiceEnabled durante la migración 

Ya sea mediante enrutamiento directo o un plan de llamadas de Microsoft, el usuario debe tener EnterpriseVoiceEnabled=true en Azure AD para que el usuario tenga funcionalidad de RTC.  EnterpriseVoiceEnabled ("EV-enabled") es una propiedad (no una directiva) que existe tanto en un directorio local como en la nube. El valor de la nube es lo importante para Teams.  La lógica exacta sobre cómo se establece la ev-enabled en true depende del escenario siguiente: 

- Si el usuario está habilitado para VA en Skype Empresarial Server local y se asigna una licencia de Sistema telefónico al usuario antes de mover el usuario a la nube con Move-CsUser, el usuario en línea se aprovisionará con EV-enabled=true. 

- Si se asigna una licencia de Sistema telefónico a un usuario de TeamsOnly o Skype Empresarial Online, la característica EV habilitada no se establece en true de forma predeterminada.  Este también es el caso si un usuario local se mueve a la nube antes de asignar la licencia de Sistema telefónico. En cualquier caso, el administrador debe especificar el cmdlet siguiente: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Vínculos relacionados

[Planear la solución de voz de Teams](cloud-voice-landing-page.md)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

