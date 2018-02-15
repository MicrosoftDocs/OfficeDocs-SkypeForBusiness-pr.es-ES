---
title: Autorizar el acceso de invitado en Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.reviwer: laal
description: "Administre las funcionalidades y las características de acceso de invitado de Microsoft Teams a través de cuatro niveles de autorización distintos."
appliesto:
- Microsoft Teams
ms.openlocfilehash: de1ceee3b884b62680353eac11c94198024b927e
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2018
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Autorizar el acceso de invitado en Microsoft Teams
===========================================

Para satisfacer los requisitos de su organización, puede administrar las funcionalidades y las características de acceso de invitado de Microsoft Teams a través de cuatro niveles de autorización distintos. Todos los niveles de autorización se aplican a su inquilino de Office 365. Cada nivel de autorización controla la experiencia de invitado como se muestra a continuación:
- **Azure Active Directory**: el acceso de invitado en Microsoft Teams depende de la plataforma negocio a negocio (B2B) de Azure AD. Controla la experiencia de invitado a nivel de directorio, inquilino y aplicación. 
- **Microsoft Teams**: solo controla Microsoft Teams. 
- **Grupos de Office 365**: controla la experiencia de invitado en los Grupos de Office 365 y Microsoft Teams.
- **SharePoint Online y OneDrive para la Empresa**: controla la experiencia de invitado en SharePoint Online, OneDrive para la Empresa, Grupos de Office 365 y Microsoft Teams.

Estos niveles de autorización distintos proporcionan la flexibilidad necesaria para configurar el acceso de invitado para su organización. Por ejemplo, si no quiere permitir usuarios invitados en su organización de Microsoft Teams, solo tiene que desactivar el acceso de invitado en Microsoft Teams. Otro ejemplo: podría habilitar el acceso de invitado en los niveles de AAD, Teams y Grupos, pero deshabilitaría la adición de usuarios invitados en equipos seleccionados que tengan un criterio o varios en común, como que la clasificación de datos es igual a confidencial. Además, quizá no use Grupos de Office 365. SharePoint Online y OneDrive para la Empresa tienen su propia configuración de acceso de invitado que no depende de Grupos de Office 365. 

> [!NOTE]
> Los invitados están sujetos a los límites de servicio de [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019). 

  En el siguiente diagrama se muestra cómo se concede y se integra la dependencia de autorización de acceso de invitado entre Azure Active Directory, Microsoft Teams y Office 365.


![Diagrama de las dependencias de autorización para el acceso de invitado.](media/teams_dependencies_image1.png)


##<a name="azure-active-directory"></a>Azure Active Directory

Con la colaboración negocio a negocio (B2B) de Azure AD, el envío de invitaciones a posibles usuarios invitados no está restringido a los administradores de inquilinos. En su lugar, puede usar directivas para delegar el envío de invitaciones a los usuarios que tengan roles que les permitan hacerlo.

La configuración de las invitaciones se aplica a nivel de inquilino y controla la experiencia de invitado a nivel de directorio, inquilino y aplicación.


![Captura de pantalla de la configuración de usuario en el portal de Azure Active Directory.](media/teams_dependencies_image2.png)


Puede establecer las siguientes directivas de invitación:
- Desactivar invitaciones.
- Solo pueden invitar los administradores y los usuarios que tengan el rol de invitador de usuarios.
- Pueden invitar los administradores, el rol de invitador de usuarios y los miembros.
- Pueden invitar todos los usuarios, incluidos los invitados. (Esta es la directiva predeterminada para los inquilinos).


##<a name="microsoft-teams"></a>Microsoft Teams

En Microsoft Teams, puede controlar si la experiencia de invitado está habilitada o deshabilitada en su organización. La configuración está deshabilitada de forma predeterminada y se aplica en el nivel de inquilino para Microsoft Teams solo.



Puede administrar la configuración del acceso de invitado de Microsoft Teams desde el Centro de administración de Office 365. Si desea más información, consulte [Activar o desactivar el acceso de invitado para Microsoft Teams](set-up-guests.md). 


##<a name="office-365-groups"></a>Grupos de Office 365

Desde Grupos de Office 365, puede controlar la adición de usuarios invitados y el acceso de invitado a todos los grupos de Office 365 y Microsoft Teams en su organización.

1. Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
  
2. En el menú de navegación, elija **Configuración** y luego **Servicios y complementos**.
    
  
3. Seleccione **Grupos de Office 365**.
    
     ![Grupos de Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. En la página de grupos de Office 365, configure el botón de alternancia en **Activado** o **Desactivado**, dependiendo de si quiere que los propietarios del equipo y el grupo que no pertenecen a la organización accedan a los grupos de Office 365. Pulse o haga clic en el botón de alternancia, cambie a **Activado** junto a **Let group owners add people outside the organization to groups** (Permitir que los propietarios de grupo agreguen a los grupos personas externas a la organización). Si cambia a Activado el botón de alternancia, verá otra opción para controlar si quiere que los propietarios de grupo y equipo puedan añadir personas externas a la organización a los grupos de Office 365 y Microsoft Teams. Establezca el botón de alternancia en Activado si desea que los propietarios de grupo y equipo agreguen usuarios invitados. ![La captura de pantalla muestra el panel Grupos de Office 365 con las opciones activadas para permitir que los miembros del grupo externos a la organización accedan al contenido del grupo y para permitir que los propietarios del grupo agreguen a los grupos personas que no pertenecen a la organización.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)




La configuración anterior se aplica a nivel de inquilino y controla la experiencia de invitado en Grupos de Office 365 y Microsoft Teams.


##<a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online y OneDrive para la Empresa

Microsoft Teams depende de SharePoint Online y OneDrive para la Empresa para almacenar archivos y documentos de canales y conversaciones de chat.  
  
    
    
Para habilitar toda la experiencia de acceso de invitado de Teams, los administradores de Office 365 tienen que seleccionar **Activado** en las siguientes opciones:
  
    
    

- En SharePoint Online: **Only allow sharing with external users already in the directory** (Permitir solo compartir con usuarios externos que ya estén en el directorio)
    
    Para obtener más información, consulte [Administrar el uso compartido externo en su entorno de SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).
    
  
- En los grupos de Office 365: **Let group owners add people outside the organization to groups** (Permitir que los propietarios de grupo agreguen a los grupos personas externas a la organización)
    
    Para obtener más información, consulte [Controlar el acceso de invitado a Microsoft Teams](#controlguest).
  

La configuración anterior se aplica a nivel de inquilino y controla la experiencia de invitado en SharePoint Online, OneDrive para la Empresa, Grupos de Office 365 y Microsoft Teams.


La configuración de usuarios externos de SharePoint Online se puede administrar para el sitio de equipos conectados a Teams. Si desea más detalles, vea [Administrar la configuración de su sitio de grupo de SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).﻿