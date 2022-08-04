---
title: Administrar el acceso a las aplicaciones de Teams en Microsoft 365
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
ms.localizationpriority: high
search.appverid: MET150
description: Obtenga información sobre cómo administrar el acceso a las aplicaciones de Teams en Microsoft 365.
ms.openlocfilehash: 4c6f12d6895bd9c11d240f460285d2aa8cf27cb4
ms.sourcegitcommit: a64574da14969a33a77c7d979ffde452b5b3a531
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175874"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Administrar el acceso a las aplicaciones de Teams en Microsoft 365

Los desarrolladores de aplicaciones pueden mejorar sus aplicaciones de Microsoft Teams para que funcionen en Outlook y en Office.com, además de la aplicación que funciona en Teams. Los usuarios finales pueden usar las aplicaciones mejoradas en Teams, en Microsoft Outlook y Microsoft Office.com después de la mejora. Actualmente, solo los usuarios finales de la versión dirigida pueden ver y usar estas aplicaciones específicas en Teams, Outlook y Office.com. La experiencia de administración de Teams existente se aplica para controlar el acceso a estas aplicaciones. Hay disponible una notificación sobre este cambio en el [centro de mensajes](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Como administrador de Teams, puede permitir que usuarios finales específicos usen las aplicaciones mejoradas o administren su acceso a las aplicaciones mejoradas en Teams, en Outlook y en Office.com. Los administradores de Teams usan el Centro de administración de Teams para administrar el acceso a la aplicación.

Para su uso en Outlook y Office.com, una aplicación mejorada sigue usando los permisos existentes concedidos en Teams. No hay [ningún cambio en los permisos de la aplicación mejorada](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

A continuación se muestra una lista de las aplicaciones mejoradas:

* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)

Puede controlar el acceso del usuario final a las aplicaciones de Teams mediante los métodos siguientes. Si es administrador de aplicaciones de Office, póngase en contacto con su administrador global o con el administrador de Teams para administrar el acceso a la aplicación.

| Opciones para administrar el acceso |Portal|Administrador global|Administrador de Teams|
|--|---|---|--|
| Solo los usuarios finales de la versión dirigida pueden acceder a la nueva aplicación. Mueva los usuarios a la versión Estándar. Consulte [Configurar las opciones de versión estándar o dirigida](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Centro de administración de Microsoft 365 | Sí | No |
| Administre el acceso a la nueva aplicación para usuarios finales específicos. Vea [Agregar una directiva de permisos personalizados](teams-app-permission-policies.md#create-a-custom-app-permission-policy) y [asignar la directiva personalizada a un usuario](policy-assignment-overview.md). | Centro de administración de Teams | Sí | Sí |
| Administre el acceso a las nuevas aplicaciones para todos los usuarios finales de su organización. Consulte [Permitir o bloquear aplicaciones](manage-apps.md#allow-and-block-apps). | Centro de administración de Teams | Sí | Sí |

> [!NOTE]
> Se recomienda usar [la opción de versión Estándar](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) para administrar el acceso del usuario final. Las otras opciones quitan el acceso del usuario final y ya no podrán usar la aplicación existente en Teams.

> [!NOTE]
> Los usuarios que hayan instalado complementos existentes en el mercado de la misma aplicación en Outlook y Office seguirán usando esa aplicación. Los complementos no son aplicaciones de Teams y los administradores de Teams no pueden controlar el acceso.

## <a name="see-also"></a>Vea también

* [Aplicaciones de Microsoft Teams diseñadas para Microsoft 365 próximamente en versión preliminar para Outlook y Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Descripción de los roles de administrador en Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Acerca de los complementos de Outlook](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Cómo amplían los desarrolladores las aplicaciones de Teams para que funcionen en Microsoft 365](/microsoftteams/platform/m365-apps/overview)
