---
title: Administrar Skype Empresarial configuración en el centro Microsoft Teams administración
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
description: Obtenga información sobre cómo administrar la configuración de Skype Empresarial características en el centro Microsoft Teams administración.
ms.openlocfilehash: f05bdd7dfb53e75d5cc83945985dd6b511635d5ab5792afc0291b5349433ae22
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280565"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Administrar Skype Empresarial configuración en el centro Microsoft Teams administración

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Como administrador, el centro Microsoft Teams administración es donde administra Skype Empresarial características de Skype Empresarial usuarios de su organización. Puede administrar la configuración [de](#manage-skype-for-business-settings-for-your-organization) su organización en la página **Skype Empresarial** y la configuración para usuarios [individuales](#manage-skype-for-business-settings-for-individual-users) en la **Skype Empresarial** de las páginas de detalles del usuario.

Solo verá la página de **Skype Empresarial** si el modo de coexistencia de su organización no está establecido en **Teams solo**. De forma similar, solo  verá la pestaña Skype Empresarial para un usuario si el modo de coexistencia del usuario no **Teams solo**. Para obtener más información sobre los modos de coexistencia, vea Comprender Teams y [Skype Empresarial coexistencia](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e interoperabilidad y Establecer la configuración de [coexistencia y actualización.](setting-your-coexistence-and-upgrade-settings.md)

> [!NOTE]
> Skype Empresarial configuración anterior se encontraba en **el portal** heredado del centro de Microsoft Teams administración. Con la retirada del portal heredado, migramos la configuración a estas nuevas ubicaciones en el centro de administración de Teams para Skype Empresarial administración.

Debe tener asignado el rol de administrador de [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global o Skype Empresarial administrador para administrar Skype Empresarial características en el centro Microsoft Teams administración.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Administrar Skype Empresarial configuración de la organización

En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Configuración **de** toda  >  **la organización Skype Empresarial**. Desde aquí, puede configurar y administrar Skype difusión de reunión, privacidad de presencia y notificaciones de dispositivos móviles para todos los Skype Empresarial usuarios de su organización.

### <a name="skype-meeting-broadcast"></a>Difusión de reunión de Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Use la siguiente configuración para administrar Skype [difusión de reunión](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) en su organización.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Captura de pantalla Skype configuración de difusión de reunión en el centro de administración":::

- **Skype difusión de reunión:** active esta opción para habilitar Skype difusión de reunión para su organización. Después de habilitar esta característica, debe configurar su red para Skype [difusión de reunión.](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)
- **Vea características de vista previa:** Active esta opción para obtener acceso anticipado a las nuevas características.
- **Los organizadores pueden** programar reuniones anónimas: active esta opción si quiere permitir que los organizadores creen eventos de difusión que permitan a cualquier persona de fuera de su organización unirse sin tener que iniciar sesión. 
- **Grabar Skype reuniones de difusión de reunión:** active esta opción para permitir que los organizadores y los presentadores graben reuniones.  
- Dirección URL de soporte técnico para los **asistentes:** escriba la dirección URL de soporte técnico de su organización que los asistentes a la reunión pueden usar si necesitan ayuda durante una reunión.

### <a name="presence-and-mobile-notifications"></a>Notificaciones de presencia y móvil

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Use la siguiente configuración para administrar la privacidad Skype Empresarial presencia y las notificaciones móviles en su organización.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Captura de pantalla de la configuración de presencia en el Centro de administración":::

#### <a name="presence"></a>Presence

De forma predeterminada, Skype Empresarial usuarios de su organización pueden ver el estado de presencia (como Disponible, Ocupado o Fuera) de otros Skype Empresarial usuarios. Elija una de las siguientes opciones para establecer quién puede ver la presencia de Skype Empresarial usuarios.

- **Mostrar automáticamente la** información de presencia: cualquier usuario de Skype Empresarial de su organización  que  no se haya agregado a la lista de bloqueados o externos del usuario puede ver la presencia de ese usuario.
- **Mostrar la** información de presencia solo a los contactos de un usuario: cualquier usuario de  Skype Empresarial  en la lista contactos del usuario que no se agrega a su lista de externos o bloqueados puede ver la presencia de ese usuario. Los usuarios pueden invalidar esta configuración en Skype Empresarial yendo a **Configuración**  >  **Opciones de**  >  **herramientas**.

#### <a name="mobile-notifications"></a>Notificaciones móviles

Puede establecer si los usuarios de Skype Empresarial móviles obtienen alertas sobre mensajes instantáneos entrantes y perdidos, mensajes de correo de voz y llamadas perdidas a través de un servicio de notificaciones push. Según los dispositivos móviles usados en su organización, puede usar el Servicio de notificaciones push de **Microsoft,** el servicio de notificaciones **push de Apple** o ambos.

Tenga en cuenta lo siguiente:

- Si desactiva las notificaciones push, los usuarios recibirán todas las alertas la próxima vez que inicien Skype Empresarial en su dispositivo móvil.
- De forma predeterminada, las notificaciones push están activadas. Los usuarios individuales pueden desactivarlos en Skype Empresarial en su dispositivo móvil.
- Si desactiva las notificaciones de inserción, los usuarios no podrán volver a activarlas. 

> [!IMPORTANT]
> Microsoft usa otras empresas que proporcionan notificaciones móviles para Skype Empresarial en tiempo real para usuarios de Windows Phone, iPhone y iPad. Vea esta [Declaración de privacidad.](https://go.microsoft.com/fwlink/p/?linkid=247732)

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Administrar Skype Empresarial configuración para usuarios individuales

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Para administrar la configuración de Skype Empresarial para usuarios individuales, en la navegación izquierda del centro de administración de Teams, vaya a **Usuarios,** haga clic en el nombre para mostrar del usuario para abrir la página de detalles del usuario y, a continuación, seleccione la pestaña **configuración** Skype Empresarial usuario. Desde aquí, puede configurar el acceso externo y la configuración de la reunión para el usuario.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Captura de pantalla de Skype Empresarial pestaña en la página de detalles del usuario":::

### <a name="external-access-settings"></a>Configuración de acceso externo

Puede permitir o bloquear selectivamente si un usuario puede comunicarse con personas ajenas a su organización.

- **Usuarios Skype Empresarial externos:** Active esta opción si desea permitir que el usuario se comunique con Skype Empresarial en dominios federados.
- **Usuarios Skype externos:** Active esta opción si desea permitir que el usuario se comunique con Skype usuarios. 

### <a name="meeting-settings"></a>Configuración de las reuniones

Puede configurar las siguientes opciones de reunión para el usuario.

- **Audio & vídeo:** elija una de las siguientes opciones de configuración de audio y vídeo:

    - **Ninguno:** el usuario no puede usar audio o vídeo.
    - **Solo audio:** el usuario puede usar audio, pero no vídeo.
    - **Audio y vídeo:** el usuario puede usar audio y vídeo.
    - **Audio y vídeo (HD):** el usuario puede usar audio y vídeo de alta definición.
    
- **Grabar conversaciones & reuniones:** active esta opción para permitir que el usuario grabe conversaciones y reuniones.
- **Cumplimiento:** Active esta opción si se le exige legalmente conservar la información almacenada electrónicamente.