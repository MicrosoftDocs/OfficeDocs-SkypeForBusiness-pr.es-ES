---
title: Administrar la Prueba de Office 365 G1 gratuita para el gobierno de Estados Unidos
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aarimm
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: high
description: Para el gobierno de Estados Unidos, si no tiene Microsoft Teams y lo necesita urgentemente, implemente la Prueba de Office 365 G1 para los usuarios que necesiten trabajar de forma remota o desde casa (WFH) en respuesta al brote de COVID-19 (coronavirus).
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d45869d015dc5486d3971bff5795cb0cc791dd5c
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377328"
---
# <a name="manage-the-office-365-g1-trial-for-us-government"></a>Administrar la Prueba de Office 365 G1 para el gobierno de Estados Unidos 

A partir del 1 de julio de 2020, la licencia de prueba de Office 365 E1 ya no está disponible. Si necesita obtener una licencia de Microsoft Teams para los usuarios, consulte la [descripción del servicio de Microsoft Teams](/office365/servicedescriptions/teams-service-description) para obtener una lista de suscripciones de pago que incluyan Teams. 

Use las instrucciones de este artículo para administrar las licencias de prueba de Office 365 G1 existentes, incluida [la actualización a una suscripción de pago](#upgrade-users-from-the-office-365-g1-trial-license). Para obtener información, consulte los [Planes de Microsoft 365 Administración Pública](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans) y las [funciones de Microsoft Teams disponibles en la nube GCC](plan-for-government-gcc.md).

No se pierda todas nuestras instrucciones para [dar soporte a los trabajadores remotos que utilicen Teams](support-remote-work-with-teams.md).

## <a name="manage-the-g1-trial"></a>Administrar la Prueba de G1

Después de activar la Prueba de Office 365 G1, active la licencia para todos los usuarios que la necesiten. Para más información, vea [Administrar el acceso de los usuarios a Teams](user-access.md).

Once you've turned on the G1 Trial for the users who need it, you'll manage these users just like you manage users who have a paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).

### <a name="upgrade-users-from-the-office-365-g1-trial-license"></a>Cambiar una licencia de Prueba de Office 365 G1 de los usuarios por una de pago

Para cambiar la licencia de Prueba de G1 de un usuario por una suscripción de pago:

1.  Adquiera una suscripción que incluya Teams.

2.  Elimine la suscripción de Prueba de Office 365 G1 del usuario.

3.  Asigne la licencia que acaba de adquirir.

Para obtener más información, vea [Teams para Administración Pública](expand-teams-across-your-org/teams-for-government-landing-page.md).

> [!NOTE]
> If the G1 Trial license ends and a user is not immediately upgraded to a subscription that includes Teams, the user data is not removed. The user still exists in Azure Active Directory and all data within Teams still remains. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist.
> 
### <a name="remove-an-office-365-g1-trial-license"></a>Eliminar una licencia de Prueba de Office 365 G1

  - Si usted desea eliminar la licencia usando PowerShell, consulte: [Eliminar las licencias de las cuentas de usuario con Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

  - Si quiere eliminar esta licencia a través del Portal de administración, consulte: [Quitar a un usuario de su organización](/microsoft-365/admin/add-users/delete-a-user)

## <a name="related-topics"></a>Temas relacionados

[Gestionar acceso de los usuarios a Microsoft Teams](user-access.md)

[Administrar la configuración de Teams para la organización](enable-features-office-365.md)
