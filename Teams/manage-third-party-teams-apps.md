---
title: Administrar el acceso a Teams aplicaciones en Microsoft 365
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Administre el acceso a Teams aplicaciones en Microsoft 365.
ms.openlocfilehash: 981dd4a36cad46085aa7e620ea893f5b62bbaa96
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584333"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Administrar el acceso a Teams aplicaciones en Microsoft 365

Los desarrolladores de aplicaciones pueden actualizar sus aplicaciones Microsoft Teams para que funcionen en Outlook y en Office.com, además de la aplicación que trabaja en Teams. Los usuarios finales pueden usar las aplicaciones actualizadas en Teams, en Microsoft Outlook y Microsoft Office.com después de la actualización. Actualmente, solo los usuarios finales de la versión dirigida pueden ver y usar estas aplicaciones específicas en Teams, Outlook y Office.com. La experiencia Teams administrador existente se aplica para gobernar el acceso a estas aplicaciones. Una notificación sobre este cambio está disponible en el centro [de mensajes](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Como administrador Teams, puede permitir que usuarios finales específicos usen las aplicaciones actualizadas o administren su acceso a las aplicaciones actualizadas en Teams, en Outlook y en Office.com. Teams administradores usan el centro Teams administración para administrar el acceso de aplicaciones.

Para su uso en Outlook y Office.com, una aplicación actualizada sigue utilizando los permisos existentes concedidos en Teams. No hay [ningún cambio en los permisos de la aplicación actualizada](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Puede controlar el acceso de los usuarios finales a Teams aplicaciones con los siguientes métodos. Si es administrador de Office aplicaciones, póngase en contacto con su administrador global o Teams administrador de aplicaciones para administrar el acceso a la aplicación.

| Opciones para administrar el acceso |Portal|Administrador global|Teams administrador|
|--|---|---|--|
| Solo los usuarios finales de la versión dirigida pueden acceder a la nueva aplicación. Mover los usuarios a la versión estándar. Consulte [Configurar las opciones de versión estándar o dirigida](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Centro de administración de Microsoft 365 | Sí | No |
| Administre el acceso a la nueva aplicación para usuarios finales específicos. Vea [Agregar una directiva de permisos personalizada y](teams-app-permission-policies.md#create-a-custom-app-permission-policy) [asignar la directiva personalizada a un usuario](policy-assignment-overview.md). | Teams de administración | Sí | Sí |
| Administre el acceso a las nuevas aplicaciones para todos los usuarios finales de su organización. Consulte [Permitir o bloquear aplicaciones](manage-apps.md#allow-and-block-apps). | Teams de administración | Sí | Sí |

> [!NOTE]
> Se recomienda usar [la opción versión estándar para](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) administrar el acceso de los usuarios finales. Las otras opciones quitan el acceso del usuario final y ya no podrán usar la aplicación existente en Teams.

> [!NOTE]
> Los usuarios que han instalado un complemento existente en el mercado de la misma aplicación en Outlook y Office seguirán usando esa aplicación. Los complementos no se Teams aplicaciones y Teams administradores no pueden gobernar el acceso.

A continuación se muestra una lista de aplicaciones actualizadas que funcionan en Microsoft 365 superficies:

* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)

## <a name="see-also"></a>Vea también

* [Comprender los roles de administrador en Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Acerca Outlook complementos](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Cómo los desarrolladores extienden Teams aplicaciones para trabajar en Microsoft 365](/microsoftteams/platform/m365-apps/overview)
