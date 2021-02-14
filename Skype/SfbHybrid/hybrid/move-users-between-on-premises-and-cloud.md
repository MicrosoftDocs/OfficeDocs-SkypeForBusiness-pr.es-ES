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
description: 'Resumen: en una implementación local de Skype Empresarial Server habilitada para entornos híbridos, puede mover usuarios entre el entorno local y la nube (ya sea a Microsoft Teams o a Skype Empresarial Online).'
ms.openlocfilehash: eede6062bd9d03a2d9d6062a6dacb861ce37e14c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221130"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover usuarios entre la implementación local y la nube

En una implementación local de Skype Empresarial Server que esté habilitada para entornos híbridos, puede trasladar usuarios entre el entorno local y la nube (tanto a Microsoft Teams como a Skype Empresarial Online). Independientemente de si el usuario se encuentra en un entorno local o en la nube, este se denomina página de inicio del usuario de Skype Empresarial:

- Los usuarios que están internos interactúan con los servidores locales de Skype Empresarial.
- Los usuarios cuya página de inicio se encuentra en línea pueden interactuar con el servicio de Skype Empresarial Online.

*Los usuarios de Teams tienen inherentemente una casa de Skype Empresarial, independientemente de si usan Skype Empresarial o no.* Si tiene usuarios locales de Skype Empresarial que también usan Teams (en paralelo), estos usuarios se encuentran en el entorno local. Los usuarios de Teams con Skype Empresarial local no tienen la capacidad de interoperar con los usuarios de Skype Empresarial desde su cliente de Teams, ni pueden comunicarse desde Teams con los usuarios de una organización federada. Esta funcionalidad solo está disponible después de que el usuario se mueve de Skype Empresarial local a online. Cuando se traslada un usuario al entorno en línea, le puede permitir que use Skype Empresarial Online (y, opcionalmente, Teams) o que solo pueda usar Teams. Si su organización ya usa Teams, se recomienda encarecidamente que los traslade al modo Teams solo, que garantizará que el enrutamiento de todas las conversaciones y llamadas entrantes se haga a su cliente de Teams. Para obtener más información, consulte La coexistencia de Teams con [Skype](/microsoftteams/coexistence-chat-calls-presence) Empresarial y la migración y la guía de interoperabilidad para las organizaciones que usan Teams junto con [Skype Empresarial.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="prerequisites"></a>Requisitos previos

Requisitos previos para mover un usuario a la nube (si solo a Skype Empresarial o al modo de solo Teams):

- La organización debe tener Azure AD Connect configurado correctamente y estar sincronizando todos los atributos relevantes para el usuario, tal como se describe en [Configurar Azure AD Connect.](configure-azure-ad-connect.md)
- Skype Empresarial híbrido debe configurarse, como se describe en [Configurar Skype Empresarial híbrido.](configure-federation-with-skype-for-business-online.md)
- El usuario debe tener asignada una licencia para Skype Empresarial Online (plan 2) y si va a usar Teams, también deben tener una licencia de Teams.  Además:
    - Si el usuario está habilitado para conferencias de acceso telefónico local, de forma predeterminada, el usuario también debe tener asignada una licencia de Audioconferencia en Microsoft 365 u Office 365 antes de ejecutar mover el usuario en línea. Una vez que se haya migrado a la nube, el usuario se aprovisionará para las conferencias de audio en la nube. Si por algún motivo desea mover un usuario a la nube, pero no usar la funcionalidad de audioconferencia, puede invalidar esta comprobación especificando el `BypassAudioConferencingCheck` parámetro en `Move-CsUser` .
    - Si el usuario está habilitado para Telefonía IP empresarial localmente, de forma predeterminada el usuario debe tener asignada una licencia del Sistema telefónico en Microsoft 365 u Office 365 antes de mover el usuario en línea. Una vez que se haya migrado a la nube, el usuario se aprovisionará para Sistema telefónico en la nube. Si por algún motivo desea mover un usuario a la nube pero no usar la funcionalidad sistema telefónico, puede invalidar esta comprobación especificando `BypassEnterpriseVoiceCheck` el parámetro en `Move-CsUser` .


## <a name="moving-users"></a>Traslado de usuarios

Cuando un usuario se traslada del entorno local a la nube:

- El usuario inicia el uso de los servicios de Skype Empresarial Online en la nube para cualquier funcionalidad de Skype Empresarial.
- Los usuarios de Teams se habilitan para la interoperabilidad con los usuarios de Skype Empresarial y también pueden federarse a otras organizaciones.
- Los contactos locales se mueven a la nube (Ya sea Skype Empresarial o Teams).
- Las reuniones existentes que organizaron programadas en el futuro se migran a línea: si los usuarios se mueven directamente a TeamsOnly (vea a continuación), las reuniones se convierten en reuniones de Teams; de lo contrario, las reuniones permanecen en Skype Empresarial, pero se migrarán para que se hospedan en línea en lugar de local.  La migración de reuniones se produce de forma asíncrona y comienza aproximadamente 90 minutos después de mover el usuario.  Para determinar el estado de la migración de reuniones, puede usar [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Tenga en cuenta que el contenido que se haya cargado por anticipado a la reunión no se traslada.

Para mover usuarios entre local y la nube (ya sea a Teams o a Skype Empresarial Online), use el cmdlet Move-CsUser o el Panel de control de administración de Skype Empresarial, que son herramientas locales. Estas herramientas son compatibles con tres rutas distintas para trasladar:

- [De Skype Empresarial Server (local) a Skype Empresarial Online.](move-users-from-on-premises-to-skype-for-business-online.md)
- [De Skype Empresarial Server (local)](move-users-from-on-premises-to-teams.md) directamente a Solo Teams (que también los mueve a Skype Empresarial Online).  The option to move directly from on premises to Teams Only is available in Skype for Business Server 2019 as well as Cumulative Update 8 for Skype for Business Server 2015. Las organizaciones que usen versiones anteriores de Skype Empresarial Server podrán trasladar usuarios a Teams solo si primero los trasladan a Skype Empresarial Online y después aplican el modo Teams solo a estos usuarios una vez que estén en el entorno en línea.
- [Desde en línea (solo Teams o no), hasta local.](move-users-from-the-cloud-to-on-premises.md)

## <a name="required-administrative-credentials"></a>Credenciales administrativas necesarias

Para mover usuarios entre local y en la nube, debe usar una cuenta con privilegios suficientes tanto en el entorno local de Skype Empresarial Server como en la organización de Microsoft 365 u Office 365. Puede usar una cuenta que tenga todos los privilegios necesarios o puede usar dos cuentas, en cuyo caso tendría acceso a las herramientas locales con credenciales locales y, a continuación, en esas herramientas proporcionaría credenciales adicionales para una cuenta administrativa de Microsoft 365 u Office 365.  

- En el entorno local, el usuario que lleva a cabo el traslado debe tener el rol CSServerAdminstrator en Skype Empresarial Server.
- En Microsoft 365 y Office 365, el usuario que realiza el movimiento debe ser un administrador global o debe tener los roles administrador de Skype Empresarial y Administrador de usuarios.  

    > [!Important]
    > - Si usa el Panel de control de administración de Skype Empresarial, se le pedirá que proporcione las credenciales de una cuenta de Microsoft 365 u Office 365 con los roles adecuados, como se indicó anteriormente. Debe proporcionar una cuenta que termine en .onmicrosoft.com. Si no es posible, use el cmdlet Move-CsUser.
    >- Si usa Move-CsUser en PowerShell, puede usar una cuenta que termine en .onmicrosoft.com o puede usar cualquier cuenta local que esté sincronizada con Azure AD, siempre que también especifique el parámetro HostedMigrationOverrideUrl en el cmdlet. El valor de la dirección URL de invalidación de migración hospedada es una variante de la siguiente dirección URL: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>En la dirección URL anterior, reemplace xx por dos o tres caracteres, determinados de la siguiente manera:
    >   - En una sesión de PowerShell de Skype Empresarial Online, ejecute el siguiente cmdlet:<br>`Get-CsTenant|ft identity`
    >    - El valor resultante tendrá el siguiente formato:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - El código de dos o tres dígitos es el XX contenido en la sección DC=lyncXX001. Si es un código de dos caracteres, será un dígito seguido de un número (como 0a). Si es un código de tres caracteres, serán dos letras seguidas de un dígito (como jp1). En todos los casos, verás 001 inmediatamente después del código XX.


## <a name="voice-configuration-requirements"></a>Requisitos de configuración de voz

Si los usuarios están configurados para la telefonía IP empresarial local, tendrá que coordinar la actualización de su configuración de voz cuando los mueva a línea o, como alternativa, podría migrarlos sin capacidades de telefonía. Las opciones disponibles dependen de si el usuario va a usar el cliente de Teams o Skype Empresarial una vez que esté conectado:

- Puede actualizar el proveedor de telefonía de un usuario para que use un [plan de llamadas de Microsoft.](/microsoftteams/calling-plans-for-office-365) Esta es una opción que indica si los usuarios usarán los clientes de Teams o Skype Empresarial.
- Puede seguir usando su proveedor de RTC local:
  - Los usuarios de voz que usarán Teams deben configurarse para [el enrutamiento directo.](/microsoftteams/direct-routing-plan) El enrutamiento directo solo está disponible después de que el usuario se mueve de local a en línea.
  - Los usuarios de voz que usarán el cliente de Skype Empresarial después de moverse en línea deben configurarse para la funcionalidad de voz híbrida de Skype Empresarial.

Para obtener más información sobre las opciones de telefonía en entornos híbridos, así como una matriz de compatibilidad, consulte Cuentas de usuario en un entorno híbrido con conectividad [RTC.](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)

## <a name="other-considerations"></a>Otras consideraciones

Las directivas (como, por ejemplo, controlar el comportamiento de la mensajería, las reuniones y las llamadas) en entornos locales y en línea son independientes. Es posible que desee considerar la posibilidad de configurar las directivas en el entorno y asignarlas al usuario antes de mover ese usuario de local a la nube, para que tenga la configuración correcta tan pronto como se migren a la conexión.

## <a name="see-also"></a>Vea también

[Mover usuarios locales a Skype para empresas Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Mover usuarios locales a Microsoft Teams](move-users-from-on-premises-to-teams.md)

[Configuración del servicio de migración de reuniones (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planear el enrutamiento directo](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
