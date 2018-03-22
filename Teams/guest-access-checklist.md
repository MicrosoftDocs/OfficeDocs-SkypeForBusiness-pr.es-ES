---
title: Lista de comprobación de acceso de invitado de los equipos de Microsoft
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Utilice esta lista de comprobación para configurar el acceso de invitado en invitado de los equipos de Microsoft Access.
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53800ddf452fd6596abe3e4404c79352483e946
ms.sourcegitcommit: ccbe086ccb2c0be716984010a1253a4c8c0276b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2018
---
<a name="teams-guest-access-checklist"></a>Lista de comprobación de acceso de invitado a los equipos
==========================================

Utilice esta lista de comprobación para habilitar y configurar la característica de acceso de invitado en Microsoft Teams según las preferencias de la organización.




## <a name="--enable-guest-access-at-the-tenant-level"></a>Acceso como invitado □ habilitar en el nivel de inquilinos

Como mínimo, debe activar Microsoft Teams para todos los usuarios del tipo de licencia **invitado**. Para obtener instrucciones detalladas, consulte [Activar o desactivar acceso de invitado a equipos de Microsoft](set-up-guests.md).

![Captura de pantalla muestra un ejemplo de un control de alternancia de la configuración de equipos](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a>□ Habilitar configuración específica de los canales 
En la aplicación de los equipos, en el nivel de equipo individual, configurar permisos de invitado para que los invitados pueden crear, actualizar y eliminar canales. Además de administradores, propietarios de equipo pueden configurar esta opción.

![Captura de pantalla muestra un ejemplo de un control de alternancia de la configuración del equipo/canal](media/guest-access-checklist-TeamsSettings2.png)


Para obtener más información, vídeos de procedimientos, consulte [acceso como invitado en los equipos de Microsoft](guest-access.md).



## <a name="--configure-sharing-in-office-365"></a>□ Configure el uso compartido en Office 365 

□ Asegúrese de que los usuarios pueden agregar invitados. Le mostramos cómo:

1. En el centro de administración de Office 365, vaya a **configuración de** > **de seguridad y privacidad**.
![Captura de pantalla muestra un ejemplo de una configuración de servicios](media/guest-access-checklist-Office365Admin_Services_addins.png)
1. En **Compartir**, seleccione **Editar**. ![Captura de pantalla muestra un ejemplo de un botón de edición de la configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
2. **Permitir a los usuarios agregar a nuevos invitados a esta organización** se establece en **On**y, a continuación, haga clic en **Guardar**. ![Captura de pantalla muestra un ejemplo de una alternancia de la configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 

 > [!NOTE]
> Este valor es equivalente a la configuración en configuración de usuario **pueden invitar miembros** > usuarios externos en Azure AD.  




## <a name="-configure-office-365-groups"></a>□ Configurar grupos de Office 365

En el centro de administración de Office 365, vaya a **configuración de** > **Servicios & Add-ins** > **Grupos de Office 365**.

Asegúrese de que **Permitir que los miembros del grupo fuera del contenido del grupo de acceso de organización** se establece en **On**. Si esta opción está desactivada, los invitados no pueden tener acceso a cualquier contenido de grupo.

Asegúrese de que **permiten agregar personas ajenas a la organización a grupos propietarios del grupo** se establece en **On**. Si esta opción está desactivada, los propietarios del equipo no pueden agregar a nuevos invitados. (Sin embargo, si un administrador había agregado un usuario invitado a Azure AD, a continuación, el propietario del equipo sería puede agregar ese usuario al equipo.) Como mínimo, este valor debe ser "on" admitir el acceso de invitado.

Para obtener instrucciones detalladas acerca de cómo configurar estas opciones, consulte la sección "Office 365 grupos" de [autorizar el acceso de invitado en los equipos de Microsoft](Teams-dependencies.md) y [Permitir o bloquear el acceso de invitado a los grupos de Office 365](https://go.microsoft.com/fwlink/?linkid=869658).
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a>Establecer la configuración del □ en AD Azure business-to-business (B2B)
1. Iniciar sesión en https://portal.azure.com.
2. En el panel izquierdo, haga clic en **Azure Active directory** .
3. En **Administrar**, haga clic en **configuración de usuario**.
4. **Los usuarios externos**, asegúrese de que **pueden invitar los miembros** está establecida en **Sí**. ![Captura de pantalla muestra un ejemplo de una alternancia de DAA configuración. ](media/guest-access-checklist-AADSettings1.png)

    

► Como mínimo para admitir a invitados, **pueden invitar miembros** debe establecerse en **Sí**.

> > [!NOTE]
> Si establece **pueden invitar miembros** a **No** y habilitar el acceso de invitado en Office 365 grupos y Teams de Microsoft, administradores pueden controlar las invitaciones de invitado a su directorio. Después de que los invitados están en el directorio, pueden agregarse a los equipos miembros no administrador (propietarios de equipo).


Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).







## <a name="-verify-sharing-setting-in-sharepoint"></a>Configuración de uso compartido de Verify □ en SharePoint
1. Inicie sesión en el Centro de administración de Office 365.
2. Haga clic en **Admin center**y, a continuación, seleccione **SharePoint**.
3. En el centro de administración de SharePoint, seleccione **Compartir**.
4. Asegúrese de que la opción *no* está seleccionada para **no permitir compartir fuera de su organización** . ![Captura de pantalla muestra un ejemplo de una alternancia de configuración en línea Sparepoint. ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a>Tipos y licencias □ comprobar cuenta

- **Cuenta con licencia para equipos**: para una cuenta de "Invitado" sus raíces en una cuenta de usuario real en algunos otros clientes de Office 365, esa cuenta de usuario real debe tener una licencia para los equipos de "Invitado". 
- **Cuenta debe ser Office 365 escuela o trabajar la cuenta, o cuenta MSA**: actualmente, los usuarios que tengan una dirección de correo electrónico correspondiente a un Active Directory de Azure, Office 365 trabajo o escuela cuenta o una cuenta de Microsoft (MSA) pueden agregarse como usuario invitado. 
 
## <a name="-configure-environment"></a>Entorno de configurar □


Los invitados deben utilizar la autenticación con varios factores (AMF) si lo requiere el inquilino alojamiento.
Para obtener más detalles, vea [modelos de identidad y la autenticación de equipos de Microsoft](identify-models-authentication.md).

## <a name="-understand-limitations-for-guests"></a>Limitaciones de entender □ para invitados

La experiencia de invitado tiene limitaciones por diseño. Asegúrese de que entender la experiencia del invitado para no intentar arreglar algo que no sea un problema.
Por ejemplo, presentamos una lista de algunas de las funciones que no está disponible para un invitado en Teams de Microsoft:

- OneDrive para el negocio
- Búsqueda de personas fuera de los equipos
- Calendario, reuniones programadas o detalles de la reunión
- RTC
- Organigrama
- Crear o revisar un equipo
- Buscar un equipo
- Cargar archivos en un chat de persona a persona

Para obtener más información, vea [cómo es la experiencia del invitado](guest-experience.md) y el [acceso como invitado en los grupos de Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).




## <a name="troubleshooting"></a>Solución de problemas

Si tiene problemas con la adición de invitados en Teams de Microsoft, consulte la [Guía de solución de problemas de acceso de invitado](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


