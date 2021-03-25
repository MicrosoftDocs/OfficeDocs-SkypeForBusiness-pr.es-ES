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
ms.openlocfilehash: 6e1052b4f4a0e85d4d18123b3c0a0f051f6065f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117008"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Administrar la configuración de Skype Empresarial en el Centro de administración de Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Como administrador, el Centro de administración de Microsoft Teams es donde administra las características de Skype Empresarial para los usuarios de Skype Empresarial de su organización. Puede administrar la configuración [de](#manage-skype-for-business-settings-for-your-organization) su organización en la página **de Skype** Empresarial y la configuración para usuarios [individuales](#manage-skype-for-business-settings-for-individual-users) en la pestaña **Skype** Empresarial de las páginas de detalles del usuario.

Solo verá la página **de Skype** Empresarial si el modo de coexistencia de su organización no está establecido en **Teams solo.** De forma similar, solo verá la pestaña **Skype** Empresarial para un usuario si el modo de coexistencia del usuario no es **Solo Teams.** Para obtener más información sobre los modos de coexistencia, vea Comprender la coexistencia e interoperabilidad de Teams y [Skype Empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y Establecer la configuración de [coexistencia y actualización.](setting-your-coexistence-and-upgrade-settings.md)

> [!NOTE]
> La configuración de Skype Empresarial se encontraba anteriormente en **el portal** heredado del Centro de administración de Microsoft Teams. Con la retirada del portal heredado, migramos la configuración a estas nuevas ubicaciones en el Centro de administración de Teams para la administración de Skype Empresarial.

Debe tener asignado el rol de administrador de [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global o administrador de Skype Empresarial para administrar las características de Skype Empresarial en el Centro de administración de Microsoft Teams.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Administrar la configuración de Skype Empresarial para su organización

En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Configuración de** toda la organización de  >  **Skype Empresarial.** Desde aquí, puede configurar y administrar la difusión de reuniones de Skype, la privacidad de presencia y las notificaciones de dispositivos móviles para todos los usuarios de Skype Empresarial de su organización.

### <a name="skype-meeting-broadcast"></a>Difusión de reunión de Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Use la siguiente configuración para administrar la [difusión de](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) reunión de Skype en su organización.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Captura de pantalla de la configuración de difusión de reunión de Skype en el centro de administración":::

- **Difusión de reunión de Skype:** active esta opción para habilitar la difusión de reunión de Skype para su organización. Después de habilitar esta característica, debe configurar su red para difusión de reunión [de Skype.](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)
- **Vea características de vista previa:** Active esta opción para obtener acceso anticipado a las nuevas características.
- **Los organizadores pueden** programar reuniones anónimas: active esta opción si quiere permitir que los organizadores creen eventos de difusión que permitan a cualquier persona de fuera de su organización unirse sin tener que iniciar sesión. 
- **Grabar reuniones de difusión de reunión de Skype:** active esta opción para permitir que los organizadores y los presentadores graben reuniones.  
- Dirección URL de soporte técnico para los **asistentes:** escriba la dirección URL de soporte técnico de su organización que los asistentes a la reunión pueden usar si necesitan ayuda durante una reunión.

### <a name="presence-and-mobile-notifications"></a>Notificaciones de presencia y móvil

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Use la siguiente configuración para administrar la privacidad de presencia de Skype Empresarial y las notificaciones móviles en su organización.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Captura de pantalla de la configuración de presencia en el Centro de administración":::

#### <a name="presence"></a>Presence

De forma predeterminada, los usuarios de Skype Empresarial de su organización pueden ver el estado de presencia (como Disponible, Ocupado o Fuera) de otros usuarios de Skype Empresarial. Elija una de las siguientes opciones para establecer quién puede ver la presencia de los usuarios de Skype Empresarial.

- **Mostrar automáticamente la** información de presencia: cualquier usuario de Skype Empresarial de su  organización  que no se haya agregado a la lista de externos o bloqueados del usuario puede ver la presencia de ese usuario.
- **Mostrar la** información de presencia solo a los contactos de un usuario: cualquier usuario de  Skype  Empresarial de la lista de contactos del usuario que no se agrega a su lista de externos o bloqueados puede ver la presencia de ese usuario. Los usuarios pueden invalidar esta configuración en Skype Empresarial yendo a **Opciones de Herramientas**  >  **de**  >  **configuración.**

#### <a name="mobile-notifications"></a>Notificaciones móviles

Puede establecer si los usuarios móviles de Skype Empresarial obtienen alertas sobre mensajes instantáneos entrantes y perdidos, mensajes de correo de voz y llamadas perdidas a través de un servicio de notificaciones push. Según los dispositivos móviles usados en su organización, puede usar el Servicio de notificaciones push de **Microsoft,** el servicio de notificaciones **push de Apple** o ambos.

Tenga en cuenta lo siguiente:

- Si desactivas las notificaciones push, los usuarios recibirán todas las alertas la próxima vez que inicien Skype Empresarial en su dispositivo móvil.
- De forma predeterminada, las notificaciones push están activadas. Los usuarios individuales pueden desactivarlos en Skype Empresarial en su dispositivo móvil.
- Si desactiva las notificaciones de inserción, los usuarios no podrán volver a activarlas. 

> [!IMPORTANT]
> Microsoft usa otras empresas que proporcionan notificaciones móviles para Skype Empresarial en tiempo real para usuarios de Windows Phone, iPhone y iPad. Vea esta [Declaración de privacidad.](https://go.microsoft.com/fwlink/p/?linkid=247732)

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Administrar la configuración de Skype Empresarial para usuarios individuales

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Para administrar la configuración de Skype Empresarial para usuarios individuales, en la navegación izquierda del Centro de administración de Teams, vaya a **Usuarios,** haga clic en el nombre para mostrar del usuario para abrir la página de detalles del usuario y, a continuación, seleccione la pestaña Configuración de **Skype** Empresarial. Desde aquí, puede configurar el acceso externo y la configuración de la reunión para el usuario.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Captura de pantalla de la pestaña Skype Empresarial en la página de detalles del usuario":::

### <a name="external-access-settings"></a>Configuración de acceso externo

Puede permitir o bloquear selectivamente si un usuario puede comunicarse con personas ajenas a su organización.

- **Usuarios externos de Skype Empresarial:** Active esta opción si quiere permitir que el usuario se comunique con usuarios de Skype Empresarial en dominios federados.
- **Usuarios externos de Skype:** Activa esta opción si quieres permitir que el usuario se comunique con los usuarios de Skype. 

### <a name="meeting-settings"></a>Configuración de las reuniones

Puede configurar las siguientes opciones de reunión para el usuario.

- **Audio & vídeo:** elija una de las siguientes opciones de configuración de audio y vídeo:

    - **Ninguno:** el usuario no puede usar audio o vídeo.
    - **Solo audio:** el usuario puede usar audio, pero no vídeo.
    - **Audio y vídeo:** el usuario puede usar audio y vídeo.
    - **Audio y vídeo (HD):** el usuario puede usar audio y vídeo de alta definición.
    
- **Grabar conversaciones & reuniones:** active esta opción para permitir que el usuario grabe conversaciones y reuniones.
- **Cumplimiento:** Active esta opción si se le exige legalmente conservar la información almacenada electrónicamente.