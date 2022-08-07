---
title: Administrar la configuración de Skype for Business en el Centro de administración de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración de las características de Skype for Business en el Centro de administración de Microsoft Teams.
ms.openlocfilehash: 26b2ba51d42a7be227b513d72add3e34f07d0fcd
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269765"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Administrar la configuración de Skype for Business en el Centro de administración de Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Como administrador, el Centro de administración de Microsoft Teams es donde puede administrar las características de Skype for Business para los usuarios de Skype for Business de su organización. Puede administrar la configuración [de su organización](#manage-skype-for-business-settings-for-your-organization) en la página **de Skype for Business** y la configuración [de usuarios individuales](#manage-skype-for-business-settings-for-individual-users) en la pestaña **Skype for Business** de las páginas de detalles de usuario.

Solo verá la página **de Skype for Business** si el modo de coexistencia para su organización no está establecido **solo en Teams**. De forma similar, solo verá la pestaña **Skype for Business** de un usuario si el modo de coexistencia del usuario no es **solo Teams**. Para obtener más información sobre los modos de coexistencia, vea [Comprender Teams y Skype for Business coexistencia e interoperabilidad](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y [Establecer la configuración de coexistencia y actualización](setting-your-coexistence-and-upgrade-settings.md).

> [!NOTE]
> Skype for Business anteriormente se encontraban en el **portal heredado** del Centro de administración de Microsoft Teams. Con la retirada del portal heredado, hemos migrado la configuración a estas nuevas ubicaciones en el Centro de administración de Teams para la administración de Skype for Business.

Debe tener asignado el rol de administrador global de [Azure AD](/azure/active-directory/roles/permissions-reference) o administrador de Skype for Business para administrar las características de Skype for Business en el Centro de administración de Microsoft Teams.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Administrar la configuración de Skype for Business de su organización

En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Configuración** >  de toda la organización **Skype for Business**. Desde aquí, puede configurar y administrar Reunión de Skype difusión, la privacidad de presencia y las notificaciones del dispositivo móvil para todos los usuarios Skype for Business de su organización.

### <a name="skype-meeting-broadcast"></a>Difusión de reunión de Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Use la siguiente configuración para administrar [Reunión de Skype Difusión](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) en su organización.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Captura de pantalla de Reunión de Skype configuración de Difusión en el centro de administración.":::

- **Reunión de Skype difusiones**: active esta opción para habilitar Reunión de Skype Difusión para su organización. Después de habilitar esta característica, debe [configurar la red para Reunión de Skype Difusión](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).
- **Consulta las características de vista previa**: actívalo para obtener acceso anticipado a nuevas características.
- **Los organizadores pueden programar reuniones anónimas**: active esta opción si quiere permitir que los organizadores creen eventos de difusión que permitan a cualquier persona de fuera de la organización unirse sin tener que iniciar sesión. 
- **Grabar Reunión de Skype Difundir reuniones**: active esta opción para permitir que los organizadores y moderadores graben reuniones.  
- **Dirección URL del departamento de soporte técnico para los asistentes**: escriba la dirección URL de soporte técnico de su organización que los asistentes a la reunión pueden usar si necesitan ayuda durante una reunión.

### <a name="presence-and-mobile-notifications"></a>Notificaciones de presencia y móvil

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Use la siguiente configuración para administrar Skype for Business privacidad de presencia y notificaciones móviles en su organización.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Captura de pantalla de la configuración de presencia en el centro de administración.":::

#### <a name="presence"></a>Presence

De forma predeterminada, Skype for Business usuarios de su organización pueden ver el estado de presencia (como Disponible, Ocupado o Ausente) de otros usuarios de Skype for Business. Elija una de las siguientes opciones para establecer quién puede ver la presencia de los usuarios de Skype for Business.

- **Mostrar automáticamente la información de presencia**: cualquier usuario Skype for Business de la organización que no se haya agregado a la lista **de usuarios externos** o **bloqueados** puede ver la presencia de ese usuario.
- **Mostrar información de presencia solo a los contactos de un usuario**: cualquier usuario Skype for Business de la lista de contactos del usuario que no se agregue a su lista **de usuarios externos** o **bloqueados** puede ver la presencia de ese usuario. Los usuarios pueden invalidar esta configuración en Skype for Business yendo a **Opciones** de **herramientas** >  **de configuración** > .

#### <a name="mobile-notifications"></a>Notificaciones móviles

Puede establecer si sus Skype for Business usuarios móviles reciben alertas sobre mensajes instantáneos entrantes y perdidos, mensajes de correo de voz y llamadas perdidas a través de un servicio de notificaciones push. En función de los dispositivos móviles que se usen en su organización, puede usar el **Servicio de notificaciones push de Microsoft**, el **Servicio de notificaciones de inserción de Apple** o ambos.

Tenga en cuenta lo siguiente:

- Si desactiva las notificaciones push, los usuarios recibirán todas las alertas la próxima vez que inicien Skype for Business en su dispositivo móvil.
- De forma predeterminada, las notificaciones push están activadas. Los usuarios individuales pueden desactivarlos en Skype for Business en su dispositivo móvil.
- Si desactiva las notificaciones de inserción, los usuarios no podrán volver a activarlas. 

> [!IMPORTANT]
> Microsoft usa otras empresas que proporcionan notificaciones móviles para Skype Empresarial en tiempo real para usuarios de Windows Phone, iPhone y iPad. Consulte esta [Declaración de privacidad](https://go.microsoft.com/fwlink/p/?linkid=247732).

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Administrar la configuración de Skype for Business para usuarios individuales

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Para administrar Skype for Business configuración para usuarios individuales, en el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Usuarios**, haga clic en el nombre para mostrar del usuario para abrir la página de detalles del usuario y, a continuación, seleccione la pestaña **configuración de Skype for Business**. Desde aquí, puede configurar las opciones de acceso externo y reunión para el usuario.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Captura de pantalla de Skype for Business pestaña en la página de detalles del usuario.":::

### <a name="external-access-settings"></a>Configuración de acceso externo

Puede permitir o bloquear selectivamente si un usuario puede comunicarse con personas de fuera de su organización.

- **Usuarios Skype for Business externos**: active esta opción si desea permitir que el usuario se comunique con Skype for Business usuarios en dominios federados.
- **Usuarios externos de Skype**: active esta opción si desea permitir que el usuario se comunique con los usuarios de Skype. 

### <a name="meeting-settings"></a>Configuración de las reuniones

Puede configurar las siguientes opciones de reunión para el usuario.

- **Vídeo de & de** audio: Elija una de las siguientes opciones de configuración de audio y vídeo:

    - **Ninguno**: el usuario no puede usar audio o vídeo.
    - **Solo audio**: el usuario puede usar el audio, pero no el vídeo.
    - **Audio y vídeo**: el usuario puede usar audio y vídeo.
    - **Audio y vídeo (HD):** el usuario puede usar audio y vídeo de alta definición.
    
- **Grabar conversaciones & reuniones**: active esta opción para permitir al usuario grabar conversaciones y reuniones.
- **Cumplimiento** normativo: active esta opción si se le exige legalmente conservar la información almacenada electrónicamente.