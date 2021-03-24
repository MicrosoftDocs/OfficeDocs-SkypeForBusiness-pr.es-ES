---
title: Autorizar el acceso de invitado en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
- m365initiative-externalcollab
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: Administre las funcionalidades y las características de acceso de invitado de Microsoft Teams a través de cuatro niveles de autorización distintos.
ms.openlocfilehash: d52fdeb1f9867ac1faa0f8cf77023109155a8967
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094472"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>Autorizar el acceso de invitado en Microsoft Teams

Para satisfacer los requisitos de su organización, puede administrar las funcionalidades y las características de acceso de invitado de Teams a través de cuatro niveles de autorización distintos. Todos los niveles de autorización se aplican a la organización de Microsoft 365. Cada nivel de autorización controla la experiencia de invitado como se muestra a continuación:

- **Azure Active Directory**: el acceso de invitado en Teams depende de la plataforma negocio a negocio (B2B) de Azure AD. Este nivel de autorización controla la experiencia de invitado a nivel de directorio, espacio empresarial y aplicación.
- **Teams**: solo controla la experiencia de invitado en Teams.
- **Microsoft 365 Grupos**: controla la experiencia de invitado en los grupos de Microsoft 365 y Teams.
- **SharePoint y OneDrive**: controla la experiencia de invitado en SharePoint, OneDrive, Grupos de Microsoft 365 y Teams.

Estos niveles de autorización distintos proporcionan la flexibilidad necesaria para configurar el acceso de invitado para su organización. Por ejemplo, si no quiere permitir usuarios invitados en Teams pero sí en la organización en general, solo tiene que desactivar el acceso de invitado en Teams. Otro ejemplo: podría habilitar el acceso de invitado en los niveles de Azure AD, Teams y Grupos, pero [deshabilitaría la adición de usuarios invitados en equipos seleccionados que tengan un criterio o varios en común, como que la clasificación de datos es igual a confidencial](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). SharePoint Online y OneDrive tienen sus propias configuraciones de acceso de invitado que no se basan en los Grupos de Microsoft 365.

Para las instrucciones de configuración de acceso de invitado de extremo a extremo, consulte [Colaborar con invitados en un equipo](/microsoft-365/solutions/collaborate-as-team).

> [!NOTE]
> Los invitados se someten a los límites descritos en [Descripciones de servicios de Microsoft 365 y Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) y [Limitaciones de la colaboración B2B de Azure AD](/azure/active-directory/external-identities/current-limitations). 

En el siguiente diagrama se muestra cómo se concede y se integra la dependencia de autorización de acceso de invitado entre Azure Active Directory, Teams y Microsoft 365.

> [!div class="mx-imgBorder"]
> ![Diagrama de las dependencias de autorización para el acceso de invitado.](media/teams_dependencies_image1.png)

El siguiente diagrama muestra, de forma general, el funcionamiento de la experiencia del usuario con el modelo de permisos mediante una invitación de acceso de invitado y un flujo de aprobación comunes.

> [!div class="mx-imgBorder"]
> ![Diagrama de flujos de invitación y aceptación](media/authorize-guest-image1.png)

Es importante destacar que conectores, bots y aplicaciones a veces requieren su propio conjunto de permisos o consentimiento específicos de la cuenta de usuario. Puede que necesiten concederse por separado. De la misma manera, SharePoint puede imponer límites adicionales de uso compartido externo para un usuario específico, grupos de usuarios o incluso en el nivel del sitio.

Los dos diagramas anteriores también están disponibles en [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).

## <a name="control-guest-access-in-azure-active-directory"></a>Controlar el acceso de invitado en Azure Active Directory

Use Azure AD para determinar si los colaboradores externos pueden invitarse a su espacio empresarial como invitados y de qué maneras. Para más información sobre el acceso de invitados de Azure B2B, consulte [¿Qué es el acceso de usuarios invitados en Azure Active Directory B2B?](/azure/active-directory/b2b/what-is-b2b) Para obtener información acerca de las funciones de Azure AD, consulte [Conceder permisos a los usuarios de organizaciones asociadas en el espacio empresarial de Azure Active Directory](/azure/active-directory/b2b/add-guest-to-role).

La configuración de las invitaciones se aplica a nivel de organización y controla la experiencia de invitado a nivel de directorio y aplicación. Puede configurar esta configuración en [Configuración de la colaboración externa](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings).

Azure AD incluye las siguientes opciones para configurar usuarios externos:

- [Restricciones de acceso para los usuarios invitados](/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- **Los administradores y los usuarios con el rol Invitador de usuarios pueden invitar**: **Sí** significa que los administradores y usuarios con la función Invitador de usuarios podrán añadir invitar a usuarios en el espacio empresarial. **No** significa que los administradores y usuarios no pueden invitar a usuarios en el espacio empresarial.
- **Los miembros pueden invitar**: para permitir que los miembros de su directorio que no sean administradores inviten a otros usuarios, establezca esta directiva en **Sí** (recomendado). Si prefiere que solo los administradores puedan agregar invitados, puede establecer esta directiva en **No**. Tenga en cuenta que, al establecer **No**, se limitará la experiencia de invitado para los propietarios de equipos que no sean administradores. Solo podrán agregar invitados a los equipos que el administrador ya haya agregado en AAD.
- **Los invitados pueden invitar**: **Sí** significa que los invitados en el directorio pueden invitar a otros usuarios a colaborar en recursos protegidos por Azure AD, como sitios de SharePoint o recursos de Azure. **No** significa que los invitados no pueden invitar a otros invitados para colaborar con su organización. Incluso si establece que **Sí**, los invitados no podrán invitar a otros en Teams.
 
Para más información sobre el control de quién puede agregar invitados, consulte [Habilitar la colaboración externa B2B y gestionar quién puede invitar a los invitados](/azure/active-directory/b2b/delegate-invitations).

> [!NOTE]
> También puede administrar los dominios que se pueden invitar a su espacio empresarial como invitados. Consulte [Permitir o bloquear invitaciones a usuarios de B2B desde organizaciones específicas](/azure/active-directory/external-identities/allow-deny-list).

No es necesario agregar la cuenta de usuario invitado manualmente en Azure AD B2B, ya que la cuenta se agregará al directorio automáticamente al agregar al invitado a Teams.

### <a name="licensing-for-guest-access"></a>Licencias para acceso de invitado

La licencia para acceso de invitado usa los precios de Azure AD External Identities y se basa en los invitados activos mensuales. Consulte el [Modelo de facturación para Azure AD External Identities](/azure/active-directory/external-identities/external-identities-pricing) para obtener más detalles.

> [!NOTE]
> Los usuarios de su organización que solo tengan planes de suscripción de Office 365 independientes, como Exchange Online Plan 2, no pueden participar como invitados en su organización porque Teams considera que estos usuarios pertenecen a la misma organización. Para que estos usuarios puedan usar Teams, deben tener asignada una suscripción a Microsoft 365 Empresa Estándar, Office 365 Enterprise u Office 365 Education. 

## <a name="external-access-federation-vs-guest-access"></a>Acceso externo (federación) frente a acceso de invitado

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>Temas relacionados

- [Referencia de la configuración de uso compartido de invitados de Microsoft 365](/Office365/Enterprise/microsoft-365-guest-settings)

[Configurar la colaboración moderna con Microsoft 365](/microsoft-365/solutions/setup-secure-collaboration-with-teams)