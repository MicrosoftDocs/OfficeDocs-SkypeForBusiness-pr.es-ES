---
title: Conectores de turnos
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre los conectores de Turnos y cómo usarlos para conectar Turnos a su sistema de administración de fuerza de trabajo.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a5e330710fcbdbda6c82db2643e1ed7c0fa5a26
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192503"
---
# <a name="shifts-connectors"></a>Conectores de turnos

## <a name="overview"></a>Información general

Los conectores de turnos le permiten integrar Turnos, la herramienta de administración de programación en Microsoft Teams, con su sistema de administración de fuerza laboral (WFM). Después de configurar una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en el sistema WFM desde Turnos.

Conectar el sistema WFM a Teams permite a los empleados de primera línea administrar las programaciones de forma más eficaz y simplifica los procesos cotidianos para aumentar la productividad y la participación. Los trabajadores de primera línea tienen un lugar para su programación, comunicación y colaboración necesita realizar el trabajo, desde cualquier lugar y desde cualquier dispositivo.

Ofrecemos conectores de turnos administrados y de código abierto. En este artículo se ofrece información general sobre los conectores de Turnos y cómo funcionan.

## <a name="how-shifts-connectors-work"></a>Cómo funcionan los conectores de Turnos

Los conectores sincronizan datos de programación entre su sistema WFM y Turnos, lo que convierte las programaciones de su organización en Teams. Turnos es donde los trabajadores de primera línea se involucran para sus necesidades de programación. El sistema WFM es el sistema de registro para las reglas empresariales, el cumplimiento y la inteligencia.

Los flujos de datos a través del conector de ambas formas para asegurarse de que las programaciones siempre están actualizadas. Las programaciones del sistema WFM se sincronizan con Turnos. Además, los cambios realizados en las programaciones en Turnos se sincronizan de nuevo con el sistema WFM en tiempo real. Como sistema de registro, el sistema WFM exige todas las reglas empresariales antes de que los datos se guarden en Turnos.

## <a name="managed-shifts-connectors"></a>Conectores de Turnos administrados

Los conectores turnos administrados son conectores desarrollados en colaboración con nuestros partners. Los conectores administrados están hospedados y administrados por nosotros o nuestros partners. Con los conectores administrados, solo se necesita una configuración mínima.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Conector Reflejos Turnos para Microsoft Teams

El conector Reflexis Shifts para Microsoft Teams está hospedado y administrado por Zebra. Con este conector, puede integrar Turnos con el sistema Reflexis WFM para administrar sus programaciones y mantenerlas actualizadas.

Los trabajadores de primera línea tienen acceso a su programación en Turnos en Teams y sus solicitudes se sincronizan de Turnos a Programador de fuerza laboral de Reflexis (RWS). El estado de las solicitudes y turnos creados en RWS se sincroniza con Turnos en Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Captura de pantalla que muestra una lista de turnos en un dispositivo móvil y una programación en Reflejos" lightbox="../../media/shifts-connector-reflexis.png":::

Los administradores de primera línea pueden:

- Publicar turnos y programaciones en Reflejos y verlos en Turnos.
- Edite turnos en Reflejos y Turnos.
- Cree, administre y asigne turnos abiertos tanto en Reflejos como en Turnos.
- Ver y aprobar solicitudes de programación de los trabajadores tanto en Reflejos como en Turnos.

Los trabajadores de primera línea pueden:

- Vea sus turnos y horarios propios y de su equipo en Turnos.
- Solicitar permiso, abrir turnos y intercambiar y ofrecer turnos en Turnos.

Para obtener más información, vaya a https://connect.zebra.com/microsoft-connectors .

## <a name="open-source-shifts-connectors"></a>Conectores de turnos de código abierto

Los conectores de turnos de código abierto son integraciones controladas por la comunidad integradas en Graph [API.](/graph/api/resources/shift) Los siguientes conectores de código abierto están disponibles:

- Kronos-to-Teams WFC local
- Conector JDA-to-Teams Shifts (para Blue Yonder versión 2017 a 2020.2)

Cada conector incluye instrucciones detalladas de implementación y configuración. Incluyen scripts de implementación de Azure Resource Manager (ARM) que le permiten hospedar todos los servicios necesarios en Microsoft Azure. El código fuente y los scripts de implementación están disponibles para su descarga en [GitHub repositorio.](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) Puede implementar tal y como está, personalizar o ampliar para satisfacer sus necesidades.

Para obtener más información, vea [Conectores de turnos](/microsoftteams/platform/samples/shifts-wfm-connectors)listos para producción.

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la aplicación Turnos](manage-the-shifts-app-for-your-organization-in-teams.md)
