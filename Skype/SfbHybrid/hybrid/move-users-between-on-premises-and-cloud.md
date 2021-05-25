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
description: 'Resumen: en una implementación local de Skype Empresarial Server habilitada para híbridos, puede mover usuarios entre el entorno local y la nube (ya sea Microsoft Teams o Skype Empresarial Online antes de su retirada).'
ms.openlocfilehash: 3140811a08f582488e672fccbfa7f34678b813d4
ms.sourcegitcommit: 9d446485aa842abbdcd34d946b247166c2bf1610
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "52642090"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover usuarios entre la implementación local y la nube

En una implementación local de Skype Empresarial Server habilitada para híbridos, puede mover usuarios entre el entorno local y la nube (ya sea Microsoft Teams o Skype Empresarial Online antes de su retirada). Independientemente de si el usuario se encuentra en un entorno local o en la nube, este se denomina página de inicio del usuario de Skype Empresarial:

- Los usuarios que se encuentran en una ubicación local interactúan con los servidores Skype Empresarial locales.
- Los usuarios cuya página de inicio se encuentra en línea pueden interactuar con el servicio de Skype Empresarial Online.

*Teams usuarios inherentemente tienen una Skype Empresarial hogar, independientemente de si usan Skype Empresarial o no.* Si tiene usuarios locales Skype Empresarial que también usan Teams (en paralelo), dichos usuarios se encuentran en el entorno local. Teams usuarios con Skype Empresarial local no tienen la capacidad de interoperar con usuarios de Skype Empresarial desde su cliente de Teams ni pueden comunicarse desde Teams con usuarios de una organización federada. Dicha funcionalidad solo está disponible después de que el usuario se Skype Empresarial local a online y se ha hecho TeamsOnly. Cuando se traslada un usuario al entorno en línea, le puede permitir que use Skype Empresarial Online (y, opcionalmente, Teams) o que solo pueda usar Teams. Se recomienda encarecidamente que mueva a los usuarios al modo de solo Teams, lo que garantizará que el enrutamiento de todos los chats y llamadas entrantes aterrice en su Teams cliente. Para obtener más información, vea [Teams coexistencia](/microsoftteams/coexistence-chat-calls-presence) con Skype Empresarial [y Guía](/microsoftteams/migration-interop-guidance-for-teams-with-skype)de migración e interoperabilidad para organizaciones que usan Teams junto con Skype Empresarial .

## <a name="prerequisites"></a>Requisitos previos

Requisitos previos para mover un usuario a la nube (ya sea Teams modo solo o Skype Empresarial Online antes de su retirada):

- La organización debe tener Azure AD Conectar configurado correctamente y estar sincronizando todos los atributos relevantes para el usuario, tal como se describe en [Configure Azure AD Conectar](configure-azure-ad-connect.md).
- Skype Empresarial debe configurarse híbrido, como se describe en [Configurar Skype Empresarial híbrido](configure-federation-with-skype-for-business-online.md).
- Al usuario se le debe asignar una licencia para Teams y Skype Empresarial Online (Plan 2). Incluso después de la retirada de Skype Empresarial Online, la licencia Skype Empresarial Online sigue siendo necesaria.  Además:
    - Si el usuario está habilitado para conferencias de acceso telefónico local, de forma predeterminada, el usuario también debe tener una licencia de audioconferencia asignada en Teams antes de mover el usuario en línea. Una vez que se haya migrado a la nube, el usuario se aprovisionará para las conferencias de audio en la nube. Si por algún motivo desea mover un usuario a la nube, pero no usar la funcionalidad de audioconferencia, puede invalidar esta comprobación especificando el `BypassAudioConferencingCheck` parámetro en `Move-CsUser` .
    - Si el usuario está habilitado para Telefonía IP empresarial local, de forma predeterminada, el usuario debe tener una licencia de Sistema telefónico asignada en Teams antes de mover el usuario en línea. Una vez que se haya migrado a la nube, el usuario se aprovisionará para Sistema telefónico en la nube. Si por algún motivo desea mover un usuario a la nube pero no usar la funcionalidad Sistema telefónico, puede invalidar esta comprobación especificando el `BypassEnterpriseVoiceCheck` parámetro en `Move-CsUser` .


## <a name="moving-users"></a>Traslado de usuarios

Cuando un usuario se traslada del entorno local a la nube:

