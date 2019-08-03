---
title: Mover usuarios entre locales y la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumen: en una implementación local de Skype empresarial Server habilitada para entornos híbridos, puede mover usuarios entre el entorno local y la nube (ya sea para Microsoft Teams o Skype empresarial online).'
ms.openlocfilehash: b7e3ecc46af5a3043848d9291394c0bff7835883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160768"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover usuarios entre locales y la nube

En una implementación local de Skype empresarial Server que está habilitada para entornos híbridos, puede mover usuarios entre el entorno local y la nube (ya sea para Microsoft Teams o Skype empresarial online). Si un usuario se encuentra en una ubicación local o en la nube se conoce como la Página principal de Skype empresarial del usuario:

- Los usuarios hospedados en locales interactúan con los servidores locales de Skype empresarial.
- Los usuarios hospedados en línea pueden interactuar con el servicio de Skype empresarial online.

*Los usuarios de Microsoft Teams tienen una página principal de Skype empresarial, independientemente de si usan Skype empresarial o no.* Si tiene usuarios locales de Skype empresarial que también usan Microsoft Teams (en paralelo), estos usuarios se hospedarán de forma local. Los usuarios de Microsoft Teams con Skype empresarial local no tienen la capacidad de interactuar con los usuarios de Skype empresarial desde el cliente de Microsoft Teams, ni pueden comunicarse desde Microsoft Teams con usuarios de una organización federada. Esta funcionalidad solo está disponible después de que el usuario se haya movido de Skype empresarial local a en línea. Al mover un usuario a en línea, puede permitirles usar Skype empresarial online (y, opcionalmente, Teams) o hacerles solo Teams. Si su organización ya está usando Microsoft Teams, se recomienda encarecidamente que los mueva al modo solo Teams, lo que garantizará que el enrutamiento de todas las llamadas y chats entrantes se encuentren en el cliente de Microsoft Teams. Para obtener más información, vea la coexistencia de [Teams con Skype empresarial](/microsoftteams/coexistence-chat-calls-presence) y la [Guía de interoperabilidad y migración para organizaciones que usan Teams junto con Skype empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Requisitos previos

Requisitos previos para mover un usuario a la nube (ya sea para Skype empresarial solo o modo de solo Teams):

- La organización debe tener Azure AD Connect correctamente configurado y sincronizar todos los atributos relevantes para el usuario, tal como se describe en [Configure Azure ad Connect](configure-azure-ad-connect.md).
- Es necesario configurar Skype empresarial híbrido, tal y como se describe en [configurar Skype empresarial híbrido](configure-federation-with-skype-for-business-online.md).
- Al usuario se le debe asignar una licencia de Skype empresarial online (plan 2) y si va a usar Teams, también deben tener una licencia de Microsoft Teams.  Además:
    - Si el usuario está habilitado para las conferencias de acceso telefónico local, de forma predeterminada, el usuario también debe tener una licencia de audioconferencia asignada en Office 365 antes de ejecutar mover al usuario en línea. Una vez que se haya migrado a la nube, se aprovisionará al usuario para audioconferencia en la nube. Si por algún motivo desea mover un usuario a la nube, pero sin usar la funcionalidad de audioconferencia, puede invalidar esta comprobación especificando el `BypassAudioConferencingCheck` parámetro en. `Move-CsUser`
    - Si el usuario está habilitado para la telefonía IP empresarial en local, de forma predeterminada, el usuario debe tener una licencia de sistema telefónico asignada en Office 365 antes de mover al usuario en línea. Una vez que se haya migrado a la nube, se aprovisionará al usuario para el sistema telefónico en la nube. Si por algún motivo desea mover un usuario a la nube pero no usar la funcionalidad del sistema telefónico, puede invalidar esta comprobación especificando el `BypassEnterpriseVoiceCheck`parámetro en. `Move-CsUser`


## <a name="moving-users"></a>Mover usuarios

Cuando un usuario se mueve de local a la nube:

- El usuario comienza a usar los servicios de Skype empresarial online en la nube para cualquier funcionalidad de Skype empresarial.
- Los usuarios de Microsoft Teams se habilitan para la interoperabilidad con usuarios de Skype empresarial y también pueden federarse con otras organizaciones.
- Los contactos de local se mueven a la nube (ya sea Skype empresarial o Teams).
- Las reuniones existentes organizadas que se han programado en el futuro se migran a Internet: si los usuarios se mueven directamente a TeamsOnly (vea a continuación), las reuniones se convierten en reuniones de Microsoft Teams, de lo contrario, las reuniones siguen siendo Skype empresarial, pero se migrarán para que estén hospedado en línea en lugar de local.  La migración de reuniones se realiza de forma asíncrona y empieza aproximadamente 90 minutos después de mover al usuario.  Para determinar el estado de la migración de reuniones, puede usar [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Tenga en cuenta que no se mueve ningún contenido que se haya cargado antes de la reunión.

Para mover usuarios entre locales y la nube (ya sea para Microsoft Teams o Skype empresarial online), use el cmdlet Move-CsUser o el panel de control de administración de Skype empresarial, ambos son herramientas locales. Estas herramientas admiten tres rutas de movimiento diferentes:

- [De Skype empresarial Server (local) a Skype empresarial online](move-users-from-on-premises-to-skype-for-business-online.md).
- [Desde Skype empresarial Server (local) directamente a](move-users-from-on-premises-to-teams.md) Microsoft Teams (también los mueve a Skype empresarial online).  La opción de desplazarse directamente de local a Microsoft Teams solo está disponible en Skype empresarial Server 2019, así como en la actualización acumulativa 8 para Skype empresarial Server 2015. Las organizaciones que usan versiones anteriores de Skype empresarial Server pueden mover a los usuarios a Microsoft Teams solo si primero los mueve a Skype empresarial online y, a continuación, aplican el modo TeamsOnly a estos usuarios una vez que están en línea.
- [De la línea (solo si Teams o no), a local](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Credenciales administrativas necesarias

Para mover usuarios entre locales y la nube, debe usar una cuenta con privilegios suficientes tanto en el entorno local de Skype empresarial Server como en el inquilino de Office 365. Puede usar una cuenta que tenga todos los privilegios necesarios, o bien puede usar dos cuentas, en cuyo caso tendrá acceso a las herramientas locales con las credenciales locales y, a continuación, en esas herramientas se proporcionarán credenciales adicionales para un Office 365 cuenta administrativa.  

- En el entorno local, el usuario que realiza el traslado debe tener el rol CSServerAdminstrator en Skype empresarial Server.
- En Office 365, el usuario que realiza el traslado debe ser administrador global o tener los roles administrador de Skype empresarial y administrador de usuarios.  

    > [!Important]
    > - Si usa el panel de control de administración de Skype empresarial, se le pedirá que proporcione las credenciales de una cuenta de Office 365 con las funciones apropiadas, como se indicó anteriormente. Debe proporcionar una cuenta que finalice en. onmicrosoft.com. Si esto no es posible, use el cmdlet Move-CsUser.
    >- Si usa Move-CsUser en PowerShell, puede usar una cuenta que acabe en. onmicrosoft.com o puede usar cualquier cuenta local que se sincronice con Azure AD, siempre y cuando también especifique el parámetro HostedMigrationOverrideUrl en el cmdlet... . El valor de la dirección URL de invalidación de migración hospedada es una variante de la siguiente dirección URL:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>En la dirección URL anterior, reemplace el XX por dos o tres caracteres, determinados como se indica a continuación:
    >   - En una sesión de PowerShell de Skype empresarial online, ejecute el siguiente cmdlet:<br>`Get-CsTenant|ft identity`
    >    - El valor resultante tendrá el siguiente formato:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - El código de dos o tres dígitos es el XX contenido en la sección, DC = lyncXX001. Si se trata de un código de dos caracteres, será un dígito seguido de un número (como 0A). Si se trata de un código de tres caracteres, tendrá dos letras seguidas de un dígito (como JP1). En todos los casos, verá 001 inmediatamente después del código XX.


## <a name="voice-configuration-requirements"></a>Requisitos de configuración de voz

Si los usuarios se configuran para la telefonía IP empresarial en local, tendrá que coordinar la actualización de la configuración de voz cuando se mueva a online o, si lo prefiere, puede migrar sin capacidades de telefonía. Las opciones disponibles dependen de si el usuario va a usar el cliente de Microsoft Teams o Skype empresarial una vez que esté en línea:

- Puede actualizar el proveedor de telefonía de un usuario para que use un [plan de llamadas de Microsoft](/microsoftteams/calling-plans-for-office-365). Esta es una opción si los usuarios van a usar los clientes de Microsoft Teams o Skype empresarial.
- Puede seguir usando su proveedor de RTC local:
  - Los usuarios de voz que usarán Teams deben estar configurados para el [enrutamiento directo](/microsoftteams/direct-routing-plan). El enrutamiento directo solo está disponible después de que el usuario se mueva de local a en línea.
  - Los usuarios de voz que usarán el cliente de Skype empresarial una vez movidos en línea deben configurarse para la funcionalidad de voz híbrida de Skype empresarial.

Para obtener más información acerca de las opciones de telefonía en entornos híbridos, así como una matriz de compatibilidad, consulte [cuentas de usuario en un entorno híbrido con conectividad RTC](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Otras consideraciones

Las directivas (como para controlar la mensajería, la reunión y el comportamiento de llamadas) en entornos locales y en línea son independientes. Es posible que desee considerar la configuración de las directivas en el entorno y asignarlas al usuario antes de mover ese usuario de local a la nube, de modo que tengan la configuración correcta en cuanto se migren a en línea.

## <a name="see-also"></a>Vea también

[Mover usuarios de local a Skype empresarial online](move-users-from-on-premises-to-skype-for-business-online.md)

[Mover usuarios de local a teams](move-users-from-on-premises-to-teams.md)

[Configuración del servicio de migración de reuniones (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planeación del enrutamiento directo](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
