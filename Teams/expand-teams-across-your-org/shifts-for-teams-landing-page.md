---
title: Turnos para Teams
description: Obtenga las instrucciones de administración que necesita para configurar y administrar Turnos, la herramienta de administración de programación, en Teams.
ms.topic: conceptual
author: LanaChin
ms.author: v-lanachin
audience: admin
manager: samanro
f1.keywords:
- NOCSH
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 59e62ad1278c2703402a1186d198ae3ad877be63
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592776"
---
# <a name="shifts-for-teams"></a>Turnos para Teams

Turnos, la herramienta de administración de programación en Teams, mantiene a su personal de primera línea conectado y sincronizado. Está diseñado para dispositivos móviles en primer lugar para la administración y las comunicaciones de programación rápidas y eficaces. Con Turnos, los jefes de línea y los trabajadores pueden administrar sin problemas las programaciones y mantenerse en contacto.

Los administradores pueden crear, actualizar y administrar programaciones de turnos para sus equipos. Pueden asignar turnos, agregar turnos abiertos y aprobar solicitudes de programación de los empleados. Los empleados pueden ver sus propias programaciones y las de su equipo, establecer su disponibilidad, solicitar intercambiar u ofrecer un turno, solicitar un permiso y hacer entrada y salida.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

Use los siguientes recursos para ayudarle a configurar y administrar turnos en su organización.

## <a name="set-up-and-manage-shifts"></a>Configurar y administrar turnos

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[Administrar turnos](shifts/manage-the-shifts-app-for-your-organization-in-teams.md)** Obtenga información sobre cómo administrar turnos para su organización.         |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[Administrar propietarios de programación para la administración de turnos](shifts/schedule-owner-for-shift-management.md)** Esta característica le permite elevar los permisos de un miembro del equipo a un propietario de programación sin convertir al empleado en propietario del equipo.         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[Preguntas más frecuentes sobre los datos de turnos](shifts/shifts-data-faq.md)** Obtenga información sobre dónde se almacenan los datos de Turnos y otros temas relacionados con los datos de Turnos, como retención, recuperación y cifrado.        |

## <a name="shifts-connectors"></a>Conectores de turnos

Si usa un sistema de administración de fuerza de trabajo (WFM) de terceros para la programación, puede integrar directamente con Turnos a través de conectores de turnos administrados y a través de las API y sdk de Shifts Graph con conectores de turnos de código abierto. Después de configurar una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en el sistema WFM desde Turnos.

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Información general sobre los conectores de turnos](shifts/shifts-connectors.md)** Obtenga información general sobre los conectores de Turnos y su forma de trabajar. Obtenga información sobre los conectores administrados y de código abierto que están disponibles y los sistemas WFM compatibles.   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Conectores de Turnos administrados](shifts/shifts-connectors.md#managed-shifts-connectors)** Los conectores de Turnos administrados, desarrollados en colaboración con nuestros partners, están hospedados y administrados tanto por nosotros como por nuestros partners. Para obtener más información, [vea Microsoft Teams de turnos para conector yonder](shifts/shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) azul y [turnos reflexis para Microsoft Teams](shifts/shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams).    |
|   | **[Usar el Asistente para conectores de turnos para conectar Turnos a Blue Yonder Workforce Management](shifts/shifts-connector-wizard.md)** El asistente para conectores turnos de la Centro de administración de Microsoft 365 le ayuda a configurar rápidamente una conexión a su sistema WFM. Actualmente, el asistente admite el conector Teams turnos para Blue Yonder para integrar Turnos con Blue Yonder Workforce Management.
|  | **[Usar PowerShell para conectar Turnos a Blue Yonder Workforce Management](shifts/shifts-connector-blue-yonder-powershell-setup.md)** Obtenga información sobre cómo usar PowerShell para configurar una conexión a Blue Yonder Workforce Management a través del conector Teams Shifts para Blue Yonder.         |
|   | **[Usar PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management](shifts/shifts-connector-powershell-manage.md)** Obtenga instrucciones sobre cómo usar PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management después de configurarla mediante el Asistente para conectores de turnos o PowerShell.
|<img src="/office/media/icons/api.png" alt="Three gears - API.">    | **[Conectores de turnos de código abierto](/microsoftteams/platform/samples/shifts-wfm-connectors)** Obtenga información sobre cómo usar conectores de código abierto [basados](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) en la comunidad para integrar su sistema de KRONOS o JDA WFM a través de Graph API y SDK.    |

## <a name="shifts-extensions"></a>Extensiones de turnos

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[Shift Graph API](/graph/api/resources/shift)** Mayús Graph API le permiten integrar datos de Turnos con sistemas de administración de fuerza de trabajo externos (WFM). Tendrá la flexibilidad de crear experiencias personalizadas de Turnos en el back-end, a la vez que ofrece a los usuarios una experiencia de front-end enriqueciendo Teams.             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Turnos + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** + Power Automate le permite tomar información de Turnos y crear flujos de trabajo personalizados con otras aplicaciones y realizar operaciones a escala. Automatice procesos clave con poco o ningún código. Los desencadenadores y plantillas admiten varios escenarios, como habilitar aprobaciones automáticas para solicitudes de turno cuando no es necesaria la aprobación de un administrador. |

## <a name="featured-training"></a>Aprendizaje destacado

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [Vídeo: ¿Qué es Turnos?](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [Vídeo: Crear una programación de turnos](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [Vídeo: Administrar una programación de turnos](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
