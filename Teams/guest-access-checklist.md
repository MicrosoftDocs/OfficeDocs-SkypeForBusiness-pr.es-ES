---
title: Lista de comprobación para el acceso de invitado de Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de comprobación para ayudarle a configurar el acceso de invitado en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0ec3fb391feefae9daa5ffaa8c7b5955b6552f93
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221663"
---
<a name="teams-guest-access-checklist"></a>Lista de comprobación de acceso de invitados de Teams
==========================================

Use esta lista de comprobación para habilitar y configurar la característica de acceso de invitado en Microsoft Teams de acuerdo con las preferencias de su organización.

## <a name="understand-the-limitations-for-guests"></a>Comprender las limitaciones de los invitados

La experiencia de invitado tiene limitaciones por diseño. Asegúrese de comprender la experiencia de invitado para no intentar corregir algo que no es un problema. Por ejemplo, aquí tiene una lista de algunas de las funciones que no están disponibles para un invitado en Microsoft Teams:

- OneDrive para la empresa
- Búsqueda de personas fuera de Teams
- Calendario, reuniones programadas o detalles de la reunión
- RTC
- Organigrama
- Crear o revisar un equipo
- Buscar un equipo
- Cargar archivos a una conversación entre usuarios
- Los invitados pueden buscar y buscar usuarios (fuera de su equipo) si saben que el identificador de correo electrónico del usuario es completo. Para evitar esto, los administradores de TI pueden usar patrones como la [búsqueda de directorios de ámbito](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) , que tienen la capacidad de restringir los invitados a su propia gal virtual.

Para obtener más información, consulte [cuál es la experiencia de invitado](guest-experience.md) y [acceso de invitados en los grupos de Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).

### <a name="guest-access-vs-external-access-federation"></a>Diferencias entre el acceso de invitados y el acceso externo (federación)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>Si los invitados experimentan errores de licencia

El acceso de invitados en Microsoft Teams usa Azure Active Directory (Azure AD) empresarial para empresas (B2B) y su modelo de licencias. Si ve errores de licencias, asegúrese de leer las instrucciones de licencias [B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para conocer los requisitos de licencia de la organización para que los usuarios puedan invitar a invitados a su organización.

Recuerde lo siguiente:

- Para cada licencia de Azure AD de pagos que asigne a un usuario, los usuarios pueden invitar a un máximo de cinco usuarios invitados según el límite del usuario externo.
- Los invitados son usuarios externos a su organización. Los empleados, los contratistas en el sitio, los agentes en el sitio, etc. no se pueden agregar como invitados. Lo mismo se aplica a tus afiliados.
- Las licencias de invitados se cuentan en relación con la organización que invita. Considere esto cuando calcule el número de licencias que necesita.
- Las licencias se cuentan en relación con su organización si los invitados invitados provienen de otro inquilino de Office 365 o si usan sus direcciones de correo electrónico personales.

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□ Paso 1: configurar las opciones de Azure AD Business-to-Business

1. Inicie sesión en https://portal.azure.com.
2. Haga clic en **Azure Active Directory** en el panel de la izquierda.
3. En **administrar**, haga clic en **configuración de usuario**.
4. En **usuarios externos**, haga clic en **administrar la configuración de colaboración externa**.
5. En la página **configuración de colaboración externa** , asegúrese de que **los miembros pueden invitar** estén establecidos en **sí**.

      ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de AAD. ](media/guest-access-checklist-AADSettings1.png)

    Para admitir invitados, **los miembros pueden invitar** a que se establezcan en **sí**.

    > [!NOTE] 
    > Si establece que **los miembros puedan invitar** a **no** y, a continuación, habilitar el acceso de invitado en Office 365 grupos y Microsoft Teams, los administradores pueden controlar invitaciones invitadas a su directorio. Una vez que los invitados estén en el directorio, los miembros que no sean administradores podrán agregarlos a teams que sean propietarios del equipo.

Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).


## <a name="-step-2-configure-office-365-groups"></a>□ Paso 2: configurar grupos de Office 365

1. En el centro de administración de Microsoft 365, vaya a **configuración** > **servicios & complementos** > **Office 365 grupos**.
2. Asegúrese de **permitir que los miembros del grupo ajenos a la organización tengan el contenido del grupo** **activado**. Si esta opción está desactivada, los invitados no podrán acceder a ningún contenido de grupo.
3. Asegúrese de **permitir que los propietarios del grupo agreguen personas fuera de la organización a groups** se establece en **activado**. Si esta opción está desactivada, los propietarios del equipo no podrán agregar invitados nuevos. Como mínimo, esta configuración debe estar activada para que sea compatible con el acceso de invitados.

     ![Captura de pantalla que muestra los alternancias de grupos de Office 365](media/guest-access-checklist-office365.png)

Para obtener instrucciones detalladas sobre cómo configurar estas opciones, consulte [administrar el acceso de invitados en office 365 grupos](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) y [controlar el acceso de invitados en los grupos de Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ Paso 3: habilitar el acceso de invitado en el nivel de inquilino

Como mínimo, debe activar el acceso de invitado para Microsoft Teams en el **centro de administración de Microsoft Teams**. 

1. En el centro de administración de Teams, seleccione**acceso de invitado a** **toda** > la organización.
2. Establezca la opción **permitir acceso de invitado en Microsoft Teams** . ****

    ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. En esta misma página, configure cualquier otra configuración de invitados que necesite.
4. Haga clic en **Guardar **.

Para obtener instrucciones detalladas, consulte [activar o desactivar el acceso de invitados a Microsoft Teams](set-up-guests.md).


## <a name="--step-4-configure-sharing-in-office-365"></a>□ Paso 4: configurar el uso compartido en Office 365 

Asegúrese de que los usuarios pueden agregar invitados. Aquí le mostramos cómo hacerlo:

1. En el centro de administración de Microsoft 365, vaya a **configuración** > **seguridad & privacidad**.

     ![Captura de pantalla que muestra un ejemplo de configuración de servicios](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. En **compartir**, seleccione **Editar**.

     ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Establezca **permitir a los usuarios agregar nuevos invitados a la organización** **en activado**y, a continuación, haga clic en **Guardar**.

     ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> Esta opción es equivalente a la opción los **miembros pueden invitar** en **configuración** > de usuario**usuarios externos** en Azure ad.  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ Paso 5: comprobar la configuración de uso compartido en SharePoint

1. Inicie sesión en el centro de administración de Microsoft 365.
2. Haga clic en **centro de administración**y, después, seleccione **SharePoint**.
3. En el centro de administración de SharePoint, seleccione **uso compartido**.
4. Asegúrese de que la opción para **no permitir el uso compartido fuera de su organización** *no* está seleccionada.
 
     ![Captura de pantalla que muestra un ejemplo de un botón de alternancia de configuración de SparePoint online.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ Paso 6: habilitar la configuración específica de los canales 

En la aplicación de Teams, en el nivel de equipo individual, configure los permisos de invitado para que los invitados puedan crear, actualizar y eliminar canales. Además de los administradores, los propietarios del equipo pueden configurar esta opción.

![Captura de pantalla que muestra un ejemplo de alternancia de configuración de un equipo o un canal](media/guest-access-checklist-TeamsSettings2.png)

Para obtener más información, incluyendo vídeos de procedimientos, consulte [acceso de invitado en Microsoft Teams](guest-access.md).


## <a name="troubleshooting"></a>Solución de problemas

Si tiene problemas al agregar invitados en Microsoft Teams, consulte la [Guía de solución de problemas de acceso de invitados](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


