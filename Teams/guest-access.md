---
title: Acceso de invitado en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: Con el acceso de invitado en Microsoft Teams, los equipos de su organización pueden colaborar con personas que no pertenecen a la organización al concederles acceso a equipos y canales.
ms.openlocfilehash: cab51fd9cf0a81c849a0baf379150ccb2e08d818
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030286"
---
# <a name="guest-access-in-microsoft-teams"></a>Acceso de invitado en Microsoft Teams

Con el acceso como invitado, puede proporcionar acceso a los equipos, documentos de canales, recursos, chats y aplicaciones a personas de fuera de su organización, a la vez que mantiene el control sobre sus datos empresariales.

Un invitado es un usuario que no es empleado, estudiante ni es un miembro de su organización. Tampoco tiene una cuenta profesional o educativa con su organización. Por ejemplo, los invitados pueden incluir socios, proveedores o consultores. Cualquier persona que no forma parte de su organización puede agregarse como invitado en Teams. Esto significa que cualquier persona que tenga una cuenta empresarial (es decir, una cuenta de Azure Active Directory) o una cuenta de correo electrónico de consumidor (con Outlook.com, Gmail.com u otros) puede participar como invitado en Teams, con acceso a los equipos y a las experiencias de los canales.

Como administrador de equipos, usted [controla las características que los invitados pueden usar en Teams (y no)](manage-guests.md). Los invitados de los equipos están cubiertos por la misma protección de cumplimiento y cumplimiento que el resto de Microsoft 365, y se pueden administrar dentro de Azure AD. El acceso de invitado está sujeto a los límites de servicio de Azure AD y de Microsoft 365 u Office 365.

La experiencia de invitado tiene limitaciones deliberadamente establecidas. Para obtener una lista completa de lo que un invitado puede o no puede hacer en Teams, vea [comparación de las capacidades de miembro del equipo y de invitado](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

> [!IMPORTANT]
> Los usuarios invitados siguen la configuración a nivel de organización en Teams para el modo de Actualización en coexistencia. Esto no se puede cambiar.

Para comparar el acceso externo (federación) con el acceso de invitado (y decidir cuál de ellos debe usar), lea [Comunicarse con usuarios de otras organizaciones en Teams](communicate-with-users-from-other-organizations.md).

## <a name="set-up-guest-access"></a>Configurar el acceso de invitados

El acceso de invitados en Teams requiere establecer otras opciones de configuración en Microsoft 365, incluyendo la configuración de Azure AD, los grupos de Microsoft 365 y SharePoint. Si está listo para empezar a invitar a invitados a los equipos, lea una de las siguientes opciones:

- Para configurar el acceso de invitado para el uso general de Teams, consulte [colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).
- Para colaborar con una organización asociada que usa Azure Active Directory y permitir que los invitados realicen una inscripción automática para obtener acceso al equipo, consulte [crear una extranet B2B con invitados administrados](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).

El acceso de invitados en Teams es una configuración de toda la organización y está desactivado de forma predeterminada. Puede controlar el acceso de invitados a equipos individuales mediante el uso de [etiquetas de confidencialidad](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>Cómo un invitado se convierte en miembro de un equipo

1. Un propietario del equipo o un administrador de Microsoft 365 [agrega un invitado a un equipo](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. El invitado recibe un correo electrónico de bienvenida del dueño del equipo, con información sobre el equipo y qué esperar ahora que es miembro.
3. El invitado acepta la invitación.
  Los usuarios invitados que tengan una cuenta profesional o educativa en Azure Active Directory pueden aceptar la invitación y autenticar directamente. Se envía a otros usuarios un código de acceso único para validar su identidad (es necesaria la[autenticación de código de acceso de un solo uso](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) ).
4. Tras aceptar la invitación, el invitado puede [participar en los equipos y los canales](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), recibir mensajes del canal y responder a ellos, [acceder a los archivos de los canales](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participar en el chat, unirse a reuniones, colaborar en documentos, etc. 

En Teams, los invitados están claramente identificados. El nombre de usuario de un invitado incluye la etiqueta **(Invitado)** y un canal incluye un icono para indicar que hay invitados en el equipo. Para obtener más detalles, vea [Cómo es la experiencia de invitado](guest-experience.md).
  
Los invitados pueden dejar el equipo en cualquier momento dentro de Teams. Para obtener más información, consulte [¿Cómo abandono un equipo?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Si abandona el equipo, no se quita la cuenta de invitado del directorio de la organización. Esto debe realizarlo un administrador global de Microsoft 365 o un administrador de Azure AD.

## <a name="licensing-for-guest-access"></a>Licencias para acceso de invitado

El acceso de invitados se incluye en todas las suscripciones de Microsoft 365 Business Standard, Microsoft 365 Enterprise y Microsoft 365 Education. No es necesaria ninguna licencia adicional de Microsoft 365. Teams no limita el número de invitados que se pueden agregar. Sin embargo, es posible que el número total de invitados que se pueden agregar a su espacio empresarial esté restringido por las características de pago de Azure AD. Para obtener más información, consulte [modelo de facturación para identidades externas de Azure ad](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

> [!NOTE]
> Los usuarios de su organización que solo tienen planes de suscripción independientes de Microsoft 365, como Exchange Online plan 2, no pueden ser invitados a su organización porque Teams considera que los usuarios pertenecen a la misma organización. Para que estos usuarios puedan usar Teams, deben tener asignada una suscripción a Microsoft 365 Empresa Estándar, Office 365 Enterprise u Office 365 Education. 

## <a name="guest-access-reviews"></a>Revisiones de acceso de invitados

Puede usar Azure AD para crear una revisión de Access para miembros del grupo o usuarios asignados a una aplicación. Crear revisiones recurrentes de Access puede ahorrar tiempo. Si necesita revisar de forma rutinaria los usuarios que tienen acceso a una aplicación, un equipo o son miembros de un grupo, puede definir la frecuencia de dichas revisiones. 

Puede realizar una revisión de acceso de invitado, pedir a los invitados que revisen su propio miembro o pedirle al propietario de la aplicación o al responsable de la toma de decisiones que realice la revisión de Access. Use el portal de Azure para realizar revisiones de acceso de invitado. Para obtener más información, vea [administrar el acceso de invitados con revisiones de Access de Azure ad](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Temas relacionados

[Colaborar con personas fuera de la organización](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Bloquear usuarios invitados de un grupo de Microsoft 365 específico o de un equipo de Microsoft Teams](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Crear un entorno seguro de uso compartido de invitados](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Contactar al soporte técnico para productos empresariales: ayuda para administradores](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Configurar equipos con tres niveles de protección](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
