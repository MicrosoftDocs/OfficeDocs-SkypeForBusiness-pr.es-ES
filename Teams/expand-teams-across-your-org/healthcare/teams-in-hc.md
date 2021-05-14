---
title: Introducción a Teams para organizaciones sanitarias
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-overview
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Obtenga información sobre características relacionadas con el ámbito de la salud como la teleasistencia sanitaria de Microsoft Teams, integración con la historia clínica electrónica, integración del sistema de personal de primera línea y la aplicación Pacientes.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: f6048d2413ea92e377358af43c7348abbbe00be1
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760603"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Introducción a Teams para organizaciones sanitarias

Microsoft Teams ofrece una serie de características de telemedicina que resultan útiles para los hospitales y otras organizaciones de salud. Las características de Teams se están desarrollando para ayudar a los hospitales con:

- Visitas virtuales y la integración de la historia clínica electrónica (EHR)
- Paquetes de directivas de Teams
- Mensajería segura
- Plantillas de Teams
- Colaboración y coordinación de atención médica

Esta función forma parte de la Nube de Microsoft para el cuidado de la salud. Obtenga más información sobre esta solución, que aúna capacidades de Azure, Dynamics 365 y Microsoft 365 en la [Nube de Microsoft para el cuidado de la salud](/industry/healthcare).

Vea el siguiente vídeo para obtener más información sobre el uso de la colección del cuidado de la salud para mejorar la colaboración de los equipos sanitarios en Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> El contenido de esta sección da por sentado que ya ha implementado Teams en su organización. Si todavía no ha implementado Teams, empiece por leer [Cómo implementar Microsoft Teams](../../deploy-overview.md).

Los siguientes escenarios están disponibles para las organizaciones del cuidado de la salud:

