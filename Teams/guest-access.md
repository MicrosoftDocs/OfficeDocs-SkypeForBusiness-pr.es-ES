---
title: Acceso de invitado en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Con el acceso de invitado en Microsoft Teams, los equipos de su organización pueden colaborar con personas que no pertenecen a la organización al concederles acceso a equipos y canales.
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67ddc045c04c1c3d8cb9bffa0ee15ebf71c70c2f
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656111"
---
<a name="guest-access-in-microsoft-teams"></a>Acceso de invitado en Microsoft Teams
======================================

El acceso de invitado le permite agregar usuarios individuales de fuera de la organización a los equipos y canales de Microsoft Teams. 

Para comparar el acceso externo (federación) con el acceso de invitado (y decidir cuál de ellos debe usar), lea [Comunicarse con usuarios de otras organizaciones en Teams](communicate-with-users-from-other-organizations.md).

Si está listo para activar el acceso de invitado en su organización, comience por la [Lista de comprobación de acceso de invitado](guest-access-checklist.md).

## <a name="guest-access-overview"></a>Introducción al acceso de invitados

Con el acceso de invitado, los equipos de su organización pueden colaborar con personas que no pertenecen a la organización al concederles acceso a equipos y canales existentes en Teams. Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook o Gmail) puede participar como invitado en Teams con acceso total a los chats, las reuniones y los archivos del equipo. Como administrador de Teams, puede controlar qué características pueden (y no pueden) usar los invitados en Teams. Para más información, consulte [Administrar el acceso de invitados](manage-guests.md).

El acceso de invitado es una configuración de Teams a nivel de toda la organización y se encuentra desactivada de forma predeterminada. El acceso de invitado está sujeto a los límites de servicio de Azure AD y de Microsoft 365 u Office 365.


> [!IMPORTANT]
> Los usuarios invitados siguen la configuración a nivel de organización en Teams para el modo de Actualización en coexistencia. Esto no se puede cambiar.

## <a name="licensing-for-guest-access"></a>Licencias para acceso de invitado

El acceso de invitados está incluido en todas las suscripciones de Microsoft 365 Empresa Estándar, Office 365 Enterprise y Office 365 Education. No se necesita ninguna otra licencia de Microsoft 365 u Office 365. Teams no limita el número de invitados que se pueden agregar. Sin embargo, es posible que el número total de invitados que se pueden agregar a su espacio empresarial esté restringido por las características de pago de Azure AD. Para obtener más información, vea [Licencia de colaboración de Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).


> [!NOTE]
> Los usuarios de su organización que solo tengan planes de suscripción de Microsoft 365 u Office 365 independientes, como Exchange Online Plan 2, no pueden participar como invitados en su organización porque Teams considera que estos usuarios pertenecen a la misma organización. Para que estos usuarios puedan utilizar Teams, se les debe asignar una suscripción a Microsoft 365 Empresa Estándar, Office 365 Enterprise o Office 365 Education. 

## <a name="who-is-a-guest"></a>¿Quién es un invitado?

Un invitado es un usuario que no es empleado, estudiante ni es un miembro de su organización. Tampoco tiene una cuenta profesional o educativa con su organización. Por ejemplo, los invitados pueden incluir socios, proveedores o consultores. Cualquier persona que no forma parte de su organización puede agregarse como invitado en Teams. Esto significa que cualquier usuario con una cuenta de empresa (es decir, una cuenta de Azure Active Directory) o una cuenta de correo electrónico de consumidor (con Outlook.com, Gmail.com u otros) puede participar como invitado en Teams con acceso completo a las experiencias de canales y equipos.

Para más información sobre qué pueden y no pueden hacer los invitados, lea [Autorización del acceso de invitado en Microsoft Teams](teams-dependencies.md). También puede consultar la tabla de [Comparación de funciones entre miembros del equipo e invitados](guest-experience.md#comparison-of-team-member-and-guest-capabilities). 

Por último, todos los invitados de Teams están protegidos con el mismo cumplimiento normativo y de auditorías que el resto de Microsoft 365 u Office 365. Además, los invitados se pueden administrar de forma segura dentro de Azure AD.

## <a name="why-use-guest-access"></a>¿Por qué usar el acceso de invitado?

Con el acceso de invitado, las organizaciones que utilizan Microsoft Teams pueden proporcionar acceso a sus socios para que accedan a equipos, documentos en canales, recursos, chats y aplicaciones, sin perder por ello el control total de sus datos corporativos. Todos los invitados de Teams están protegidos con el mismo cumplimiento normativo y de auditorías que el resto de Microsoft 365 u Office 365. Además, los invitados se pueden administrar de forma segura dentro de Azure AD.  

## <a name="understand-the-limitations-for-guests"></a>Comprender las limitaciones para los invitados

La experiencia de invitado tiene limitaciones deliberadamente establecidas. Asegúrese de comprender la experiencia de invitado para no intentar solucionar algo que no sea realmente un problema. Por ejemplo, aquí tiene una lista de algunas de las funciones que no están disponibles para un invitado en Microsoft Teams:

- OneDrive para la Empresa
- Búsqueda de personas fuera de Teams
- Calendario, Reuniones programadas o Detalles de la reunión
- RTC
- Organigrama
- Crear o revisar un equipo
- Explorar en un equipo
- Cargar archivos en un chat entre personas
- Actualmente, Teams solo admiten los tipos de estado 1 y estado 2 de usuarios invitados [definido por Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)

Para obtener una lista completa de qué puede y no puede hacer un invitado en Teams, vea la tabla de [comparación entre las funciones de los miembros del equipo y los invitados](guest-experience.md#comparison-of-team-member-and-guest-capabilities). Para obtener más información sobre el acceso de invitados en el nivel de Microsoft 365 y Office 365, lea [Agregar invitados a Microsoft 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).


## <a name="more-information"></a>Más información

[Contactar al soporte técnico para productos empresariales: ayuda para administradores](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)  
[Acceso de invitados a Microsoft 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
