---
title: Mover usuarios entre la implementación local y la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
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
ms.openlocfilehash: aea3bed7db6c7821d957aa0e6d56cbafd548edb7
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780089"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover usuarios entre la implementación local y la nube

En una implementación local de Skype Empresarial Server que esté habilitada para entornos híbridos, puede trasladar usuarios entre el entorno local y la nube (tanto a Microsoft Teams como a Skype Empresarial Online). Independientemente de si el usuario se encuentra en un entorno local o en la nube, este se denomina página de inicio del usuario de Skype Empresarial:

- Los usuarios hospedados en locales interactúan con los servidores locales de Skype empresarial.
- Los usuarios cuya página de inicio se encuentra en línea pueden interactuar con el servicio de Skype Empresarial Online.

*Los usuarios de Teams tienen una página de inicio de Skype Empresarial, tanto si lo usan como si no.* Si tiene usuarios locales de Skype empresarial que también usan Microsoft Teams (en paralelo), estos usuarios se hospedarán de forma local. Los usuarios de Microsoft Teams con Skype empresarial local no tienen la capacidad de interactuar con los usuarios de Skype empresarial desde el cliente de Microsoft Teams, ni pueden comunicarse desde Microsoft Teams con usuarios de una organización federada. Esta funcionalidad solo está disponible después de que el usuario se haya movido de Skype empresarial local a en línea. Cuando se traslada un usuario al entorno en línea, le puede permitir que use Skype Empresarial Online (y, opcionalmente, Teams) o que solo pueda usar Teams. Si su organización ya usa Teams, se recomienda encarecidamente que los traslade al modo Teams solo, que garantizará que el enrutamiento de todas las conversaciones y llamadas entrantes se haga a su cliente de Teams. Para obtener más información, vea la [coexistencia de Teams con Skype empresarial](/microsoftteams/coexistence-chat-calls-presence) y la [Guía de interoperabilidad y migración para organizaciones que usan Teams junto con Skype empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Requisitos previos

Requisitos previos para mover un usuario a la nube (ya sea para Skype empresarial solo o modo de solo Teams):

- La organización debe tener Azure AD Connect correctamente configurado y sincronizar todos los atributos relevantes para el usuario, tal como se describe en [Configure Azure ad Connect](configure-azure-ad-connect.md).
- Es necesario configurar Skype empresarial híbrido, tal y como se describe en [configurar Skype empresarial híbrido](configure-federation-with-skype-for-business-online.md).
- El usuario debe tener asignada una licencia para Skype Empresarial Online (plan 2) y si va a usar Teams, también deben tener una licencia de Teams.  Además:
    - Si el usuario está habilitado para las conferencias de acceso telefónico local, de forma predeterminada, el usuario también debe tener una licencia de audioconferencia asignada en Office 365 antes de ejecutar mover al usuario en línea. Una vez que se haya migrado a la nube, el usuario se aprovisionará para las conferencias de audio en la nube. Si por algún motivo desea mover un usuario a la nube, pero sin usar la funcionalidad de audioconferencia, puede invalidar esta comprobación especificando el `BypassAudioConferencingCheck` parámetro en. `Move-CsUser`
    - Si el usuario está habilitado para la telefonía IP empresarial en local, de forma predeterminada, el usuario debe tener una licencia de sistema telefónico asignada en Office 365 antes de mover al usuario en línea. Una vez que se haya migrado a la nube, el usuario se aprovisionará para Sistema telefónico en la nube. Si por algún motivo desea mover un usuario a la nube pero no usar la funcionalidad del sistema telefónico, puede invalidar esta comprobación especificando el `BypassEnterpriseVoiceCheck`parámetro en. `Move-CsUser`


## <a name="moving-users"></a>Traslado de usuarios

Cuando un usuario se traslada del entorno local a la nube:

- El usuario inicia el uso de los servicios de Skype Empresarial Online en la nube para cualquier funcionalidad de Skype Empresarial.
- Los usuarios de Teams se habilitan para la interoperabilidad con los usuarios de Skype Empresarial y también pueden federarse a otras organizaciones.
- Los contactos de local se mueven a la nube (ya sea Skype empresarial o Teams).
- Las reuniones existentes organizadas que se han programado en el futuro se migran a Internet: si los usuarios se mueven directamente a TeamsOnly (vea a continuación), las reuniones se convierten en reuniones de Teams, de lo contrario, las reuniones siguen siendo Skype empresarial, pero se migrarán para que se hospeden en línea en lugar de locales.  La migración de reuniones se produce de forma asíncrona y comienza aproximadamente 90 minutos después de mover el usuario.  Para determinar el estado de la migración de reuniones, puede usar [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Tenga en cuenta que el contenido que se haya cargado por anticipado a la reunión no se traslada.

Para mover usuarios entre locales y la nube (ya sea para Microsoft Teams o Skype empresarial online), use el cmdlet Move-CsUser o el panel de control de administración de Skype empresarial, ambos son herramientas locales. Estas herramientas son compatibles con tres rutas distintas para trasladar:

- [De Skype empresarial Server (local) a Skype empresarial online](move-users-from-on-premises-to-skype-for-business-online.md).
- [De Skype empresarial Server (local) directamente a Microsoft Teams](move-users-from-on-premises-to-teams.md) (que también los mueve a Skype empresarial online).  La opción de desplazarse directamente de local a Microsoft Teams solo está disponible en Skype empresarial Server 2019, así como en la actualización acumulativa 8 para Skype empresarial Server 2015. Las organizaciones que usen versiones anteriores de Skype Empresarial Server solo podrán trasladar usuarios a Teams si primero los trasladan a Skype Empresarial Online y después aplican el modo TeamsOnly a estos usuarios una vez que estén en el entorno en línea.
- [De la línea (solo si Teams o no), a local](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Credenciales administrativas necesarias

Para mover usuarios entre locales y la nube, debe usar una cuenta con privilegios suficientes tanto en el entorno local de Skype empresarial Server como en la organización de Office 365. Puede usar una cuenta que tenga todos los privilegios necesarios, o puede usar dos cuentas, en cuyo caso necesitaría tener acceso a las herramientas locales con las credenciales locales y, después, en esas herramientas, deberá especificar credenciales adicionales para una cuenta administrativa de Office 365.  

- En el entorno local, el usuario que lleva a cabo el traslado debe tener el rol CSServerAdminstrator en Skype Empresarial Server.
- En Office 365, el usuario que lleva a cabo el traslado debe ser administrador global o debe tener los roles Administrador de Skype Empresarial y Administrador de usuarios.  

    > [!Important]
    > - Si usa el panel de control de administración de Skype empresarial, se le pedirá que proporcione las credenciales de una cuenta de Office 365 con las funciones apropiadas, como se indicó anteriormente. Debe proporcionar una cuenta que finalice en. onmicrosoft.com. Si esto no es posible, use el cmdlet Move-CsUser.
    >- Si usa Move-CsUser en PowerShell, puede usar una cuenta que acabe en. onmicrosoft.com o puede usar cualquier cuenta local que se sincronice con Azure AD, siempre y cuando también especifique el parámetro HostedMigrationOverrideUrl en el cmdlet de. El valor de la dirección URL de invalidación de migración hospedada es una variante de la siguiente dirección URL:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>En la dirección URL anterior, reemplace el XX por dos o tres caracteres, determinados como se indica a continuación:
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

Las directivas (como, por ejemplo, controlar el comportamiento de la mensajería, las reuniones y las llamadas) en entornos locales y en línea son independientes. Es posible que desee considerar la configuración de las directivas en el entorno y asignarlas al usuario antes de mover ese usuario de local a la nube, de modo que tengan la configuración correcta en cuanto se migren a en línea.

## <a name="see-also"></a>Ver también

[Mover usuarios locales a Skype para empresas Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Mover usuarios locales a Microsoft Teams](move-users-from-on-premises-to-teams.md)

[Configuración del servicio de migración de reuniones (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planear el enrutamiento directo](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
