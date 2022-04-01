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
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592895"
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

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams de turnos para Blue Yonder
<a name="blue_yonder"> </a>

El Teams shifts para Blue Yonder es una oferta de primer mundo hospedada y administrada por Microsoft. Con este conector, puede integrar Turnos con blue yonder Workforce Management (Blue Yonder WFM) versiones 2020.3, 2021.1 o 2021.2 para administrar sus programaciones y mantenerlas actualizadas.  

> [!NOTE]
> Si tiene la versión 2020.3 o 2021.1 de Blue Yonder WFM, aplique la revisión 2020.3.0.4 o 2021.1.0.3. Esta revisión corrige un problema por el que los usuarios obtienen un mensaje de error persistente en Turnos. También corrige un problema que impide que los usuarios actualicen su disponibilidad en Turnos.

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="Captura de pantalla que muestra una solicitud de intercambio en Turnos en un dispositivo móvil, solicitar la aprobación en Teams en el escritorio y una programación en Blue Yonder WFM." lightbox="../../media/shifts-connector-blue-yonder.png":::

Los administradores de primera línea pueden:

- Publicar turnos y programaciones en Blue Yonder WFM y verlos en Turnos.
- Cree, administre y asigne turnos abiertos en Blue Yonder WFM y visual ábralos en Turnos.
- Asigne turnos abiertos creados en Blue Yonder WFM en Turnos.
- Cree, edite y elimine el tiempo libre en Blue Yonder WFM y vea en Turnos.
- Vea y apruebe las solicitudes de programación de los trabajadores en Blue Yonder WFM y Shifts.
- Establecer y actualizar la disponibilidad de los trabajadores en Blue Yonder WFM y ver en Turnos.

Los trabajadores de primera línea pueden:

- Vea sus turnos y horarios propios y de su equipo en Turnos.
- Solicite permiso, abra turnos e intercambie turnos en Turnos.
- Establezca su disponibilidad en Turnos.

Actualmente, no se admiten las siguientes acciones:

- Agregar, editar, eliminar, guardar o publicar turnos en Turnos.
- Agregue, edite, elimine, guarde o publique el tiempo libre en Turnos.
- Agregar, editar, eliminar, guardar o publicar turnos abiertos en Turnos.

Cuando un administrador de primera línea o un trabajador intenta realizar cualquiera de estas acciones en Turnos, recibirán un mensaje para que sepan que la acción no es compatible.

#### <a name="example-scenario"></a>Ejemplo ficticio

Eden, un administrador, publica una programación en Blue Yonder WFM, que se sincroniza con Turnos en Teams a través del conector. Alex, un miembro del personal, recibe una notificación en Teams en su dispositivo móvil, y ve su programación y turnos asignados.

Alex necesita tomar un tiempo libre y solicita un día libre con Turnos. La solicitud se envía a Blue Yonder WFM a través del conector en tiempo real. Blue Yonder WFM garantiza que la solicitud cumple con las reglas empresariales y se crea la solicitud. Edén ve y aprueba la solicitud en Blue Yonder WFM y la aprobación se sincroniza con Teams. (Eden también puede ver y aprobar la solicitud en Turnos). Alex se notifica en Teams que su solicitud está aprobada y ve su programación actualizada.

Alex quiere intercambiar un turno con un compañero de trabajo. En Turnos, Alex ve una lista de todos los turnos que son aptos para un intercambio basado en reglas empresariales en Blue Yonder WFM. Alex elige un turno asignado actualmente a Gena. Gena se notifica en Teams en su dispositivo móvil y acepta la solicitud de intercambio. Edén ve y aprueba la solicitud en Turnos y la aprobación se sincroniza con Blue Yonder WFM. (Eden también puede ver y aprobar la solicitud en Blue Yonder WFM). Alex y Gena se notifican en Teams y ven sus programaciones actualizadas.

#### <a name="set-up-a-connection"></a>Configurar una conexión

La integración de turnos con Blue Yonder WFM con el conector requiere unos pocos pasos. Puede usar el Asistente para conectores de turnos en el Centro de administración de Microsoft 365 para configurar rápidamente una conexión. El asistente configura el conector en función de la configuración que elija y crea la conexión. Si prefiere usar PowerShell, también proporcionamos scripts de PowerShell que puede usar para conectarse.

Para obtener instrucciones paso a paso, vea:

- [Usar el Asistente para conectores de turnos para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Usar PowerShell para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)

Después de configurar una conexión, puede usar PowerShell para actualizar y cambiar la configuración de conexión en cualquier momento, según sea necesario. En cuanto al conector en sí, no es necesario que se preocupe por las actualizaciones o el mantenimiento. Nos encargamos de eso.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Conector Reflexis Shifts para Microsoft Teams

El conector Reflexis Shifts para Microsoft Teams está hospedado y administrado por Zebra. Con este conector, puede integrar Turnos con el sistema Reflexis WFM para administrar sus programaciones y mantenerlas actualizadas.

Los trabajadores de primera línea tienen acceso a su programación en Turnos en Teams y sus solicitudes se sincronizan de Turnos a Programador de fuerza laboral de Reflexis (RWS). El estado de las solicitudes y turnos creados en RWS se sincroniza con Turnos en Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Captura de pantalla que muestra una lista de turnos en un dispositivo móvil y una programación en Reflexis." lightbox="../../media/shifts-connector-reflexis.png":::

Los administradores de primera línea pueden:

- Publicar turnos y programaciones en Reflejos y verlos en Turnos.
- Edite turnos en Reflejos y Turnos.
- Cree, administre y asigne turnos abiertos tanto en Reflejos como en Turnos.
- Ver y aprobar solicitudes de programación de los trabajadores tanto en Reflejos como en Turnos.

Los trabajadores de primera línea pueden:

- Vea sus turnos y horarios propios y de su equipo en Turnos.
- Solicitar permiso, abrir turnos y intercambiar y ofrecer turnos en Turnos.

Para obtener más información, vaya a https://connect.zebra.com/microsoft-connectors.

## <a name="open-source-shifts-connectors"></a>Conectores de turnos de código abierto

Los conectores de turnos de código abierto son integraciones controladas por la comunidad [integradas en Las Graph API](/graph/api/resources/shift). Los siguientes conectores de código abierto están disponibles:

- Kronos-to-Teams WFC local
- Conector JDA-to-Teams Shifts (para Blue Yonder versión 2017 a 2020.2)

Cada conector incluye instrucciones detalladas de implementación y configuración. Incluyen scripts de implementación de Azure Resource Manager (ARM) que le permiten hospedar todos los servicios necesarios en Microsoft Azure. El código fuente y los scripts de implementación están disponibles para su descarga en [GitHub repositorio.](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) Puede implementar tal y como está, personalizar o ampliar para satisfacer sus necesidades.

Para obtener más información, vea [Conectores de turnos listos para producción](/microsoftteams/platform/samples/shifts-wfm-connectors).

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la aplicación Turnos](manage-the-shifts-app-for-your-organization-in-teams.md)
