---
title: Autorizar el acceso de invitado en Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 04/01/19
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Administre las funcionalidades y las características de acceso de invitado de Microsoft Teams a través de cuatro niveles de autorización distintos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87b0e6bf1f920ea4eaab4a4ed2bfb3f314b60601
ms.sourcegitcommit: 70d3a3b162fdbca1cf2c2713d6bce54c3cbad3bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026067"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Autorizar el acceso de invitado en Microsoft Teams
===========================================

Para satisfacer los requisitos de su organización, puede administrar las funcionalidades y las características de acceso de invitado de Microsoft Teams a través de cuatro niveles de autorización distintos. Todos los niveles de autorización se aplican a su inquilino de Office 365. Cada nivel de autorización controla la experiencia de invitado como se muestra a continuación:

- **Azure Active Directory**: el acceso de invitado en Microsoft Teams depende de la plataforma negocio a negocio (B2B) de Azure AD. Controla la experiencia de invitado a nivel de directorio, inquilino y aplicación. 
- **Microsoft Teams**: solo controla Microsoft Teams. 
- **Grupos de Office 365**: controla la experiencia de invitado en los Grupos de Office 365 y Microsoft Teams.
- **SharePoint Online y OneDrive para la Empresa**: controla la experiencia de invitado en SharePoint Online, OneDrive para la Empresa, Grupos de Office 365 y Microsoft Teams.

Estos niveles de autorización distintos proporcionan la flexibilidad necesaria para configurar el acceso de invitado para su organización. Por ejemplo, si no desea permitir que a los usuarios invitados de su Teams Microsoft pero desea permitir general de la organización, simplemente desactivar acceso de invitado en Microsoft Teams. Otro ejemplo: podría habilitar el acceso de invitado en los niveles de AAD, Teams y Grupos, pero deshabilitaría la adición de usuarios invitados en equipos seleccionados que tengan un criterio o varios en común, como que la clasificación de datos es igual a confidencial. SharePoint Online y OneDrive para la Empresa tienen su propia configuración de acceso de invitado que no depende de Grupos de Office 365. 

> [!NOTE]
> Los invitados están sujetos a los límites de servicio de [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019). 

En el siguiente diagrama se muestra cómo se concede y se integra la dependencia de autorización de acceso de invitado entre Azure Active Directory, Microsoft Teams y Office 365.

![Diagrama de las dependencias de autorización para el acceso de invitado.](media/teams_dependencies_image1.png)

El diagrama siguiente muestra, en un nivel alto, cómo funciona la experiencia del usuario con el modelo de permisos a través de un flujo de invitación y amortización de acceso de invitado típica.

![Diagrama de flujos de invitación y amortización de](media/authorize-guest-image1.png)

Es importante tener en cuenta aquí que es posible que requieren su propio conjunto de permisos o específicos de la cuenta de usuario de consentimiento conectores, bots y aplicaciones. Estos es posible que deba concederse por separado. De forma similar, SharePoint puede imponer extra externos límites uso compartidos para un usuario específico, grupos de usuarios, o incluso en el nivel de sitio.

## <a name="control-guest-access-in-azure-active-directory"></a>Controlar el acceso de invitado en Azure Active Directory

Use Azure AD para determinar si los colaboradores externos pueden ser invitados en el inquilino como invitados y de qué manera. Para obtener más información sobre el acceso de invitado B2B de Azure, vea [¿Qué es el acceso de usuarios invitado en Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b). Para obtener información acerca de las funciones de Azure AD, consulte [concesión de permisos a los usuarios de las organizaciones asociadas en el inquilino de Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/b2b/add-guest-to-role).

La configuración de las invitaciones se aplica a nivel de inquilino y controla la experiencia de invitado a nivel de directorio, inquilino y aplicación. 

![Captura de pantalla de la configuración de usuario en el portal de Azure Active Directory.](media/teams_dependencies_image2.png)

Azure AD incluye las siguientes opciones para configurar los usuarios externos:

- **Los permisos de usuario de invitado están limitados**: **Sí** significa que los invitados no tiene permiso para determinadas tareas de Active directory, como enumerar los usuarios, grupos u otros recursos de Active directory. Además, los invitados no se pueden asignar a las funciones administrativas en el directorio. **No** significa que los invitados tiene el mismo acceso a los datos de Active directory que tienen los usuarios regulares en el directorio.
- **Pueden invitar los administradores y usuarios de la función de autor de la invitación de invitado**: **Sí** significa que los administradores y usuarios de la función "Autor de la invitación invitado" podrán invitar a personas para el inquilino. **No** significa que los administradores y los usuarios no pueden invitar a los invitados en el inquilino.
- **Pueden invitar los miembros**: **Sí** significa que los miembros sin permisos de administrador del directorio de pueden invitar a los invitados puedan colaborar en recursos protegidos mediante la implementación de AD Azure, como sitios de SharePoint o los recursos de Azure. **No** significa que sólo los administradores pueden invitar a invitados a su directorio.</br>
      
    > [!NOTE]
    > Actualmente, los equipos no es compatible con el rol de autor de la invitación de invitado. como mínimo el **pueden invitar los miembros** de alternancia se debe establecer en **Sí** para el acceso de invitado para que funcionen en los equipos.
