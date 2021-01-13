---
title: Administrar la configuración de Skype Empresarial en el Centro de administración de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
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
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración de las características de Skype Empresarial en el Centro de administración de Microsoft Teams.
ms.openlocfilehash: 944a5f8101b8355f4a2cc3e18966e5eb01b94be9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834220"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Administrar la configuración de Skype Empresarial en el Centro de administración de Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Como administrador, el Centro de administración de Microsoft Teams es donde administra las características de Skype Empresarial para los usuarios de Skype Empresarial de su organización. Puede administrar la configuración [de](#manage-skype-for-business-settings-for-your-organization) su organización en la página **Skype** Empresarial y la configuración para usuarios [individuales](#manage-skype-for-business-settings-for-individual-users) en la pestaña **Skype** Empresarial de las páginas de detalles de usuario.

Solo verá la página **de Skype Empresarial** si el modo de coexistencia de su organización no se establece solo en **Teams.** De forma similar, solo verá la pestaña **Skype** Empresarial de un usuario si el modo de coexistencia del usuario no es **Solo Teams.** Para obtener más información sobre los modos de coexistencia, consulte [Comprender la](teams-and-skypeforbusiness-coexistence-and-interoperability.md) coexistencia e interoperabilidad de Teams y Skype Empresarial, y Establecer la configuración de [coexistencia y actualización.](setting-your-coexistence-and-upgrade-settings.md)

> [!NOTE]
> La configuración de Skype Empresarial estaba anteriormente en **el portal heredado** del Centro de administración de Microsoft Teams. Con la retirada del portal heredado, migramos la configuración a estas nuevas ubicaciones en el Centro de administración de Teams para la administración de Skype Empresarial.

Debe tener asignado el rol de administrador de [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de Administrador global o de administrador de Skype Empresarial para poder administrar las características de Skype Empresarial en el Centro de administración de Microsoft Teams.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Administrar la configuración de Skype Empresarial para su organización

En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la configuración de Skype Empresarial **para**  >  **toda la organización.** Desde aquí, puede configurar y administrar las notificaciones de Difusión de reunión de Skype, privacidad de presencia y dispositivos móviles para todos los usuarios de Skype Empresarial de su organización.

### <a name="skype-meeting-broadcast"></a>Difusión de reunión de Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Use las siguientes opciones para administrar la [Difusión de reunión de Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) en su organización.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Captura de pantalla de la configuración de Difusión de reunión de Skype en el centro de administración":::

- **Difusiones de reunión de Skype:** active esta opción para habilitar Difusión de reunión de Skype para su organización. Después de habilitar esta característica, debe configurar la red para Difusión de reunión [de Skype.](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)
- **Ver características de vista** previa: Active esta opción para obtener acceso anticipado a las nuevas características.
- **Los organizadores pueden** programar reuniones anónimas: active esta opción si quiere permitir a los organizadores crear eventos de difusión que permitan a cualquier persona de fuera de su organización unirse sin tener que iniciar sesión. 
- **Grabar reuniones de Difusión de reunión de Skype:** active esta opción para permitir que los organizadores y presentadores graben reuniones.  
- Dirección URL del departamento de soporte técnico para los **asistentes:** escriba la dirección URL de soporte técnico de su organización que los asistentes a la reunión pueden usar si necesitan ayuda durante una reunión.

### <a name="presence-and-mobile-notifications"></a>Notificaciones de presencia y de móvil

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Use las siguientes opciones para administrar la privacidad de presencia de Skype Empresarial y las notificaciones móviles en su organización.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Captura de pantalla de la configuración de presencia en el centro de administración":::

#### <a name="presence"></a>Presence

De forma predeterminada, los usuarios de Skype Empresarial de su organización pueden ver el estado de presencia (como Disponible, Ocupado o No disponible) de otros usuarios de Skype Empresarial. Elija una de las siguientes opciones para establecer quién puede ver la presencia de sus usuarios de Skype Empresarial.

- **Mostrar automáticamente** la información de presencia: cualquier usuario de Skype Empresarial de su  organización  que no se haya agregado a la lista de bloqueados o externos del usuario puede ver su presencia.
- **Mostrar la** información de presencia solo a los contactos de un usuario: cualquier usuario de  Skype  Empresarial que no se agrega a su lista De contactos externos o Bloqueados puede ver la presencia de ese usuario. Los usuarios pueden invalidar esta configuración en Skype Empresarial en Opciones **de**  >  **herramientas de**  >  **configuración.**

#### <a name="mobile-notifications"></a>Notificaciones móviles

Puede establecer si los usuarios móviles de Skype Empresarial pueden recibir alertas sobre mensajes instantáneos entrantes y perdidos, mensajes de correo de voz y llamadas perdidas a través de un servicio de notificación de inserción. Según los dispositivos móviles usados en su organización, puede usar el Servicio de notificaciones de inserción de **Microsoft,** el Servicio de notificaciones push **de Apple** o ambos.

Tenga en cuenta lo siguiente:

- Si desactiva las notificaciones de inserción, los usuarios recibirán todas las alertas la próxima vez que inicien Skype Empresarial en su dispositivo móvil.
- De forma predeterminada, las notificaciones push están activadas. Los usuarios individuales pueden desactivarlas en Skype Empresarial en sus dispositivos móviles.
- Si desactiva las notificaciones de inserción, los usuarios no podrán volver a activarlas. 

> [!IMPORTANT]
> Microsoft usa otras empresas que proporcionan notificaciones móviles para Skype Empresarial en tiempo real para usuarios de Windows Phone, iPhone y iPad. Consulte esta declaración [de privacidad.](https://go.microsoft.com/fwlink/p/?linkid=247732)

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Administrar la configuración de Skype Empresarial para usuarios individuales

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Para administrar la configuración de Skype Empresarial para usuarios individuales, en el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Usuarios,** haga clic en el nombre para mostrar del usuario para abrir la página de detalles del usuario y, a continuación, seleccione la pestaña de configuración de **Skype** Empresarial. Desde aquí, puede configurar las opciones de acceso externo y reunión para el usuario.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Captura de pantalla de la pestaña Skype Empresarial en la página de detalles del usuario":::

### <a name="external-access-settings"></a>Configuración de acceso externo

Puede permitir o bloquear de forma selectiva si un usuario puede comunicarse con personas fuera de su organización.

- **Usuarios externos de Skype** Empresarial: active esta opción si desea permitir que el usuario se comunique con usuarios de Skype Empresarial en dominios federados.
- **Usuarios externos de Skype:** active esta opción si desea permitir que el usuario se comunique con otros usuarios de Skype. 

### <a name="meeting-settings"></a>Configuración de las reuniones

Puede configurar las siguientes opciones de reunión para el usuario.

- **Vídeo &** audio: elija una de las siguientes opciones de configuración de audio y vídeo:

    - **Ninguna:** el usuario no puede usar audio o vídeo.
    - **Solo audio:** el usuario puede usar el audio, pero no el vídeo.
    - **Audio y vídeo:** el usuario puede usar audio y vídeo.
    - **Audio y vídeo (HD):** el usuario puede usar audio y vídeo de alta definición.
    
- **Grabar conversaciones & reuniones:** active esta opción para permitir al usuario grabar conversaciones y reuniones.
- **Cumplimiento:** active esta opción si se le exige legalmente que conserve la información almacenada de forma electrónica. 
