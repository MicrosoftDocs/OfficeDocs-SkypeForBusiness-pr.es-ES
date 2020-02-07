---
title: Lista de comprobación para el acceso de invitado de Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de comprobación para ayudarle a configurar el acceso de invitado en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b60b0e5f0972d862ec1b945f1b267b04faae9a8a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833260"
---
<a name="microsoft-teams-guest-access-checklist"></a>Lista de comprobación para el acceso de invitado de Microsoft Teams
==========================================

Use esta lista de comprobación para que le resulte más fácil activar y configurar el acceso de invitado en Microsoft Teams. Debe ser administrador global o administrador de Teams para poder realizar estos cambios.

> [!IMPORTANT]
> Es posible que tenga que esperar hasta 24 horas para que los cambios surtan efecto. 

Vea este vídeo breve (5:31 minutos) para obtener información sobre cómo activar el acceso de invitados en Microsoft 365, incluidos los equipos.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a>Paso 1: activar el acceso de invitados en el nivel de toda la organización de los equipos

Para activar el acceso de invitados, vaya al **centro de administración de Microsoft Teams**. 

1. En el centro de administración de Teams, seleccione**acceso de invitado a** **toda** > la organización.
2. Establezca la opción **permitir acceso de invitado en Microsoft Teams** **.**

    ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. En esta misma página, Active o desactive las opciones de **llamada**, **reunión**y **Mensajería** de los invitados.
4. Haga clic en **Guardar **.

> [!TIP]
> Si está usando la configuración predeterminada en Azure Active Directory, SharePoint Online y grupos de Office 365, es posible que haya terminado de configurar el acceso de invitado. En este caso, puede omitir el resto de los pasos. Si no está seguro, o si está usando una configuración personalizada para los grupos de AAD, SharePoint Online u Office 365, continúe con el resto de los pasos de esta lista de comprobación.

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a>Paso 2: configurar las opciones de empresa a empresa de Azure AD

Estas son las opciones de configuración de Azure AD que admiten el acceso de invitado en Teams. Una vez configurada esta configuración, podrá [Agregar](add-guests.md) y [administrar invitados](manage-guests.md) en Teams.

