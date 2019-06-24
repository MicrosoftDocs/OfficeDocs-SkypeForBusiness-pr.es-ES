---
title: Autorizar el acceso de invitado en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 04/01/19
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
localization_priority: Priority
search.appverid: MET150
description: Administre las funcionalidades y las características de acceso de invitado de Microsoft Teams a través de cuatro niveles de autorización distintos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f027a4626fef2fbfbdad5e6ceb52ca6c3828d1c7
ms.sourcegitcommit: 66213b972920b4e09faf7d7e732c4bfe7b322ac4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131412"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Autorizar el acceso de invitado en Microsoft Teams
===========================================

Para satisfacer los requisitos de su organización, puede administrar las funcionalidades y las características de acceso de invitado de Microsoft Teams a través de cuatro niveles de autorización distintos. Todos los niveles de autorización se aplican a su inquilino de Office 365. Cada nivel de autorización controla la experiencia de invitado como se muestra a continuación:

- **Azure Active Directory**: el acceso de invitado en Microsoft Teams depende de la plataforma negocio a negocio (B2B) de Azure AD. Controla la experiencia de invitado a nivel de directorio, inquilino y aplicación. 
- **Microsoft Teams**: solo controla Microsoft Teams. 
- **Grupos de Office 365**: controla la experiencia de invitado en los Grupos de Office 365 y Microsoft Teams.
- **SharePoint Online y OneDrive para la Empresa**: controla la experiencia de invitado en SharePoint Online, OneDrive para la Empresa, Grupos de Office 365 y Microsoft Teams.

Estos niveles de autorización distintos proporcionan la flexibilidad necesaria para configurar el acceso de invitado para su organización. Por ejemplo, si no quiere permitir usuarios invitados en su organización de Microsoft Teams pero sí en la organización en general, solo tiene que desactivar el acceso de invitado en Microsoft Teams. Otro ejemplo: podría habilitar el acceso de invitado en los niveles de AAD, Teams y Grupos, pero deshabilitaría la adición de usuarios invitados en equipos seleccionados que tengan un criterio o varios en común, como que la clasificación de datos es igual a confidencial. SharePoint Online y OneDrive para la Empresa tienen su propia configuración de acceso de invitado que no depende de Grupos de Office 365. 

> [!NOTE]
> Los invitados están sujetos a los límites de servicio de [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019). 

En el siguiente diagrama se muestra cómo se concede y se integra la dependencia de autorización de acceso de invitado entre Azure Active Directory, Microsoft Teams y Office 365.

![Diagrama de las dependencias de autorización para el acceso de invitado.](media/teams_dependencies_image1.png)

El siguiente diagrama muestra, de forma general, el funcionamiento de la experiencia del usuario con el modelo de permisos mediante una invitación de acceso de invitado y un flujo de aprobación comunes.

![Diagrama de flujos de invitación y aceptación](media/authorize-guest-image1.png)

Es importante destacar que conectores, bots y aplicaciones a veces requieren su propio conjunto de permisos o consentimiento específicos de la cuenta de usuario. Puede que necesiten concederse por separado. De la misma manera, SharePoint puede imponer límites adicionales de uso compartido externo para un usuario específico, grupos de usuarios o incluso en el nivel del sitio.

Los dos diagramas anteriores también están disponibles en [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).

## <a name="control-guest-access-in-azure-active-directory"></a>Controlar el acceso de invitado en Azure Active Directory

