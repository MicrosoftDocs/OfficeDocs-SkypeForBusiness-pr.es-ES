---
title: Agregar un invitado a un equipo
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/23/2017
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: "Conozca las herramientas que un administrador tiene a su disposición para agregar usuarios invitados nuevos a una organización, incluidos los clientes web y de escritorio de Microsoft Teams y el portal de colaboración B2B de Azure Active Directory."
appliesto:
- Microsoft Teams
ms.openlocfilehash: 384572ee714d8fbf25f7b7640a4e5e9687324262
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2018
---
<a name="add-a-guest-to-a-team"></a>Agregar un invitado a un equipo
=====================

Solo se podrá agregar como usuario invitado a los usuarios que tengan una dirección de correo electrónico que corresponda a una cuenta profesional o educativa de Azure Active Directory u Office 365.


Como administrador, puede agregar un usuario invitado nuevo a la organización de dos formas: 
- Los administradores globales que sean propietarios de un equipo y los propietarios de un equipo pueden agregar un invitado a un equipo mediante los clientes web o de escritorio de Microsoft Teams.
- Agregue invitados a la organización a través de la colaboración B2B de Azure Active Directory. La colaboración B2B de Azure Active Directory permite a un administrador global invitar y autorizar a un conjunto de usuarios externos mediante la carga de un archivo de valores separados por comas (CSV) de no más de 2000 líneas en el portal de colaboración B2B. Para obtener más información, consulte [Colaboración de B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=826383).



Con la colaboración B2B de Azure Active Directory, las organizaciones pueden exigir que se cumplan las directivas de acceso condicional y autenticación multifactor (MFA) para los usuarios de B2B. Estas directivas se pueden aplicar al nivel de inquilino, aplicación o usuario individual, del mismo modo que se aplican para empleados a tiempo completo y miembros de la organización. Estas directivas se aplican en la organización de recursos. Para obtener más información, vea [Acceso condicional para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/?linkid=857454). No es posible bloquear a usuarios invitados particulares.



Los usuarios invitados que ya haya agregado a través de B2B de Azure Active Directory, los Grupos de Office 365 o SharePoint Online tienen todo listo. El administrador de Office 365 o el propietario de un equipo podrá agregar a esos invitados a sus respectivos equipos. Si un equipo ya está con un grupo de Office 365 y se agrega un invitado al grupo, el invitado tendrá acceso al equipo. Cuando se agrega un invitado a través del grupo de Office 365, el invitado no recibe ninguna invitación por correo electrónico, por lo que algún miembro del equipo tendrá que notificárselo.

> [!NOTE]
> Los invitados están sujetos a los límites de servicio de [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).



Se puede llevar un registro de qué invitados se han agregado en Azure Active Directory o en el Centro de seguridad y cumplimiento de Office 365. Cuando se agrega un invitado en Microsoft Teams, esta actividad se audita y se registra como actividad de administración del grupo de Azure AD "Added member to group" (Se ha agregado un miembro al grupo). Si desea más detalles, vea [Auditoría y generación de informes para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) y [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

