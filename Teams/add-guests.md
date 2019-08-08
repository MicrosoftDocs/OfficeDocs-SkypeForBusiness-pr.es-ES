---
title: Agregar un invitado a un equipo
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
localization_priority: Priority
description: Conozca las herramientas que un administrador tiene a su disposición para agregar usuarios invitados nuevos a una organización, incluidos los clientes web y de escritorio de Microsoft Teams y el portal de colaboración B2B de Azure Active Directory.
appliesto:
- Microsoft Teams
ms.openlocfilehash: acf62fe23a5b22f2cbe07e94e073037e1f95b041
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236324"
---
<a name="add-a-guest-to-a-team"></a>Agregar un invitado a un equipo
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook.com o Gmail.com) puede participar como invitado en Teams.

Como administrador, puede agregar un usuario invitado nuevo a la organización de dos formas:
- Los administradores globales que sean propietarios de un equipo y los propietarios de un equipo pueden agregar un invitado a un equipo mediante los clientes web o de escritorio de Microsoft Teams. Para obtener más detalles, consulte [Agregar invitados a un equipo](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)

> [!NOTE] 
> Esto no es aplicable cuando se activa que **los administradores y usuarios del rol Invitador de usuarios invitados puedan invitar**. La razón es que el rol de Invitador de usuarios invitados no es compatible con Teams.

- Agregue invitados a la organización a través de la colaboración B2B de Azure Active Directory (Azure AD). La colaboración B2B de Azure AD permite a un administrador global invitar y autorizar a un conjunto de usuarios externos mediante la carga de un archivo de valores separados por comas (CSV) de no más de 2 000 líneas en el portal de colaboración B2B. Para obtener más información, consulte [Colaboración de B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=826383).

Con la colaboración B2B de Azure AD, las organizaciones pueden exigir que se cumplan las directivas de acceso condicional y autenticación multifactor (MFA) para los usuarios de B2B. Estas directivas se pueden exigir en el nivel de inquilino, aplicación o usuario individual, del mismo modo que pueden habilitarse para empleados a tiempo completo y miembros de la organización. Estas directivas se aplican en la organización de recursos. Para obtener más información, vea [Acceso condicional para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/?linkid=857454). No es posible bloquear a usuarios invitados particulares.

Los usuarios invitados que ya haya agregado a través de B2B de Azure AD, los Grupos de Office 365 o SharePoint Online tienen todo listo. El administrador de Office 365 o el propietario de un equipo podrá agregar a esos invitados a sus respectivos equipos. Si un equipo ya está con un grupo de Office 365 y se agrega un invitado al grupo, el invitado tendrá acceso al equipo. Cuando se agrega un invitado a través del grupo de Office 365, el invitado no recibe ninguna invitación por correo electrónico, por lo que algún miembro del equipo tendrá que notificárselo.

> [!NOTE]
> Los invitados están sujetos a los límites de servicio de [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Se puede llevar un registro de qué invitados se han agregado en Azure AD o en el Centro de seguridad y cumplimiento de Office 365. Cuando se agrega un invitado en Microsoft Teams, esta actividad se audita y se registra como actividad de administración del grupo de Azure AD "Added member to group" (Se ha agregado un miembro al grupo). Si desea más detalles, vea [Auditoría y generación de informes para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) y [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="guest-access-vs-external-access-federation"></a>Diferencias entre el acceso de invitados y el acceso externo (federación)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Más información

[Autorizar el acceso de invitado en Microsoft Teams](teams-dependencies.md)</br>
[Activar o desactivar el acceso de invitado en Microsoft Teams](set-up-guests.md)</br>
[Usar PowerShell para controlar el acceso de invitados a un equipo](guest-access-powershell.md)
