---
title: Agregar un invitado a un equipo
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: Los administradores pueden aprender a agregar nuevos invitados a una organización en clientes web y de escritorio de Microsoft Teams, así como en el portal de colaboración B2B de Azure Active Directory.
ms.openlocfilehash: 7f75589c5252998fb0389c743b951c0fe88e613b
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662445"
---
# <a name="add-a-guest-to-a-team"></a>Agregar un invitado a un equipo

Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook.com o Gmail.com) puede participar como invitado en Teams.

Como administrador, puede agregar un nuevo invitado a la organización de dos maneras:

- Los administradores globales o de Teams y los propietarios de equipo agregan un invitado a un equipo en los clientes de Teams o en el Centro de administración de Teams. Para obtener más información, consulte [Agregar invitados a un equipo](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Si aún no ha configurado el acceso de invitado, siga los pasos de [Colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

- Agregue invitados a la organización a través de la colaboración B2B de Azure Active Directory (Azure AD). Para obtener más información, [consulte Inicio rápido: Agregar invitados a su directorio en Azure Portal.](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)

Los administradores también pueden delegar permisos para agregar invitados a otras personas de su organización asignando el rol de invitado. Para más información, consulte [Habilitar la colaboración externa B2B y gestionar quién puede invitar a los invitados](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).

Con la colaboración B2B de Azure AD, las organizaciones pueden exigir que se cumplan las directivas de acceso condicional y autenticación multifactor (MFA) para los usuarios de B2B. Estas directivas se pueden exigir en el nivel de inquilino, aplicación o usuario individual, del mismo modo que pueden habilitarse para empleados a tiempo completo y miembros de la organización. Estas directivas se aplican en la organización de recursos. Para obtener más información, vea [Acceso condicional para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/?linkid=857454). No se pueden bloquear invitados individuales.

Los invitados que ya haya agregado a través de B2B de Azure AD, grupos de Microsoft 365 o SharePoint ya están listos. El administrador de Microsoft 365 o el propietario de un equipo puede agregar a esos invitados a sus respectivos equipos. Si agrega un invitado directamente al grupo de Microsoft 365 asociado con un equipo, el invitado tendrá acceso al equipo, pero el grupo de Microsoft 365 no genera un correo electrónico de invitación al invitado, por lo que alguien del equipo debe notificar al invitado.

> [!NOTE]
> Los invitados están sujetos a los límites de servicio de [Microsoft 365 u Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Puede llevar un registro de qué invitados se han agregado en Azure AD o en el Centro de seguridad de Microsoft 365. Cuando se agrega un invitado en Microsoft Teams, esta actividad se audita y se registra como actividad de administración del grupo de Azure AD "Added member to group" (Se ha agregado un miembro al grupo). Para obtener más información, consulte Auditoría e informes de un usuario de colaboración [B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) y Busque el registro de [auditoría en el Centro de cumplimiento.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)


## <a name="related-topics"></a>Temas relacionados

[Autorizar el acceso de invitado en Microsoft Teams](teams-dependencies.md)

[Activar o desactivar el acceso de invitado en Microsoft Teams](set-up-guests.md)
