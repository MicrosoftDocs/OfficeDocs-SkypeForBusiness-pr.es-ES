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
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: Los administradores pueden obtener más información sobre cómo agregar nuevos usuarios invitados a una organización en clientes de escritorio y web de Microsoft Teams y en el portal de colaboración de Azure Active Directory B2B.
ms.openlocfilehash: e74819ba46af8a9f6bcf3b2198f78354bf7bfb79
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346181"
---
# <a name="add-a-guest-to-a-team"></a>Agregar un invitado a un equipo

Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook.com o Gmail.com) puede participar como invitado en Teams.

Como administrador, puede agregar un usuario invitado nuevo a la organización de dos formas:

- Los administradores globales o de Teams y los propietarios de equipo agregan un invitado a un equipo en los clientes de Teams o en el Centro de administración de Teams. Para obtener más información, consulte [Agregar invitados a un equipo](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Si aún no ha configurado el acceso de invitado, siga los pasos de [Colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

- Agregue invitados a la organización a través de la colaboración B2B de Azure Active Directory (Azure AD). Para obtener información detallada, consulte [QuickStart: agregar usuarios invitados a su directorio en el portal de Azure](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

Los administradores también pueden delegar permisos para agregar invitados a otras personas de su organización asignando el rol de invitado. Para más información, consulte [Habilitar la colaboración externa B2B y gestionar quién puede invitar a los invitados](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).

Con la colaboración B2B de Azure AD, las organizaciones pueden exigir que se cumplan las directivas de acceso condicional y autenticación multifactor (MFA) para los usuarios de B2B. Estas directivas se pueden exigir en el nivel de inquilino, aplicación o usuario individual, del mismo modo que pueden habilitarse para empleados a tiempo completo y miembros de la organización. Estas directivas se aplican en la organización de recursos. Para obtener más información, vea [Acceso condicional para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/?linkid=857454). No es posible bloquear a usuarios invitados particulares.

Los usuarios invitados que ya ha agregado mediante la B2B de Azure AD, los grupos de Microsoft 365 o SharePoint están listos para usar. El administrador de Microsoft 365 o el propietario de un equipo pueden agregar a esos invitados a sus respectivos equipos. Si agrega un invitado directamente al grupo de Microsoft 365 asociado a un equipo, el invitado obtendrá acceso al equipo pero el grupo Microsoft 365 no generará un correo electrónico de invitación al invitado, por lo que una persona del equipo debe notificar al invitado.

> [!NOTE]
> Los invitados están sujetos a los límites de servicio de [Microsoft 365 u Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Puede llevar un registro de qué invitados se han agregado en Azure AD o en el Centro de seguridad de Microsoft 365. Cuando se agrega un invitado en Microsoft Teams, esta actividad se audita y se registra como actividad de administración del grupo de Azure AD "Added member to group" (Se ha agregado un miembro al grupo). Para obtener más información, consulte [Auditoría e informes de un usuario de colaboración B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) y [Buscar en el registro de auditoría del centro de cumplimiento](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).


## <a name="related-topics"></a>Temas relacionados

[Autorizar el acceso de invitado en Microsoft Teams](teams-dependencies.md)

[Activar o desactivar el acceso de invitado en Microsoft Teams](set-up-guests.md)