- **Pueden invitar los invitados**: **Sí** significa que los invitados en el directorio pueden ellos mismos invitar a otros invitados a colaborar en recursos protegidos mediante la implementación de AD Azure, como sitios de SharePoint o los recursos de Azure. **No** significa que los invitados no puede invitar a otros invitados para colaborar con su organización.
 
Para obtener más información acerca de cómo controlar quién puede invitar a los invitados, vea [las invitaciones de delegado para la colaboración B2B de Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/b2b/delegate-invitations)

> [!NOTE]
> También puede administrar qué dominios se pueden invitar a su inquilino como invitados. Vea [Permitir o bloquear el acceso de invitado a los grupos de Office 365](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups). 

Agregar la cuenta de usuario invitado manualmente a Azure AD B2B no es necesario, como la cuenta se agregará al directorio automáticamente cuando se agrega el invitado a los equipos. 

Licencias de Azure AD le permite agregar a hasta 5 invitados por licencia. Para obtener más información acerca de las licencias de Azure AD, vea la [orientación de licencias de colaboración de Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).

## <a name="control-guest-access-in-teams"></a>Controlar el acceso de invitado en los equipos

En los equipos, puede controlar si la experiencia de invitado está habilitada o deshabilitada para su organización. La configuración está deshabilitada de forma predeterminada y solo se aplica en el nivel de inquilino para los equipos.

Puede administrar la configuración de acceso de invitado de los equipos desde el centro de administración de Microsoft Teams. Si desea más información, consulte [Activar o desactivar el acceso de invitado para Microsoft Teams](set-up-guests.md). 


## <a name="control-guest-access-in-office-365-groups"></a>Controlar el acceso de invitado en grupos de Office 365

Desde Grupos de Office 365, puede controlar la adición de usuarios invitados y el acceso de invitado a todos los grupos de Office 365 y Microsoft Teams en su organización.

1. Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. En el menú de navegación, elija **Configuración** y luego **Servicios y complementos**.
    
3. Seleccione **Grupos de Office 365**.
    
     ![Grupos de Office 365](media/authorize-guest-image2.png)
  
4. En la página grupos de Office 365, establezca la alternancia para **activado** o **desactivado**, dependiendo de si desea permitir que los propietarios de equipo y grupo fuera de los grupos de acceso a Office 365 de la organización. Pulse o haga clic en el botón de alternancia, cambie a **Activado** junto a **Let group owners add people outside the organization to groups** (Permitir que los propietarios de grupo agreguen a los grupos personas externas a la organización). Si activa esta alternancia **activado**, verá otra opción para controlar si desea permitir que el grupo y los propietarios de equipo agregar personas externas a su organización a los grupos de Office 365 y los equipos de Microsoft. Establezca este alternancia **activado** si desea permitir que el grupo y los propietarios de equipo agregar los usuarios invitados. 
 
   ![La captura de pantalla muestra el panel Grupos de Office 365 con las opciones activadas para permitir que los miembros del grupo externos a la organización accedan al contenido del grupo y para permitir que los propietarios del grupo agreguen a los grupos personas que no pertenecen a la organización.](media/authorize-guest-image3.png)

Estas opciones se aplican en el nivel de inquilino y controlan la experiencia de invitado en grupos de Office 365 y Microsoft Teams.

Para obtener más información sobre el acceso de invitado en grupos, incluido cómo funciona el acceso como invitado, cómo administrar el acceso de invitado y respuestas a las preguntas más frecuentes, consulte [invitado acceso en grupos de Office 365](https://support.office.com/en-us/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) .

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a>Controlar el acceso de invitado a SharePoint Online y OneDrive para la empresa

Microsoft Teams depende de SharePoint Online y OneDrive para la Empresa para almacenar archivos y documentos de canales y conversaciones de chat.  
   
Para habilitar toda la experiencia de acceso de invitado de Teams, los administradores de Office 365 tienen que seleccionar **Activado** en las siguientes opciones:

- En SharePoint Online: **Only allow sharing with external users already in the directory** (Permitir solo compartir con usuarios externos que ya estén en el directorio)
    
    Para obtener más información, consulte [Administrar el uso compartido externo en su entorno de SharePoint Online](https://docs.microsoft.com/sharepoint/external-sharing-overview).
    
- En los grupos de Office 365: **Let group owners add people outside the organization to groups** (Permitir que los propietarios de grupo agreguen a los grupos personas externas a la organización)
    
    Para obtener más información, vea [controlar el acceso de invitado en Office 365 grupos](#control-guest-access-in-office-365-groups), anteriormente.
  
Estas opciones se aplican en el nivel de inquilino y controlan la experiencia de invitado en SharePoint Online, OneDrive para la empresa, Office 365 grupos y equipos.

La configuración de usuarios externos de SharePoint Online se puede administrar para el sitio de equipos conectados a Teams. Si desea más detalles, vea [Administrar la configuración de su sitio de grupo de SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).﻿

## <a name="guest-access-vs-external-access-federation"></a>Acceso de invitado frente a acceso externo (federación de)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]