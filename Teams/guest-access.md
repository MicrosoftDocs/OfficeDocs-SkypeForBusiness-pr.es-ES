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
ms.localizationpriority: high
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
ms.openlocfilehash: d7f850855ab131267b20bae07b015127777a21f4
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "64839071"
---
# <a name="guest-access-in-microsoft-teams"></a>Acceso de invitado en Microsoft Teams

Con el acceso de invitado, puede proporcionar acceso a equipos, documentos de canales, recursos, chats y aplicaciones a personas que no pertenezcan a la organización, sin perder por ello el control sobre los datos corporativos. Consulte [Configurar la colaboración segura con Microsoft 365 y Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams). El acceso de invitado en Teams es una configuración a nivel de toda la organización que está activada de forma predeterminada. Puede controlar el acceso de invitado a equipos individuales mediante [etiquetas de confidencialidad](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!NOTE]
> Si solo quiere buscar, llamar, chatear y configurar reuniones con personas de otras organizaciones, use el [acceso externo](manage-external-access.md).

Un invitado es alguien que no tiene una cuenta profesional o educativa con su organización. Por ejemplo, los invitados pueden incluir socios, proveedores o consultores. Cualquier persona que no forma parte de su organización puede agregarse como invitado en Teams. Esto significa que cualquier usuario con una cuenta de empresa (es decir, una cuenta de Azure Active Directory) o una cuenta de correo electrónico de consumidor (con Outlook.com, Gmail.com u otros) puede participar como invitado en Teams con acceso a las experiencias de canales y equipos.

Cuando invita a un alguien a Teams, se crea una cuenta de invitado para esa persona en Azure Active Directory y está cubierto por la misma protección de cumplimiento y auditoría que otros usuarios de Microsoft 365. El acceso de invitado está sujeto a los límites de servicio Azure AD y Microsoft 365.

La experiencia de invitado tiene limitaciones de forma deliberada. Para obtener una lista completa de lo que un invitado puede y no puede hacer en Teams, vea [Acceso de invitado en Microsoft Teams](guest-experience.md).

> [!IMPORTANT]
> Los invitados siguen la configuración a nivel de organización en Teams para el Modo de actualización en coexistencia.

Para comparar el acceso externo (federación) con el acceso de invitado (y decidir cuál de ellos debe usar), lea [Comunicarse con usuarios de otras organizaciones en Teams](communicate-with-users-from-other-organizations.md).

Los canales compartidos ofrecen una alternativa al acceso de invitado, lo que le permite invitar a personas ajenas a su organización sin necesidad de una cuenta de invitado en Azure AD. Para comparar el acceso de invitado con los canales compartidos, consulte [Planear la colaboración externa](/microsoft-365/solutions/plan-external-collaboration).

Para configurar el acceso de invitado, consulte [Colaborar con invitados en un equipo](/microsoft-365/solutions/collaborate-as-team). 

## <a name="set-up-guest-access"></a>Configurar el acceso de invitado

El acceso de invitado en Teams requiere que se establezcan otras opciones de configuración en Microsoft 365, así como en Azure AD, Grupos de Microsoft 365 y SharePoint. Si quiere empezar a invitar a usuarios a los equipos, elija una de las siguientes opciones:

- Para configurar el acceso de invitado para Microsoft Teams para un uso general, consulte [Colaborar con invitados en un equipo](/microsoft-365/solutions/collaborate-as-team).
- Para colaborar con una organización asociada que usa Azure Active Directory y permitir que los invitados se inscriban a sí mismos para tener acceso al equipo, consulte [Crear una extranet de B2B con invitados administrados](/microsoft-365/solutions/b2b-extranet).

