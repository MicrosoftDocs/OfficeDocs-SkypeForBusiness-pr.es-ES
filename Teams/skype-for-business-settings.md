---
title: Administrar la configuración de Skype empresarial en el centro de administración de Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Obtenga información sobre cómo administrar la configuración de las características de Skype empresarial en el centro de administración de Microsoft Teams.
ms.openlocfilehash: 18f1de99964a36485e69a210c71b6350313aa1cb
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753565"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Administrar la configuración de Skype empresarial en el centro de administración de Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Como administrador, el centro de administración de Microsoft Teams es donde administra las características de Skype empresarial para los usuarios de Skype empresarial de su organización. Puede administrar la configuración [de su organización](#manage-skype-for-business-settings-for-your-organization) en la página de **Skype empresarial** y la configuración [de usuarios individuales](#manage-skype-for-business-settings-for-individual-users) en la pestaña **Skype empresarial** de las páginas de detalles del usuario.

Solo verá la página de **Skype empresarial** si el modo de coexistencia de su organización no está establecido como **solo para equipos**. De forma similar, solo verá la pestaña de **Skype empresarial** para un usuario si el modo de coexistencia del usuario no es **solo de Teams**. Para obtener más información sobre los modos de coexistencia, consulte [comprender Teams y la coexistencia y la interoperabilidad de Skype empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y [establecer la coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md).

> [!NOTE]
> La configuración de Skype empresarial se encontraba en el **portal heredado** en el centro de administración de Microsoft Teams. Con la retirada del portal heredado, hemos migrado la configuración a estas nuevas ubicaciones en el centro de administración de Teams para la administración de Skype empresarial.

Debe tener asignado el [rol de administrador de Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de administrador global o administrador de Skype empresarial para administrar las características de Skype empresarial en el centro de administración de Microsoft Teams.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Administrar la configuración de Skype empresarial para su organización

En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **configuración de toda la organización**  >  **Skype empresarial**. Desde aquí, puede configurar y administrar la difusión de reunión de Skype, la privacidad de presencia y las notificaciones de dispositivos móviles para todos los usuarios de Skype empresarial de su organización.

### <a name="skype-meeting-broadcast"></a>Difusión de reunión de Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Use la siguiente configuración para administrar la [difusión de reunión de Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) en su organización.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Captura de pantalla de la configuración de difusión de reunión de Skype en el centro de administración":::

- **Difusiones de reunión de Skype**: Active esta opción para habilitar la difusión de reunión de Skype para su organización. Después de habilitar esta característica, debe [configurar la red para la difusión de reunión de Skype](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).
- **Vea características de vista previa**: Active esta opción para obtener acceso anticipado a las nuevas características.
- Los **organizadores pueden programar reuniones anónimas**: Active esta opción si desea permitir a los organizadores que creen eventos de difusión que permitan a cualquier persona fuera de su organización unirse sin tener que iniciar sesión. 
- **Grabar reuniones de difusión de reunión de Skype**: Active esta opción para permitir a los organizadores y moderadores grabar reuniones.  
- **Dirección URL del Departamento de soporte técnico para los asistentes**: escriba la dirección URL de soporte técnico de la organización que los asistentes pueden usar si necesitan ayuda durante una reunión.

### <a name="presence-and-mobile-notifications"></a>Presencia y notificaciones de telefonía móvil

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Use la siguiente configuración para administrar la privacidad de presencia y las notificaciones móviles de Skype empresarial en su organización.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Captura de pantalla de la configuración de presencia en el centro de administración":::

#### <a name="presence"></a>Presence

De forma predeterminada, los usuarios de Skype empresarial de su organización pueden ver el estado de presencia (por ejemplo, disponible, ocupado o ausente) de otros usuarios de Skype empresarial. Elija una de las opciones siguientes para establecer quién puede ver la presencia de los usuarios de Skype empresarial.

- **Mostrar información de presencia automáticamente**: cualquier usuario de Skype empresarial de su organización que no se haya agregado a la lista **externa** o **bloqueada** del usuario puede ver la presencia de ese usuario.
- **Mostrar información de presencia solo a los contactos de un usuario**: cualquier usuario de Skype empresarial de la lista de contactos del usuario que no se haya agregado a la lista **externa** o **bloqueada** puede ver la presencia de ese usuario. Los usuarios pueden anular esta configuración en Skype empresarial yendo a **configuración**  >  **Tools**  >  **Opciones**de herramientas.

#### <a name="mobile-notifications"></a>Notificaciones de teléfono móvil

Puede establecer si los usuarios móviles de Skype empresarial recibirán alertas sobre mensajes instantáneos entrantes y perdidos, mensajes de voz y llamadas perdidas a través de un servicio de notificaciones Push. Según los dispositivos móviles usados en su organización, puede usar el **servicio de notificaciones de inserción de Microsoft**, el servicio de **notificaciones push de Apple**, o ambos.

Tenga en cuenta lo siguiente:

- Si desactiva las notificaciones de inserción, los usuarios recibirán todas las alertas la próxima vez que inicien Skype empresarial en sus dispositivos móviles.
- De forma predeterminada, las notificaciones de inserción están activadas. Los usuarios individuales pueden desactivarlas en Skype empresarial en sus dispositivos móviles.
- Si desactiva las notificaciones de inserción, los usuarios no podrán volver a activarlas. 

> [!IMPORTANT]
> Microsoft usa otras empresas que proporcionan notificaciones móviles para Skype Empresarial en tiempo real para usuarios de Windows Phone, iPhone y iPad. Consulta esta [declaración de privacidad](https://go.microsoft.com/fwlink/p/?linkid=247732).

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Administrar la configuración de Skype empresarial para usuarios individuales

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Para administrar la configuración de Skype empresarial para usuarios individuales, en la barra de navegación izquierda del centro de administración de Teams, vaya a **usuarios**, haga clic en el nombre para mostrar del usuario para abrir la página de detalles del usuario y, a continuación, seleccione la pestaña **configuración de Skype empresarial** . Desde aquí, puede configurar el acceso externo y la configuración de la reunión para el usuario.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Captura de pantalla de la pestaña de Skype empresarial en la página de detalles del usuario":::

### <a name="external-access-settings"></a>Configuración de acceso externo

Puede permitir o bloquear de forma selectiva la posibilidad de que un usuario se comunique con personas de fuera de su organización.

- **Usuarios externos de Skype empresarial**: Active esta opción si desea permitir que el usuario se comunique con usuarios de Skype empresarial en dominios federados.
- **Usuarios externos de Skype**: activa esta opción si deseas permitir que el usuario se comunique con usuarios de Skype. 

### <a name="meeting-settings"></a>Configuración de la reunión

Puede configurar las siguientes opciones de la reunión para el usuario.

- **Audio & vídeo**: elija una de las siguientes configuraciones de audio y vídeo:

    - **Ninguno**: el usuario no puede usar audio o vídeo.
    - **Solo audio**: el usuario puede usar el audio pero no el vídeo.
    - **Audio y vídeo**: el usuario puede usar el audio y el vídeo.
    - **Audio y vídeo (HD)**: el usuario puede usar el audio y el vídeo de alta definición.
    
- **Grabar conversaciones & reuniones**: Active esta opción para permitir que el usuario grabe conversaciones y reuniones.
- **Cumplimiento**: Active esta opción si tiene la obligación legal de conservar información almacenada electrónicamente. 
