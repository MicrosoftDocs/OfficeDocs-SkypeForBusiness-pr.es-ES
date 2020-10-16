---
title: Actualizar a teams desde una implementación local de Skype empresarial-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Actualización de las consideraciones de voz de Skype empresarial a teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a6df112d0ea8359e3fe7db07bd644b0b90404f0
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48486765"
---
# <a name="pstn-considerations-when-upgrading-to-teams-mdash-for-it-administrators"></a>Consideraciones sobre RTC al actualizar a teams &mdash; para administradores de ti

En este artículo se describen consideraciones de la red telefónica conmutada (RTC) al actualizar a teams. Este artículo es el sexto de varios que describen los conceptos de actualización y la implementación para administradores de ti.  

- [Información general](upgrade-to-teams-on-prem-overview.md)
- [Métodos de actualización](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Herramientas para administrar la actualización](upgrade-to-teams-on-prem-tools.md)
- [Consideraciones adicionales para las organizaciones con Skype empresarial local](upgrade-to-teams-on-prem-considerations.md)
- [Implementar la actualización](upgrade-to-teams-on-prem-implement.md)
- **Consideraciones sobre la red telefónica pública conmutada (RTC)** (este artículo)

Además, los artículos siguientes describen los conceptos de actualización importantes y los comportamientos de coexistencia:

- [Coexistencia de Teams y Skype empresarial](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - El uso del sistema telefónico con Teams solo se admite cuando el usuario está en modo TeamsOnly.  Si el usuario está en modo islas, el sistema telefónico solo es compatible con Skype empresarial. 
 > - La configuración del desvío de llamadas y de la delegación de Skype empresarial no se migrará y tendrá que volver a crearla para Teams.


## <a name="pstn-calling-scenarios"></a>Escenarios de llamadas RTC

Hay cuatro escenarios posibles de llamadas al pasar al modo TeamsOnly:

- [Un usuario de Skype empresarial online con un plan de llamadas de Microsoft](#from-skype-for-business-online-with-microsoft-calling-plans). Después de la actualización, este usuario seguirá teniendo un plan de llamadas de Microsoft.

- [Un usuario de Skype empresarial online con funcionalidad de voz local](#from-skype-for-business-online-with-on-premises-voice) a través de Skype empresarial local o Cloud Connector Edition. La actualización del usuario a teams debe coordinarse con la migración del usuario al enrutamiento directo para garantizar que el usuario de TeamsOnly tiene la funcionalidad de RTC.

- [Un usuario de Skype empresarial local con telefonía IP empresarial](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), que se va a migrar a en línea y mantener la conectividad RTC local.  Migrar este usuario a teams requiere mover la cuenta de Skype empresarial local del usuario a la nube y coordinar ese movimiento con la migración del usuario al enrutamiento directo. 

- [Un usuario de Skype empresarial local con telefonía IP empresarial](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), que se va a migrar a en línea y usar un plan de llamadas de Microsoft.  Migrar este usuario a teams requiere mover la cuenta de Skype empresarial local del usuario a la nube y coordinar el movimiento con una o A una) el puerto del número de ese usuario a un plan de llamadas de Microsoft o B asignar un nuevo número de suscriptor de las regiones disponibles.

Este artículo proporciona una descripción general de alto nivel únicamente. Para obtener más información, consulte [planes de llamadas](calling-plan-landing-page.md)y [enrutamiento directo de sistema telefónico](direct-routing-landing-page.md) . 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Desde Skype empresarial online con planes de llamadas de Microsoft 

Este es el escenario de actualización más sencillo que implica voz. 

1. Asegúrese de que los usuarios tienen asignada una licencia de Teams. De forma predeterminada, cuando asigna una licencia de Microsoft 365 o de Office 365, Teams está habilitado, por lo que, a menos que previamente haya deshabilitado la licencia de Teams, no es necesario realizar ninguna acción.

2.  Si los usuarios ya tienen un plan de llamadas de Microsoft con un número de teléfono, el único cambio necesario es asignar el modo de TeamsOnly de usuario en TeamsUpgradePolicy.  Antes de asignar el modo de TeamsOnly, las llamadas RTC entrantes estarán en el cliente de Skype empresarial del usuario. Después de la actualización a modo TeamsOnly, las llamadas RTC entrantes estarán en el cliente de equipos del usuario.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Desde Skype empresarial online con voz local

En este escenario, el usuario ya está en Skype empresarial online, pero su conectividad RTC es local, ya sea usando Skype empresarial Server en modo híbrido o en la edición de la nube. Migrar a estos usuarios al modo de TeamsOnly con la funcionalidad de RTC significa habilitarlos para el enrutamiento directo, en el que los troncos RTC se conectan directamente al servicio de enrutamiento directo en la nube, a través del controlador de borde de sesión (SBC) local.

A continuación se enumeran los pasos básicos.  Los pasos 1-4 se enumeran en la secuencia sugerida, pero se pueden realizar en cualquier orden. La clave es que todas estas opciones deben completarse antes del paso 5.

1. Si va a establecer la Directiva de todo el inquilino en uno de los modos de Skype empresarial, asegúrese de que los usuarios de las islas actuales les asignen expresamente el modo islas, tal como se ha descrito anteriormente.

2. Configure el inquilino para el enrutamiento directo. Consulte [Resumen de la configuración por inquilino de enrutamiento directo](#summary-of-per-tenant-configuration-of-direct-routing).

3. Si lo desea, configure varias directivas de Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Esto se puede hacer en cualquier momento, pero si desea asegurarse de que los usuarios tengan la configuración correcta cuando se actualicen, es mejor hacerlo antes de que el usuario se actualice al modo TeamsOnly.

4. Preparar usuarios para la migración de voz: 
   - Si es necesario, asigne la licencia de Teams.  Suponiendo que el usuario ya es funcional en la voz local de Skype empresarial online, el usuario ya tiene Skype empresarial plan 2 y Microsoft Phone System. Deje ambos planes habilitados, incluyendo la licencia de Skype empresarial online plan 2.  
   - Asigne el OnlineVoiceRoutingPolicy deseado. 

5. Actualice el usuario: estos pasos deben ser coordinados. 

   - En Microsoft 365 u Office 365, actualice el usuario al modo TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - En la SBC, configure el enrutamiento de voz para habilitar las llamadas entrantes enviando llamadas al enrutamiento directo en lugar de al servidor de mediación local.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Desde Skype empresarial Server local, con telefonía IP empresarial, para dirigir el enrutamiento

En este escenario, el usuario aún se ha alojado en Skype empresarial local y su conectividad RTC también es local. Migrar a estos usuarios a modo TeamsOnly con la funcionalidad de RTC significa habilitarlos para el enrutamiento directo y, después, mover el usuario a la nube. 
 
A continuación se enumeran los pasos básicos.  Los pasos 1-5 se enumeran en la secuencia sugerida, pero se pueden realizar en cualquier orden. La clave es que todas estas opciones deben completarse antes del paso 6.

1. Si va a establecer la Directiva de todo el inquilino en uno de los modos de Skype empresarial, asegúrese de que los usuarios de las islas existentes les asignan expresamente el modo islas, tal como se ha descrito anteriormente.

2. Si aún no lo ha hecho, [Configure la organización para la implementación híbrida de Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Configure el inquilino para el enrutamiento directo. Consulte [Resumen de la configuración por inquilino de enrutamiento directo](#summary-of-per-tenant-configuration-of-direct-routing).

4. Si lo desea, configure varias directivas de Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Esto se puede hacer en cualquier momento, pero si desea asegurarse de que los usuarios tengan la configuración correcta cuando se actualicen, es mejor hacerlo antes de que el usuario se actualice a TeamsOnly.

5. Asigne las licencias de Microsoft 365 u Office 365 si es necesario.  El usuario debe tener tanto equipos como Skype empresarial online plan 2, así como un sistema telefónico. Si el plan 2 de Skype empresarial online está deshabilitado, vuelva a habilitarlo.  

6. Actualice el usuario: estos pasos deben ser coordinados. 

   - Con las herramientas locales de Skype empresarial, ejecute Move-CsUser con el modificador-MoveToTeams. Si está usando una versión de Skype empresarial Server que no admite el modificador-MoveToTeams, ejecute primero Move-CsUser y, después, asigne el modo TeamsOnly en PowerShell remoto del inquilino o en la consola de administración de Teams.

   - En la SBC, configure el enrutamiento de voz para habilitar las llamadas entrantes enviando llamadas al enrutamiento directo en lugar de al servidor de mediación local. 

   - En Microsoft 365 u Office 365: asigne el OnlineVoiceRoutingPolicy relevante para habilitar las llamadas salientes. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Desde Skype empresarial Server local, con telefonía IP empresarial, plan de llamadas de Microsoft

En este escenario, el usuario aún se ha alojado en Skype empresarial local y su conectividad RTC también es local. Migrar a estos usuarios a modo TeamsOnly con la funcionalidad de RTC significa mover el usuario a la nube y migrar su número desde el antiguo operador a un plan de llamadas de Microsoft o asignar un número nuevo al usuario. 

A continuación se enumeran los pasos básicos.Los pasos 1-5 se enumeran en la secuencia sugerida, pero se pueden realizar en cualquier orden. La clave es que todas estas opciones deben completarse antes del paso 6. 

1. Si va a establecer la Directiva de todo el inquilino en uno de los modos de Skype empresarial, asegúrese de que los usuarios de las islas existentes les asignan expresamente el modo islas, tal como se ha descrito anteriormente. 

2. Si aún no lo ha hecho, [Configure la organización para la implementación híbrida de Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity). 

3. Si lo desea, configure varias directivas de Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Esto se puede hacer en cualquier momento, pero si desea asegurarse de que los usuarios tengan la configuración correcta cuando se actualicen, es mejor hacerlo antes de que el usuario se actualice a TeamsOnly. 

4. Asigne las licencias de Microsoft 365 u Office 365 si es necesario.El usuario debe tener tanto equipos como Skype empresarial online plan 2, así como un sistema telefónico. Si el plan 2 de Skype empresarial online está deshabilitado, vuelva a habilitarlo.  

5. Obtener números de teléfono para los usuarios. (Para obtener información detallada, consulte [administrar números de teléfono de su organización](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)).

   - Si va a volver a usar los números, envíe una solicitud de portabilidad a su operador.  
   - También puede adquirir números nuevos directamente desde Microsoft. 

6. Actualice el usuario y, si es necesario, asigne LineUri. Con las herramientas de Skype para empresas locales, ejecute Move-CsUser con el modificador-MoveToTeams.  

    - Si va a trasladar números a Microsoft, debe coordinar los intervalos de esta operación para que se produzcan cuando se produzca el puerto. 

    - Si está usando números nuevos de Microsoft, tendrá que cambiar el LineUri para el usuario. Esto debe hacerse después de que el usuario se haya movido a Internet con set-CsOnlineVoiceUser.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Resumen de la configuración por inquilino de enrutamiento directo 

1. Para asegurarse de que el controlador de borde de sesión (SBC) es compatible con el enrutamiento directo, revisamos [esta lista](direct-routing-border-controllers.md). También debe asegurarse de que tiene la versión correcta del firmware.  

2. Empareje su SBC local con el servicio de enrutamiento directo de Teams. Para obtener más información, consulte [emparejar la SBC al servicio de enrutamiento directo del sistema telefónico](direct-routing-configure.md). 

3. Esta configuración es esencialmente un reflejo de la configuración local. La configuración electrónica consiste en: 
   - OnlineVoiceRoutingPolicy (basado en la VoiceRoutingPolicy local si migra usuarios de Skype empresarial online y se basa en VoicePolicy Si migra usuarios de local con Enterprise Voice).
   - Objetos OnlinePSTNUsage (basados en el uso local de RTC). 
   - Objetos OnlineVoiceRoute (basados en VoiceRoute locales). 

Para obtener más información, vea [configurar el enrutamiento directo](direct-routing-configure.md). 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Administrar la propiedad EnterpriseVoiceEnabled durante la migración 

Si usa enrutamiento directo o un plan de llamadas de Microsoft, un usuario debe tener EnterpriseVoiceEnabled = true en Azure AD para que el usuario tenga la funcionalidad RTC.  EnterpriseVoiceEnabled ("EV-Enabled") es una propiedad (no una directiva) que existe en un directorio local y en la nube. El valor en la nube es lo que importa a teams.  La lógica exacta de cómo se establece la función EV-Enabled en true depende del siguiente escenario: 

- Si el usuario está habilitado para EV en el servidor local de Skype empresarial y se asigna una licencia de sistema telefónico al usuario antes de mover el usuario a la nube con Move-CsUser, se aprovisionará al usuario en línea con EV-Enabled = true. 

- Si un TeamsOnly existente o un usuario de Skype empresarial online tiene asignada una licencia de sistema telefónico, la función EV-Enabled no se establece en true de forma predeterminada.  Esto también sucede si un usuario local se mueve a la nube antes de asignar la licencia de sistema telefónico. En cualquiera de los casos, el administrador debe especificar el siguiente cmdlet: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

