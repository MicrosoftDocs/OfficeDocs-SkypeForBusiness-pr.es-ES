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
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: Los administradores pueden obtener más información sobre cómo agregar nuevos usuarios invitados a una organización en clientes de escritorio y web de Microsoft Teams y en el portal de colaboración de Azure Active Directory B2B.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 099e7a0a1fd7368385d564f46e2df12d5aced4b2
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656131"
---
<a name="add-a-guest-to-a-team"></a>Agregar un invitado a un equipo
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook.com o Gmail.com) puede participar como invitado en Teams.

Como administrador, puede agregar un usuario invitado nuevo a la organización de dos formas:
- Los administradores globales o de Teams y los propietarios de equipo agregan un invitado a un equipo en los clientes de Teams o en el Centro de administración de Teams. Para obtener más información, consulte [Agregar invitados a un equipo](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Si aún no configuró el acceso de invitado, siga los pasos de la [Lista de comprobación de acceso de invitado](guest-access-checklist.md).

> [!NOTE] 
> Esto no sirve cuando se activa que **los administradores y usuarios del rol Invitador de usuarios invitados puedan invitar**. La razón es que el rol de Invitador de usuarios invitados no es compatible con Teams.

- Agregue invitados a la organización a través de la colaboración B2B de Azure Active Directory (Azure AD). La colaboración B2B de Azure AD permite a un administrador global invitar y autorizar a un conjunto de usuarios externos mediante la carga de un archivo de valores separados por comas (CSV) de no más de 2 000 líneas en el portal de colaboración B2B. Para obtener más información, consulte [Colaboración de B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=826383).

Con la colaboración B2B de Azure AD, las organizaciones pueden exigir que se cumplan las directivas de acceso condicional y autenticación multifactor (MFA) para los usuarios de B2B. Estas directivas se pueden exigir en el nivel de inquilino, aplicación o usuario individual, del mismo modo que pueden habilitarse para empleados a tiempo completo y miembros de la organización. Estas directivas se aplican en la organización de recursos. Para obtener más información, vea [Acceso condicional para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/?linkid=857454). No es posible bloquear a usuarios invitados particulares.

Los usuarios invitados que ya ha agregado a través de Azure AD B2B, los Grupos de Microsoft 365, o SharePoint Online están listos. El administrador de Microsoft 365 u Office 365 o el propietario de un equipo podrá agregar a esos invitados a sus respectivos equipos. Si un equipo ya está con un grupo de Microsoft 365 y se agrega un invitado al grupo, el invitado tendrá acceso al equipo. Cuando se agrega un invitado a través del grupo de Microsoft 365, el invitado no recibe ninguna invitación por correo electrónico, por lo que algún miembro del equipo tendrá que notificárselo.

> [!NOTE]
> Los invitados están sujetos a los límites de servicio de [Microsoft 365 u Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Puede llevar un registro de qué invitados se han agregado en Azure AD o en el Centro de seguridad de Microsoft 365. Cuando se agrega un invitado en Microsoft Teams, esta actividad se audita y se registra como actividad de administración del grupo de Azure AD "Added member to group" (Se ha agregado un miembro al grupo). Si desea más detalles, vea [Auditoría y generación de informes para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) y [Buscar en el registro de auditoría del Centro de seguridad de Microsoft 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).


## <a name="more-information"></a>Más información

[Autorizar el acceso de invitado en Microsoft Teams](teams-dependencies.md)</br>
[Activar o desactivar el acceso de invitado en Microsoft Teams](set-up-guests.md)</br>
[Usar PowerShell para controlar el acceso de invitados a un equipo](guest-access-powershell.md)
