---
title: Conectores de Turnos
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre los conectores de Turnos y cómo usarlos para conectar Turnos a su sistema de administración de la fuerza de trabajo.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a4759bc010367e6531a557e2a5ff951d1b613505
ms.sourcegitcommit: 3b86e55787c34da76428d6915964ac4f3c6239fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "65598363"
---
# <a name="shifts-connectors"></a>Conectores de Turnos

## <a name="overview"></a>Información general

Los conectores de turnos le permiten integrar Turnos, la herramienta de administración de programación en Microsoft Teams, con su sistema de gestión de la fuerza de trabajo (WFM). Después de configurar una conexión, sus trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en su sistema WFM desde Shifts.

Conectar su sistema WFM con Teams permite que su personal de primera línea administre programaciones de forma más eficaz y simplifique los procesos diarios para lograr una mayor participación y productividad. Sus trabajadores de primera línea tienen un lugar para que su programación, comunicación y colaboración necesiten realizar el trabajo, desde cualquier lugar y con cualquier dispositivo.

En este artículo se ofrece información general sobre los conectores de Turnos y cómo funcionan.

## <a name="how-shifts-connectors-work"></a>Cómo funcionan los conectores de Mayús

Los conectores sincronizan los datos de programación entre su sistema WFM y Shifts, incorporando las programaciones de su organización a Teams. Turnos es donde los trabajadores de primera línea se involucran para sus necesidades de programación. Su sistema WFM es el sistema de registro para reglas empresariales, cumplimiento e inteligencia.

Los flujos de datos a través del conector de ambas maneras para asegurarse de que las programaciones siempre están actualizadas. Las programaciones en su sistema WFM se sincronizan con Turnos. Además, los cambios realizados en las programaciones en Turnos se sincronizan de nuevo con su sistema WFM en tiempo real. Como sistema de registro, todas las reglas de negocio son aplicadas por su sistema WFM antes de que los datos se guarden en Shifts.

## <a name="managed-shifts-connectors"></a>Conectores de Turnos administrados

Los conectores de Turnos administrados son conectores desarrollados en colaboración con nuestros asociados. Los conectores administrados los hospedamos y administramos nosotros o nuestros asociados. Con los conectores administrados, solo se necesita una configuración mínima.

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>conector Microsoft Teams Turnos para Yonder azul
<a name="blue_yonder"> </a>

El conector Teams Shifts para Blue Yonder es una oferta de origen hospedada y administrada por Microsoft. Con este conector, puede integrar Turnos con Blue Yonder Workforce Management (Blue Yonder WFM) versiones 2020.3, 2021.1 o 2021.2 para administrar sus programaciones y mantenerlas actualizadas.  

> [!NOTE]
> Si tiene la versión 2020.3 o 2021.1 de Blue Yonder WFM, aplique la revisión 2020.3.0.4 o 2021.1.0.3. Esta revisión corrige un problema por el que los usuarios reciben un mensaje de error persistente en Turnos. También se corrige un problema que impide que los usuarios actualicen su disponibilidad en Turnos.

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="Captura de pantalla que muestra una solicitud de intercambio en Turnos en un dispositivo móvil, solicitar aprobación en Teams en el escritorio y una programación en Blue Yonder WFM." lightbox="../../media/shifts-connector-blue-yonder.png":::

Los jefes de frente pueden:

- Publique turnos y programaciones en Blue Yonder WFM y visualicelos en Turnos.
- Cree, administre y asigne turnos abiertos en Blue Yonder WFM y visualicelos en Turnos.
- Asigne turnos abiertos que se crearon en Blue Yonder WFM en Turnos.
- Cree, edite y elimine permisos en Blue Yonder WFM y visualice en Turnos.
- Vea y apruebe solicitudes de programación de los trabajadores tanto en WFM de Blue Yonder como en Turnos.
- Establezca y actualice la disponibilidad de los trabajadores en Blue Yonder WFM y visualícela en Turnos.

Los trabajadores de primera línea pueden:

- Vea sus propios turnos y las programaciones de su equipo en Turnos.
- Solicite permisos, abra turnos y permuta turnos en Turnos.
- Establezca su disponibilidad en Turnos.

Las siguientes acciones no son compatibles actualmente:

