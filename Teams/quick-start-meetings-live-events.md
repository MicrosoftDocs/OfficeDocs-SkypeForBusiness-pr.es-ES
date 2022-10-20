---
title: Reuniones, seminarios web y eventos en vivo
ms.reviewer: ''
description: Una guía para que los administradores implementen y configuren reuniones, seminarios web y eventos en directo en Microsoft Teams.
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
ms.subservice: meetings
ms.custom: intro-overview
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 982730f7c839eeab2a55bc8997eade8aec31bebc
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614273"
---
# <a name="meetings-webinars-and-live-events"></a>Reuniones, seminarios web y eventos en vivo

Existen varias formas de reunirse en Microsoft Teams: reuniones, seminarios web y eventos en directo.

En este artículo, destinado a administradores y profesionales de TI, se describen las diferencias entre reuniones, seminarios web y eventos en directo. A continuación, le ofrece vínculos con la información que necesita para implementar rápidamente esta funcionalidad para los usuarios.

[Meetings](#meetings), [webinars](#webinars), and [live events](#live-events) are all types of meetings, but webinars and live events provide additional control for the organizer over the conversation and participants. Webinars provide two-way interaction while live events provide a managed Q&A experience. 

Los distintos tipos de reuniones también tienen diferentes límites de participantes y de capacidades de los participantes. 

En la tabla siguiente, se resumen los tres tipos de reuniones, el número de participantes recomendados y cómo pueden los participantes interactuar en la reunión. Para obtener más información sobre cada tipo de reunión, siga la tabla. En este artículo, también se incluye una sección sobre los [procedimientos recomendados para las reuniones grandes](#best-practices-for-large-meetings).

| Tipo de reunión | Número de participantes | Interacción | Registro admitido |
|----------|--------|--------|-----|
| Reuniones  | Hasta 20 000* | - Los participantes hasta llegar a 1000 tienen capacidades de reunión totalmente interactivas e idénticas. <br> - Los participantes de 1000 hasta 20 000 tienen capacidades de [solo vista](view-only-meeting-experience.md).  | No |
| Seminarios web | - Hasta 1000<br>- Próximamente se aumentarán los límites con capacidades de [solo vista](view-only-meeting-experience.md). |- Los participantes hasta llegar a 1000 tienen capacidades de reunión totalmente interactivas.<br> - Interacción de audiencia configurable.<br> - Puede especificar moderadores. | Sí |
| Eventos en directo | Hasta 20 000** |- Difusión a grandes audiencias. <br>- Preguntas y respuestas moderadas para la interacción del público. <br> - Se puede especificar productores y moderadores, incluidos moderadores externos.<br>- Compatible con más capacidades de producción avanzadas. | No |

*Los 10 000 habituales se incrementan a 20 000 hasta el 31 de diciembre de 2022.

**Los 10 000 habituales se incrementan a 20 000 hasta el 31 de diciembre de 2022. Puede programar reuniones para incluso más asistentes con eventos en directo en Yammer o Microsoft Stream. Para obtener más información, consulte [Eventos en directo en todo Microsoft 365](/stream/live-event-m365).  Tenga en cuenta que los eventos de más de 20 000 asistentes requieren el [Programa de asistencia de eventos en directo](/stream/live-events-assistance).

Note that NDI is fully supported in meetings, webinars, and live events, allowing you to produce the broadcast by using tools such as OBS and Wirecast. For more information, see [Use NDI® technology in Microsoft Teams](use-ndi-in-meetings.md).

> [!NOTE]
> Para obtener información adicional y obtener orientación por rol para ofrecer eventos en línea con Microsoft Teams, consulte el Libro de reproducción de [eventos virtuales](https://aka.ms/VirtualEventPlaybook). También puede unirse al [Foro de eventos virtuales](https://aka.ms/VirtualEventForum) en el Microsoft Tech Community.

> [!NOTE]
> Para obtener más información sobre cómo configurar rápidamente las reuniones y los eventos de Teams en las distintas plataformas, consulte [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="meetings"></a>Reuniones

Las **reuniones** en Teams incluyen audio, vídeo y uso compartido de la pantalla para hasta 1000 personas y [capacidades de solo vista](view-only-meeting-experience.md) para más de 1000 personas. Los participantes no necesitan ser miembros de una organización (ni tener una cuenta de Teams) para unirse a una reunión de Teams. Pueden unirse directamente desde la invitación del calendario a través del vínculo Unirse a la reunión o llamar a través de audio si esta opción está disponible.  

Como administrador, configurará las opciones de reunión y controlará qué características de reunión están habilitadas para su organización gracias a las directivas de reunión.  

Además de las reuniones programadas periódicamente, los usuarios pueden crear reuniones de canal. Con las reuniones de canal, todos los miembros de un equipo pueden ver que hay una reunión, unirse a la reunión y usar el chat de reunión. Las reuniones de canal son una manera de invitar rápidamente a todos los miembros de un equipo a una reunión. Para obtener más información sobre cómo los usuarios finales programan reuniones, vea [Programar una reunión](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5).

Para obtener información sobre la experiencia de reunión de solo vista, vea [Experiencia de reunión de solo vista de Teams](view-only-meeting-experience.md).

### <a name="articles-for-administrators"></a>Artículos para administradores

En la tabla siguiente se resaltan los artículos clave que desea revisar:

| Artículo | Descripción |
|----------|--------|
| [Configuración de las reuniones](meeting-settings-in-teams.md) |  Describe cómo configurar las reuniones para usuarios anónimos, invitaciones a reuniones y tráfico multimedia.  |
| [Directivas de reunión](meeting-policies-overview.md)  | Describe cómo crear y administrar las directivas que determinan qué características están disponibles para los participantes de la reunión. | 
| [Administración de grabaciones de reuniones en la nube de Teams](cloud-recording.md) | Describe cómo administrar las grabaciones de reuniones. |
| [Administración de los dispositivos de su organización](device-management.md)| Describe cómo administrar los dispositivos de su organización, como teléfonos y Salas de Teams. |
| [Usar telemetría en tiempo real para solucionar problemas de mala calidad de la reunión](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md) | Describe cómo usar el análisis en tiempo real (RTA) para solucionar problemas de calidad deficiente de las reuniones de Microsoft Teams para usuarios individuales.|

### <a name="key-training-for-end-users"></a>Aprendizaje clave para usuarios finales

En la tabla siguiente se muestra el aprendizaje disponible para los usuarios finales de su organización:

| Aprendizaje | Descripción |
|----------|--------|
| [Administrar reuniones](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) | Vídeo de aprendizaje rápido para los usuarios que no están familiarizados con las reuniones de Teams. |
| [Programar una reunión](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5) | Artículo que describe cómo programar diferentes tipos de reuniones. |
| [Ejecutar reuniones efectivas con Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings) | Una clase gratuita dirigida por un instructor sobre cómo hacer que las reuniones sean más atractivas, productivas y significativas. |
| [Cambiar la configuración de los participantes de una reunión de Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) | Artículo sobre la administración de opciones de reunión. |

## <a name="webinars"></a>Seminarios web

**Los seminarios web** son reuniones estructuradas en las que los moderadores y participantes tienen roles claramente definidos. Una diferencia clave entre los seminarios web y las reuniones de Teams es que los seminarios web permiten registrarse y proporcionan datos de participación de los asistentes. Para habilitar seminarios web en su organización, consulte [Configurar seminarios web en Teams](set-up-webinars.md).

### <a name="key-training-for-end-users"></a>Aprendizaje clave para usuarios finales

En la tabla siguiente se muestra el aprendizaje disponible para los usuarios finales de su organización:

| Aprendizaje | Descripción | 
|----------|--------|
| [Introducción a los seminarios web de Teams](https://support.microsoft.com/office/get-started-with-teams-webinars-42f3f874-22dc-4289-b53f-bbc1a69013e3) | Vídeo de aprendizaje rápido para los usuarios que no están familiarizados con los seminarios web de Teams. |
| [Guía de inicio rápido visual](https://adoption.microsoft.com/files/assets/TeamsWebinarsGetStartedGuide.pdf) | Guía visual descargable que describe cómo empezar a programar seminarios web. |


## <a name="live-events"></a>Eventos en directo

Los **eventos en directo** son reuniones estructuradas que permiten a su organización programar y producir eventos transmitidos a audiencias de hasta 20 000 personas en línea. Con los eventos en directo, se interactúa con el público en el formato de Preguntas y respuestas administradas.

### <a name="articles-for-administrators"></a>Artículos para administradores

En la tabla siguiente se resaltan los artículos clave que desea revisar:

| Artículo | Descripción |
|----------|--------|
| [¿Qué son los eventos en directo en Teams?](teams-live-events/what-are-teams-live-events.md)  | Una introducción rápida a los eventos en directo |
| [Planear eventos en directo en Teams](teams-live-events/plan-for-teams-live-events.md) | Lo que necesita saber antes de configurar los eventos en directo. |
| [Configuración de eventos en directo en Teams](teams-live-events/set-up-for-teams-live-events.md) | Describe los requisitos previos, como el planeamiento de red. |
| [Configuración de eventos en directo](teams-live-events/configure-teams-live-events.md) | Pasos para configurar los eventos en directo.|

### <a name="key-training-for-end-users"></a>Aprendizaje clave para usuarios finales

En la tabla siguiente se muestra el aprendizaje disponible para los usuarios finales de su organización:

| Aprendizaje | Descripción |
|:----------|:--------|
| [Introducción a los eventos en directo](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a) | Introducción a los eventos en directo y cómo empezar. |
| [Vídeo de aprendizaje de Eventos en directo de Teams](https://support.microsoft.com/en-us/office/plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502?ui=en-US&rs=en-US&ad=US) | Vídeo que describe cómo planear y programar un evento en directo.  |

Para generar eventos virtuales a mayor escala, revise la [guía de eventos virtuales](https://adoption.microsoft.com/virtual-event-guidance/), que contiene instrucciones para organizadores de eventos, productores técnicos, profesionales de TI y creadores de contenido.

## <a name="apps-for-meetings"></a>Aplicaciones para reuniones

Microsoft enables you to enhance meeting experiences by integrating and using meeting apps. For example, whiteboard integration in Teams meetings is powered by the Whiteboard web app, which lets Teams meeting participants draw, sketch, and write together on a shared digital canvas.

Puede agregar aplicaciones de reuniones a su implementación de Teams con las aplicaciones que le proporciona Teams, con plantillas y aplicaciones de terceros certificadas, o creando sus propias aplicaciones personalizadas.

En la tabla siguiente se enumeran artículos con los que puede obtener más información:

| Artículo | Descripción |
|----------|--------|
| [Información general sobre las aplicaciones de Teams](deploy-apps-microsoft-teams-landing-page.md) | Introducción a las aplicaciones y cómo implementarlas en su organización. |
| [Aplicaciones para reuniones de Teams](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings) | Información general sobre la extensibilidad de aplicaciones de reuniones, referencias de API y cómo habilitar y configurar aplicaciones para reuniones. |
| [Administrar Microsoft Whiteboard en Teams](manage-whiteboard.md) | Describe la funcionalidad de Whiteboard y cómo habilitarla y deshabilitarla en su organización. |

## <a name="license-requirements-for-meetings-webinars-and-live-events"></a>Requisitos de licencia para reuniones, seminarios web y eventos en directo

Cualquier usuario puede asistir a un seminario web, un evento en directo público o una reunión de Teams, ya que no se requiere ninguna licencia.

Para las personas que organizan, programan y hospedan reuniones, seminarios web o eventos en directo, necesitarán una de las licencias de Microsoft 365 enumeradas en la [Descripción del servicio Microsoft Teams](/office365/servicedescriptions/teams-service-description). Si ya usa Teams, es probable que tenga la licencia que necesita para organizar y hospedar reuniones, seminarios web y eventos en directo.

Para permitir que los usuarios inicien sesión en una reunión por teléfono, deberá configurar las audioconferencias. Para obtener más información sobre las audioconferencias, vea [Audioconferencia en Teams](deploy-audio-conferencing-teams-landing-page.md).

## <a name="best-practices-for-large-meetings"></a>Procedimientos recomendados para reuniones grandes

En esta sección, se proporcionan instrucciones para los administradores, junto con sugerencias que los administradores pueden compartir con sus moderadores y organizadores.

Para ejecutar un evento correcto, siga las prácticas que se describen a continuación:

- Para obtener la mejor experiencia con seminarios web, eventos en directo y reuniones de gran tamaño, Microsoft recomienda usar la última versión del cliente de escritorio o los clientes móviles de Teams.

- Asegúrese de que se hayan seguido todos los [principios de conectividad de red de Microsoft ](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles) tanto en el entorno local como para los usuarios remotos.
- Use la [telemetría de datos en tiempo real](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-real-time-call-quality-analytics/ba-p/2912146) para supervisar el evento e identificar los posibles problemas y su origen.
  - Designe monitores de reunión para [analizar](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md) la telemetría de los usuarios que tienen una experiencia deficiente causada por métricas que superan los umbrales.
  - Establezca los monitores de la reunión como presentadores para desactivar las transmisiones de vídeo no deseadas, silenciar los micrófonos en directo no deseados y eliminar a los asistentes si es necesario.

### <a name="guidelines-for-your-end-users"></a>Directrices para los usuarios finales

Los organizadores y moderadores deben implementar las siguientes recomendaciones:

- Para reuniones con más de 10 participantes, use [Preguntas y respuestas](/MicrosoftTeams/manage-qna-for-teams) para dar a los participantes la oportunidad de formular y recibir respuestas formalmente a preguntas, así como participar en conversaciones estructuradas.

- Para crear una reunión fluida, los organizadores de eventos pueden establecer moderadores predefinidos. Una vez iniciada una reunión, los moderadores también pueden promover a otros asistentes al rol de moderador.

- Definir un coorganizador mediante opciones de reunión (versión preliminar pública)

- Configurar de manera previa las opciones de vídeo y micrófono para controlar las experiencias de los asistentes.
  - Deshabilitar los micrófonos de los asistentes para evitar las molestias. Si alguien necesita interactuar durante la reunión, permítale desactivar el silencio cuando levante la mano.
  - Deshabilite el vídeo de los asistentes para evitar distracciones visuales. En los momentos convenientes de la reunión, se puede permitir el vídeo para todos los asistentes o para personas concretas.

- Use sondeos, y preguntas y respuestas durante la reunión.

- Use los controles de sala de espera para controlar las retenciones de la sala de espera o de la entrada a la reunión.

- Ejecute la [prueba de conectividad de red de Microsoft 365](https://connectivity.office.com/) para comprobar la idoneidad de la red varios días antes y el día del evento.

- Si realiza la presentación desde casa, compruebe que otros dispositivos no consumen un ancho de banda alto (servicios de streaming, juegos en línea, descargas grandes).

- Presente desde un punto de conexión con una conexión cableada para un uso compartido de pantalla, vídeo y audio más confiable.

- Asegúrese de que los usuarios tengan aplicación de Teams más reciente en un dispositivo móvil o de escritorio.

- Al usar un portátil, compruebe si tiene conectividad de red alta y suficiente energía.

- Programe un simulacro antes del evento para identificar problemas de dispositivo, iluminación o red. Esto también garantizará que los organizadores o moderadores estén familiarizados con las características que usarán.
  - Programe ejecuciones de prácticas adicionales si se han encontrado problemas para asegurarse de que los esfuerzos de corrección se hayan realizado de manera correcta.
  
- Use características como destacados, PowerPoint Live, grabación de reuniones, subtítulos y transcripciones para promover la participación y la eficacia.

- Los moderadores y participantes deben usar la aplicación de escritorio de Teams para proporcionar una experiencia óptima.

- Los participantes deben desactivar las notificaciones de chat durante las reuniones de gran tamaño para evitar distracciones.

- Para obtener más consejos sobre cómo organizar reuniones grandes, consulte [Prácticas recomendadas para una reunión grande de equipos](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16).

## <a name="related-topics"></a>Temas relacionados

[Reuniones y conferencias a través de Teams](deploy-meetings-microsoft-teams-landing-page.md)

[Configurar seminarios web en Teams](set-up-webinars.md)

[Eventos en directo en Yammer](teams-live-events/what-are-teams-live-events.md)

[Experiencia de reunión de solo vista para Teams](view-only-meeting-experience.md)

[Especificaciones y límites de Teams](limits-specifications-teams.md)

