---
title: Consideraciones de RTC al actualizar a Teams desde Skype Empresarial
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Consideraciones de voz para actualizar de Skype Empresarial a Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 130ff6164de3cae82902487f70dd6eaefb631c27
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681351"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Consideraciones de RTC para actualizar a Teams desde Skype Empresarial local

En este artículo se describen las consideraciones de la red telefónica conmutada (RTC) al actualizar a Teams.

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

En los artículos siguientes se describen conceptos de actualización importantes y comportamientos de coexistencia:

- [Coexistencia de Teams y Skype Empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!NOTE]
>
> - El uso de Sistema telefónico con Teams solo se admite cuando se asigna una directiva de actualización Teams a la cuenta del usuario con el modo Solo Teams.
> - El uso de Sistema telefónico con Skype Empresarial solo se admite cuando se asigna una directiva de actualización Teams a la cuenta del usuario con un modo SfB.
> - Sistema telefónico no se admite cuando se asigna una directiva de actualización Teams a la cuenta del usuario con el modo Islas.
> - No se migran las opciones de desvío de llamadas, grupo de llamadas de equipo y delegación desde Skype Empresarial y es necesario volver a crearla para Teams.
> - Para obtener información general sobre Microsoft Teams características de voz en la nube y ayudar a decidir qué solución de voz de Microsoft es la adecuada para su organización, consulte [Planear la solución de voz Teams](cloud-voice-landing-page.md).

## <a name="pstn-calling-scenarios"></a>Escenarios de llamadas RTC

Hay cuatro escenarios de llamada posibles al pasar al modo TeamsOnly:

- [Un usuario de Skype Empresarial Online, con un plan de llamadas de Microsoft](#from-skype-for-business-online-with-microsoft-calling-plans). Tras la actualización, este usuario seguirá teniendo un plan de llamadas de Microsoft.

- [Un usuario de Skype Empresarial Online, con funcionalidad de voz local](#from-skype-for-business-online-with-on-premises-voice) a través de Skype Empresarial local o Cloud Connector Edition. Para asegurarse de que el usuario de TeamsOnly tiene funcionalidad RTC, debe coordinar la actualización del usuario a Teams con la migración del usuario a Enrutamiento directo.

- [Un usuario de Skype Empresarial local con Telefonía IP empresarial](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), que se moverá a en línea y mantendrá la conectividad con RTC local.  Para migrar este usuario a Teams, debe mover la cuenta de Skype Empresarial local del usuario a la nube y coordinarlo con la migración del usuario a Enrutamiento directo.

- [Un usuario de Skype Empresarial local con Telefonía IP empresarial](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), que pasará a estar conectado y usando un plan de llamadas de Microsoft.  Para migrar este usuario a Teams, debe mover la cuenta de Skype Empresarial local del usuario a la nube. Debe coordinar el movimiento con A) el puerto del número de teléfono de ese usuario a un Plan de llamadas de Microsoft o B) asignando un nuevo número de suscriptor de las regiones disponibles.

En este artículo solo se proporciona información general de alto nivel. Para obtener más información, consulte [Sistema telefónico Planes de enrutamiento directo](direct-routing-landing-page.md) y [llamadas](calling-plan-landing-page.md).

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Desde Skype Empresarial en línea con planes de llamadas de Microsoft

Este escenario es el escenario de actualización más sencillo que implica voz.

1. Asegúrese de que se ha asignado a los usuarios una licencia de Teams. De forma predeterminada, al asignar una licencia de Microsoft 365 o Office 365, Teams está habilitado. A menos que haya deshabilitado previamente la licencia de Teams, no es necesario realizar ninguna acción.

2. Si los usuarios ya tienen un plan de llamadas de Microsoft con un número de teléfono, el único cambio necesario es asignar al usuario el modo TeamsOnly en TeamsUpgradePolicy. Antes de asignar el modo TeamsOnly, las llamadas RTC entrantes llegarán al cliente de Skype Empresarial del usuario. Después de la actualización al modo TeamsOnly, las llamadas RTC entrantes llegarán al cliente Teams del usuario.

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Desde Skype Empresarial Online con voz local

En este escenario, el usuario ya está en Skype Empresarial Online. La conectividad con RTC del usuario es local, ya sea mediante Skype Empresarial Server en modo híbrido o Cloud Connector Edition. Para migrar estos usuarios al modo TeamsOnly con funcionalidad RTC, debe habilitar a los usuarios para el enrutamiento directo. Con el enrutamiento directo, los troncos RTC se conectan directamente al servicio enrutamiento directo a través de su controlador de borde de sesión local (SBC).

