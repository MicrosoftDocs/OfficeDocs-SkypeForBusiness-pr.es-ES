---
title: Mover usuarios entre local y la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumen: En una implementación local de Skype para servidor empresarial que está habilitado para la implementación híbrida, puede mover usuarios entre el entorno local y la nube (si va a Skype para profesionales en línea o Microsoft Teams)..'
ms.openlocfilehash: 492a2a7d14af77bc0b90afe03f0d36de0f830129
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247736"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover usuarios entre local y la nube

En una implementación local de Skype para servidor empresarial que está habilitado para la implementación híbrida, puede mover usuarios entre el entorno local y la nube (si va a Microsoft Teams o Skype para profesionales en línea). Si se encuentra un usuario local o en la nube se conoce como Skype del usuario para la página principal de Business:

- Los usuarios que están hospedados en local interactúan con Skype local para servidores empresariales.
- Los usuarios que están hospedados en línea pueden interactuar con Skype para servicios en línea de negocio.

*Los usuarios de los equipos tienen inherente un Skype para la página principal de Business, si usar Skype para la empresa o no.* Si dispone de Skype local para los usuarios de negocios que también está usando los equipos (en paralelo), los usuarios están hospedados en local. Los usuarios de los equipos con Skype para la empresa local no tienen la capacidad para interoperar con Skype para los usuarios de negocio de su cliente de los equipos, ni pueden se comunican desde los equipos de los usuarios de una organización federada. Esta funcionalidad sólo está disponible después de que el usuario se mueve de Skype para la empresa local a en línea. Cuando un usuario se mueve a online, se pueden permitir que puedan utilizar Skype para profesionales en línea (y, opcionalmente, los equipos) o puede realizar únicamente los equipos. Si su organización ya usa los equipos, se recomienda encarecidamente que se mueva al modo sólo los equipos, lo que asegura que el enrutamiento de todos los chats entrantes y las llamadas aterriza en su cliente de los equipos. Para obtener más detalles, vea [coexistencia de los equipos con Skype para la empresa](/microsoftteams/coexistence-chat-calls-presence) y [migración e instrucciones de interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Requisitos previos

Requisitos previos para mover un usuario a la nube (si se Skype para el modo sólo de negocio o los equipos sólo):

- La organización debe tener Azure Connect AD configurado correctamente y se está sincronizando los todos los atributos relevantes para el usuario tal y como se describe en [Configurar Azure AD conectarse](configure-azure-ad-connect.md).
- Skype para entornos híbridos de negocio debe configurarse como se describe en [Configurar Skype para entornos híbridos de negocio](configure-federation-with-skype-for-business-online.md).
- El usuario debe estar asignado una licencia de Skype para profesionales Online (Plan 2) y, si se van a usar los equipos, también debe tener una licencia de los equipos.  Además:
    - Si el usuario está habilitado para las conferencias de acceso telefónico en local, de forma predeterminada, que el usuario también debe tener una licencia de conferencias de Audio asignada en Office 365 antes de ejecutar mover el usuario en línea. Una vez que se migran a la nube, el usuario se aprovisionará para conferencias de audio en la nube. Si por algún motivo que desea mover a un usuario a la nube, pero no usar la funcionalidad de conferencia de audio, se puede invalidar esta comprobación mediante la especificación de la `BypassAudioConferencingCheck` parámetro en `Move-CsUser`.
    - Si el usuario está habilitado para Enterprise Voice en local, de forma predeterminada el usuario debe tener una licencia de sistema telefónico asignada en Office 365 antes de mover el usuario en línea. Una vez migrados a la nube, el usuario se aprovisionará para el sistema telefónico en la nube. Si por algún motivo que desea mover a un usuario a la nube, pero no use la funcionalidad del sistema de teléfono, puede invalidar esta comprobación mediante la especificación de la `BypassEnterpriseVoiceCheck`parámetro en `Move-CsUser`.


## <a name="moving-users"></a>Mover a los usuarios

Cuando un usuario se mueve de local a la nube:

- El usuario comienza a usar Skype para servicios en línea de negocio en la nube para cualquier Skype para la funcionalidad empresarial.
- Los usuarios de los equipos se convierten en habilitado para la interoperabilidad con Skype para usuarios profesionales y también pueden federarse con otras organizaciones.
- Los contactos de en local se mueven a la nube en (Skype para la empresa) o en los equipos.
- Reuniones existentes que organizados que están programadas en el futuro se migran a en línea. Migración de las reuniones se realiza de forma asincrónica y empieza aproximadamente 90 minutos después de mover el usuario.  Para determinar el estado de la migración de la reunión, puede usar [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Tenga en cuenta que no se mueve cualquier contenido que se cargó antes de la reunión.

Para mover usuarios entre en local y la nube (si va a los equipos o Skype para profesionales en línea), use el cmdlet Move-CsUser o el Skype para el Panel de Control de administración empresarial, que son herramientas local. Estas herramientas admiten tres rutas de acceso de movimiento diferentes:

- [De Skype para Business Server (local) para Skype para profesionales en línea](move-users-from-on-premises-to-skype-for-business-online.md).
- [De Skype para Business Server (local) directamente a los equipos sólo](move-users-from-on-premises-to-teams.md) (que también los mueve a Skype para profesionales en línea).  La opción para mover directamente desde local a los equipos sólo está disponible en Skype para Business Server 2019, así como 8 de actualización acumulativa de Skype para Business Server 2015. Las organizaciones que utilizan versiones anteriores de Skype para Business Server pueden mover usuarios a los equipos sólo moverlos primero a Skype para profesionales en línea y, a continuación, aplicando el modo de TeamsOnly a estos usuarios una vez que estén en línea.
- [De online (si los equipos sólo o no), a local](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Credenciales administrativas necesarias

Para mover usuarios entre local y la nube, debe usar una cuenta con privilegios suficientes en ambos el Skype local para el entorno de Business Server así como en el inquilino de Office 365. Puede usar una cuenta que tiene todos los privilegios necesarios, o puede usar dos cuentas, en cuyo caso se tiene acceso a las herramientas de local con credenciales local y, a continuación, en dichas herramientas podría proporcionar credenciales adicionales para un Office 365 cuenta administrativa.  

- En el entorno local, el usuario que realiza el movimiento debe tener el rol de CSServerAdminstrator de Skype para Business Server.
- En Office 365, el usuario que realiza el movimiento debe ser un administrador Global o debe tener ambos Skype para roles de administrador empresarial y Administrador de usuarios.  

    > [!Important]
    > - Si está utilizando la Skype para el Panel de Control de administración empresarial, se le pedirá que proporcione credenciales de una cuenta de Office 365 con los roles correspondientes, como se ha indicado anteriormente. Debe proporcionar una cuenta que termina en. onmicrosoft.com. Si eso no es posible, a continuación, use el cmdlet Move-CsUser.
    >- Si está utilizando Move-CsUser en PowerShell, puede utilizar ya sea una cuenta que termina en. onmicrosoft.com, o se puede usar cualquier cuenta local que se sincroniza en Azure AD, siempre que también especificar el parámetro HostedMigrationOverrideUrl en el cmdlet . El valor de la dirección URL de reemplazo de migración hospedado es una variante de la siguiente dirección URL:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>En la dirección URL anterior, reemplace el XX con dos o tres caracteres, determinados como sigue:
    >   - En un Skype para la sesión de PowerShell en línea de negocio, ejecute el siguiente cmdlet:<br>`Get-CsTenant|ft identity`
    >    - El valor resultante estará en el siguiente formato:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - El código de dos o tres dígitos es el XX contenido en la sección, DC = lyncXX001. Si es un código de dos caracteres, será un dígito seguido de un número (por ejemplo, 0a). Si es un código de tres caracteres, será de dos letras seguidas por un dígito (por ejemplo, jp1). En todos los casos, verá 001 inmediatamente después del código XX.


## <a name="voice-configuration-requirements"></a>Requisitos de configuración de voz

Si los usuarios están configurados para enterprise voice en local, debe actualizar su configuración de voz al moverlos a en línea o, como alternativa, puede migrar sin funciones de telefonía de coordenadas. Las opciones disponibles dependen de si el usuario va a utilizar los equipos o Skype para clientes empresariales una vez que estén en línea:

- Puede actualizar el proveedor de un usuario de telefonía para usar un [Plan de llamada de Microsoft](/microsoftteams/calling-plans-for-office-365). Esta es una opción si los usuarios utilizarán los equipos o Skype para clientes empresariales.
- Se puede seguir usando su proveedor de RTC local:
  - Los usuarios de voz que utilizarán los equipos deben configurarse para [El enrutamiento directo](/microsoftteams/direct-routing-plan). Enrutamiento directo sólo está disponible después de que el usuario se mueve de local a en línea.
  - Los usuarios de voz que usarán el Skype para cliente empresarial después de que se muevan en línea deben configurarse para Skype para la funcionalidad de voz híbrida de negocio.

Para obtener más información acerca de las opciones de telefonía en entornos híbridos, así como una matriz de compatibilidad, vea [cuentas de usuario en un entorno híbrido con conectividad RTC](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Otras consideraciones

Las directivas (como para controlar la mensajería, de la reunión y comportamiento de llamada) en locales y online entornos son independientes. Es posible que desee tener en cuenta la configuración de las directivas en el entorno y la asignación de ellos al usuario antes de mover ese usuario de local a la nube, para que tengan la configuración correcta tan pronto como se migran a online.

## <a name="see-also"></a>Vea también

[Mover usuarios de local a Skype Empresarial Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Mover usuarios de local a los equipos](move-users-from-on-premises-to-teams.md)

[Configuración del servicio de migración de reuniones (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planear el enrutamiento directo](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)