> [!NOTE]
> Si es administrador y tiene problemas con el acceso de invitado en Microsoft Teams, seleccione **Ejecutar pruebas** a continuación, lo cual rellenará el diagnóstico de acceso de invitado en el Centro de Administración de Microsoft 365. Estas pruebas comprobarán la configuración y recomendarán rápidamente los pasos a seguir para habilitar el acceso de invitado en el espacio empresarial.
>> [!div class="nextstepaction"]
>> [Ejecutar pruebas: acceso de invitado](https://aka.ms/TeamsGuestAccessDiagDMC)

## <a name="how-a-guest-gets-added-to-a-team"></a>Cómo se agrega un invitado a un equipo

1. El propietario del equipo o un administrador de Microsoft 365 [agrega un invitado a un equipo](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. El invitado recibe un correo electrónico de bienvenida de parte del propietario del equipo, con información sobre el equipo y qué se puede esperar ahora que ha sido agregado.
3. El invitado acepta la invitación.
  Los invitados que tengan una cuenta profesional o educativa en Azure Active Directory pueden aceptar la invitación y autenticarse directamente. A otros invitados se les enviará un código de acceso de un solo uso para validar su identidad (se requiere la [autenticación con un código de acceso de un solo uso](/azure/active-directory/external-identities/one-time-passcode)).
4. Tras aceptar la invitación, el invitado puede [participar en los equipos y los canales](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), recibir mensajes del canal y responder a ellos, [acceder a los archivos de los canales](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participar en el chat, unirse a reuniones, colaborar en documentos, etc. 

En Teams, los invitados están claramente identificados. El nombre de usuario de un invitado incluye la etiqueta **(Invitado)** y un canal incluye un icono para indicar que hay invitados en el equipo. Para obtener más detalles, vea [Cómo es la experiencia de invitado](guest-experience.md).
  
Los invitados pueden dejar el equipo en cualquier momento dentro de Teams. Para obtener más información, consulte [¿Cómo abandono un equipo?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Al salir del equipo, no se elimina la cuenta de invitado del directorio de la organización. Eso debe hacerlo un administrador global de Microsoft 365 o un administrador de Azure AD.

## <a name="licensing-for-guest-access"></a>Licencias para el acceso de invitado

El acceso de invitado está incluido en todas las suscripciones de Microsoft 365 Empresa Estándar, Microsoft 365 Enterprise y Microsoft 365 Educación. No se necesita ninguna otra licencia de Microsoft 365. El [modelo de facturación para Azure AD External Identities](/azure/active-directory/b2b/licensing-guidance) se aplica a los invitados de Microsoft 365. Solo las personas fuera de la organización pueden ser invitadas como invitados.

> [!NOTE]
> Teams no admite la conversión de una cuenta de invitado en una cuenta de miembro de Azure AD o la conversión de una cuenta de miembro de Azure AD en una cuenta de invitado.

## <a name="guest-access-reviews"></a>Revisiones de accesos de invitado

Puede usar Azure AD para crear una revisión de acceso para los usuarios que están en grupos o que se han asignado a una aplicación. Crear revisiones de acceso periódicas le ahorrará tiempo. Si necesita revisar, de manera periódica, los usuarios que tienen acceso a una aplicación, un equipo o un grupo, puede definir la frecuencia de esas revisiones. 

Puede realizar una revisión de acceso de invitado usted mismo, pedirles a los invitados que revisen su propio acceso, o pedirle al propietario de una aplicación o a uno de los responsables de la empresa que realicen la revisión de acceso. Use Azure Portal para realizar las revisiones de acceso de invitado. Para obtener más información, consulte [Administración del acceso de los invitados con las revisiones de acceso de Azure AD](/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Temas relacionados

[Colaborar con personas ajenas a la organización](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Bloquear el acceso de invitados a un grupo de Microsoft 365 o equipo de Microsoft Teams específico](/microsoft-365/solutions/per-group-guest-access)

[Crear un entorno seguro de uso compartido para invitados](/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Contactar con el soporte técnico para productos empresariales: ayuda para administradores](/microsoft-365/admin/contact-support-for-business-products)

[Configurar Teams con tres niveles de protección](/microsoft-365/solutions/configure-teams-three-tiers-protection)