- Teams los usuarios se habilitan para la interoperabilidad con Skype Empresarial usuarios y, si son TeamsOnly, también pueden federar con otras organizaciones.
- El usuario inicia el uso de los servicios de Skype Empresarial Online en la nube para cualquier funcionalidad de Skype Empresarial.
- Los contactos locales se mueven a la nube (ya sea para Teams o Skype Empresarial online).
- Las reuniones existentes que organizaron y que están programadas en el futuro se migran a línea: si los usuarios se mueven directamente a TeamsOnly (vea más adelante), las reuniones se convierten en reuniones Teams, de lo contrario las reuniones permanecen Skype Empresarial pero se migrarán para que se hospedan en línea en lugar de locales.  La migración de reuniones se produce de forma asíncrona y comienza aproximadamente 90 minutos después de mover el usuario.  Para determinar el estado de la migración de reuniones, puede usar [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Tenga en cuenta que el contenido que se haya cargado por anticipado a la reunión no se traslada.

Para mover usuarios entre la nube y local (ya sea Teams o Skype Empresarial Online), use el cmdlet Move-CsUser o el Panel de control de administración de Skype Empresarial, que son herramientas locales. Estas herramientas son compatibles con tres rutas distintas para trasladar:

- [De Skype Empresarial Server (local) directamente](move-users-from-on-premises-to-teams.md) a Teams solo (que también los mueve a Skype Empresarial Online).  La opción de pasar directamente de local a  Teams Only está disponible actualmente en Skype Empresarial Server 2019, así como la actualización acumulativa 8 para Skype Empresarial Server 2015. Las organizaciones que usen versiones anteriores de Skype Empresarial Server podrán trasladar usuarios a Teams solo si primero los trasladan a Skype Empresarial Online y después aplican el modo Teams solo a estos usuarios una vez que estén en el entorno en línea. 

> [!NOTE] 
> Pronto ya no será necesario especificar el modificador -MoveToTeams en Move-CsUser mover usuarios directamente de local a TeamsOnly. Actualmente, si no se especifica este modificador, los usuarios pueden pasar de hospedarse en Skype Empresarial Server local a Skype Empresarial Online y su modo permanece sin cambios. Después de retirarse, al mover un usuario de local a la nube con Move-CsUser, los usuarios se asignarán automáticamente al modo TeamsOnly y sus reuniones desde locales se convertirán automáticamente en reuniones de Teams, igual que si se hubiera especificado el modificador -MoveToTeams, independientemente de si el modificador está especificado realmente. Esperamos liberar esta funcionalidad antes de la retirada real del 31 de julio de 2021.

- [De Skype Empresarial Server (local) a Skype Empresarial Online](move-users-from-on-premises-to-skype-for-business-online.md). Esta opción pronto ya no estará disponible.
- [Desde en línea (Teams solo o no), a local](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Credenciales administrativas necesarias

Para mover usuarios entre locales y la nube, debe usar una cuenta con privilegios suficientes tanto en el entorno Skype Empresarial Server local como en la Teams organización. Puede usar una cuenta que tenga todos los privilegios necesarios o puede usar dos cuentas, en cuyo caso tendría acceso a las herramientas locales con credenciales locales y, a continuación, en esas herramientas, proporcionaría credenciales adicionales para una cuenta administrativa de Teams.  

- En el entorno local, el usuario que realiza el movimiento debe tener el rol CSServerAdministrator en Skype Empresarial Server.
- En Teams, el usuario que realiza el movimiento debe cumplir uno de los siguientes criterios:
  - El usuario es miembro del rol Administrador global.
  - El usuario es miembro de los roles administrador Teams administrador y administrador de usuarios.
  - El usuario es miembro de los roles administrador Skype Empresarial administrador y administrador de usuarios.  

    > [!Important]
    > - Si usa el Panel de control de administración Skype Empresarial, se le pedirá que proporcione credenciales para una cuenta de Microsoft 365 con los roles adecuados, como se mencionó anteriormente. Debe proporcionar una cuenta que termine en .onmicrosoft.com. Si no es posible, use el cmdlet Move-CsUser.
    >- Si usa Move-CsUser en PowerShell, puede usar una cuenta que termine en .onmicrosoft.com o puede usar cualquier cuenta local que esté sincronizada en Azure AD, siempre que también especifique el parámetro HostedMigrationOverrideUrl en el cmdlet. El valor de la dirección URL de invalidación de migración hospedada es una variante de la siguiente dirección URL: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>En la dirección URL anterior, reemplace el XX por dos o tres caracteres, determinados de la siguiente manera:
    >   - En una Teams de PowerShell, ejecute el siguiente cmdlet:<br>`Get-CsTenant|ft identity`
    >   - El valor resultante tendrá el siguiente formato:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >   - El código de dos o tres dígitos es el XX contenido en la sección DC=lyncXX001. Si es un código de dos caracteres, será un dígito seguido de un número (como 0a). Si es un código de tres caracteres, serán dos letras seguidas de un dígito (como jp1). En todos los casos, verá 001 inmediatamente después del código XX.


## <a name="voice-configuration-requirements"></a>Requisitos de configuración de voz

Si los usuarios están configurados para la voz empresarial local, tendrá que coordinar la actualización de su configuración de voz cuando los mueva a línea o, como alternativa, podría migrarlos sin capacidades de telefonía. Las opciones disponibles dependen de si el usuario va a usar el Teams o Skype Empresarial cliente una vez que estén en línea:

- Puede actualizar el proveedor de telefonía de un usuario para que use un [Plan de llamadas de Microsoft](/microsoftteams/calling-plans-for-office-365). Esta es una opción que indica si los usuarios usarán Teams o Skype Empresarial cliente.
- Puede seguir usando su proveedor de RTC local:
  - Los usuarios de voz que usarán Teams deben configurarse para [enrutamiento directo](/microsoftteams/direct-routing-plan). El enrutamiento directo solo está disponible después de que el usuario se mueve de local a en línea.
  - Los usuarios de voz que van a usar Skype Empresarial cliente después de que se mueven en línea deben configurarse para la Skype Empresarial Hybrid de voz.

Para obtener más información acerca de las opciones de telefonía en entornos híbridos, así como una matriz de compatibilidad, vea Cuentas de usuario en un entorno híbrido con [conectividad RTC.](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)

## <a name="other-considerations"></a>Otras consideraciones

Las directivas (como, por ejemplo, controlar el comportamiento de la mensajería, las reuniones y las llamadas) en entornos locales y en línea son independientes. Es posible que desee considerar la posibilidad de configurar las directivas del entorno y asignarlas al usuario antes de mover ese usuario desde local a la nube, de modo que tengan la configuración correcta tan pronto como se migren a la red.

## <a name="see-also"></a>Vea también

[Mover usuarios locales a Microsoft Teams](move-users-from-on-premises-to-teams.md)

[Mover usuarios locales a Skype para empresas Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Configuración del servicio de migración de reuniones (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planear el enrutamiento directo](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
