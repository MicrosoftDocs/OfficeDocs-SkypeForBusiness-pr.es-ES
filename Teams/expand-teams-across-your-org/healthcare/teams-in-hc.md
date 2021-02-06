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
description: Obtenga información sobre características de cuidado de la salud como Microsoft Teams telehealth, integración con EHR, integración del sistema de los trabajadores de frontline y la aplicación Pacientes.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: a5b8ea7cddba8def74a1f5b839710cf73bafc67e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125773"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Introducción a Teams para organizaciones sanitarias

Microsoft Teams ofrece varias características avanzadas útiles para hospitales y otras organizaciones sanitarias. Las características de Teams están en desarrollo para ayudar a los hospitales con:

- Visitas virtuales e integración del registro sanitario electrónico (EHR)
- Paquetes de directivas de Teams
- Mensajería segura
- Plantillas de Teams
- Colaboración y coordinación de cuidados

Esta funcionalidad forma parte de Microsoft Cloud para la salud. Obtenga más información sobre el uso de esta solución, que reúne funcionalidades de Azure, Dynamics 365 y Microsoft 365 en [Microsoft Cloud para el sector sanitario.](https://docs.microsoft.com/industry/healthcare)

Vea el siguiente vídeo para obtener más información sobre el uso de la colección sanitaria para mejorar la colaboración entre equipos de salud en Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> El contenido de esta sección asume que ya ha implementado Teams en su organización. Si aún no ha lanzado Teams, empiece leyendo [cómo lanzamiento Microsoft Teams.](../../How-to-roll-out-teams.md)

Las organizaciones sanitarias pueden ver los escenarios siguientes:

| Escenario | Descripción | Requisitos |
| -------- | -------- | -------- |
| [Visitas virtuales con integración del registro sanitario electrónico (EHR)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Programe, administre y realice visitas virtuales con pacientes. Este escenario conecta Microsoft Teams y la plataforma Épicos para admitir visitas virtuales. | Suscripción activa a Microsoft Cloud para el ámbito sanitario o suscripción a la oferta independiente de Microsoft Teams EHR Connector. <br> Los usuarios deben tener una licencia adecuada de Microsoft 365 u Office 365 que incluya reuniones de Microsoft Teams*. <br> Las organizaciones deben tener la versión épicos de noviembre de 2018 o posterior. <br>[Detalles de los requisitos de EHR](ehr-admin.md#before-you-begin) |
| [Visitas virtuales con Microsoft Bookings y la aplicación Bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Programe, administre y realice visitas virtuales con pacientes. Este escenario depende de Microsoft Bookings para admitir visitas virtuales. | Microsoft Bookings debe estar activado para la organización. <br> Todos los usuarios de la aplicación Bookings y todos los miembros del personal que participen en las reuniones deben tener una licencia compatible con la programación de reuniones de Teams*. <br>[Detalles de los requisitos de Bookings](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Paquetes de directivas de Teams](#teams-policy-packages)| Asegúrese de que los trabajadores clínicos, los trabajadores de la información y los dispositivos de la sala del paciente tengan acceso adecuado a la funcionalidad de Teams.| Los usuarios deben tener una licencia adecuada*. |
| [Mensajería segura](#secure-messaging) | Obtenga una atención más rápida a los mensajes urgentes y tenga la confianza de que el mensaje se ha recibido y leído. | Los usuarios deben tener una licencia adecuada*.  |
| [Plantillas de Teams](#teams-templates-for-healthcare-organizations) | Cree equipos que incluyan una plantilla predefinida de configuración, canales y aplicaciones preinstaladas para la comunicación y la colaboración en un centro hospitalario, una vaina o un departamento, o entre varios lendores, vainas y departamentos de un hospital. | Los usuarios deben tener una licencia adecuada*.  |
| [Colaboración y coordinación de cuidados](#care-coordination-and-collaboration) | Los médicos y el personal pueden colaborar internamente en programaciones, documentos, tareas, entre otros.| Los usuarios deben tener una licencia adecuada*. |

*Se admiten Office 365 A3, A5, E3 y E5, así como Microsoft 365 Empresa Estándar, A3, A5, E3 y E5. Para obtener más información sobre las licencias generales de Teams, consulte [Administrar el acceso de los usuarios a Teams.](../../user-access.md)

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Visitas virtuales e integración del registro sanitario electrónico (EHR)

Use la plataforma completa de reuniones en Microsoft Teams para programar, administrar y realizar visitas virtuales con pacientes.

- Si su organización ya usa registros de salud electrónicos o EHR, puede integrar Microsoft Teams para una experiencia más fluida. El conector del registro sanitario electrónico (EHR) de Microsoft Teams facilita a los médicos iniciar una visita virtual a un paciente o una consulta con otro proveedor en Teams directamente desde el sistema EHR. Para obtener más información, [consulte visitas virtuales con Teams : integración en EHR.](ehr-admin.md)
- Si no usa ehr compatible, puede usar Microsoft Bookings y la aplicación Bookings en Teams. Para obtener más información, [consulte la aplicación Bookings y las visitas virtuales en Microsoft Teams.](../../bookings-app-admin.md)

![Visitas virtuales con Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Paquetes de directivas de Teams

Aplique paquetes de directiva de Teams para definir qué pueden hacer los diferentes roles en Teams. Por ejemplo, especifique directivas para:

- Los trabajadores clínicos, como los servicios de enfermería registrados, las enfermeras, los médicos y los trabajadores sociales, pueden tener acceso total a chat, llamadas, administración de turnos y reuniones.
- Los trabajadores de la información de su organización sanitaria, como el personal de IT, el personal de informática, el personal de finanzas y los responsables de cumplimiento normativo, pueden tener acceso total al chat, las llamadas y las reuniones.
- Salas de pacientes, para controlar la configuración de los dispositivos de la sala del paciente.

Para obtener más información, consulte los [paquetes de directivas de Teams para la salud.](../../policy-packages-healthcare.md)

## <a name="secure-messaging"></a>Mensajería segura

La mensajería segura admite la colaboración dentro de los equipos de estado, incluidas varias características nuevas:

- Un remitente de mensajes puede establecer una prioridad especial para su mensaje, por lo que se le notificará repetidamente al destinatario hasta que lea el mensaje.
- Un remitente de mensajes puede solicitar una confirmación de lectura, por lo que se le notifica cuando el destinatario del mensaje ha leído un mensaje que ha enviado.

Juntos, estas características permiten una atención más rápida a los mensajes urgentes y la confianza de que el mensaje se ha recibido y leído. Los nuevos equipos de salud que usan estas características se pueden crear por paciente. Estas características están basadas en directivas y se pueden asignar a individuos o a equipos completos.

Para obtener más información, consulte [Introducción a las directivas de mensajería segura para organizaciones sanitarias.](messaging-policies-hc.md)

También relacionada con la mensajería segura es la capacidad de tener otros inquilinos federados por organizaciones sanitarias, lo que permite una comunicación entre inquilinos más rica. (Consulte [Administrar acceso externo (federación) en Microsoft Teams).](../../manage-external-access.md)

## <a name="teams-templates-for-healthcare-organizations"></a>Plantillas de Teams para organizaciones sanitarias

Las nuevas plantillas para crear Teams se desarrollaron para aplicarse a un entorno hospitalario y pronto se espera más. Esto facilita la creación de equipos que los trabajadores de salud usan para coordinar la atención a los pacientes de varios departamentos o centros de salud. Para obtener más información, consulte [Introducción a las plantillas de Teams para organizaciones sanitarias.](healthcare-templates.md) Se pueden iniciar equipos para departamentos internos como la reanude o para cuidadores, y se están en desarrollo más plantillas.

## <a name="care-coordination-and-collaboration"></a>Colaboración y coordinación de cuidados

Colabore con su equipo de salud para coordinar la atención y colaborar con Microsoft Teams.

![Salud: Colabore con su equipo de salud en Teams](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams permite que médicos, médicos, enfermeras y otros docentes colaboren de forma eficaz con las características de colaboración incluidas en Microsoft Teams, como:

- Configure equipos y canales para los equipos de salud y los trabajadores de la información. Use los canales con pestañas como forma de estructurar su trabajo, con ayuda adicional de fichas en las que pueden anclar orígenes de información.
- Chatear, publicar mensajes y comunicarse. Su equipo puede mantener conversaciones persistentes sobre diferentes pacientes que necesitan atención.
- Llame y reúnase con los miembros del equipo de salud. Configure reuniones individuales o use reuniones de canal para administrar las reuniones diarias, ambas con la potencia de las características de audio, vídeo, pantalla compartida, grabación y transcripción de Teams.
- Almacene y comparta archivos y documentos. El equipo de estado forma parte de un único equipo virtualizado que trabaja y colabora en documentos de Office.

Además, su equipo puede usar aplicaciones en Teams para:

- Compartir listas y realizar un seguimiento de la información con la aplicación Listas
- Realizar un seguimiento de las tareas y supervisar las tareas con la aplicación Tareas
- Simplificar las aprobaciones con la aplicación Aprobaciones
- Crear, administrar y compartir programaciones con la aplicación Turnos

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Compartir listas y realizar un seguimiento de la información con la aplicación Listas

> [!NOTE]
> A partir del 30 de octubre de 2020, la aplicación Pacientes se ha retirado y reemplazado por la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Con Listas, los equipos de cuidado de su organización sanitaria pueden crear listas de pacientes para situaciones que van desde rounds y reuniones de equipo interdisciplinarias hasta la supervisión general del paciente.

La aplicación Listas de Teams ayuda a los equipos a realizar un seguimiento de la información y organizar el trabajo. La aplicación está preinstalada para todos los usuarios de Teams y está disponible como pestaña en todos los equipos y canales. Las listas se pueden crear desde cero, a partir de plantillas predefinidas o importando datos a Excel.

los equipos de salud pueden usar la plantilla Pacientes para empezar. Pueden crear listas para realizar un seguimiento de las necesidades y el estado de los pacientes. Los datos de pacientes existentes en las hojas de cálculo de Excel se pueden agregar para crear una lista en Teams. Estas listas se pueden usar para situaciones como redondear y supervisar al paciente para coordinar la atención.

Por ejemplo, una enfermera de cargo crea una lista de pacientes en un equipo que incluye a todos los miembros del equipo de salud. Durante las rondas, el equipo de salud accede a Teams en sus dispositivos móviles y actualiza la información del paciente en la lista, que todos los miembros del equipo pueden ver para mantenerse sincronizado. En las sesiones de redondeo en las que el equipo de salud se reúne para analizar y evaluar las métricas clave de rendimiento de salud para garantizar que un paciente está en la ruta correcta para realizar la descarga, pueden compartir esta información mediante Teams en una pantalla de pantalla grande. los miembros del equipo de estado que no están en el sitio pueden unirse de forma remota.

Esta es una lista de ejemplo que se ha configurado para el redondeo del paciente.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Captura de pantalla de la lista de ejemplo para el redondeo del paciente":::

Para obtener más información, [consulte Administrar la aplicación Listas para su organización en Teams.](../../manage-lists-app.md)

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Realizar un seguimiento de las tareas y supervisar las tareas con la aplicación Tareas

Use [Tareas](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) en Teams para realizar un seguimiento de tareas pendientes para todo su equipo de estado. El equipo de estado puede crear, asignar y programar tareas, clasificar tareas y actualizar el estado en cualquier momento desde cualquier dispositivo que ejecute Teams.

Para obtener más información, [consulte Administrar la aplicación Tareas de su organización en Microsoft Teams](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Simplificar las aprobaciones con la aplicación Aprobaciones

Use [aprobaciones](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) para simplificar todas sus solicitudes y procesos con su equipo. Cree, administre y comparta aprobaciones directamente desde su hub para el trabajo en equipo. Inicie un flujo de aprobación desde el mismo lugar en el que envía un chat, en una conversación de canal o desde la propia aplicación Aprobaciones. Solo tiene que seleccionar un tipo de aprobación, agregar detalles, adjuntar archivos y elegir aprobadores. Una vez enviados, se notifica a los aprobadores, que pueden revisar y actuar en la solicitud.

Puede permitir la aplicación Aprobaciones para su organización y agregarla a sus equipos. Para obtener más información sobre la administración de aplicaciones, vea [Administrar las aplicaciones en el Centro de administración de Microsoft Teams.](../../manage-apps.md)

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Crear, administrar y compartir programaciones con la aplicación Turnos y la integración con el trabajador de frontline

Microsoft Teams se integra con la aplicación Turnos y el trabajador de la línea frontal, que se puede usar para coordinar características de personal de turnos y mucho más. Por ejemplo, en Turnos, los administradores de enfermeras pueden configurar y coordinar programaciones para el personal, y las enfermeras pueden comprobar programaciones e intercambiar turnos. Teams incluye una directiva de configuración de la aplicación Frontline Worker integrada que puede asignar a los trabajadores de frontline workers de su organización. De forma predeterminada, la directiva incluye las aplicaciones Actividad, Turnos, Chat y Llamadas. Esta directiva controla el comportamiento de estas aplicaciones, por ejemplo, al anclar la aplicación Turnos a la barra de la aplicación para que el equipo pueda obtener acceso a ella rápidamente.

Para obtener más información, [consulte Administrar la aplicación Turnos para su organización en Microsoft Teams.](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Ayude a su médico e a los trabajadores de la información a empezar a trabajar con Teams

Hay muchos recursos disponibles para ayudar a todos los usuarios de su organización a que se sientan cómodos con Teams:

- Visite el centro de [adopción](https://adoption.microsoft.com/microsoft-teams/) de Teams para obtener consejos sobre cómo implementar Teams si solo va a iniciar el viaje de su organización con Teams o a expandir Teams en más áreas de su organización.
- Considere la posibilidad de configurar [rutas de aprendizaje personalizadas](https://adoption.microsoft.com/microsoft-365-learning-pathways/) para que los usuarios cubran solo las tareas que tienen que hacer.
- Obtenga ayuda y formación para sus usuarios sobre cómo realizar tareas básicas en Microsoft Teams en el sitio de soporte técnico de [Teams,](https://support.microsoft.com/teams)incluidos vídeos [de aprendizaje rápido.](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7) Este sitio también tiene ayuda y formación para las [](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)aplicaciones de Teams, como [Listas,](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) [Tareas,](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)Aprobaciones, [Reservas](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)y [Turnos.](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
