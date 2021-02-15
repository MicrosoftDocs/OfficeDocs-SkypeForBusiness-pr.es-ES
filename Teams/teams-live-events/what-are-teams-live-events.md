---
title: What are Microsoft Teams live events? (¿Qué son los eventos en directo de Microsoft Teams?)
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365solution-spcomms
- m365solution-scenario
ms.reviewer: sonua
audience: admin
search.appverid: MET150
description: Descubra cómo los eventos en directo permiten a los usuarios difundir vídeo y contenido a un amplio público en Teams, Yammer y Stream.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.liveevents
- ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 78e2fdb6b205316dfd8a715c12613be1486302f5
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918996"
---
# <a name="what-are-microsoft-teams-live-events"></a>¿Qué son los eventos en directo de Microsoft Teams?

## <a name="overview"></a>Información general

Con los eventos en directo de Teams, los usuarios de su organización pueden difundir contenido de vídeo y reuniones a un amplio público en línea.

Los eventos en directo de Microsoft 365 llevan el streaming de vídeo en directo a otro nivel. Los eventos en directo promueven la conexión durante todo el ciclo de vida de interacción con los participantes antes, durante y tras los eventos en directo. Puede crear un evento en directo dondequiera que se encuentre el público, el equipo o la comunidad, con Microsoft Stream, Teams o Yammer.  

Teams ofrece colaboración basada en el chat, llamadas, reuniones y eventos en directo, para que pueda ampliar el público de sus reuniones. Los eventos en directo de Teams son una extensión de las reuniones de Teams que permiten a los usuarios difundir contenido de vídeo y de reuniones a un público en línea más amplio. Los eventos en directo están pensados para las comunicaciones de una persona con varias personas; en dichas comunicaciones, el organizador del evento dirige las interacciones y la participación del público consiste principalmente en visualizar el contenido que el organizador comparte. Los asistentes pueden ver el evento en directo o grabado en Yammer, Teams o Stream, y pueden interactuar con los moderadores con Preguntas y respuestas moderadas o una conversación de Yammer.

Los eventos en directo de Teams se consideran la nueva versión de Difusión de reunión de Skype y en algún momento sustituirán las funciones de Difusión de reunión de Skype. En estos momentos, Microsoft seguirá ofreciendo compatibilidad con Difusión de reunión de Skype para los usuarios que empleen Skype Empresarial en sus organizaciones, y no tendrá lugar una interrupción del servicio en eventos nuevos o futuros. Sin embargo, animamos a los usuarios a probar los eventos en directo de Teams para aprovechar todas las nuevas e interesantes características que ofrece, incluida la opción de pantalla compartida y la compatibilidad con codificadores externos de hardware o software.

Empecemos. En primer lugar, echemos un vistazo al siguiente diagrama, que muestra los componentes de alto nivel presentes en los eventos en directo de Microsoft 365 y cómo están conectados.

![Componentes clave de los eventos en directo](../media/live-event-flow-diagram.png  "Componentes clave de eventos en directo, programación, producción, plataforma de Stream, proveedores de terceros certificados de eCDN")

### <a name="event-group-roles"></a>Roles de grupo para eventos

Los eventos en directo en Teams posibilitan múltiples roles (organizador, productor, moderador y asistente) para difundir y participar en un evento con éxito. Para más información, consulte [Roles de grupo para eventos](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles).

## <a name="key-components"></a>Componentes clave

Como puede ver en la imagen superior, hay cinco componentes clave que se emplean en los eventos en directo en Teams.

> [!NOTE]
> Para información general sobre cómo configurar eventos en directo y sobre la experiencia de los asistentes, vea estos breves [vídeos](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).

### <a name="scheduling"></a>Programar

Teams ofrece la posibilidad de que los organizadores puedan crear un evento con los permisos de asistente correspondientes, designar miembros del equipo de eventos, seleccionar un método de producción e invitar a los asistentes. Si el evento en directo se creó desde un grupo de Yammer, los asistentes al evento en directo podrán usar la conversación de Yammer para interactuar con las personas en el evento.

![la pantalla de Nuevos eventos en directo](../media/teams-live-events-schedule.png "Captura de pantalla de la pantalla de Nuevo evento en directo para crear y programar un nuevo evento en directo")

> [!IMPORTANT]
> Microsoft Teams no permitirá que los usuarios programen reuniones o eventos en directo cuando estén desconectados o tengan un ancho de banda limitado.

### <a name="production"></a>Producción

La entrada de vídeo constituye la base de un evento en directo y el método puede variar desde una única cámara web hasta una producción de vídeo profesional con varias cámaras. Los eventos en directo en Microsoft 365 admiten toda una serie de escenarios de producción, e incluyen eventos producidos en Teams mediante una cámara web o eventos producidos en una aplicación o dispositivo externos. Puede elegir entre estas opciones en función de los requisitos de su proyecto y su presupuesto. Puede producir eventos de dos maneras:

