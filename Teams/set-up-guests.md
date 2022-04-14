---
title: Activar o desactivar el acceso de invitado en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
ms.localizationpriority: medium
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Obtenga más información sobre cómo habilitar o deshabilitar el acceso de invitado en Microsoft Teams como administrador de Office 365.
ms.openlocfilehash: 1658ef97dd172209a965088caa2842a71e09e4e7
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "64839201"
---
# <a name="turn-guest-access-in-microsoft-teams-on-or-off"></a>Activar o desactivar el acceso de invitado en Microsoft Teams

En este artículo se describe cómo configurar las opciones de acceso de invitado (incluidas llamadas, reuniones y chat) en Teams. El acceso de invitado en Teams también requiere configurar otras opciones en Microsoft 365, incluidas las opciones de Azure AD, Grupos de Microsoft 365 y SharePoint. Si quiere empezar a invitar a usuarios a los equipos, elija una de las siguientes opciones:

- Para configurar el acceso de invitado para Microsoft Teams para un uso general, consulte [Colaborar con invitados en un equipo](/microsoft-365/solutions/collaborate-as-team).
- Para colaborar con una organización asociada que usa Azure Active Directory y permitir que los invitados se inscriban a sí mismos para tener acceso al equipo, consulte [Crear una extranet de B2B con invitados administrados](/microsoft-365/solutions/b2b-extranet).

> [!NOTE]
> Si solo quiere buscar, llamar, chatear y configurar reuniones con personas de otras organizaciones, use el [acceso externo](manage-external-access.md).

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Configurar el acceso de invitado en el centro de administración de Teams

1. Inicie sesión en el [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/).

2. Seleccione **UsuariosGuest** >  Access.

3. Establezca **Permitir el acceso de invitado en Teams** en **Activado**.

    ![Permitir el acceso de invitado establecido en Activado.](media/guest-access-setting.png)

4. En **Llamadas**, **Reuniones** y **Mensajes**, seleccione **Activado** o **Desactivado** para cada funcionalidad, dependiendo de lo que quiera permitir para invitados.

      - **Realizar llamadas privadas**: cambie esta opción a **Activado** para permitir que los invitados realicen llamadas entre compañeros.
      - **Vídeo IP** : active **esta configuración para** permitir que los invitados usen vídeo en sus llamadas y reuniones.
      - **Modo de uso compartido** de pantalla: esta configuración controla la disponibilidad del uso compartido de la pantalla para los invitados.
          - Establezca esta opción como **Desactivado** para eliminar la posibilidad de que los invitados compartan sus pantallas en Teams.
          - Establezca esta opción como **Solicitud única** para permitir el uso compartido de aplicaciones individuales.
          - Establezca esta opción como **Pantalla completa** para permitir el uso de pantalla completa compartida.
      - **Reunirse ahora**: active **esta configuración para** permitir que los invitados usen la característica Reunirse ahora en Microsoft Teams.
      - **Editar mensajes enviados**: establezca esta opción como **Activado** para permitir que los invitados editen los mensajes que han enviado anteriormente.
      - **Eliminar mensajes enviados** : active **esta opción para** permitir que los invitados eliminen los mensajes enviados anteriormente.
      - **Chat**: establezca esta opción como **Activado** para permitir a los invitados usar el chat en Teams.
      - **Giphy en conversaciones** : active **esta opción para** permitir que los invitados usen Giphy en las conversaciones. Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados. A cada Giphy se le asigna una clasificación de contenido.
      - **Clasificación de contenido Giphy**: seleccione una clasificación de la lista desplegable:
          - **Permitir todo el contenido**: los invitados podrán insertar todos los Giphy en chats, independientemente de la clasificación de contenido.
          - **Moderado**: los invitados pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma moderada.
          - **Estricto** : los invitados pueden insertar imágenes de Giphy en chats, pero se restringirá la inserción de contenido para adultos.
      - **Memes en conversaciones** : active **esta configuración para** permitir que los invitados usen Memes en las conversaciones.
      - **Adhesivos en conversaciones** : active **esta configuración para** permitir que los invitados usen adhesivos en las conversaciones.
      - **Lector inmersivo para mensajes**: active **esta configuración para** permitir que los invitados usen el [lector inmersivo en Teams](https://support.microsoft.com/topic/a700c0d0-bc53-4696-a94d-4fbc86ac7a9a).

    ![Configuración de permisos de invitado en Teams.](media/manage-guest-access-image1.png)

5. Seleccione **Guardar**.

## <a name="turning-guest-access-off"></a>Desactivar el acceso de invitado

Si desactiva el acceso de invitado en Teams, los invitados existentes perderán el acceso a su equipo. Sin embargo, no se quitan del equipo. Siguen siendo visibles para las personas del equipo y estas los pueden @mencionar. Si vuelve a activar el acceso de invitado de Teams, recuperarán el acceso.

Si tiene previsto dejar el acceso de invitado desactivado, puede aconsejar a los propietarios de su equipo que quiten manualmente las cuentas de invitado de sus equipos. Aunque estos invitados no tendrán acceso, si mantiene sus cuentas visibles en el equipo, esto podría provocar confusión para otras personas del equipo.


## <a name="see-also"></a>Vea también

[Configurar la colaboración moderna con Microsoft 365](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[Bloquear invitados de un equipo específico](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)