Los pasos básicos se enumeran a continuación.  Los pasos 1-4 se enumeran en la secuencia sugerida, pero se pueden realizar en cualquier orden. Estos pasos deben completarse antes del paso 5.

1. Si está configurando la directiva para todos los inquilinos en uno de los modos de Skype Empresarial, asegúrese de ampliar cualquier usuario existente de las Islas asignándoles explícitamente el modo Islas, como se describió anteriormente.

2. Configure su espacio empresarial para enrutamiento directo. Consulte [Resumen de la configuración por espacio empresarial de Enrutamiento directo](#summary-of-per-tenant-configuration-of-direct-routing).

3. Si lo desea, configure varias directivas de Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Puede configurar puntos de interés en cualquier momento. Sin embargo, si desea asegurarse de que los usuarios tengan la configuración correcta cuando se actualicen, configure estas directivas antes de que el usuario se actualice al modo TeamsOnly.

4. Preparar usuarios seleccionados para la migración de voz:
   - Si es necesario, asigne la licencia de Teams.  Suponiendo que el usuario ya es funcional en Skype Empresarial voz local en línea, el usuario ya tiene Skype Empresarial Plan 2 y sistema Teléfono Microsoft. Deje ambos planes habilitados, incluida la licencia Skype Empresarial Online Plan 2.
   - Asigne la OnlineVoiceRoutingPolicy deseada.

5. Actualizar al usuario: estos pasos deben coordinarse.

   - En Microsoft 365 o Office 365, actualice el usuario al modo TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - En el SBC, configure el enrutamiento de voz para habilitar las llamadas entrantes mediante el envío de llamadas al enrutamiento directo en lugar de al servidor de mediación local.

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Desde Skype Empresarial Server local, con Telefonía IP empresarial, hasta Enrutamiento directo

En este escenario, el usuario aún se aloja en Skype Empresarial local. La conectividad con RTC del usuario también es local. Para migrar este usuario al modo TeamsOnly con funcionalidad RTC, debe habilitar al usuario para enrutamiento directo y, a continuación, moverlo a la nube.

Los pasos básicos se enumeran a continuación. Los pasos 1-5 se enumeran en la secuencia sugerida, pero se pueden realizar en cualquier orden. Debe completar los pasos 1-5 antes del paso 6.

1. Si va a establecer la directiva para todos los inquilinos en uno de los modos de Skype Empresarial, asegúrese de que los usuarios existentes de las Islas están asignándoles explícitamente el modo Islas, como se describió anteriormente.

2. Si aún no lo ha hecho, [configure la organización para Skype Empresarial híbrida](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Configure su espacio empresarial para enrutamiento directo. Consulte [Resumen de la configuración por espacio empresarial de Enrutamiento directo](#summary-of-per-tenant-configuration-of-direct-routing).

4. Si lo desea, configure varias directivas de Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy). Puede configurar directivas en cualquier momento. Sin embargo, si desea asegurarse de que los usuarios tengan la configuración correcta cuando se actualicen, configure estas directivas antes de que el usuario se actualice a TeamsOnly.

5. Asigne las licencias de Microsoft 365 o Office 365 si es necesario.  El usuario debe tener tanto Teams como Skype Empresarial Plan 2 y Sistema telefónico. Si la Skype Empresarial Plan 2 en línea está deshabilitada, vuelva a habilitarla.

6. Actualizar al usuario: estos pasos deben coordinarse.

   - Con las herramientas de Skype Empresarial locales, ejecute Move-CsUser con el modificador -MoveToTeams. Si usa una versión de Skype Empresarial Server que no admite el modificador -MoveToTeams, ejecute primero Move-CsUser y, a continuación, asigne el modo TeamsOnly en el PowerShell remoto de inquilino o en Teams Administración Consola.

   - En el SBC, configure el enrutamiento de voz para habilitar las llamadas entrantes mediante el envío de llamadas al enrutamiento directo en lugar de al servidor de mediación local.

   - En Microsoft 365 o Office 365: asigne el onlineVoiceRoutingPolicy pertinente para habilitar las llamadas salientes.

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Desde Skype Empresarial Server local, con Telefonía IP empresarial, hasta Plan de llamadas de Microsoft

En este escenario, el usuario aún se aloja en Skype Empresarial local. La conectividad con RTC del usuario también es local. Para migrar este usuario al modo TeamsOnly con funcionalidad RTC, debe mover el usuario a la nube y transferir su número del operador anterior a un plan de llamadas de Microsoft, o bien asignar un nuevo número al usuario.

Los pasos básicos se enumeran a continuación. Los pasos 1-5 se enumeran en la secuencia sugerida, pero se pueden realizar en cualquier orden. Debe completar los pasos 1-5 antes del paso 6.

1. Si va a establecer la directiva para todos los inquilinos en uno de los modos de Skype Empresarial, asegúrese de que los usuarios existentes de las Islas están asignándoles explícitamente el modo Islas, como se describió anteriormente.

2. Si aún no lo ha hecho, [configure la organización para Skype Empresarial híbrida](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Si lo desea, configure varias directivas de Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Puede configurar directivas en cualquier momento. Sin embargo, si desea asegurarse de que los usuarios tengan la configuración correcta cuando se actualicen, configure estas directivas antes de que el usuario se actualice a TeamsOnly.

4. Asigne las licencias de Microsoft 365 o Office 365 si es necesario. El usuario debe tener tanto Teams como Skype Empresarial Plan 2 y Sistema telefónico. Si la Skype Empresarial Plan 2 en línea está deshabilitada, vuelva a habilitarla.

5. Obtenga números de teléfono para los usuarios. (Para obtener más información, consulte [Administrar números de teléfono de la organización](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)).

   - Si va a reutilizar los números, envíe una solicitud de portabilidad a su operador.
   - Como alternativa, puede adquirir números nuevos directamente a Microsoft.

6. Actualice al usuario y, si es necesario, asigne LineUri. Con las herramientas de Skype Empresarial locales, ejecute Move-CsUser con el modificador -MoveToTeams.

    - Si está realizando la portabilidad de números a Microsoft, debe coordinar los intervalos de esta operación para que se produzcan cuando se produzca el puerto.

    - Si usa números nuevos de Microsoft, tendrá que cambiar el LineUri para el usuario después de mover el usuario en línea mediante Set-CsPhoneNumberAssignment.

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Resumen de la configuración por espacio empresarial de Enrutamiento directo

1. Revise [esta lista](direct-routing-border-controllers.md) para asegurarse de que el controlador de borde de sesión (SBC) es compatible con el enrutamiento directo. Asegúrese también de que tiene la versión correcta del firmware.

2. Empareje su SBC local con el servicio de enrutamiento directo de Teams. Para obtener más información, consulte [Emparejar el SBC con el servicio de enrutamiento directo de Sistema telefónico](direct-routing-configure.md).

3. Esta configuración es básicamente un reflejo de la configuración local. La configuración en línea consta de:
   - OnlineVoiceRoutingPolicy (basado en VoiceRoutingPolicy local si se migran usuarios desde Skype Empresarial Online y se basa en VoicePolicy si se migran usuarios desde el entorno local con Telefonía IP empresarial).
   - OnlinePSTNUsage objetos (basado en el uso de RTC local).
   - Objetos OnlineVoiceRoute (basados en VoiceRoute local).

Para obtener más información, consulte [Configurar enrutamiento directo](direct-routing-configure.md).

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Administrar la propiedad EnterpriseVoiceEnabled durante la migración

Ya sea mediante enrutamiento directo o un plan de llamadas de Microsoft, un usuario debe tener EnterpriseVoiceEnabled=true en Azure AD para que el usuario tenga la funcionalidad de RTC.  EnterpriseVoiceEnabled ("EV habilitado") es una propiedad (no una directiva) que existe tanto en un directorio local como en la nube. El valor de la nube es lo que importa para Teams.  La lógica exacta de cómo ev-enabled se establece en true depende del siguiente escenario:

- Si el usuario está habilitado ev en local Skype Empresarial Server y se asigna una licencia de Sistema telefónico al usuario antes de mover el usuario a la nube con Move-CsUser, el usuario en línea se aprovisionará con EV-enabled=true.

- Si se asigna una licencia de Sistema telefónico a un usuario existente de TeamsOnly o Skype Empresarial Online, ev-enabled no se establece en true de forma predeterminada. Este también es el caso si un usuario local se mueve a la nube antes de asignar la licencia de Sistema telefónico. En cualquier caso, el administrador debe especificar el siguiente cmdlet:

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True
  ```

## <a name="related-links"></a>Vínculos relacionados

[Planear la solución de voz Teams](cloud-voice-landing-page.md)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md)

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Usar el servicio de migración de reuniones (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
