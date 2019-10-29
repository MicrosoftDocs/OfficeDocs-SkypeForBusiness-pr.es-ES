---
title: Lista de comprobación para el acceso de invitado de Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de comprobación para ayudarle a configurar el acceso de invitado en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04594f578d2375f69c38243251ee64506880d00e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753325"
---
<a name="microsoft-teams-guest-access-checklist"></a>Lista de comprobación para el acceso de invitado de Microsoft Teams
==========================================

Use esta lista de comprobación para que le resulte más fácil activar y configurar el acceso de invitado en Microsoft Teams.

> [!IMPORTANT]
> Es posible que tenga que esperar hasta 24 horas para que los cambios surtan efecto. 



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

1. Inicie sesión en el [portal de Azure](https://portal.azure.com) como administrador de inquilinos.
2. Seleccione**configuración de usuario**de**usuarios** > de **Azure Active Directory** > .
3. En **usuarios externos**, seleccione **administrar la configuración de colaboración externa**.
   > [!NOTE]
   > La **configuración de colaboración externa** también está disponible en la página relaciones de la **organización** . En Azure Active Directory, en **administrar**, vaya a > **configuración**de **relaciones organizativas**.
4. En la página **configuración de colaboración externa** , elija las directivas que quiera habilitar.

  - **Los permisos de los usuarios invitados son limitados**: esta Directiva determina los permisos para los invitados de su directorio. Seleccione **sí** para bloquear a los invitados de determinadas tareas de directorio, como la enumeración de usuarios, grupos u otros recursos de directorio. Seleccione **no** para proporcionar a los invitados el mismo acceso a los datos de directorio que los usuarios habituales de su directorio.
   - **Los administradores y usuarios del rol invitado invitar pueden invitar**: para permitir que los administradores y los usuarios del rol "invitado invitar" puedan invitar a invitados, establezca esta directiva en **sí**.
   - **Los miembros pueden invitar**: para que los miembros que no sean administradores de su directorio puedan invitar a invitados, establezca esta directiva en **sí**.
   
       > [!NOTE]
       > Si establece que **los miembros puedan invitar** a **no** y, a continuación, habilitar el acceso de invitado en Office 365 grupos y Microsoft Teams, los administradores pueden controlar invitaciones invitadas a su directorio. Una vez que los invitados estén en el directorio, los miembros que no sean administradores podrán agregarlos a teams que sean propietarios del equipo. Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).
       > [!IMPORTANT]
       > Para que el acceso de invitados funcione en todos los equipos, debe establecer que **los miembros puedan invitar** a **sí**.   
   - Los **invitados pueden invitar**: para permitir que los invitados inviten a otros invitados, establezca esta directiva en **sí**.
       > [!IMPORTANT]
       > Actualmente, Teams no es compatible con el rol invitado, por lo tanto, aunque establezca que los **invitados puedan invitar** a **sí**, los invitados no pueden invitar a otros invitados en Teams.
   - **Habilitar el código de acceso de un solo uso de correo electrónico para invitados (vista previa)**: para obtener más información sobre la característica de código de acceso de un solo uso, consulte [autenticación de código de acceso de un solo uso de correo electrónico (vista previa)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)
   - **Restricciones de colaboración**: para obtener más información sobre cómo permitir o bloquear invitaciones a dominios específicos, consulte [permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
      > [!NOTE]
      > Para obtener las restricciones de colaboración, consulte [Habilitar la colaboración externa B2B y administrar quién puede invitar a invitados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).
      
 
Para obtener más información acerca de cómo controlar quién puede invitar a invitados, consulte [Delegar invitaciones para la colaboración de Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).


## <a name="step-3-configure-office-365-groups"></a>Paso 3: configurar grupos de Office 365

1. En el centro de administración de Microsoft 365, vaya a **configuración** > **servicios & complementos** > **Office 365 grupos**.
2. Asegúrese de **permitir que los miembros del grupo ajenos a la organización tengan el contenido del grupo** **activado**. Si esta opción está desactivada, los invitados no podrán acceder a ningún contenido de grupo.
3. Asegúrese de **permitir que los propietarios del grupo agreguen personas fuera de la organización a groups** se establece en **activado**. Si esta opción está desactivada, los propietarios del equipo no podrán agregar invitados nuevos. Como mínimo, esta configuración debe estar activada para que sea compatible con el acceso de invitados.

     ![Captura de pantalla que muestra los alternancias de grupos de Office 365](media/guest-access-checklist-office365.png)

Para obtener instrucciones detalladas sobre cómo configurar estas opciones, consulte [administrar el acceso de invitados en office 365 grupos](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) y [controlar el acceso de invitados en los grupos de Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).
 

## <a name="step-4-configure-sharing-in-office-365"></a>Paso 4: configurar el uso compartido en Office 365 

Asegúrese de que los usuarios pueden agregar invitados. Aquí le mostramos cómo hacerlo:

1. En el centro de administración de Microsoft 365, vaya a **configuración** > **seguridad & privacidad**.

     ![Captura de pantalla que muestra un ejemplo de configuración de servicios](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. En **compartir**, seleccione **Editar**.

     ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Establezca **permitir a los usuarios agregar nuevos invitados a la organización** **en activado**y, a continuación, haga clic en **Guardar**.

     ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> Esta opción es equivalente a la opción los **miembros pueden invitar** en **configuración** > de usuario**usuarios externos** en Azure ad.  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>Paso 5: comprobar la configuración de uso compartido en SharePoint

Este es un poco de un rompecabezas. El acceso de invitados en Teams no funciona si la opción **no permitir el uso compartido fuera de la organización** está seleccionada en el centro de administración de SharePoint.

1. Inicie sesión en el centro de administración de Microsoft 365.
2. Haga clic en **centro de administración**y, después, seleccione **SharePoint**.
3. En el centro de administración de SharePoint, seleccione **uso compartido**.
4. Asegúrese de que la opción para **no permitir el uso compartido fuera de su organización** *no* está seleccionada.
 
     ![Captura de pantalla que muestra un ejemplo de un botón de alternancia de configuración de SparePoint online.](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a>Paso 6: configurar permisos de usuario invitados

En la aplicación de Teams, en el nivel de equipo individual, configure los permisos de invitado que controlan si los invitados pueden crear, actualizar o eliminar canales. Los administradores de equipos y los propietarios de equipo pueden configurar esta configuración.

![Captura de pantalla que muestra un ejemplo de alternancia de configuración de un equipo o un canal](media/guest-access-checklist-TeamsSettings2.png)

Para obtener más información sobre el acceso de invitados, consulte [acceso de invitados en Teams](guest-access.md) y [activar o desactivar el acceso de invitados a Microsoft Teams](set-up-guests.md).


## <a name="troubleshooting"></a>Solución de problemas

Si tiene problemas para configurar el acceso de invitados o agregar invitados en Teams, use estos recursos para ayudarle:

[Solución de problemas con el acceso de invitado en Microsoft Teams](troubleshoot-guest-access.md)

[Solución de problemas de equipos](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



