---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593696"
---
Antes de empezar, asegúrate de que tienes los siguientes requisitos previos:

- Blue Yonder WFM versión 2020.3, 2021.1 o 2021.2.

    > [!NOTE]
    > Si tiene Blue Yonder WFM 2020.3 o 2021.1, aplique la revisión 2020.3.0.4 o 2021.1.0.3. Esta revisión corrige un problema por el que los usuarios reciben un mensaje de error persistente en Turnos. También se corrige un problema que impide que los usuarios actualicen su disponibilidad en Turnos.

- Su nombre de cuenta de servicio de WfM de Blue Yonder y las direcciones URL de servicio y contraseña:

    - URL de autenticación federada
    - Url de autenticación de cookies
    - DIRECCIÓN URL de autoservicio de empleado
    - DIRECCIÓN URL de la API web comercial
    - DIRECCIÓN URL de la API de administrador del sitio
    - DIRECCIÓN URL de la API de administración

    Si no tienes esta información, ponte en contacto con el soporte técnico de Blue Yonder. La cuenta la crea un administrador de empresa de Blue Yonder en el nivel de empresa raíz. Debe tener acceso a API Access, Client Admin y Store Manager. La cuenta y la contraseña son necesarias para crear una conexión.
- La autenticación SSO federada está habilitada en su entorno de WfM de Blue Yonder. Póngase en contacto con el soporte técnico de Blue Yonder para asegurarse de que esté habilitado el SSO federado. Necesitarán la siguiente información:

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` donde {tenantId} es tu tenantId
     - proxyHeader: X-MS-AuthToken

- Se ha configurado al menos un equipo en Teams.
- Ha agregado su cuenta del sistema de Microsoft 365 como propietario de un equipo a todos los equipos que quiera asignar.</br> [Cree esta cuenta en Microsoft 365](/microsoft-365/admin/add-users/add-users) y asígnele una licencia de Microsoft 365. Después, agregue la cuenta como propietario de un equipo a todos los equipos que quiera asignar. El conector Shifts usa esta cuenta al sincronizar los cambios de Turnos desde Blue Yonder WFM.

    Le recomendamos que cree una cuenta específicamente para este propósito y que no use su cuenta de usuario.