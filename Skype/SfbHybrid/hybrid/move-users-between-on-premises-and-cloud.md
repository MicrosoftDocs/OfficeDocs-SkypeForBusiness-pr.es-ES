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
ms.openlocfilehash: ac32c4037cf275d9a6a7545701c1899742d8fd12
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705879"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover usuarios entre la implementación local y la nube

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En una implementación local de Skype Empresarial Server, los usuarios de Skype Empresarial también pueden usar Teams, pero no todas las funciones de Teams están disponibles para dichos usuarios, siempre y cuando estén configurados para usar la implementación de Skype Empresarial Server local. Se dice que estos usuarios están "hospedados" en el entorno local y que cierta funcionalidad de Teams no está disponible mientras estos usuarios están hospedados en el entorno local, por ejemplo:
- Las llamadas federadas y los chats a través del cliente de Teams del usuario con usuarios de otras organizaciones no están disponibles
- Comunicación de interoperabilidad a través del cliente de Teams del usuario con otros usuarios de la organización que usan Skype Empresarial cliente.
- Funcionalidad de llamada RTC (si al usuario se le asigna una licencia del sistema telefónico).

Para obtener una funcionalidad completa de Teams, estos usuarios deben moverse de Skype Empresarial local a la nube, momento en el que el usuario se convierte en TeamsOnly. El acto de mover un usuario del entorno local a la nube establecerá el modo de coexistencia del usuario en TeamsOnly. Una vez que los usuarios se mueven a la nube, son TeamsOnly, lo que significa que todos los chats y llamadas entrantes llegan a su cliente de Teams. Para obtener más información, consulte [Coexistencia de Teams con Skype Empresarial](/microsoftteams/coexistence-chat-calls-presence) y [Guía de migración e interoperabilidad para organizaciones que usan Teams junto con Skype Empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Para mover usuarios de la implementación de Skype Empresarial Server local a la nube, es necesario configurar [Skype Empresarial híbrido](/skypeforbusiness/hybrid/plan-hybrid-connectivity).  Una vez que la implementación está habilitada para la implementación híbrida, puede mover usuarios del entorno local a la nube para convertirlos en TeamsOnly, como se describe a continuación. Si es necesario, también puede mover a los usuarios de TeamsOnly a la implementación local de Skype for Bsuiness. 



## <a name="prerequisites"></a>Requisitos previos

Requisitos previos para mover un usuario al modo TeamsOnly:

- La organización debe tener Azure AD Connect configurado correctamente y estar sincronizando todos los atributos pertinentes para el usuario, como se describe en [Configuración de Azure AD Connect](configure-azure-ad-connect.md).
- Skype Empresarial híbrido debe configurarse, como se describe en [Configurar Skype Empresarial híbrido](configure-federation-with-skype-for-business-online.md).
- Al usuario se le debe asignar una licencia para Teams y Skype Empresarial En línea (plan 2). Incluso después de la retirada de Skype Empresarial Online, la licencia de Skype Empresarial Online sigue siendo necesaria.  Además:
    - Si el usuario está habilitado para las conferencias de acceso telefónico local, el usuario también debe tener una licencia de audioconferencia asignada en Teams antes de mover al usuario en línea. Una vez que se haya migrado a la nube, el usuario se aprovisionará para las conferencias de audio en la nube. 
    - Si el usuario está habilitado para Telefonía IP empresarial en el entorno local, el usuario debe tener una licencia de Teléfono de Teams asignada en Teams antes de mover el usuario en línea. Una vez migrado a la nube, el usuario se aprovisionará para El sistema telefónico en la nube. 
  
A partir del 31 de julio de 2022, para mover usuarios entre una implementación local y la nube, debe usar la siguiente versión mínima de Skype Empresarial Server o Lync Server:

</br>
</br>

|Producto local|Versión mínima necesaria|Compilación mínima necesaria|
|---|---|---|
|Skype Empresarial Server 2019| CU6 |7.0.2046.385|
|Skype Empresarial Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 con revisión 7|5.0.8308.1182|

</br>
</br>

## <a name="moving-users"></a>Traslado de usuarios

Cuando un usuario se traslada del entorno local a la nube:

- El usuario se convierte en un usuario de TeamsOnly, lo que significa que el usuario:
   -  Recibe e inicia todos los chats y llamadas en el cliente de Teams.
   -  Programa todas las reuniones en Teams.
   -  No se pueden iniciar chats ni llamadas, ni programar reuniones en Skype Empresarial.
   -  Puede unirse a Skype Empresarial reuniones que ya tengan o reciban en el futuro. Sin embargo, después de que Microsoft quite la infraestructura de Skype Empresarial Online para un usuario de TeamsOnly determinado, los usuarios de TeamsOnly solo pueden unirse a Skype Empresarial reuniones de forma anónima. A partir de octubre de 2022, los usuarios que se muevan del entorno local a Teams Solo en las organizaciones híbridas ya no se aprovisionarán con la infraestructura de Skype Empresarial Online. Si se invita a estos usuarios a una reunión de Skype Empresarial, tendrían que unirse de forma anónima. Para obtener más información, consulte [Guía para organizaciones con implementaciones locales de Skype Empresarial Server](/MicrosoftTeams/skype-for-business-online-retirement.md#guidance-for-organizations-with-on-premises-deployments-of-skype-for-business-server).

- Los usuarios se habilitan para la interoperabilidad con Skype Empresarial usuarios y también pueden federarse con otras organizaciones.
- Los contactos del entorno local se mueven a Teams.
- Las reuniones existentes que organizaron y que están programadas en el futuro se convierten en reuniones de Teams. La migración de reuniones se produce de forma asíncrona y comienza aproximadamente 90 minutos después de mover el usuario.  Para determinar el estado de la migración de reuniones, puede usar [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). No se mueve ningún contenido que se haya cargado antes de la reunión.
- Los usuarios a los que se les asigna una licencia de Teléfono de Teams pueden acceder a la funcionalidad RTC una vez configurados correctamente.
 
Para mover usuarios a Teams, use el cmdlet Move-CsUser o el Skype Empresarial Administración Panel de control, que son herramientas locales. Estas herramientas admiten las siguientes rutas de acceso de movimiento:

- [De Skype Empresarial Server (local) a Solo Teams](move-users-from-on-premises-to-teams.md).
- [Desde en línea (ya sea solo Teams o no), a local](move-users-from-the-cloud-to-on-premises.md).


> [!NOTE] 
>  El comportamiento para moverse directamente desde el entorno local a Solo Teams es automático, independientemente de qué versión de Skype Empresarial Server o Lync Server se use. Ya no es necesario especificar el `-MoveToTeams` modificador en `Move-CsUser` para mover usuarios directamente del entorno local a TeamsOnly. Anteriormente, si no se especificaba este modificador, los usuarios pasaron de estar hospedados en Skype Empresarial Server local a Skype Empresarial En línea y su modo permaneció sin cambios. Ahora, al mover un usuario del entorno local a la nube con `Move-CsUser`, a los usuarios se les asigna automáticamente el modo TeamsOnly y sus reuniones del entorno local se convierten automáticamente en reuniones de Teams, igual que si se hubiera especificado el `-MoveToTeams` modificador, independientemente de si realmente se especificó el modificador. 


## <a name="required-administrative-credentials"></a>Credenciales administrativas necesarias

Para mover usuarios entre el entorno local y la nube, debe usar una cuenta con privilegios suficientes tanto en el entorno local Skype Empresarial Server como en la organización de Teams. Puede usar una cuenta que tenga todos los privilegios necesarios o puede usar dos cuentas. Si usa dos cuentas, accedería a las herramientas locales mediante credenciales locales y, a continuación, en esas herramientas proporcionaría credenciales adicionales para una cuenta administrativa de Teams.  

- En el entorno local, el usuario que realiza el traslado debe tener los roles CSServerAdministrator, CsUserAdministrator y RTCUniversalUserAdmins en Skype Empresarial Server.
- En Teams, el usuario que realiza el traslado debe ser miembro de al menos uno de los siguientes roles:
  - Rol de administrador global
  - Rol administrador de Teams
  - Skype Empresarial rol de administrador.  

    > [!Important]
    > - Si usa la Skype Empresarial Administración Panel de control, se le pedirá que proporcione las credenciales de una cuenta de Microsoft 365 con los roles adecuados, como se indicó anteriormente. Debe proporcionar una cuenta que termine en .onmicrosoft.com. Si no es posible, use el cmdlet Move-CsUser.
    >- Si usa Move-CsUser en PowerShell, puede usar una cuenta que termine en .onmicrosoft.com o cualquier cuenta local que esté sincronizada con Azure AD, siempre que también especifique el parámetro HostedMigrationOverrideUrl en el cmdlet. El valor de la dirección URL de invalidación de migración hospedada es una variante de la siguiente dirección URL: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>En la dirección URL anterior, reemplace xx por dos o tres caracteres, determinados de la siguiente manera:
    >   - En una sesión de PowerShell de Teams, ejecute el siguiente cmdlet:<br>`Get-CsTenant | ft ServiceInstance`
    >   - El valor resultante tendrá el formato siguiente:<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - El código de dos o tres caracteres es el XX contenido en la sección AAAA-XX-ZZ. Si es un código de dos caracteres, será un dígito seguido de un número (por ejemplo, 4A). Si es un código de tres caracteres, serán dos letras seguidas de un dígito (como JP1). Un ejemplo es NOAM-4A-S7.


## <a name="voice-configuration-requirements"></a>Requisitos de configuración

Si los usuarios están configurados para la voz empresarial en el entorno local, debe coordinar la actualización de su configuración de voz al moverlos a en línea. Como alternativa, podría migrarlos sin funcionalidades de telefonía. 
- Puede actualizar el proveedor de telefonía de un usuario para usar un [plan de llamadas de Microsoft](/microsoftteams/calling-plans-for-office-365). Esta es una opción si los usuarios usarán Teams o Skype Empresarial clientes.
- Puede seguir usando el proveedor RTC local:
  - Los usuarios de voz que usarán Teams deben estar configurados para [el enrutamiento directo](/microsoftteams/direct-routing-plan). El enrutamiento directo solo está disponible después de que el usuario se mueva de local a en línea.

Para obtener más información sobre las opciones de telefonía en entornos híbridos, incluida una matriz de compatibilidad, consulte [Cuentas de usuario en un entorno híbrido con conectividad RTC](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Otras consideraciones

Las directivas (como, por ejemplo, controlar el comportamiento de la mensajería, las reuniones y las llamadas) en entornos locales y en línea son independientes. Es posible que quiera considerar la posibilidad de configurar las directivas en el entorno y asignarlas al usuario antes de mover ese usuario del entorno local a la nube, de modo que tenga la configuración correcta en cuanto se migre a en línea.

## <a name="see-also"></a>Vea también

[Mover usuarios locales a Microsoft Teams](move-users-from-on-premises-to-teams.md)

[Configuración del servicio de migración de reuniones (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planear el enrutamiento directo](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
