---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593696"
---
Antes de empezar, asegúrese de que tiene los siguientes requisitos previos:

- Blue Yonder WFM versión 2020.3, 2021.1 o 2021.2.

    > [!NOTE]
    > Si tiene Blue Yonder WFM 2020.3 o 2021.1, aplique la revisión 2020.3.0.4 o 2021.1.0.3. Esta revisión corrige un problema por el que los usuarios obtienen un mensaje de error persistente en Turnos. También corrige un problema que impide que los usuarios actualicen su disponibilidad en Turnos.

- El nombre de la cuenta del servicio WFM de Blue Yonder y las direcciones URL de contraseña y servicio:

    - URL de autenticación federada
    - Url de autenticación de cookies
    - Dirección URL de autoservicio de empleados
    - URL de API web minorista
    - Url de api del administrador de sitios
    - DIRECCIÓN URL de api de administración

    Si no tiene esta información, póngase en contacto con el soporte técnico de Blue Yonder. Un administrador de la empresa Blue Yonder crea la cuenta en el nivel de empresa raíz. Debe tener acceso de API Access, Administrador de cliente y Administrador de store. La cuenta y la contraseña son necesarias para crear una conexión.
- La autenticación de SSO federada está habilitada en su entorno wfm de Yonder azul. Póngase en contacto con el soporte técnico de Blue Yonder para asegurarse de que sso federado está habilitado. Necesitarán la siguiente información:

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` donde {tenantId} es tu tenantId
     - proxyHeader: X-MS-AuthToken

- Al menos un equipo está configurado en Teams.
- Ha agregado su cuenta Microsoft 365 sistema como propietario del equipo a todos los equipos que desea asignar.</br> [Cree esta cuenta en Microsoft 365](/microsoft-365/admin/add-users/add-users) y asígnele una Microsoft 365 licencia. A continuación, agregue la cuenta como propietario del equipo a todos los equipos que desee asignar. El conector Turnos usa esta cuenta al sincronizar los cambios de Turnos de Blue Yonder WFM.

    Le recomendamos que cree una cuenta específicamente para este fin y que no use su cuenta de usuario.