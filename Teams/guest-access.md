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
localization_priority: Priority
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
ms.openlocfilehash: 6bbee4609bad74fb89f98debadd3a37efc9b7759
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908994"
---
# <a name="guest-access-in-microsoft-teams"></a>Acceso de invitado en Microsoft Teams

Con el acceso de invitado, puede proporcionar acceso a equipos, documentos de canales, recursos, chats y aplicaciones a personas que no pertenezcan a la organización, sin perder por ello el control sobre los datos corporativos.

Un invitado es un usuario que no es empleado, estudiante ni es un miembro de su organización. Tampoco tiene una cuenta profesional o educativa con su organización. Por ejemplo, los invitados pueden incluir socios, proveedores o consultores. Cualquier persona que no forma parte de su organización puede agregarse como invitado en Teams. Esto significa que cualquier usuario con una cuenta de empresa (es decir, una cuenta de Azure Active Directory) o una cuenta de correo electrónico de consumidor (con Outlook.com, Gmail.com u otros) puede participar como invitado en Teams con acceso a las experiencias de canales y equipos.

Los invitados de Teams están protegidos por los mismos cumplimientos normativos y auditorías que el resto de Microsoft 365 y pueden administrarse de forma segura en Azure AD. El acceso de invitado está sujeto a los límites de servicio de Azure AD y de Microsoft 365 u Office 365.

La experiencia de invitado tiene limitaciones deliberadamente establecidas. Para obtener una lista completa de qué puede y no puede hacer un invitado en Teams, vea la [comparación entre las funciones de los miembros del equipo y los invitados](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

> [!IMPORTANT]
> Los invitados siguen la configuración a nivel de organización en Teams para el modo de Actualización en coexistencia. Esto no se puede cambiar.

Para configurar el acceso de invitado, consulte [Colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team). 

Para comparar el acceso externo (federación) con el acceso de invitado (y decidir cuál de ellos debe usar), lea [Comunicarse con usuarios de otras organizaciones en Teams](communicate-with-users-from-other-organizations.md).

## <a name="set-up-guest-access"></a>Configurar el acceso de invitado

El acceso de invitado en Teams requiere que se establezcan otras opciones de configuración en Microsoft 365, así como en Azure AD, Grupos de Microsoft 365 y SharePoint. Si quiere empezar a invitar a usuarios a los equipos, elija una de las siguientes opciones:

- Para configurar el acceso de invitado para Microsoft Teams para un uso general, consulte [Colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).
- Para colaborar con una organización asociada que usa Azure Active Directory y permitir que los invitados se inscriban a sí mismos para tener acceso al equipo, consulte [Crear una extranet de B2B con invitados administrados](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).

El acceso de invitado en Microsoft Teams es una configuración a nivel de toda la organización y está desactivada de forma predeterminada. Puede controlar el acceso de invitado a equipos individuales mediante [etiquetas de confidencialidad](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>Cómo un invitado se convierte en miembro de un equipo

1. El propietario del equipo o un administrador de Microsoft 365 [agrega un invitado a un equipo](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. El invitado recibe un correo electrónico de bienvenida del dueño del equipo, con información sobre el equipo y qué esperar ahora que es miembro.
3. El invitado acepta la invitación.
  Los invitados que tengan una cuenta profesional o educativa en Azure Active Directory pueden aceptar la invitación y autenticarse directamente. A otros invitados se les enviará un código de acceso de un solo uso para validar su identidad (se requiere la [autenticación con un código de acceso de un solo uso](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode)).
4. Tras aceptar la invitación, el invitado puede [participar en los equipos y los canales](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), recibir mensajes del canal y responder a ellos, [acceder a los archivos de los canales](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participar en el chat, unirse a reuniones, colaborar en documentos, etc. 

En Teams, los invitados están claramente identificados. El nombre de usuario de un invitado incluye la etiqueta **(Invitado)** y un canal incluye un icono para indicar que hay invitados en el equipo. Para obtener más detalles, vea [Cómo es la experiencia de invitado](guest-experience.md).
  
Los invitados pueden dejar el equipo en cualquier momento dentro de Teams. Para obtener más información, consulte [¿Cómo abandono un equipo?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Al salir del equipo, no se elimina la cuenta de invitado del directorio de la organización. Eso debe hacerlo un administrador global de Microsoft 365 o un administrador de Azure AD.

## <a name="licensing-for-guest-access"></a>Licencias para el acceso de invitado

El acceso de invitado está incluido en todas las suscripciones de Microsoft 365 Empresa Estándar, Microsoft 365 Enterprise y Microsoft 365 Educación. No se necesita ninguna otra licencia de Microsoft 365. Teams no limita el número de invitados que se pueden agregar. Sin embargo, es posible que el número total de invitados que se pueden agregar a su espacio empresarial esté restringido por las características de pago de Azure AD. Para obtener más información, consulte el [Modelo de facturación para Azure AD External Identities](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

> [!NOTE]
> Los usuarios de la organización que solo tengan planes de suscripción de Microsoft 365 independientes, como Exchange Online (plan 2), no pueden participar como invitados en la organización porque Teams considera que esos usuarios pertenecen a la misma organización. Para que esos usuarios puedan usar Teams, deben tener asignada una suscripción de Microsoft 365 Empresa Estándar, Office 365 Enterprise u Office 365 Educación. 

## <a name="guest-access-reviews"></a>Revisiones de accesos de invitado

Puede usar Azure AD para crear una revisión de acceso para los miembros del grupo o usuarios asignados a una aplicación. Crear revisiones de acceso periódicas le ahorrará tiempo. Si necesita revisar de forma rutinaria los usuarios que tienen acceso a una aplicación o a un equipo, o son miembros de un grupo, puede definir la frecuencia de dichas revisiones. 

Puede realizar una revisión de acceso de invitado usted mismo, pedirles a los invitados que revisen su propia pertenencia o pedirle al propietario de una aplicación o a uno de los responsables de la empresa que realicen la revisión de acceso. Use Azure Portal para realizar las revisiones de acceso de invitado. Para obtener más información, consulte [Administración del acceso de los invitados con las revisiones de acceso de Azure AD](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Temas relacionados

[Colaborar con personas ajenas a la organización](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Bloquear el acceso de invitados a un grupo de Microsoft 365 o equipo de Microsoft Teams específico](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Crear un entorno seguro de uso compartido para invitados](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Contactar con el soporte técnico para productos empresariales: ayuda para administradores](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Configurar Teams con tres niveles de protección](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
