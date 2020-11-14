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
ms.openlocfilehash: 40bc8c68ac3f1ad3117fa47aa0aad5f14ff3be69
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030996"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>Autorizar el acceso de invitado en Microsoft Teams

Para cumplir los requisitos de la organización, puede administrar las características y funciones de acceso de invitados de Teams a través de cuatro niveles diferentes de autorización. Todos los niveles de autorización se aplican a su organización de 365 de Microsoft. Cada nivel de autorización controla la experiencia de invitado como se muestra a continuación:

- **Azure Active Directory** : el acceso de invitado en Teams depende de la plataforma empresa-to-Business (B2B) de Azure ad. Este nivel de autorización controla la experiencia de invitado a nivel de directorio, espacio empresarial y aplicación.
- **Teams** : controla la experiencia de invitado solo en Teams.
- **Microsoft 365 Groups** : controla la experiencia de invitado en grupos y equipos de Microsoft 365.
- **SharePoint y onedrive** : controla la experiencia de invitado en SharePoint, Onedrive, Microsoft 365 Groups y Teams.

Estos niveles de autorización distintos proporcionan la flexibilidad necesaria para configurar el acceso de invitado para su organización. Por ejemplo, si no desea permitir que los usuarios invitados estén en Teams pero desea permitir el acceso general a su organización, desactive el acceso de invitados en Teams. Otro ejemplo: puede habilitar el acceso de invitado en los niveles de Azure AD, Teams y Groups, pero, a continuación, [deshabilitar la adición de usuarios invitados en determinados equipos que coincidan con uno o más criterios, como la clasificación de datos sea igual a confidencial](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). SharePoint y OneDrive tienen su propia configuración de acceso de invitado que no dependen de los grupos de Microsoft 365.

Para obtener instrucciones de configuración de acceso de invitado de principio a fin, consulte [colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

> [!NOTE]
> Los invitados se someten a los límites descritos en [Descripciones de servicios de Microsoft 365 y Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Limitaciones de la colaboración B2B de Azure AD](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations). 

En el siguiente diagrama se muestra cómo se otorga e integrado la dependencia de autorización de acceso de invitados entre Azure Active Directory, Teams y Microsoft 365.

> [!div class="mx-imgBorder"]
> ![Diagrama de las dependencias de autorización para el acceso de invitado.](media/teams_dependencies_image1.png)

El siguiente diagrama muestra, de forma general, el funcionamiento de la experiencia del usuario con el modelo de permisos mediante una invitación de acceso de invitado y un flujo de aprobación comunes.

> [!div class="mx-imgBorder"]
> ![Diagrama de flujos de invitación y aceptación](media/authorize-guest-image1.png)

Es importante tener en cuenta que las aplicaciones, los bots y los conectores pueden requerir su propio conjunto de permisos y/o el consentimiento específico de la cuenta de usuario. Puede que necesiten concederse por separado. De la misma manera, SharePoint puede imponer límites adicionales de uso compartido externo para un usuario específico, grupos de usuarios o incluso en el nivel del sitio.

Los dos diagramas anteriores también están disponibles en [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).

## <a name="control-guest-access-in-azure-active-directory"></a>Controlar el acceso de invitado en Azure Active Directory

Use Azure AD para determinar si los colaboradores externos pueden invitarse a su espacio empresarial como invitados y de qué maneras. Para más información sobre el acceso de invitados de Azure B2B, consulte [¿Qué es el acceso de usuarios invitados en Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) Para obtener información acerca de las funciones de Azure AD, consulte [Conceder permisos a los usuarios de organizaciones asociadas en el espacio empresarial de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).

La configuración de las invitaciones se aplica a nivel de la organización y controla la experiencia de invitado en el directorio y en el nivel de aplicación. Puede establecer esta configuración en la [configuración de colaboración externa](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings).

Azure AD incluye las siguientes opciones para configurar usuarios externos:

- [Restricciones de acceso de usuarios invitados](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- **Los administradores y los usuarios con el rol Invitador de usuarios pueden invitar** : **Sí** significa que los administradores y usuarios con la función Invitador de usuarios podrán añadir invitar a usuarios en el espacio empresarial. **No** significa que los administradores y usuarios no pueden invitar a usuarios en el espacio empresarial.
- **Los miembros pueden invitar** : para permitir que los miembros de su directorio que no sean administradores inviten a otros usuarios, establezca esta directiva en **Sí** (recomendado). Si prefiere que solo los administradores puedan agregar invitados, puede establecer esta directiva en **No**. Tenga en cuenta que, al establecer **No** , se limitará la experiencia de invitado para los propietarios de equipos que no sean administradores. Solo podrán agregar invitados a los equipos que el administrador ya haya agregado en AAD.
- **Los invitados pueden invitar** : **Sí** significa que los invitados en el directorio pueden invitar a otros usuarios a colaborar en recursos protegidos por Azure AD, como sitios de SharePoint o recursos de Azure. **No** significa que los invitados no pueden invitar a otros invitados para colaborar con su organización. Incluso si se establece en **sí** , los invitados no pueden invitar a otros invitados de Teams.
 
Para obtener más información sobre cómo controlar quién puede invitar a invitados, consulte [Habilitar la colaboración externa B2B y administrar quién puede invitar a invitados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).

> [!NOTE]
> También puede administrar los dominios que se pueden invitar a su espacio empresarial como invitados. Consulte [permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list).

No es necesario agregar la cuenta de usuario invitado manualmente en Azure AD B2B, ya que la cuenta se agregará al directorio automáticamente al agregar al invitado a Teams.

### <a name="licensing-for-guest-access"></a>Licencias para acceso de invitado

Licencias de acceso de invitado usa el precio de identidades externas de Azure AD y se basa en los invitados activos mensuales. Consulte [modelo de facturación para](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) obtener más información sobre las identidades externas de Azure ad.

> [!NOTE]
> Los usuarios de su organización que solo tengan planes de suscripción de Office 365 independientes, como Exchange Online Plan 2, no pueden participar como invitados en su organización porque Teams considera que estos usuarios pertenecen a la misma organización. Para que estos usuarios puedan usar Teams, deben tener asignada una suscripción a Microsoft 365 Empresa Estándar, Office 365 Enterprise u Office 365 Education. 

## <a name="external-access-federation-vs-guest-access"></a>Acceso externo (federación) frente a acceso de invitado

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>Temas relacionados

- [Referencia de la configuración de uso compartido de invitados de Microsoft 365](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[Configurar una colaboración segura con Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