- Agregue, edite, elimine, guarde o publique turnos en Turnos.
- Agregue, edite, elimine, guarde o publique permisos en Turnos.
- Agregue, edite, elimine, guarde o publique turnos abiertos en Turnos.

Cuando un administrador o un trabajador de primera línea intenta realizar cualquiera de estas acciones en Turnos, recibirán un mensaje para informarles de que la acción no es compatible.

#### <a name="example-scenario"></a>Ejemplo ficticio

Eden, un gerente, publica una programación en Blue Yonder WFM, que se sincroniza con Turnos en Teams a través del conector. Alex, un miembro del personal, recibe una notificación en Teams en su dispositivo móvil, y ve su programación y turnos asignados.

Alex debe tomarse un tiempo libre y solicitar un día libre con turnos. La solicitud se envía a Blue Yonder WFM a través del conector en tiempo real. Blue Yonder WFM se asegura de que la solicitud cumple con las reglas de negocio y se crea la solicitud. Eden ve y aprueba la solicitud en Blue Yonder WFM, y la aprobación se sincroniza con Teams. (Eden también puede ver y aprobar la solicitud en Turnos). Alex recibe una notificación en Teams de que su solicitud es aprobada y ve su programación actualizada.

Alex quiere intercambiar un turno con un compañero de trabajo. En Turnos, Alex ve una lista de todos los turnos que son elegibles para un intercambio basado en las reglas de negocio en Blue Yonder WFM. Alex elige un turno que está asignado actualmente a Gena. Gena recibe una notificación en Teams en su dispositivo móvil y acepta la solicitud de intercambio. Eden ve y aprueba la solicitud en Turnos, y la aprobación se sincroniza con Blue Yonder WFM. (Eden también puede ver y aprobar la solicitud en WfM de Blue Yonder). Alex y Gena reciben una notificación en Teams y ven sus programaciones actualizadas.

#### <a name="set-up-a-connection"></a>Configurar una conexión

La integración de Turnos con Blue Yonder WFM utilizando el conector requiere solo unos cuantos pasos. Puede usar el asistente del conector Mayús en el Centro de administración de Microsoft 365 para configurar rápidamente una conexión. El asistente configura el conector en función de las opciones que elija y crea la conexión. Si prefiere usar PowerShell, también proporcionamos scripts de PowerShell que puede usar para conectarse.

Para obtener instrucciones detalladas, vea:

- [Usar el asistente del conector Turnos para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Usar PowerShell para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)

Después de configurar una conexión, puede usar PowerShell para actualizar y cambiar la configuración de conexión en cualquier momento, según sea necesario. En cuanto al conector en sí, no tiene que preocuparse por las actualizaciones o el mantenimiento. Nos ocupamos de eso.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Conector Reflexis Shifts para Microsoft Teams

El conector Reflexis Shifts para Microsoft Teams está hospedado y administrado por Zebra. Con este conector, puede integrar Turnos con el sistema Reflexis WFM para administrar sus programaciones y mantenerlos actualizados.

Los trabajadores de primera línea tienen acceso a su programación en Turnos en Teams, y sus solicitudes se sincronizan desde Turnos a Reflexis Workforce Scheduler (RWS). El estado de las solicitudes y los turnos creados en RWS se sincroniza con Turnos en Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Captura de pantalla que muestra una lista de turnos en un dispositivo móvil y una programación en Reflexis." lightbox="../../media/shifts-connector-reflexis.png":::

Los jefes de frente pueden:

- Publique turnos y programaciones en Reflexis y visualicelos en Turnos.
- Edite los turnos tanto en Reflexis como en Turnos.
- Cree, administre y asigne turnos abiertos tanto en Reflexis como en Turnos.
- Vea y apruebe las solicitudes de programación de los trabajadores tanto en Reflexis como en Turnos.

Los trabajadores de primera línea pueden:

- Vea sus propios turnos y las programaciones de su equipo en Turnos.
- Solicite permisos, abra turnos, intercambie y ofrezca turnos en Turnos.

Para obtener más información, ve a https://connect.zebra.com/microsoft-connectors.

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la aplicación Turnos](manage-the-shifts-app-for-your-organization-in-teams.md)
