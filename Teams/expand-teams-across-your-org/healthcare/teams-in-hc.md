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
description: Obtenga información sobre las características de atención sanitaria como la telesalud de Microsoft Teams, la integración con EHR, la integración del sistema de trabajadores de Frontline y la aplicación Pacientes.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 1bf890c7ffb6fa13730870cb1f4eabecb5df7c85
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558389"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Introducción a Teams para organizaciones sanitarias

Microsoft Teams ofrece una serie de características de telemedicina útiles para hospitales y otras organizaciones sanitarias. Las características de Teams están en desarrollo para ayudar a los hospitales con:

- Visitas virtuales e integración de registros electrónicos de atención sanitaria (EHR)
- Paquetes de directivas de Teams
- Mensajería segura
- Plantillas de Teams
- Coordinación y colaboración en el cuidado

Esta funcionalidad forma parte de Microsoft Cloud para el cuidado de la salud. Obtenga más información sobre el uso de esta solución, que reúne las capacidades de Azure, Dynamics 365 y Microsoft 365 en Microsoft Cloud para el cuidado de [la salud.](https://docs.microsoft.com/industry/healthcare)

Vea el siguiente vídeo para obtener más información sobre el uso de la colección de servicios de salud para mejorar la colaboración del equipo de salud en Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> El contenido de esta sección supone que ya ha implementado Teams en su organización. Si aún no ha lanzado Teams, empiece por leer [Cómo realizar Microsoft Teams](../../How-to-roll-out-teams.md).

Los siguientes escenarios están disponibles para las organizaciones sanitarias:

| Escenario | Descripción | Requisitos |
| -------- | -------- | -------- |
| [Visitas virtuales con integración de registro de atención sanitaria electrónica (EHR)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Programe, administre y realice visitas virtuales con los pacientes. Este escenario conecta Microsoft Teams y la plataforma Epic para admitir visitas virtuales. | Suscripción activa a Microsoft Cloud para la salud o suscripción a la oferta independiente de Microsoft Teams EHR Connector. <br> Los usuarios deben tener una licencia adecuada de Microsoft 365 u Office 365 que incluya reuniones de Microsoft Teams*. <br> Las organizaciones deben tener la versión Epic de noviembre de 2018 o posterior. <br>[Detalles de los requisitos de EHR](ehr-admin.md#before-you-begin) |
| [Visitas virtuales con Microsoft Bookings y la aplicación Bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Programe, administre y realice visitas virtuales con los pacientes. Este escenario depende de Microsoft Bookings para admitir las visitas virtuales. | Microsoft Bookings debe estar activado para la organización. <br> Todos los usuarios de la aplicación Bookings y todo el personal que participe en las reuniones deben tener una licencia compatible con la programación de reuniones de Teams*. <br>[Detalles de los requisitos de Bookings](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Paquetes de directivas de Teams](#teams-policy-packages)| Asegúrese de que los trabajadores clínicos, los trabajadores de la información y los dispositivos de sala de pacientes tengan el acceso adecuado a la funcionalidad de Teams.| Los usuarios deben tener una licencia adecuada*. |
| [Mensajería segura](#secure-messaging) | Preste más atención a los mensajes urgentes y tenga confianza en que el mensaje se ha recibido y leído. | Los usuarios deben tener una licencia adecuada*.  |
| [Plantillas de Teams](#teams-templates-for-healthcare-organizations) | Cree equipos que incluyan una plantilla predefinida de configuración, canales y aplicaciones preinstaladas para la comunicación y la colaboración dentro de una sala, pod o departamento, o entre varios barrios, vainas y departamentos dentro de un hospital. | Los usuarios deben tener una licencia adecuada*.  |
| [Coordinación y colaboración en el cuidado](#care-coordination-and-collaboration) | Los médicos y el personal pueden colaborar internamente en programaciones, documentos, tareas, entre otros.| Los usuarios deben tener una licencia adecuada*. |

*Se admiten Office 365 A3, A5, E3 y E5, así como Microsoft 365 Business Standard, A3, A5, E3 y E5. Para obtener más información sobre las licencias generales de Teams, vea [Administrar el acceso de usuario a Teams.](../../user-access.md)

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Visitas virtuales e integración de registros electrónicos de atención sanitaria (EHR)

Use la plataforma de reuniones completas en Microsoft Teams para programar, administrar y realizar visitas virtuales con pacientes.

- Si su organización ya usa registros de estado electrónicos o EHR, puede integrar Microsoft Teams para una experiencia más fluida. Microsoft Teams Electronic Health Record (EHR) Connector facilita que los médicos inicien una visita virtual a pacientes o consultas con otro proveedor de Teams directamente desde el sistema EHR. Para obtener más información, [vea Visitas virtuales con Teams: integración en EHR.](ehr-admin.md)
- Si no usa un EHR compatible, puede usar Microsoft Bookings y la aplicación Bookings en Teams. Para obtener más información, consulte [La aplicación Bookings y las visitas virtuales en Microsoft Teams.](../../bookings-app-admin.md)

![Visitas virtuales con Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Paquetes de directivas de Teams

Aplique paquetes de directivas de Teams para definir qué roles diferentes pueden hacer en Teams. Por ejemplo, especifique directivas para:

- Los trabajadores clínicos, como las enfermeras registradas, las enfermeras de cargo, los médicos y los trabajadores sociales, para que puedan tener acceso completo a chats, llamadas, administración de turnos y reuniones.
- Los trabajadores de la información de su organización sanitaria, como el personal de INFORMÁTICA, el personal de informática, el personal de finanzas y los responsables de cumplimiento, pueden tener acceso completo a chats, llamadas y reuniones.
- Salas de pacientes, para controlar la configuración de los dispositivos de salas de pacientes.

Para obtener más información, vea [Paquetes de directivas de Teams para el cuidado de la salud.](../../policy-packages-healthcare.md)

## <a name="secure-messaging"></a>Mensajería segura

La mensajería segura admite la colaboración de los equipos de salud, incluidas varias características nuevas:

- Un remitente de mensajes puede establecer una prioridad especial para su mensaje, por lo que se notifica repetidamente al destinatario hasta que lea el mensaje.
- Un remitente de mensajes puede solicitar una confirmación de lectura, por lo que se les notifica cuando el destinatario del mensaje ha leído un mensaje que envió.

Juntos, estas características permiten una atención más rápida a los mensajes urgentes y confianza en que el mensaje se ha recibido y leído. Los nuevos equipos de salud que usan estas características se pueden crear por paciente. Estas características están basadas en directivas y se pueden asignar a personas individuales o a todo Teams.

Para obtener más información, vea [Introducción a las directivas de mensajería segura para organizaciones sanitarias.](messaging-policies-hc.md)

También está relacionada con la mensajería segura es la capacidad de tener otros inquilinos federados por organizaciones sanitarias, lo que permite una comunicación entre inquilinos más enriquecida. (Vea [Administrar el acceso externo (federación) en Microsoft Teams).](../../manage-external-access.md)

## <a name="teams-templates-for-healthcare-organizations"></a>Plantillas de Teams para organizaciones sanitarias

Se desarrollaron nuevas plantillas para crear Teams para aplicar a una configuración de hospital y se esperan más pronto. Esto facilita la creación de equipos que los trabajadores sanitarios usan para coordinar la atención a los pacientes de varios departamentos o barrios. Para obtener más información, vea [Introducción a las plantillas de Teams para organizaciones sanitarias.](healthcare-templates.md) Los equipos se pueden iniciar para departamentos internos como cardiología o para salas de atención, y hay más plantillas en desarrollo.

## <a name="care-coordination-and-collaboration"></a>Coordinación y colaboración en el cuidado

Reúne a tu equipo de salud para coordinar la atención y colaborar con Microsoft Teams.

![Atención sanitaria: Colaborar con su equipo de salud en Teams](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams permite a médicos, médicos, enfermeras y otros docentes colaborar de forma eficiente con características de colaboración incluidas en Microsoft Teams, como:

- Configure equipos y canales para los equipos de salud y los trabajadores de la información. Use canales con pestañas como forma de estructurar su trabajo, con ayuda adicional de pestañas a las que pueden anclar orígenes de información.
- Chatear, publicar mensajes y comunicarse. Su equipo puede tener conversaciones persistentes sobre diferentes pacientes que necesitan atención.
- Llame y reúnase con los miembros del equipo de salud. Configure reuniones individuales o use reuniones de canal para administrar reuniones diarias, tanto con la potencia de las características de audio, vídeo, uso compartido de pantalla, grabación y transcripción de Teams.
- Almacene y comparta archivos y documentos. Su equipo de estado forma parte de un único equipo virtualizado que funciona y colabora en documentos de Office.

Además, su equipo puede usar aplicaciones en Teams para:

- Compartir listas y realizar un seguimiento de la información con la aplicación Listas
- Realizar un seguimiento y supervisar tareas con la aplicación Tareas
- Simplificar las aprobaciones con la aplicación Aprobaciones
- Crear, administrar y compartir programaciones con la aplicación Turnos

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Compartir listas y realizar un seguimiento de la información con la aplicación Listas

> [!NOTE]
> A partir del 30 de octubre de 2020, la aplicación Pacientes se ha retirado y sustituido por la aplicación Listas [en](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) Teams. Con Listas, los equipos de atención en su organización sanitaria pueden crear listas de pacientes para escenarios que van desde rondas y reuniones de equipo interdisciplinarias hasta la supervisión general de pacientes.

La aplicación Listas de Teams ayuda a los equipos a realizar un seguimiento de la información y organizar el trabajo. La aplicación está preinstalada para todos los usuarios de Teams y está disponible como pestaña en todos los equipos y canales. Las listas se pueden crear desde cero, a partir de plantillas predefinidas o importando datos a Excel.

los equipos de salud pueden usar la plantilla Pacientes para empezar. Pueden crear listas para realizar un seguimiento de las necesidades y el estado de los pacientes. Los datos de pacientes existentes en hojas de cálculo de Excel se pueden agregar para crear una lista en Teams. Estas listas se pueden usar para escenarios como las rondas y la supervisión de pacientes para coordinar la atención.

Por ejemplo, una enfermera de cargo crea una lista de pacientes en un equipo que incluye a todos los miembros del equipo de salud. Durante las rondas, el equipo de salud accede a Teams en sus dispositivos móviles y actualiza la información del paciente en la lista, que todos los miembros del equipo pueden ver para mantenerse sincronizado. En las sesiones de redondeo en las que el equipo de salud se reúne para analizar y evaluar las métricas clave de rendimiento del estado para asegurarse de que un paciente está en la ruta de deslizamiento correcta para el alta, pueden compartir esta información con Teams en una pantalla grande. los miembros del equipo de salud que no están en el sitio pueden unirse de forma remota.

Esta es una lista de ejemplo que se ha configurado para el redondeo de pacientes.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Captura de pantalla de lista de ejemplo para el redondeo de pacientes":::

Para obtener más información, vea [Administrar la aplicación Listas para su organización en Teams.](../../manage-lists-app.md)

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Realizar un seguimiento y supervisar tareas con la aplicación Tareas

Use [Tareas](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) en Teams para realizar un seguimiento de los elementos de todo el equipo de estado. El equipo de estado puede crear, asignar y programar tareas, clasificar tareas y actualizar el estado en cualquier momento desde cualquier dispositivo que ejecute Teams.

Para obtener más información, vea [Administrar la aplicación Tareas de su organización en Microsoft Teams](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Simplificar las aprobaciones con la aplicación Aprobaciones

Use [aprobaciones](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) para simplificar todas sus solicitudes y procesos con su equipo. Cree, administre y comparta aprobaciones directamente desde el hub para trabajar en equipo. Inicie un flujo de aprobación desde el mismo lugar en el que envía un chat, en una conversación de canal o desde la propia aplicación Aprobaciones. Solo tiene que seleccionar un tipo de aprobación, agregar detalles, adjuntar archivos y elegir aprobadores. Una vez enviado, se notifica a los aprobadores y pueden revisar y actuar según la solicitud.

Puede permitir la aplicación Aprobaciones para su organización y agregarla a sus equipos. Para obtener más información, vea Disponibilidad de la aplicación [Aprobaciones de Teams.](../../approval-admin.md)

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Crear, administrar y compartir programaciones con la aplicación Turnos y la integración de trabajadores de frontline

Microsoft Teams se integra con la aplicación Turnos y El trabajador en primera línea, que se puede usar para coordinar las características de personal de turnos y mucho más. Por ejemplo, en Turnos, los jefes de enfermería pueden configurar y coordinar las programaciones para su personal, y las enfermeras pueden comprobar las programaciones e intercambiar turnos. Teams incluye una directiva de configuración integrada de la aplicación Trabajador de frontline que puede asignar a trabajadores de frontline en su organización. De forma predeterminada, la directiva incluye las aplicaciones Actividad, Turnos, Chat y Llamadas. Esta directiva controla el comportamiento de estas aplicaciones, por ejemplo, anclando la aplicación Turnos a la barra de aplicaciones para que el equipo pueda acceder a ella rápidamente.

Para obtener más información, vea [Administrar la aplicación Turnos para su organización en Microsoft Teams.](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Ayudar a los trabajadores de la información y a la clínica a empezar a trabajar con Teams

Hay muchos recursos disponibles para ayudar a todos los usuarios de su organización a sentirse cómodos con el uso de Teams:

- Visite el [Centro de](https://adoption.microsoft.com/microsoft-teams/) adopción de Teams para obtener consejos sobre la implementación de Teams si acaba de iniciar el viaje de su organización con Teams o expandir Teams a más áreas de su organización.
- Considere la posibilidad de configurar las [rutas de](https://adoption.microsoft.com/microsoft-365-learning-pathways/) aprendizaje personalizadas para que los usuarios puedan cubrir solo las tareas que deben realizar.
- Obtenga ayuda y aprendizaje para los usuarios sobre cómo realizar tareas básicas en Microsoft Teams en el sitio de soporte técnico de [Teams,](https://support.microsoft.com/teams)incluidos vídeos [de aprendizaje rápido.](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7) Este sitio también tiene ayuda y aprendizaje para las aplicaciones [](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)de Teams, como [Listas,](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) [Tareas,](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)Aprobaciones, Reservas y [](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) [Turnos.](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
