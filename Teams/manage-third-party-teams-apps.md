---
title: Administrar el acceso a las aplicaciones de Teams en Microsoft 365
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Obtenga información sobre cómo administrar el acceso a las aplicaciones de Teams en Microsoft 365.
ms.openlocfilehash: 73a90aec04b6e3dcccda6aa4902506ff9eacccc4
ms.sourcegitcommit: 117adad5224dbf84f53b98341cd6a899ffc4eab1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68673446"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Administrar el acceso a las aplicaciones de Teams en Microsoft 365

Los desarrolladores de aplicaciones pueden mejorar sus aplicaciones de Microsoft Teams para que funcionen en Outlook y en Office.com, además de la aplicación que funciona en Teams. Los usuarios finales pueden usar las aplicaciones mejoradas en Teams, en Microsoft Outlook y Microsoft Office.com después de la mejora. Actualmente, solo los usuarios finales de la versión dirigida pueden ver y usar estas aplicaciones específicas en Teams, Outlook y Office.com. La experiencia de administración de Teams existente se aplica para controlar el acceso a estas aplicaciones. Hay disponible una notificación sobre este cambio en el [centro de mensajes](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Como administrador de Teams, puede permitir que usuarios finales específicos usen las aplicaciones mejoradas o administren su acceso a las aplicaciones mejoradas en Teams, en Outlook y en Office.com. Los administradores de Teams usan el Centro de administración de Teams para administrar el acceso a la aplicación.

Para su uso en Outlook y Office.com, una aplicación mejorada sigue usando los permisos existentes concedidos en Teams. No hay [ningún cambio en los permisos de la aplicación mejorada](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Las aplicaciones mejoradas se enumeran a continuación:

* [Adobe Acrobat Sign](https://teams.microsoft.com/l/app/0f56a9d1-f502-40f9-a9e8-816d7adbb68b?source=app-details-dialog)
* [ELearning brains bigger brains](https://teams.microsoft.com/l/app/12345514-afee-abcd-acde-c5b34109abcd?source=app-details-dialog)
* [Bookings](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=app-details-dialog)
* [e2e-assure](https://teams.microsoft.com/l/app/8bdf3437-e038-4a93-abdc-00461630f6c3?source=app-details-dialog)
* [ESi-Tik](https://teams.microsoft.com/l/app/fe9627db-f23e-42b1-b454-d4d1ca5af33e?source=app-details-dialog)
* Lente
* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Mis adhesivos](https://teams.microsoft.com/l/app/46fae4d0-faf5-11e9-80f3-53ad33b77bce?source=app-details-dialog)
* [Herramientas de PDF](https://teams.microsoft.com/l/app/ca4b5141-5c46-47bc-a05e-2733d9bd69aa?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [Priority Matrix](https://teams.microsoft.com/l/app/5be2b320-a5b7-4221-893c-dee506e4e365?source=app-details-dialog)
* [Smart Connect para Jira](https://teams.microsoft.com/l/app/6402de97-ce33-4386-bf28-b37e9e139c09?source=app-details-dialog)
* [Programación próxima](https://teams.microsoft.com/l/app/bf280b0d-b87d-4158-9f2a-70b63674cd27?source=app-details-dialog)
* [Optimizar](https://teams.microsoft.com/l/app/aa6e7fb6-34ac-4947-9c13-3565c66e368b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* Asistente de transcripción TNA2
* [Umbiko](https://teams.microsoft.com/l/app/23fc1de6-dda0-4043-9ebb-a555e845843d?source=app-details-dialog)
* [Waldo](https://teams.microsoft.com/l/app/1d041f16-ab49-4627-bfda-6b60ad2cab6a?source=app-details-dialog)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)

Puede controlar el acceso del usuario final a las aplicaciones de Teams mediante los métodos siguientes. Si es administrador de aplicaciones de Office, póngase en contacto con su administrador global o con el administrador de Teams para administrar el acceso a la aplicación.

| Opciones para administrar el acceso |Portal|Administrador global|Administrador de Teams|
|--|---|---|--|
| Solo los usuarios finales de la versión dirigida pueden acceder a la nueva aplicación. Mueva los usuarios a la versión Estándar. Consulte [Configurar las opciones de versión estándar o dirigida](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Centro de administración de Microsoft 365 | Sí | No |
| Administre el acceso a la nueva aplicación para usuarios finales específicos. Vea [Agregar una directiva de permisos personalizados](teams-app-permission-policies.md#create-an-app-permission-policy) y [asignar la directiva personalizada a un usuario](policy-assignment-overview.md). | Centro de administración de Teams | Sí | Sí |
| Administre el acceso a las nuevas aplicaciones para todos los usuarios finales de su organización. Consulte [Permitir o bloquear aplicaciones](manage-apps.md#allow-and-block-apps). | Centro de administración de Teams | Sí | Sí |

> [!NOTE]
> Se recomienda usar [la opción de versión Estándar](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) para administrar el acceso del usuario final. Las otras opciones quitan el acceso del usuario final y ya no podrán usar la aplicación existente en Teams.

> [!NOTE]
> Los usuarios que hayan instalado complementos existentes en el mercado de la misma aplicación en Outlook y Office seguirán usando esa aplicación. Los complementos no son aplicaciones de Teams y los administradores de Teams no pueden controlar el acceso.

## <a name="related-articles"></a>Artículos relacionados

* [Aplicaciones de Microsoft Teams diseñadas para Microsoft 365 próximamente en versión preliminar para Outlook y Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Descripción de los roles de administrador en Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Acerca de los complementos de Outlook](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Cómo amplían los desarrolladores las aplicaciones de Teams para que funcionen en Microsoft 365](/microsoftteams/platform/m365-apps/overview)