Use Azure AD para determinar si los colaboradores externos pueden invitarse a su espacio empresarial como invitados y de qué maneras. Para más información sobre el acceso de invitados de Azure B2B, consulte [¿Qué es el acceso de usuarios invitados en Azure Active Directory B2B?](https://docs.microsoft.com/es-ES/azure/active-directory/b2b/what-is-b2b) Para obtener información acerca de las funciones de Azure AD, consulte [Conceder permisos a los usuarios de organizaciones asociadas en el espacio empresarial de Azure Active Directory](https://docs.microsoft.com/es-ES/azure/active-directory/b2b/add-guest-to-role).

La configuración de las invitaciones se aplica a nivel de inquilino y controla la experiencia de invitado a nivel de directorio, inquilino y aplicación. Para configurar estas opciones en Microsoft Azure Portal, vaya a **Azure Active Directory** > **Usuarios** > **Configuración de usuario** y, en **Usuarios externos**, seleccione **Administrar configuraciones de colaboración externas**.

Azure AD incluye las siguientes opciones para configurar usuarios externos:

- **Los permisos de usuario invitado están limitados**: **Sí** significa que los invitados no tienen permiso para determinadas tareas de directorio, como enumerar los usuarios, grupos y otros recursos de directorio. Además, los invitados no se pueden asignar a las funciones administrativas en el directorio. **No** significa que los invitados tienen el mismo acceso a los datos que los usuarios normales en el directorio.
- **Los administradores y los usuarios con el rol Invitador de usuarios pueden invitar**: **Sí** significa que los administradores y usuarios con la función "Invitador de usuarios" podrán añadir invitar a usuarios en el espacio empresarial. **No** significa que los administradores y usuarios no pueden invitar a usuarios en el espacio empresarial.
- **Los miembros pueden invitar**: **Sí** significa que los usuarios que no sean administradores del directorio pueden invitar a usuarios a colaborar en recursos protegidos por Azure AD, como sitios de SharePoint o recursos de Azure. **No** significa que solo los administradores pueden invitar a usuarios al directorio.</br>
      
    > [!NOTE]
    > Actualmente, Teams no admite el rol de Invitador de usuarios. Como mínimo, la opción **Los miembros pueden invitar** debe establecerse en **Sí** para que el acceso de invitados funcione en Teams.
- **Los invitados pueden invitar**: **Sí** significa que los invitados en el directorio pueden invitar a otros usuarios a colaborar en recursos protegidos por Azure AD, como sitios de SharePoint o recursos de Azure. **No** significa que los invitados no pueden invitar a otros invitados para colaborar con su organización.
 
Para obtener más información acerca de cómo controlar quién puede invitar a invitados, consulte [Delegar invitaciones para la colaboración de Azure Active Directory B2B](https://docs.microsoft.com/es-ES/azure/active-directory/b2b/delegate-invitations).

> [!NOTE]
> También puede administrar los dominios que se pueden invitar a su espacio empresarial como invitados. Vea [Permitir o bloquear el acceso de invitado a los grupos de Office 365](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups). 

No es necesario agregar la cuenta de usuario invitado manualmente en Azure AD B2B, ya que la cuenta se agregará al directorio automáticamente al agregar al invitado a Teams. 

Las licencias de Azure AD le permiten agregar hasta 5 invitados por licencia. Para obtener más información sobre las licencias de Azure AD, consulte [Guía de concesión de licencias de colaboración B2B de Azure Active Directory](https://docs.microsoft.com/es-ES/azure/active-directory/b2b/licensing-guidance).

## <a name="control-guest-access-in-teams"></a>Controlar el acceso de invitado en Teams

En Teams, puede controlar si la experiencia de invitado está habilitada o deshabilitada en su organización. La configuración está deshabilitada de forma predeterminada y se aplica en el nivel de inquilino solo para Teams.

Puede administrar la configuración del acceso de invitado de Teams desde el Centro de administración de Microsoft Teams. Para obtener más información, vea [Activar o desactivar el acceso de invitado a Microsoft Teams](set-up-guests.md). 


## <a name="control-guest-access-in-office-365-groups"></a>Controlar el acceso de invitados a Grupos de Office 365

Desde Grupos de Office 365, puede controlar la adición de usuarios invitados y el acceso de invitado a todos los grupos de Office 365 y Microsoft Teams en su organización.

1. Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. En el menú de navegación, elija **Configuración** y luego **Servicios y complementos**.
    
3. Seleccione **Grupos de Office 365**.
    
     ![Captura de pantalla de grupos de Office 365 en configuración](media/authorize-guest-image2.png)
  
4. En la página de Grupos de Office 365, configure el botón de alternancia en **Activado** o **Desactivado**, dependiendo de si quiere que los propietarios del equipo y el grupo que no pertenecen a la organización accedan a los grupos de Office 365. Haga clic o pulse el botón en para establecerlo como **Activado** junto a **Permitir que los propietarios del grupo agreguen usuarios de fuera de la organización a grupos**. Si cambia a **Activado** el botón de alternancia, verá otra opción para controlar si quiere que los propietarios de grupo y equipo puedan añadir personas externas a la organización a los grupos de Office 365 y Microsoft Teams. Establezca el botón de alternancia en **Activado** si desea que los propietarios de grupo y equipo agreguen usuarios invitados. 
 
   ![Captura de pantalla del panel Grupos de Office 365 con las opciones activadas](media/authorize-guest-image3.png)

La configuración anterior se aplica a nivel de espacio empresarial y controla la experiencia de invitado en Grupos de Office 365 y Microsoft Teams.

Vea [Acceso de invitado en Grupos de Office 365](https://support.office.com/es-ES/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) para obtener más información sobre el acceso de invitado en Grupos, como su funcionamiento, cómo administrar el acceso de invitados y respuestas a las preguntas más frecuentes.

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a>Controlar el acceso de invitado a SharePoint Online y OneDrive para la Empresa

Microsoft Teams depende de SharePoint Online y OneDrive para la Empresa para almacenar archivos y documentos de canales y conversaciones de chat.  
   
Para habilitar toda la experiencia de acceso de invitado de Teams, los administradores de Office 365 tienen que seleccionar **Activado** en las siguientes opciones:

- En SharePoint Online: invitados existentes**, invitados nuevos y existentes**, o cualquiera
    
    Para obtener más información, vea [Activar o desactivar el uso compartido externo](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off).
    
- En los grupos de Office 365: **Let group owners add people outside the organization to groups** (Permitir que los propietarios de grupo agreguen a los grupos personas externas a la organización)
    
    Para obtener más información, vea [Controlar el acceso de invitados a Grupos de Office 365](#control-guest-access-in-office-365-groups) más arriba.
  
Esta configuración se aplica a nivel de espacio empresarial y controla la experiencia de invitado en SharePoint Online, OneDrive para la Empresa, Grupos de Office 365 y Teams.

La configuración de usuarios externos de SharePoint Online se puede administrar para el sitio de equipos conectados a Teams. Si desea más detalles, vea [Administrar la configuración de su sitio de grupo de SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).﻿

## <a name="guest-access-vs-external-access-federation"></a>Diferencias entre el acceso de invitados y el acceso externo (federación)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
