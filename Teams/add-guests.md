---
title: Agregar un invitado a un equipo
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: sbhatta
description: Conozca las herramientas que un administrador tiene a su disposición para agregar usuarios invitados nuevos a una organización, incluidos los clientes web y de escritorio de Microsoft Teams y el portal de colaboración B2B de Azure Active Directory.
appliesto:
- Microsoft Teams
ms.openlocfilehash: efd44fade33f611148dc2ab4ca9afb4040705123
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772747"
---
<a name="add-a-guest-to-a-team"></a>Agregar un invitado a un equipo
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Cualquier usuario con una cuenta de correo electrónico empresariales o de clientes, como Outlook, Gmail u otras personas, puede participar como invitado en los equipos.


Como administrador, puede agregar un usuario invitado nuevo a la organización de dos formas: 
- Los administradores globales que sean propietarios de un equipo y los propietarios de un equipo pueden agregar un invitado a un equipo mediante los clientes web o de escritorio de Microsoft Teams.
- Agregue invitados a la organización a través de la colaboración B2B de Azure Active Directory. La colaboración B2B de Azure Active Directory permite a un administrador global invitar y autorizar a un conjunto de usuarios externos mediante la carga de un archivo de valores separados por comas (CSV) de no más de 2000 líneas en el portal de colaboración B2B. Para obtener más información, consulte [Colaboración de B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=826383).



Con la colaboración B2B de Azure Active Directory, las organizaciones pueden exigir que se cumplan las directivas de acceso condicional y autenticación multifactor (MFA) para los usuarios de B2B. Estas directivas se pueden aplicar al nivel de inquilino, aplicación o usuario individual, del mismo modo que se aplican para empleados a tiempo completo y miembros de la organización. Estas directivas se aplican en la organización de recursos. Para obtener más información, vea [Acceso condicional para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/?linkid=857454). No es posible bloquear a usuarios invitados particulares.



Los usuarios invitados que ya se ha agregado a través de Azure Active Directory B2B, grupos de Office 365 o SharePoint Online están listos para ir. El administrador de Office 365 o el propietario de un equipo podrá agregar a esos invitados a sus respectivos equipos. Si un equipo ya está con un grupo de Office 365 y se agrega un invitado al grupo, el invitado tendrá acceso al equipo. Cuando se agrega un invitado a través del grupo de Office 365, el invitado no recibe ninguna invitación por correo electrónico, por lo que algún miembro del equipo tendrá que notificárselo.

> [!NOTE]
> Los invitados están sujetos a los límites de servicio de [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).



Se puede llevar un registro de qué invitados se han agregado en Azure Active Directory o en el Centro de seguridad y cumplimiento de Office 365. Cuando se agrega un invitado en Microsoft Teams, esta actividad se audita y se registra como actividad de administración del grupo de Azure AD "Added member to group" (Se ha agregado un miembro al grupo). Si desea más detalles, vea [Auditoría y generación de informes para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) y [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="more-information"></a>Más información

[Autorizar el acceso de invitado en Microsoft Teams](teams-dependencies.md)</br>
[Activar o desactivar el acceso como invitado en Microsoft Teams](set-up-guests.md)</br>
[Usar PowerShell para controlar el acceso de invitados a un equipo](guest-access-powershell.md)