---
title: Administrar la Prueba gratuita de Office 365 E1
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aytange
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Si no tiene Microsoft Teams y lo necesita de urgencia, distribuya la Prueba de Office 365 E1 a los usuarios que necesiten trabajar de forma remota o desde casa (WFH) como respuesta al ataque COVID-19 (coronavirus).
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46984365e574ed7f55ad92117750385d02942747
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234775"
---
# <a name="manage-the-office-365-e1-trial"></a>Administrar la Prueba de Office 365 E1

A partir del 1 de julio de 2020, la licencia de prueba de Office 365 E1 ya no está disponible. Si necesita obtener una licencia de Microsoft Teams para los usuarios, consulte la [descripción del servicio de Microsoft Teams](/office365/servicedescriptions/teams-service-description) para obtener una lista de suscripciones de pago que incluyan Teams. Como alternativa, las organizaciones elegibles pueden usar la **[versión gratuita de Teams](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c)** o los empleados pueden activar la experiencia de **[Teams Exploratory](teams-exploratory.md)**.

Si es cliente de Teams para el ámbito educativo, consulte la [licencia de Microsoft Office 365 A1](teams-edu-licensing.md) gratuita.

Use las instrucciones de este artículo para administrar las licencias de prueba de Office 365 E1 existentes, incluida [la actualización a una suscripción de pago](#upgrade-users-from-the-office-365-e1-trial-license).

No se pierda todas nuestras instrucciones para [dar soporte a los trabajadores remotos que utilicen Teams](support-remote-work-with-teams.md).

## <a name="manage-the-e1-trial"></a>Administrar la Prueba de E1

Después de activar la Prueba de Office 365 E1, active la licencia para todos los usos necesarios. Para obtener más información, vea [Administrar el acceso de los usuarios a Teams](user-access.md).


Una vez que haya activado la Prueba de E1 para los usuarios que la necesitan, administre a estos usuarios igual que administraría los usuarios con una licencia de pago. Para obtener más información, vea [Administrar la configuración de Teams para su organización](enable-features-office-365.md)



### <a name="upgrade-users-from-the-office-365-e1-trial-license"></a>Cambiar una licencia de Prueba de Office 365 E1 por una de pago

Para que sus usuarios mejoren a una suscripción de pago de E1:

1. Adquiera una suscripción que incluya Teams.

2. Elimine la suscripción de Prueba de Office 365 E1 del usuario.

3. Asignar la licencia que acaba de adquirir.

Para más información, consulte [Descripción del servicio de Microsoft Teams](/office365/servicedescriptions/teams-service-description).

> [!NOTE]
> Si la licencia exploratoria E1 de Teams finaliza y un usuario no se actualiza inmediatamente a una suscripción que incluye Teams, la información del usuario no se quitará. El usuario aún existe en Azure Active Directory y toda la información dentro de Team aún permanece. Una vez que al usuario le es asignada una nueva licencia para volver a habilitar la funcionalidad de Teams, todo el contenido continuará existiendo. 

### <a name="remove-an-office-365-e1-trial-license"></a>Quitar una licencia de Prueba de Office 365 E1

- Si usted desea eliminar la licencia usando PowerShell, vea: [Eliminar las licencias de las cuentas de usuario con Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- Si quiere eliminar esta licencia a través del Portal de administración, consulte: [Quitar a un usuario de su organización](/microsoft-365/admin/add-users/delete-a-user)

## <a name="related-topics"></a>Temas relacionados

[Gestionar acceso de los usuarios a Microsoft Teams](user-access.md)

[Administrar la configuración de Teams de su organización](enable-features-office-365.md)

[Administrar la experiencia de Teams Exploratory](teams-exploratory.md)

[Microsoft 365 u Office 365 para ONG](https://www.microsoft.com/microsoft-365/nonprofit/office-365-nonprofit)

[Obtener ayuda para implementar Teams](https://go.microsoft.com/fwlink/?linkid=780698)