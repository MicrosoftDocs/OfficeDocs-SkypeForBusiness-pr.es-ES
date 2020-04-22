---
title: Lista de control de acceso de invitados de Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Usa esta lista para ayudar a configurar el acceso de invitados en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 22a0c2a8641203e764d6c490a008525cf71e8d5c
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776955"
---
<a name="microsoft-teams-guest-access-checklist"></a>Lista de control de acceso de invitados de Microsoft Teams
=========================================

Use esta lista para ayudarse a activar y configurar el acceso de invitados en Microsoft Teams. Es necesario ser un Administrador global o un Administrador de Teams para hacer estos cambios.

> [!IMPORTANT]
> Es posible que tenga que esperar hasta 24 horas para que sus cambios surtan efecto. 

Mire este corto vídeo (5:31 minutos) para ver cómo activar el acceso de invitados a través de Microsoft 365, incluyendo Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a>Paso 1: activar el acceso de invitados a nivel de toda la organización de Teams

Para activar el acceso de invitados, diríjase al **centro de administración de Microsoft Teams**. 

1. En el centro de administración de Teams, seleccione **configuración de Toda la organización** > ** Acceso de invitado**.
2. Establezca cambiar**Permitir el acceso de invitado en Microsoft Teams** en **Activado**.

    ![La captura de pantalla muestra un ejemplo de un conmutador de configuración de Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. En esta misma página, active o desactive **Llamada**, **Reunión**, y **Configuración** de mensajería para invitados.
4. Haga clic en **Guardar **.

> [!TIP]
> Si está usando la configuración predeterminada en Azure Active Directory, SharePoint Online y Microsoft 365 Groups, es posible que haya terminado de configurar el acceso de invitado. En este caso, puede saltarse el resto de los pasos. Si no está seguro, o si está usando una configuración personalizada para los grupos de AAD, SharePoint Online o Microsoft 365, continúe con el resto de los pasos de esta lista de comprobación.

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a>Paso 2: configurar las opciones de empresa a empresa de Azure AD

Estos son los ajustes de Azure AD que permiten el acceso de invitados en Teams. Una vez que estos ajustes estén configurados, estará habilitado para[agregar](add-guests.md) y [administrar invitados](manage-guests.md) en Teams.

1. Inicie sesión en [Azure Portal](https://portal.azure.com) como administrador de inquilinos.
2. Seleccione **Azure Active Directory** > **Usuarios** > **Configuración de usuarios**.
3. En **Usuarios externos**, seleccione **Administrar configuración de colaboración externa**.
   > [!NOTE]
   > Los **Ajustes de colaboración externa** también están disponibles en la página **Relaciones con la organización**. En el Azure Active Directory, en **Administrar**, vaya a **Configuración de relaciones** > ** organizacionales**.
4. En la página de **Configuración de la colaboración externa**, elija las directivas que desea habilitar.

    - **Los permisos de los usuarios invitados están limitados**: esta directiva determina los permisos de los invitados en su directorio. Seleccione **Sí** para bloquear invitados de ciertas tareas del directorio, como enumerar usuarios, grupos u otros recursos del directorio. Seleccione **No** para dar a los invitados el mismo acceso a los datos del directorio que a los usuarios habituales de su directorio.
     - **Los administradores y usuarios en el rol de invitado pueden invitar**: para permitir a los administradores y usuarios en el papel de "Invitador de huéspedes" invitar a los huéspedes, establecer esta directiva a **Si**.
     - **Los miembros pueden invitar**: para permitir que los miembros de su directorio que no sean administradores inviten a otros usuarios, establezca esta directiva en **Sí** (recomendado). Si prefiere que solo los administradores puedan agregar invitados, puede establecer esta directiva en **No**. Tenga en cuenta que, al establecer **No**, se limitará la experiencia de invitado para los propietarios de equipos que no sean administradores. Solo podrán agregar invitados a los equipos que el administrador ya haya agregado en AAD.
     - **Los invitados pueden invitar**: para permitir que los invitados inviten a otros invitados, configure esta directiva a **Sí**. 
         > [!IMPORTANT]
         > Actualmente, Teams no permite el rol de invitador de usuarios invitados, por lo que, aunque configure **Los miembros pueden invitar** como **Sí**, los invitados no pueden invitar a otros invitados en Teams.
     - **Habilitar la contraseña de correo electrónico de un solo uso para invitados (Vista previa)**: Para obtener más información sobre la función de contraseña de un solo uso, consulte [Autenticación de la contraseña de correo electrónico de un solo uso (vista previa)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).
     - **Restricciones a la colaboración**: Para obtener más información sobre cómo permitir o bloquear invitaciones a dominios específicos, consulte[Permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
        > [!NOTE]
        > Para las restricciones de colaboración, consulte [Habilitar la colaboración externa B2B y gestionar quién puede invitar a los invitados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).
      
    Para más información sobre el control de quién puede invitar a los invitados, consulte [Invitaciones de delegados para la colaboración B2B de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).

## <a name="step-3-configure-microsoft-365-groups"></a>Paso 3: configurar grupos de Microsoft 365

1. En el centro de administración de Microsoft 365, **vaya a** > configuración**configuración**, haga clic en **servicios**y, a continuación, seleccione **grupos de Microsoft 365**.

     ![Captura de pantalla que muestra la configuración de grupos de Microsoft 365](media/guest-access-checklist-services-settings.png)
2. Asegúrese de que la casilla de verificación **Dejar que los miembros del grupo fuera de la organización accedan al contenido del grupo** esté seleccionada. Si no se selecciona esta opción, los invitados no podrán acceder a ningún contenido del grupo.

    ![Captura de pantalla que muestra la configuración de grupos de Microsoft 365](media/guest-access-checklist-office365.png)
3. Asegúrese de que la casilla de verificación **Dejar que los propietarios de los grupos añadan personas ajenas a la organización a los grupos** esté seleccionada. Si no se selecciona esta opción, los propietarios de los equipos no podrán añadir nuevos invitados. Como mínimo, esta configuración debe estar activada para permitir el acceso de invitado.

Para obtener instrucciones detalladas sobre cómo configurar estas opciones, vea [administrar el acceso de invitado en microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) y [controlar el acceso de invitados en grupos de Microsoft 365](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).

## <a name="step-4-configure-sharing-in-office-365"></a>Paso 4: Configurar el uso compartido en Office 365 

Asegúrate de que los usuarios puedan añadir invitados. A continuación se describe cómo:

1. En el Centro de administración de Microsoft 365, diríjase a **Configuraciones** > **Configuraciones**, haga clic en**Seguridad y privacidad**, y luego seleccione **Compartir**.

     ![La captura de pantalla muestra un ejemplo de configuración de servicios](media/guest-access-checklist-security-privacy-settings.png)
 
2. Seleccione la casilla **Permitir que los usuarios agreguen nuevos invitados a esta organización**, y luego haga clic en **Guardar los cambios**.

     ![La captura de pantalla muestra un ejemplo de un cambio de configuración del uso compartido](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > Esta configuración es equivalente a la configuración de los **Miembros pueden invitar** en **Configuración de usuario** > **Usuarios externos** en Azure AD.  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>Paso 5: Verificar la configuración de compartir en SharePoint

1. Inicie sesión en el Centro de administración de Microsoft 365.
2. En **Centros de administración**, **seleccione SharePoint**.
3. En el nuevo Centro de administración de SharePoint, en **Sitios**, seleccione **Sitios activos**.

    ![Sitios activos en el Centro de administración de SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. Seleccione el sitio, y luego haga clic en **Compartir**.
4. Asegúrese de que la opción se establece en **Cualquiera** o en **Huéspedes nuevos y existentes**.

     ![La captura de pantalla muestra un ejemplo de un cambio de configuración de SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a>Paso 6: establecer los permisos de usuario invitado

En la aplicación Teams, a nivel de equipo individual, configure los permisos de los invitados que controlan si los invitados pueden crear, actualizar o borrar canales. Tanto los administradores de los equipos como los propietarios de los mismos pueden configurar estos ajustes.

![La captura de pantalla muestra un ejemplo de una configuración de equipo/canal](media/guest-access-checklist-TeamsSettings2.png)

Para obtener más información sobre el acceso de invitados, consulte [Acceso de invitados en Teams](guest-access.md) y [Activar o desactivar el acceso de invitados a Microsoft Teams](set-up-guests.md).

## <a name="troubleshooting"></a>Solución de problemas

Si tiene problemas para configurar el acceso de invitados o para añadir invitados en Teams, utilice estos recursos para ayudarle:

[Solucionar problemas con el acceso de invitados en Microsoft Teams](troubleshoot-guest-access.md)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
