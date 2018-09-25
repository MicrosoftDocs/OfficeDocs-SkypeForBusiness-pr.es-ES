---
title: Lista de comprobación de acceso de invitado de los equipos de Microsoft
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Use esta lista de comprobación para ayudar a configurar el acceso de invitado en invitado de los equipos de Microsoft Access.
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f7a1464159bf613800756eb8568510c3749939e
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017186"
---
<a name="teams-guest-access-checklist"></a>Lista de comprobación de acceso de invitado a los equipos
==========================================

Use esta lista de comprobación que le ayudarán a habilitar y configurar la característica de acceso de invitado en Microsoft Teams según las preferencias de la organización.




## <a name="--enable-guest-access-at-the-tenant-level"></a>Acceso como invitado □ habilitar en el nivel de inquilino

Como mínimo, debe activar Microsoft Teams para todos los usuarios del tipo de licencia **invitado**. Para obtener instrucciones detalladas, vea [Activar o desactivar el acceso de invitado a los equipos de Microsoft](set-up-guests.md).

![Captura de pantalla muestra un ejemplo de un control de alternancia de la configuración de los equipos](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a>□ Habilitar opciones específicas de canales 
En la aplicación de los equipos, en el nivel de equipo individual, configurar permisos de invitado para que los invitados pueden crear, actualizar y eliminar canales. Además de los administradores, los propietarios de equipo pueden configurar esta opción.

![Captura de pantalla muestra un ejemplo de un control de alternancia de configuración del equipo/canal](media/guest-access-checklist-TeamsSettings2.png)


Para obtener más información, vídeos de procedimientos, vea [acceso como invitado en los equipos de Microsoft](guest-access.md).



## <a name="--configure-sharing-in-office-365"></a>□ Configurar el uso compartido en Office 365 

□ Asegúrese de que los usuarios pueden agregar invitados. Aquí es cómo:

1. En el centro de administración de Office 365, vaya a **configuración de** > **de seguridad y privacidad**.
![Captura de pantalla muestra un ejemplo de una configuración de servicios](media/guest-access-checklist-Office365Admin_Services_addins.png)
1. En **el uso compartido**, seleccione **Editar**. ![Captura de pantalla muestra un ejemplo de un botón de edición de la configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
2. **Permitir a los usuarios agregar a nuevos invitados a esta organización** se establece en **On**y, a continuación, haga clic en **Guardar**. ![Captura de pantalla muestra un ejemplo de alternancia de una configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 

 > [!NOTE]
> Esta configuración es equivalente a la configuración **pueden invitar los miembros** en configuración del usuario > usuarios externos en Azure AD.  




## <a name="-configure-office-365-groups"></a>□ Configurar grupos de Office 365

En el centro de administración de Office 365, vaya a **configuración de** > **Services & Add-ins** > **Grupos de Office 365**.

Asegúrese de **Permitir que los miembros del grupo fuera el contenido de grupo de acceso de la organización** está establecido en **On**. Si esta opción está desactivada, los invitados no puedan tener acceso a cualquier contenido de grupo.

Asegúrese de **que permitir a los propietarios de grupo agregar personas fuera de la organización a grupos** se establece en **On**. Si esta opción está desactivada, los propietarios de equipo no puedan agregar a nuevos invitados. Como mínimo, este valor debe ser "en" admitir el acceso de invitado.

Para obtener instrucciones detalladas acerca de cómo configurar estas opciones, vea la sección "Grupos de Office 365" en [autorizar el acceso de invitado en los equipos de Microsoft](Teams-dependencies.md) y [Permitir o bloquear el acceso de invitado a los grupos de Office 365](https://go.microsoft.com/fwlink/?linkid=869658).
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a>Establecer la configuración del □ en Azure AD business-to-business (B2B)
1. Inicie sesión en https://portal.azure.com.
2. En el panel izquierdo, haga clic en **Azure Active directory** .
3. En **Administrar**, haga clic en **Configuración del usuario**.
4. En **los usuarios externos**, haga clic en **Administrar externo configuración de colaboración**
5. En la página **configuración de colaboración externa** Asegúrese de que **pueden invitar los miembros** está establecida en **Sí**. ![Captura de pantalla muestra un ejemplo de un control de alternancia AAD configuración. ](media/guest-access-checklist-AADSettings1.png)

    

► Como mínimo para admitir a los invitados, **pueden invitar los miembros** se debe establecer en **Sí**.

> > [!NOTE]
> Si establece **pueden invitar los miembros** en **No** y habilitar el acceso de invitado en grupos de Office 365 y Microsoft Teams, los administradores pueden controlar las invitaciones de invitado a su directorio. Después de que los invitados se encuentran en el directorio, puede agregarse a los equipos de los miembros sin permisos de administrador (propietarios de equipo).


Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).







## <a name="-verify-sharing-setting-in-sharepoint"></a>Configuración de uso compartido de Verify □ en SharePoint
1. Inicie sesión en el Centro de administración de Office 365.
2. Haga clic en **Centro de administración**y, a continuación, seleccione **SharePoint**.
3. En el centro de administración de SharePoint, seleccione **Compartir**.
4. Asegúrese de que la opción para **no permitir el uso compartido de fuera de su organización** *no* está seleccionado. ![Captura de pantalla muestra un ejemplo de alternancia de una configuración de Online Sparepoint. ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a>Tipos y licencias □ Verify cuenta

- **Cuenta con licencia para equipos**: para una cuenta de "Invitado" con raíz en una cuenta de usuario real en algunos otro inquilino de Office 365, debe tener licencia para los equipos de esa cuenta de usuario real para "Invitado". 
- **Cuenta debe ser school de Office 365 o trabajar cuenta, o cuenta MSA**: actualmente, se pueden agregar los usuarios que tienen una dirección de correo electrónico correspondiente a un Azure Active Directory, del trabajo de Office 365 o cuenta de escuela o una cuenta de Microsoft (MSA) como un usuario invitado. 
 
## <a name="-configure-environment"></a>Entorno de Configure □


Los invitados son necesarios para usar la autenticación multifactor (MFA) si así lo requiere el inquilino de hospedaje.
Para obtener más información, vea [modelos de identidad y la autenticación en los equipos de Microsoft](identify-models-authentication.md).

## <a name="-understand-limitations-for-guests"></a>Limitaciones de □ comprenda el funcionamiento de los invitados

La experiencia de invitado tiene limitaciones por diseño. Asegúrese de que comprende la experiencia de invitado por lo que no intente corregir algo que no es un problema.
Por ejemplo, aquí es una lista de algunas de las funciones que no está disponible para un invitado en Microsoft Teams:

- OneDrive para la empresa
- Búsqueda de personas fuera de los equipos
- Calendario, las reuniones programadas o detalles de la reunión
- RTC
- Gráfico de organización
- Crear o revisar un equipo
- Buscar un equipo
- Cargar archivos a una conversación entre dos persona

Para obtener más información, vea [¿Qué es la experiencia de invitado como](guest-experience.md) y [acceso de invitado en grupos de Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).




## <a name="troubleshooting"></a>Solución de problemas

Si tiene problemas con la adición de invitados en Microsoft Teams, consulte la [Guía de solución de problemas de acceso de invitado](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


