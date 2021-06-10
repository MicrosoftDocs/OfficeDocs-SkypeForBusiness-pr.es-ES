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
description: Los administradores pueden aprender a agregar nuevos invitados a una organización Microsoft Teams clientes web y de escritorio y Azure Active Directory portal de colaboración B2B.
ms.openlocfilehash: 1d44aff9b62a5ba6de7c22499f5a20f187d7781b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109086"
---
# <a name="add-a-guest-to-a-team"></a>Agregar un invitado a un equipo

Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook.com o Gmail.com) puede participar como invitado en Teams.

Como administrador, puede agregar un nuevo invitado a la organización de varias maneras:

- Los administradores globales o de Teams y los propietarios de equipo agregan un invitado a un equipo en los clientes de Teams o en el Centro de administración de Teams. Para obtener más información, consulte [Agregar invitados a un equipo](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Si aún no ha configurado el acceso de invitado, siga los pasos de [Colaborar con invitados en un equipo](/microsoft-365/solutions/collaborate-as-team).

- Agregue invitados a la organización a través de la colaboración B2B de Azure Active Directory (Azure AD). Para obtener más información, consulte [Inicio rápido: Agregar invitados a su directorio en Azure Portal.](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)

Los administradores también pueden delegar permisos para agregar invitados a otras personas de su organización asignando el rol de invitado. Para más información, consulte [Habilitar la colaboración externa B2B y gestionar quién puede invitar a los invitados](/azure/active-directory/external-identities/delegate-invitations).

Con la colaboración B2B de Azure AD, las organizaciones pueden exigir que se cumplan las directivas de acceso condicional y autenticación multifactor (MFA) para los usuarios de B2B. Estas directivas se pueden exigir en el nivel de inquilino, aplicación o usuario individual, del mismo modo que pueden habilitarse para empleados a tiempo completo y miembros de la organización. Estas directivas se aplican en la organización de recursos. Para obtener más información, vea [Acceso condicional para usuarios de colaboración B2B](/azure/active-directory/external-identities/conditional-access). Los invitados individuales no se pueden bloquear.

Los invitados que ya haya agregado a través de Azure AD B2B, Microsoft 365 grupos o SharePoint ya están listos. El Microsoft 365 o el propietario de un equipo pueden agregarlos a sus respectivos equipos. Si agrega un invitado directamente al grupo de Microsoft 365 asociado a un equipo, el invitado tendrá acceso al equipo, pero el grupo de Microsoft 365 no genera un correo electrónico de invitación al invitado, por lo que alguien del equipo debe notificar al invitado.

> [!NOTE]
> Los invitados están sujetos a los límites de servicio de [Microsoft 365 u Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) y [Azure Active Directory](/azure/active-directory/external-identities/current-limitations).

Puede llevar un registro de qué invitados se han agregado en Azure AD o en el Centro de seguridad de Microsoft 365. Cuando se agrega un invitado en Microsoft Teams, esta actividad se audita y se registra como actividad de administración del grupo de Azure AD "Added member to group" (Se ha agregado un miembro al grupo). Para obtener más información, vea Auditoría e informes de un usuario de colaboración [B2B](/azure/active-directory/external-identities/auditing-and-reporting) y Buscar el registro de [auditoría en el Centro de cumplimiento.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)


## <a name="related-topics"></a>Temas relacionados

[Autorizar el acceso de invitado en Microsoft Teams](teams-dependencies.md)

[Activar o desactivar el acceso de invitado en Microsoft Teams](set-up-guests.md)