- **Teams**: Este método de producción permite a los usuarios producir los eventos en directo en Teams mediante su cámara web o entrada A/V desde los sistemas Sala de Teams. Esta es la mejor opción y la más rápida si desea utilizar los dispositivos de audio y vídeo conectados al PC o si invita a presentadores a participar en el evento. Esta opción permite a los usuarios usar su cámara web y compartir su pantalla con facilidad para participar en el evento.

- **Aplicación o dispositivo externos**: los codificadores externos permiten a los usuarios producir eventos en directo de manera directa desde un codificador externo basado en hardware o en software con [Stream](https://stream.microsoft.com). Esta es la mejor opción si ya cuenta con equipo de estudio de calidad (por ejemplo, mezcladoras de sonido) que sea compatible con la transmisión a un servicio de protocolo de mensajería en tiempo real (RTMP). Este tipo de producción se suele usar en eventos de gran escala, como asambleas públicas, en las que se transmite desde un solo equipo de mezcladora de sonido al público.

    ![un evento en directo producido con un dispositivo o aplicación externa](../media/teams-live-events-external-encoder.png "Captura de pantalla de un nuevo evento producido con el método de producción con aplicación o dispositivo externo")

>[!Note]
> El cambio de uso desde Microsoft Stream a [OneDrive para la Empresa y SharePoint para grabar las reuniones](../tmr-meeting-recording-change.md) estará basado en fases. Durante el lanzamiento podrá participar en esta experiencia, en noviembre tendrá que cancelar la suscripción si desea continuar usando Stream y por un tiempo, a principios de 2021, requeriremos que todos los clientes usen OneDrive para la Empresa y SharePoint para grabar nuevas reuniones.

### <a name="streaming-platform"></a>Plataforma de streaming

La plataforma de streaming de eventos en directo se compone de lo siguiente:

- **Azure Media Services**: [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/) ofrece servicios de streaming de vídeo de calidad para llegar a un público más amplio desde los dispositivos móviles más populares de la actualidad. Azure Media Services mejora la accesibilidad, distribución y escalabilidad y hace que resulte más fácil y rentable transmitir contenido a un público local o global, al tiempo que protege su contenido.
- **Azure Content Delivery Network (CDN)**: La transmisión en directo la lleva a cabo [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/). Azure Media Services ofrece puntos de conexión integrados de CDN para streaming. Esto permite a un público global seguir la transmisión sin almacenamiento en búfer.

### <a name="enterprise-content-delivery-network-ecdn"></a>Content Delivery Network para empresas (eCDN)

El objetivo de eCDN consiste en tomar el contenido de vídeo de internet y distribuirlo por toda su empresa sin que el rendimiento de red se vea afectado. Puede utilizar uno de los siguientes socios certificados de eCDN para optimizar la red para eventos en directo que tengan lugar en su organización:

- [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](https://kollective.com/ecdn-solutions/microsoft-live-events/)
- [Ramp](https://rampecdn.com)
- [Riverbed](https://www.riverbed.com/solutions/office-365.html)

### <a name="attendee-experience"></a>Experiencia de los asistentes

La experiencia de los asistentes es el aspecto más importante de los eventos en directo y es fundamental que los asistentes puedan participar en el evento en directo sin experimentar problemas. La experiencia de los asistentes utiliza Stream Player (para eventos producidos en Teams) y Azure Media Player (para eventos producidos en una aplicación o dispositivo externos) y funciona en escritorios, exploradores y dispositivos móviles (iOS, Android). Microsoft 365 y Office 365 ofrecen Yammer y Teams como dos centros de colaboración, y la experiencia de los asistentes de eventos en directo se integra en estas herramientas de colaboración.

![Ejemplo de la experiencia de los asistentes de eventos en directo](../media/teams-live-events-attendee.png "Captura de pantalla de la experiencia de los asistentes de eventos en directo")

### <a name="live-event-usage-report"></a>Informe de uso de eventos en directo

Los administradores de espacio empresarial pueden visualizar análisis de uso en tiempo real de eventos en directo en el Centro de administración de Microsoft Teams.  El [informe de uso de eventos en directo](../teams-analytics-and-reports/teams-live-event-usage-report.md) muestra información general de actividad de los eventos en directo que se han realizado en la organización.  Los administradores pueden visualizar la información de uso de los eventos, incluido el status del evento, hora de inicio, visualizaciones y tipo de producción.  

## <a name="next-steps"></a>Pasos siguientes

Vaya a [Planear eventos en directo en Teams](plan-for-teams-live-events.md).

### <a name="related-topics"></a>Temas relacionados

- [Eventos en directo en Microsoft 365 en Yammer, Microsoft Teams y Microsoft Stream](https://docs.microsoft.com/stream/live-event-m365).
- [Introducción a los eventos en vivo de Microsoft Teams](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [Eventos en directo en Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Eventos en directo en Microsoft Stream](https://docs.microsoft.com/stream/live-event-overview)