1. Inicie sesión en el [portal de Azure](https://portal.azure.com) como administrador de inquilinos.
2. Seleccione**configuración de usuario**de**usuarios** > de **Azure Active Directory** > .
3. En **usuarios externos**, seleccione **administrar la configuración de colaboración externa**.
   > [!NOTE]
   > La **configuración de colaboración externa** también está disponible en la página relaciones de la **organización** . En Azure Active Directory, en **administrar**, vaya a > **configuración**de **relaciones organizativas**.
4. En la página **configuración de colaboración externa** , elija las directivas que quiera habilitar.

    - **Los permisos de los usuarios invitados son limitados**: esta Directiva determina los permisos para los invitados de su directorio. Seleccione **sí** para bloquear a los invitados de determinadas tareas de directorio, como la enumeración de usuarios, grupos u otros recursos de directorio. Seleccione **no** para proporcionar a los invitados el mismo acceso a los datos de directorio que los usuarios habituales de su directorio.
     - **Los administradores y usuarios del rol invitado invitar pueden invitar**: para permitir que los administradores y los usuarios del rol "invitado invitar" puedan invitar a invitados, establezca esta directiva en **sí**.
     - **Los miembros pueden invitar**: para permitir que los miembros de su directorio que no sean administradores inviten a otros usuarios, establezca esta directiva en **Sí** (recomendado). Si prefiere que solo los administradores puedan agregar invitados, puede establecer esta directiva en **No**. Tenga en cuenta que, al establecer **No**, se limitará la experiencia de invitado para los propietarios de equipos que no sean administradores. Solo podrán agregar invitados a los equipos que el administrador ya haya agregado en AAD.
     - Los **invitados pueden invitar**: para permitir que los invitados inviten a otros invitados, establezca esta directiva en **sí**.
         > [!IMPORTANT]
         > Actualmente, Teams no permite el rol de invitador de usuarios invitados, por lo que, aunque configure **Los miembros pueden invitar** como **Sí**, los invitados no pueden invitar a otros invitados en Teams.
     - **Habilitar el código de acceso de un solo uso de correo electrónico para invitados (vista previa)**: para obtener más información sobre la característica de código de acceso de un solo uso, consulte [autenticación de código de acceso de un solo uso de correo electrónico (vista previa)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)
     - **Restricciones de colaboración**: para obtener más información sobre cómo permitir o bloquear invitaciones a dominios específicos, consulte [permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
        > [!NOTE]
        > Para obtener las restricciones de colaboración, consulte [Habilitar la colaboración externa B2B y administrar quién puede invitar a invitados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).
      
    Para obtener más información acerca de cómo controlar quién puede invitar a invitados, consulte [Delegar invitaciones para la colaboración de Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).

## <a name="step-3-configure-office-365-groups"></a>Paso 3: configurar grupos de Office 365

1. En el centro de administración de Microsoft 365, **vaya a** > configuración**configuración**, haga clic en **servicios**y, a continuación, seleccione **grupos de Office 365**.

     ![Captura de pantalla que muestra la configuración de grupos de Office 365](media/guest-access-checklist-services-settings.png)
2. Asegúrese de que la casilla permitir que los **miembros del grupo fuera de la organización tengan activada la casilla contenido del grupo de acceso** . Si esta opción no está seleccionada, los invitados no podrán acceder a ningún contenido de grupo.

    ![Captura de pantalla que muestra la configuración de grupos de Office 365](media/guest-access-checklist-office365.png)
3. Asegúrese de que la casilla permitir que los **propietarios del grupo agreguen personas fuera de la organización a los grupos** estén activadas. Si esta opción no está seleccionada, los propietarios del equipo no podrán agregar invitados nuevos. Como mínimo, esta configuración debe estar activada para que sea compatible con el acceso de invitados.

Para obtener instrucciones detalladas sobre cómo configurar estas opciones, consulte [administrar el acceso de invitados en office 365 grupos](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) y [controlar el acceso de invitados en los grupos de Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).

## <a name="step-4-configure-sharing-in-office-365"></a>Paso 4: configurar el uso compartido en Office 365 

Asegúrese de que los usuarios pueden agregar invitados. Aquí le mostramos cómo hacerlo:

1. En el centro de administración de Microsoft 365, **vaya a** > configuración**Settings**, haga clic en **seguridad & privacidad**y, después, seleccione **uso compartido**.

     ![Captura de pantalla que muestra un ejemplo de configuración de servicios](media/guest-access-checklist-security-privacy-settings.png)
 
2. Active la casilla **permitir que los usuarios agreguen nuevos invitados a la organización** y, a continuación, haga clic en **Guardar cambios**.

     ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de uso compartido](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > Esta opción es equivalente a la opción los **miembros pueden invitar** en **configuración** > de usuario**usuarios externos** en Azure ad.  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>Paso 5: comprobar la configuración de uso compartido en SharePoint

1. Inicie sesión en el centro de administración de Microsoft 365.
2. En **centros de administración**, seleccione **SharePoint**.
3. En el nuevo centro de administración de SharePoint, en **sitios**, seleccione **sitios activos**.

    ![Sitios activos en el centro de administración de SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. Seleccione el sitio y, a continuación, haga clic en **compartir**.
4. Asegúrese de que la opción está establecida en **cualquiera** o en **invitados nuevos o existentes**.

     ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a>Paso 6: configurar permisos de usuario invitados

En la aplicación de Teams, en el nivel de equipo individual, configure los permisos de invitado que controlan si los invitados pueden crear, actualizar o eliminar canales. Los administradores de equipos y los propietarios de equipo pueden configurar esta configuración.

![Captura de pantalla que muestra un ejemplo de alternancia de configuración de un equipo o un canal](media/guest-access-checklist-TeamsSettings2.png)

Para obtener más información sobre el acceso de invitados, consulte [acceso de invitados en Teams](guest-access.md) y [activar o desactivar el acceso de invitados a Microsoft Teams](set-up-guests.md).

## <a name="troubleshooting"></a>Solución de problemas

Si tiene problemas para configurar el acceso de invitados o agregar invitados en Teams, use estos recursos para ayudarle:

[Solución de problemas con el acceso de invitado en Microsoft Teams](troubleshoot-guest-access.md)

[Solución de problemas de equipos](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
