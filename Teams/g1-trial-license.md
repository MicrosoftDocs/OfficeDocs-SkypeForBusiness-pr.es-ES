---
title: Administrar la Prueba de Office 365 G1 gratuita para el gobierno de Estados Unidos
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aarimm
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Para el gobierno de Estados Unidos, si no tiene Microsoft Teams y lo necesita urgentemente, implemente la Prueba de Office 365 G1 para los usuarios que necesiten trabajar de forma remota o desde casa (WFH) en respuesta al brote de COVID-19 (coronavirus).
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: f49adc03e8bb7481fa6cd682a2dcc401d783c0e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120741"
---
<a name="manage-the-office-365-g1-trial-for-us-government"></a>Administrar la Prueba de Office 365 G1 para el gobierno de Estados Unidos 
==============================

A partir del 1 de julio de 2020, la licencia de prueba de Office 365 E1 ya no está disponible. Si necesita obtener una licencia de Microsoft Teams para los usuarios, consulte la [descripción del servicio de Microsoft Teams](/office365/servicedescriptions/teams-service-description) para obtener una lista de suscripciones de pago que incluyan Teams. 

Use las instrucciones de este artículo para administrar las licencias de prueba de Office 365 G1 existentes, incluida [la actualización a una suscripción de pago](#upgrade-users-from-the-office-365-g1-trial-license). Para obtener información, consulte los [Planes de Microsoft 365 Administración Pública](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans) y las [funciones de Microsoft Teams disponibles en la nube GCC](plan-for-government-gcc.md).

No se pierda todas nuestras instrucciones para [dar soporte a los trabajadores remotos que utilicen Teams](support-remote-work-with-teams.md).

## <a name="manage-the-g1-trial"></a>Administrar la Prueba de G1

Después de activar la Prueba de Office 365 G1, active la licencia para todos los usuarios que la necesiten. Para más información, vea [Administrar el acceso de los usuarios a Teams](user-access.md).

Una vez que haya activado la Prueba de G1 para los usuarios que la necesitan, administre estos usuarios tal como administraría a los usuarios con una licencia de pago. Para más información, vea [Administrar la configuración de Teams para su organización](enable-features-office-365.md).

### <a name="upgrade-users-from-the-office-365-g1-trial-license"></a>Cambiar una licencia de Prueba de Office 365 G1 de los usuarios por una de pago

Para cambiar la licencia de Prueba de G1 de un usuario por una suscripción de pago:

1.  Adquiera una suscripción que incluya Teams.

2.  Elimine la suscripción de Prueba de Office 365 G1 del usuario.

3.  Asigne la licencia que acaba de adquirir.

Para obtener más información, vea [Teams para Administración Pública](expand-teams-across-your-org/teams-for-government-landing-page.md).

> [!NOTE]
> Si la licencia de Prueba de G1 finaliza y no se cambia la licencia del usuario inmediatamente a una suscripción que incluya Teams, los datos del usuario no se eliminarán. El usuario seguirá existiendo en Azure Active Directory y todos los datos dentro de Teams se conservarán. Cuando una nueva licencia se asigne al usuario para volver a habilitar las funciones de Teams, todo el contenido seguirá existiendo.
> 
### <a name="remove-an-office-365-g1-trial-license"></a>Eliminar una licencia de Prueba de Office 365 G1

  - Si usted desea eliminar la licencia usando PowerShell, consulte: [Eliminar las licencias de las cuentas de usuario con Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

  - Si quiere eliminar esta licencia a través del Portal de administración, consulte: [Quitar a un usuario de su organización](/microsoft-365/admin/add-users/delete-a-user)

## <a name="related-topics"></a>Temas relacionados

[Gestionar acceso de los usuarios a Microsoft Teams](user-access.md)

[Administrar la configuración de Teams para la organización](enable-features-office-365.md)