| Escenario | Descripción | Requirements |
| -------- | -------- | -------- |
| [Visitas virtuales con integración de la historia clínica electrónica (EHR)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Programe, administre y realice visitas virtuales con los pacientes. Este escenario conecta Microsoft Teams y la plataforma Epic para admitir las visitas virtuales. | Oferta independiente de suscripción activa de la Nube de Microsoft para el cuidado de la salud o suscripción del conector de EHR para Microsoft Teams. <br> Los usuarios deben tener una licencia adecuada de Microsoft 365 u Office 365 que incluya reuniones de Microsoft Teams*. <br> Las organizaciones deben tener la versión de Epic de noviembre de 2018 o posterior. <br>[Detalles de los requisitos de EHR](ehr-admin.md#before-you-begin) |
| [Visitas virtuales con Microsoft Bookings y la aplicación de Bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Programe, administre y realice visitas virtuales con los pacientes. Este escenario depende de Microsoft Bookings para admitir visitas virtuales. | Microsoft Bookings debe estar activado para la organización. <br> Todos los usuarios de la aplicación de Bookings y todo el personal que participe en las reuniones debe tener una licencia que admita la programación de reuniones de Teams. <br>[Detalles de los requisitos de Bookings](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Paquetes de directivas de Microsoft Teams](#teams-policy-packages)| Asegúrese de que los dispositivos del personal clínico, del personal de información y de las salas de pacientes tengan el acceso adecuado a la función de Teams.| Los usuarios deben tener una licencia adecuada*. |
| [Mensajería segura](#secure-messaging) | Obtenga atención más rápida de los mensajes urgentes y tenga la seguridad de que los mensajes se reciben y se leen. | Los usuarios deben tener una licencia adecuada*.  |
| [Plantillas de Teams](#teams-templates-for-healthcare-organizations) | Cree equipos que incluyan una plantilla predefinida de configuración, canales y aplicaciones preinstaladas para la comunicación y colaboración en una planta, sala o departamento, o entre varias plantas, salas o departamentos en un hospital. | Los usuarios deben tener una licencia adecuada*.  |
| [Colaboración y coordinación de atención médica](#care-coordination-and-collaboration) | El personal de medicina clínica y el personal general pueden colaborar internamente en los horarios, documentos, tareas, etc.| Los usuarios deben tener una licencia adecuada*. |

*Se admiten Office 365 A3, A5, E3 y E5, así como Microsoft 365 Empresa Estándar, A3, A5, E3 y E5. Para obtener más información sobre las licencias de Teams en general, consulte [Administrar el acceso del usuario a Teams](../../user-access.md).

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Visitas virtuales y la integración de la historia clínica electrónica (EHR)

Use la plataforma completa de reuniones en Microsoft Teams para programar, administrar y realizar visitas virtuales con pacientes.

- Si su organización ya utiliza la historia clínica electrónica o EHR, puede integrar Microsoft Teams para disfrutar de una experiencia más sencilla. El conector de Microsoft Teams para la historia clínica electrónica (EHR) hace que resulte fácil para el personal médico iniciar una visita virtual con un paciente o una consulta con otro proveedor en Teams directamente desde el sistema de EHR. Para más información, consulte [Visitas virtuales con Teams: integración en EHR](ehr-admin.md).
- Si no usa una EHR admitida, puede usar Microsoft Bookings y la aplicación de Bookings en Teams. Para más información, consulte [Aplicación de reservas y visitas virtuales de Microsoft Teams](../../bookings-app-admin.md).

![Visitas virtuales con Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Paquetes de directivas de Teams

Aplique paquetes de directivas de Teams para definir lo que los diferentes roles pueden hacer en Teams. Por ejemplo, especifique directivas para:

- Personal sanitario, como personal titulado de enfermería, personal encargado de enfermería, personal médico y trabajadores sociales, para que tengan acceso completo al chat, llamadas, administración de turnos y reuniones.
- Personal de la información en su organización del cuidado de la salud, como personal de TI, personal de informática, personal de finanzas y responsables del cumplimiento normativo, para que tengan acceso completo al chat, llamadas y reuniones.
- Salas de pacientes, para control la configuración de los dispositivos en salas de pacientes.

Para más información, consulte [Paquetes de directivas de Teams para sanidad](../../policy-packages-healthcare.md).

## <a name="secure-messaging"></a>Mensajería segura

La mensajería segura admite la colaboración dentro de los equipos de salud, incluidas varias características nuevas:

- El remitente de un mensaje puede establecer prioridad especial para su mensaje, de modo que el destinatario reciban notificaciones repetidamente hasta que lea el mensaje.
- El remitente de un mensaje puede solicitar una confirmación de lectura, para recibir una notificación cuando el destinatario lea el mensaje.

Combinadas, estas características ofrecen una atención más rápida de los mensajes urgentes y la seguridad de que los mensajes se reciben y se leen. Se pueden crear por paciente nuevos equipos de salud que usen estas características. Estas características se basan en directivas y se pueden asignar a individuos o al equipos enteros.

Para más información, consulte [Introducción a las directivas de mensajería segura para las organizaciones sanitarias](messaging-policies-hc.md).

Otro aspecto relacionado con la mensajería segura es la posibilidad de que otros espacios empresariales sean federados por organizaciones sanitarias, lo que permite una mejor comunicación entre espacios empresariales. (Consulte [Administrar el acceso externo (federación) en Microsoft Teams](../../manage-external-access.md)).

## <a name="teams-templates-for-healthcare-organizations"></a>Plantillas de Teams para organizaciones sanitarias

Se ha desarrollado nuevas plantillas para crear equipos para aplicar a hospitales, y se espera que pronto se publiquen más. Esto hace que resulte más fácil crear equipos que el personal sanitario puede usar para coordinar el cuidado de los pacientes en varios departamentos o plantas. Para más información, consulte [Introducción a las plantillas para las organizaciones sanitarias de Teams](./healthcare-templates-admin-console.md). Los equipos se pueden iniciar para departamentos internos como cardiología o para salas de pacientes, y se están desarrollando más plantillas.

## <a name="care-coordination-and-collaboration"></a>Colaboración y coordinación de atención médica

Estreche la colaboración de su equipo sanitario para coordinar el cuidado de la salud y colaborar con Microsoft Teams.

![Cuidado de la salud: colabore con su equipo sanitario en Teams](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams permite al personal médico, personal clínico, personal de enfermería y otros colaborar de manera eficiente con características incluidas de colaboración en Microsoft Teams, tales como:

- Configurar equipos y canales para sus equipos sanitarios y personal de la información. Usar canales con pestañas para estructurar el trabajo, con la ayuda adicional que proporcionan pestañas en las que el personal puede anclar fuentes de información.
- Chatear, publicar mensajes y comunicarse. Su equipo puede comunicarse constantemente sobre diferentes pacientes que necesitan atención.
- Realizar llamadas y reunirse con miembros del equipo sanitario. Configure reuniones individuales o utilice las reuniones de canal para administrar reuniones diarias, con la tecnología de las características de Teams de audio, vídeo, pantalla compartida, grabación y transcripción.
- Almacenar y compartir archivos y documentos. Su equipo sanitario forma parte de un único equipo virtualizado que trabaja y colabora en documentos de Office.

Además, su equipo puede usar aplicaciones en Teams para:

- Compartir listas y hacer un seguimiento de la información con la aplicación Listas
- Hacer un seguimiento de tareas y monitorearlas con la aplicación Tasks
- Simplificar aprobaciones con la aplicación Aprobaciones
- Crear, administrar y compartir horarios con la aplicación Turnos

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Compartir listas y hacer un seguimiento de la información con la aplicación Listas

> [!NOTE]
> Desde el 30 de octubre de 2020, la aplicación Pacientes se retiró y se reemplazó por la aplicación [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Con Listas, los equipos del cuidado de la salud en su organización sanitaria pueden crear listas de pacientes para escenarios que van desde guardias y reuniones interdisciplinarias de equipo hasta seguimiento general de pacientes.

La aplicación Lists en Microsoft Teams ayuda a los equipos a realizar un seguimiento de la información y a organizar el trabajo. La aplicación viene preinstalada para todos los usuarios de Teams y en una pestaña en todos los equipos y canales. Se pueden crear listas desde cero, desde plantillas predefinidas o mediante la importación de datos de Excel.

Loa equipos sanitarios pueden usar la plantilla de Pacientes para empezar. Pueden crear listas para hacer un seguimiento de las necesidades y estado de los pacientes. Se pueden importar datos existentes sobre pacientes en hojas de cálculo de Excel para crear una lista en Teams. Estas listas se pueden usar para escenarios como guardias y supervisión de pacientes para coordinar el cuidado de la salud.

Por ejemplo, un miembro del personal encargado de enfermería puede crear una lista de pacientes en un equipo que incluya a todos los miembros del equipo sanitario. Durante las guardias, el equipo sanitario tiene acceso a Teams en sus dispositivos móviles y puede actualizar la información de los pacientes de la lista. Todos los miembros del equipo pueden ver la lista para sincronizarse. En las sesiones de guardia en las que el equipo sanitario se reúne para comentar y evaluar métricas clave de salud para asegurarse de que un paciente vaya por buen camino para recibir el alta, pueden compartir esta información mediante Teams en una pantalla grande de visualización. Los miembros del equipo sanitario que no se encuentren en el lugar de la reunión se pueden unir a distancia.

Aquí tiene una lista de muestra para guardias de pacientes.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Recorte de pantalla de lista de muestra para guardias de pacientes":::

Para más información, consulte [Administrar la aplicación Listas para su organización en Teams](../../manage-lists-app.md).

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Hacer un seguimiento de tareas y monitorearlas con la aplicación Tasks

Use [Tasks](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) en Teams para hacer un seguimiento elementos pendientes para todo el equipo sanitario. Su equipo sanitario puede crear, asignar y programar tareas, categorizar tareas y actualizar estados en cualquier momento, desde cualquier dispositivo que tenga Teams. Los administradores y profesionales de TI también pueden publicar tareas en equipos específicos para su organización. Por ejemplo, podría publicar un conjunto de tareas para los nuevos protocolos de seguridad o un nuevo paso de ingreso para su uso en un hospital.

Para más información, consulte [Administrar la aplicación Tasks para su organización en Microsoft Teams](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Simplificar aprobaciones con la aplicación Aprobaciones

Use [Aprobaciones](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) para simplificar todas sus solicitudes y procesos con su equipo. Cree, administre y comparta aprobaciones directamente desde su centro para el trabajo en equipo. Inicie un flujo de aprobación desde el mismo sitio desde el que envía un chat, en una conversación de canal o desde la propia lista de Aprobaciones. Solo tiene que seleccionar el tipo de aprobación, agregar detalles, adjuntar archivos y elegir aprobadores. Una vez enviado, los aprobadores reciben una notificación y pueden revisar y responder a la solicitud.

Puede permitir la aplicación Aprobaciones para su organización y agregarla a sus equipos. Para más información, consulte [Disponibilidad de la aplicación Aprobaciones de Teams](../../approval-admin.md).

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Crear, administrar y compartir horarios con la aplicación Turnos y la integración de personal de primera línea

Microsoft Teams se integra con la aplicación Turnos y personal de primera línea, que se puede usar para coordinar características de turnos del personal y más. Por ejemplo, en Turnos, los gerentes de enfermería pueden configurar y coordinar los horarios de su personal, y el personal de enfermería puede consultar horarios y cambiar turnos. Teams incluye una política de configuración de la aplicación incorporada para trabajadores de primera línea puede asignar a los trabajadores de primera línea en su organización. De forma predeterminada, la directiva incluye las aplicaciones Actividad, Turnos, Chat y Llamadas. Esta directiva controla el comportamiento de estas aplicaciones, por ejemplo, se puede anclar la aplicación Turnos en la barra de la aplicación para que el equipo pueda acceder a la misma rápidamente.

Para más información, consulte [Administrar la aplicación Turnos para su organización en Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Ayude a su personal médico y de la información a empezar a usar Teams

Hay muchos recursos disponibles para ayudar a todos los usuarios en su organización a familiarizarse con Teams:

- Visite el [centro de adopción de Teams](https://adoption.microsoft.com/microsoft-teams/) para obtener consejos sobre la implementación de Teams si está iniciando la experiencia de su organización con Teams, o para expandir Teams a más ámbitos de su organización.
- Considere configurar [formas de aprendizaje](https://adoption.microsoft.com/microsoft-365-learning-pathways/) personalizado para que los usuarios aprendan solamente a hacer sus tareas.
- Obtenga ayuda y aprendizaje para sus usuarios sobre cómo realizar tareas básicas en Microsoft Teams en el [sitio de soporte técnico de Teams](https://support.microsoft.com/teams), incluidos [vídeos breves de aprendizaje](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7). Asimismo, el sitio incluye ayuda y aprendizaje para las aplicaciones de Teams, incluidas [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db), [Tasks](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070), [Aprobaciones](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3), [Bookings](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b) y [Turnos](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821).
