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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumen: en una implementación local de Skype Empresarial Server habilitada para híbridos, puede mover usuarios entre el entorno local y la nube.'
ms.openlocfilehash: 15e237fdf54854a86216bc3890ae26209449c146
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "65304012"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover usuarios entre la implementación local y la nube

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En una implementación local de Skype Empresarial Server habilitada para el entorno híbrido, puede mover usuarios entre el entorno local y Teams. Independientemente de si el usuario se encuentra en un entorno local o en la nube, este se denomina página de inicio del usuario de Skype Empresarial:

- Los usuarios hospedados en el entorno local interactúan con servidores de Skype Empresarial locales.
- Los usuarios hospedados en línea pueden interactuar con el servicio de Teams.

*Teams los usuarios tienen inherentemente un hogar Skype Empresarial, tanto si usan Skype Empresarial como si no.* Si tiene usuarios locales Skype Empresarial que también usan Teams (en paralelo), esos usuarios se alojan en el entorno local. Teams los usuarios con Skype Empresarial locales no pueden interoperar con Skype Empresarial usuarios de su cliente Teams, ni tampoco pueden comunicarse desde Teams con los usuarios de una organización federada. Esta funcionalidad solo está totalmente disponible después de que el usuario se mueva de Skype Empresarial local a en línea y se haya hecho TeamsOnly. Se recomienda mover a los usuarios al modo TeamsOnly, lo que garantizará que el enrutamiento de todos los chats y llamadas entrantes llegue a su cliente Teams. Para obtener más información, consulte [Teams coexistencia con Skype Empresarial](/microsoftteams/coexistence-chat-calls-presence) y [guía de migración e interoperabilidad para las organizaciones que usan Teams junto con Skype Empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Requisitos previos

Requisitos previos para mover un usuario al modo TeamsOnly:

- La organización debe tener Azure AD Conectar configurado correctamente y estar sincronizando todos los atributos pertinentes para el usuario, tal como se describe en [Configuración de azure AD Conectar](configure-azure-ad-connect.md).
- Skype Empresarial híbrido debe configurarse, como se describe en [Configurar Skype Empresarial híbrido](configure-federation-with-skype-for-business-online.md).
- Al usuario se le debe asignar una licencia para Teams y Skype Empresarial Online (plan 2). Incluso después de la retirada de Skype Empresarial Online, todavía se requiere la licencia de Skype Empresarial Online.  Además:
    - Si el usuario está habilitado para las conferencias de acceso telefónico local, el usuario también debe tener una licencia de Audioconferencia asignada en Teams antes de mover al usuario en línea. Una vez que se haya migrado a la nube, el usuario se aprovisionará para las conferencias de audio en la nube. 
    - Si el usuario está habilitado para Telefonía IP empresarial en el entorno local, el usuario debe tener una licencia de Sistema telefónico asignada en Teams antes de mover al usuario en línea. Una vez migrado a la nube, el usuario se aprovisionará para Sistema telefónico en la nube. 


## <a name="moving-users"></a>Traslado de usuarios

Cuando un usuario se traslada del entorno local a la nube:

- Teams los usuarios se habilitan para la interoperabilidad con Skype Empresarial usuarios y, si son TeamsOnly, también pueden federarse con otras organizaciones.

- Los contactos del entorno local se mueven a Teams.

- Las reuniones existentes que organizaron y que están programadas en el futuro se convierten en reuniones Teams. La migración de reuniones se produce de forma asíncrona y comienza aproximadamente 90 minutos después de mover el usuario.  Para determinar el estado de la migración de reuniones, puede usar [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). No se mueve ningún contenido que se haya cargado antes de la reunión.

Para mover a los usuarios a Teams, use el cmdlet Move-CsUser o el Panel de control Skype Empresarial Admin, que son herramientas locales. Estas herramientas admiten las siguientes rutas de acceso de movimiento:

- [De Skype Empresarial Server (local) directamente a solo Teams](move-users-from-on-premises-to-teams.md).  El comportamiento para pasar directamente del entorno local a Teams Solo ahora es automático, independientemente de la versión de Skype Empresarial Server o Lync Server. Ya no es necesario especificar el `-MoveToTeams` modificador para obtener este comportamiento.  
- [Desde en línea (ya sea Teams solo o no), a local](move-users-from-the-cloud-to-on-premises.md).

> [!NOTE] 
> Ya no es necesario especificar el modificador -MoveToTeams en Move-CsUser para mover usuarios directamente del entorno local a TeamsOnly. Anteriormente, si no se especificaba este modificador, los usuarios pasaron de estar hospedados en Skype Empresarial Server local a Skype Empresarial En línea y su modo permaneció sin cambios. Ahora, al mover un usuario del entorno local a la nube con Move-CsUser, se asigna automáticamente el modo TeamsOnly a los usuarios y sus reuniones desde el entorno local se convierten automáticamente en reuniones Teams, como si se hubiera especificado el `-MoveToTeams` conmutador, independientemente de si realmente se especificó el modificador. 
> 

## <a name="required-administrative-credentials"></a>Credenciales administrativas necesarias

Para mover usuarios entre el entorno local y la nube, debe usar una cuenta con privilegios suficientes tanto en el entorno de Skype Empresarial Server local como en la organización Teams. Puede usar una cuenta que tenga todos los privilegios necesarios o puede usar dos cuentas. Si usa dos cuentas, accedería a las herramientas locales mediante credenciales locales y, a continuación, en esas herramientas proporcionaría credenciales adicionales para una cuenta administrativa de Teams.  

- En el entorno local, el usuario que realiza el traslado debe tener los roles CSServerAdministrator, CsUserAdministrator y RTCUniversalUserAdmins en Skype Empresarial Server.
- En Teams, el usuario que realiza el traslado debe ser miembro de al menos uno de los roles siguientes:
  - Rol de administrador global
  - rol administrador de Teams
  - Skype Empresarial rol de administrador.  

    > [!Important]
    > - Si usa el Panel de control de administrador de Skype Empresarial, se le pedirá que proporcione las credenciales de una cuenta de Microsoft 365 con los roles adecuados, como se indicó anteriormente. Debe proporcionar una cuenta que termine en .onmicrosoft.com. Si no es posible, use el cmdlet Move-CsUser.
    >- Si usa Move-CsUser en PowerShell, puede usar una cuenta que termine en .onmicrosoft.com o cualquier cuenta local que esté sincronizada con Azure AD, siempre que también especifique el parámetro HostedMigrationOverrideUrl en el cmdlet. El valor de la dirección URL de invalidación de migración hospedada es una variante de la siguiente dirección URL: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>En la dirección URL anterior, reemplace xx por dos o tres caracteres, determinados de la siguiente manera:
    >   - En una sesión de PowerShell Teams, ejecute el siguiente cmdlet:<br>`Get-CsTenant | ft ServiceInstance`
    >   - El valor resultante tendrá el formato siguiente:<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - El código de dos o tres caracteres es el XX contenido en la sección AAAA-XX-ZZ. Si es un código de dos caracteres, será un dígito seguido de un número (por ejemplo, 4A). Si es un código de tres caracteres, serán dos letras seguidas de un dígito (como JP1). Un ejemplo es NOAM-4A-S7.


## <a name="voice-configuration-requirements"></a>Requisitos de configuración de voz

Si los usuarios están configurados para la voz empresarial en el entorno local, debe coordinar la actualización de su configuración de voz al moverlos a en línea. Como alternativa, podría migrarlos sin funcionalidades de telefonía. Las opciones disponibles dependen de si el usuario usará la Teams o Skype Empresarial cliente una vez que esté en línea:

- Puede actualizar el proveedor de telefonía de un usuario para usar un [plan de llamadas de Microsoft](/microsoftteams/calling-plans-for-office-365). Esta es una opción si los usuarios usarán Teams o Skype Empresarial clientes.
- Puede seguir usando el proveedor RTC local:
  - Los usuarios de voz que usarán Teams deben estar configurados para [el enrutamiento directo](/microsoftteams/direct-routing-plan). El enrutamiento directo solo está disponible después de que el usuario se mueva de local a en línea.
  - Los usuarios de voz que usarán el cliente de Skype Empresarial después de que se muevan en línea deben configurarse para Skype Empresarial Hybrid funcionalidad de voz.

Para obtener más información sobre las opciones de telefonía en entornos híbridos, incluida una matriz de compatibilidad, consulte [Cuentas de usuario en un entorno híbrido con conectividad RTC](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Otras consideraciones

Las directivas (como, por ejemplo, controlar el comportamiento de la mensajería, las reuniones y las llamadas) en entornos locales y en línea son independientes. Es posible que quiera considerar la posibilidad de configurar las directivas en el entorno y asignarlas al usuario antes de mover ese usuario del entorno local a la nube, de modo que tenga la configuración correcta en cuanto se migre a en línea.

## <a name="see-also"></a>Vea también

[Mover usuarios locales a Microsoft Teams](move-users-from-on-premises-to-teams.md)

[Configuración del servicio de migración de reuniones (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planear el enrutamiento directo](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
