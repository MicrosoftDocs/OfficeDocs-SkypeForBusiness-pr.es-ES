---
title: ¿Qué son los eventos en directo de Microsoft Teams?
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: sonua
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo los eventos en vivo permiten a los usuarios difundir vídeo y contenido a grandes audiencias en línea en Teams, Yammer y Stream.
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.liveevents
- ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43a5914c0ad9690859264e5c64e0652a5095decb
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570151"
---
# <a name="what-are-microsoft-teams-live-events"></a>¿Qué son los eventos en directo de Microsoft Teams?

## <a name="overview"></a>Información general

Con los eventos de Teams Live, los usuarios de su organización pueden difundir contenido de vídeo y de reuniones a grandes audiencias en línea. 

Los eventos en directo de Microsoft 365 proporcionan streaming de video en vivo a un nuevo nivel, lo que fomenta la conexión durante todo el ciclo de vida del compromiso con los asistentes antes, durante y después de eventos en vivo. Puede crear un evento en vivo dondequiera que esté el público, el equipo o la comunidad, usando Microsoft Stream, Teams o Yammer.  

Teams ofrece colaboración, llamadas, reuniones y eventos en vivo basados en chat, de modo que pueda ampliar la audiencia de sus reuniones. Teams Live Events es una extensión de las reuniones de Teams, que permite a los usuarios difundir contenido de vídeo y de reunión a una gran audiencia en línea. Estas son las destinadas a las comunicaciones de uno a varios en las que el anfitrión del evento está haciendo que las interacciones y la participación de los participantes se vean principalmente con el contenido compartido por el anfitrión. Los asistentes pueden ver el evento en vivo o grabado en Yammer, Teams o Stream, y pueden interactuar con los moderadores mediante la & una conversación de preguntas o respuestas moderados A de Yammer.

Los eventos de Teams Live se consideran la siguiente versión de difusión de reunión de Skype y, finalmente, sustituirán las capacidades proporcionadas en difusión de reunión de Skype. En este momento, Microsoft seguirá admitiendo difusión de reunión de Skype para los usuarios que usen Skype empresarial en sus organizaciones, sin interrupciones en el servicio de eventos nuevos o futuros. Sin embargo, le recomendamos que pruebe los eventos de Teams Live para aprovechar todas las características nuevas e interesantes, como la pantalla compartida y la compatibilidad con codificadores de software y hardware externos.

Por tanto, vamos a empezar. En primer lugar, eche un vistazo al siguiente diagrama en el que se muestran los componentes de alto nivel relacionados con los eventos en directo de Microsoft 365 y cómo se conectan. 

![Diagrama que muestra componentes clave de eventos en directo](../media/teams-live-events.png  "Diagrama en el que se muestran componentes clave de eventos en directo, programación, producción, plataforma de secuencias, proveedores certificados de eCDN de terceros")

### <a name="event-group-roles"></a>Roles de grupos de eventos
Los eventos en directo de Teams permiten a varias funciones (organizador, productor, moderador y asistente) difundir y participar correctamente en un evento. Para obtener más información, consulte [roles de grupos de eventos](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles).

## <a name="key-components"></a>Componentes clave
Puede ver en la imagen de arriba que hay cuatro componentes clave que se usan con eventos en directo de Teams.

> [!NOTE]
> Para obtener información general sobre cómo configurar los eventos en directo y la experiencia de los asistentes, consulte estos [vídeos](https://support.office.com/en-us/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)breves.

### <a name="scheduling"></a>Programación
Teams permite a los organizadores crear un evento con los permisos de asistente apropiados, designar miembros del equipo del evento, seleccionar un método de producción e invitar a los asistentes. Si el evento en directo se creó desde un grupo de Yammer, los asistentes del evento en directo podrán usar la conversación de Yammer para interactuar con las personas en el evento. 

![Captura de pantalla que muestra la pantalla de eventos nuevos en directo](../media/teams-live-events-schedule.png "Captura de pantalla que muestra la nueva pantalla de eventos en directo para crear y programar un evento en directo")

### <a name="production"></a>Elaboración
La entrada de video es el fundamento del evento en vivo y puede variar desde una sola cámara web a una producción de video profesional con varias cámaras. Los eventos en directo de Microsoft 365 admiten un espectro de escenarios de producción, incluido un evento producido en Teams con una cámara web o un evento generado en una aplicación o dispositivo externo. Puede elegir estas opciones en función de los requisitos del proyecto y el presupuesto. Existen dos formas de generar eventos:

- **Equipos**: este método de producción permite a los usuarios producir sus eventos en vivo en Teams usando su cámara web o usar la entrada a/V de los equipos de la sala de equipos. Esta es la opción más rápida y rápida si desea usar los dispositivos de audio y vídeo conectados al equipo o invitar a los moderadores remotos a participar en el evento. Esta opción permite a los usuarios utilizar fácilmente sus cámaras Web y compartir su pantalla como entrada en el evento. 

    ![Captura de pantalla que muestra un evento en directo producido con el método de inicio rápido](../media/teams-live-events-quick-start.png "Captura de pantalla que muestra un evento en directo que se produce con el método de inicio rápido de producción")

- **Dispositivo o aplicación externa**: los codificadores externos permiten a los usuarios producir sus eventos en directo directamente desde un hardware externo o codificador basado en software con [Stream](https://stream.microsoft.com). Esta opción es la mejor si ya tiene equipos de calidad de estudio (por ejemplo, las mezclas multimedia) que admiten transmisiones a un servicio RTMP (Protocolo de mensajería en tiempo real). Este tipo de producción suele usarse en eventos de gran escala, como salas de la ciudad Ejecutiva, donde una sola transmisión de un mezclador de medios se difunde al público. 

    ![Captura de pantalla que muestra un evento en directo producido mediante una aplicación o un dispositivo externo](../media/teams-live-events-external-encoder.png "Captura de pantalla que muestra un evento en directo que se produce con el método de producción de dispositivo o aplicación externa")

### <a name="streaming-platform"></a>Plataforma de streaming
La plataforma de transmisión por secuencias de eventos en directo consta de las siguientes partes:

- **Servicios multimedia de Azure**: [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/) le ofrece servicios de streaming de video de alta calidad para alcanzar audiencias mayores en los dispositivos móviles más populares de la actualidad. Servicios multimedia mejora la accesibilidad, la distribución y la escalabilidad, y hace que sea más fácil y rentable transmitir contenido a sus audiencias locales o de todo el mundo, a la vez que protege su contenido.
- **Red de entrega de contenido (CDN) de Azure**: una vez que la secuencia llega a funcionar, se realiza a través de la [red de entrega de contenido (CDN) de Azure](https://docs.microsoft.com/azure/cdn/). Servicios multimedia de Azure proporciona CDN integrado para los puntos de conexión de streaming. Esto permite que las transmisiones se vean en todo el mundo sin ningún almacenamiento en búfer.

### <a name="enterprise-content-delivery-network-ecdn"></a>Red de entrega de contenido empresarial (eCDN)
El objetivo de eCDN es tomar el contenido de video de Internet y distribuir el contenido en toda la empresa sin afectar al rendimiento de la red. Puede usar uno de los siguientes socios certificados de eCDN para optimizar su red para eventos en directo de su organización:
- [Subárbol](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](http://www.kollective.com)
- [Movimiento](http://www.ramp.com)

### <a name="attendee-experience"></a>Experiencia de asistente 
La experiencia de los asistentes es el aspecto más importante de los eventos en directo y es fundamental que los asistentes puedan participar en el evento en vivo sin tener ningún problema. La experiencia de asistente usa el reproductor multimedia de Azure (para eventos generados en Teams) y el reproductor de transmisión por secuencias (para eventos producidos en una aplicación o dispositivo externo) y funciona a través de escritorio, explorador y móvil (iOS, Android). Office 365 ofrece Yammer y Teams como dos concentradores de colaboración y la experiencia de los asistentes en vivo se integra en estas herramientas de colaboración. 

![Captura de pantalla que muestra la experiencia de asistente de eventos en directo](../media/teams-live-events-attendee.png "Captura de pantalla que muestra la experiencia de asistente de eventos en directo")

### <a name="live-event-usage-report"></a>Informe de uso de eventos en directo 
Los administradores de inquilinos pueden ver análisis de uso de tiempo real de eventos en directo en el centro de administración de Microsoft Teams.  El [Informe de uso de eventos en directo](../teams-analytics-and-reports/teams-live-event-usage-report.md) muestra la información general de actividad de los eventos en directo que se mantienen en la organización.  Los administradores pueden ver la información de uso de eventos, como el estado de los eventos, la hora de inicio, las vistas y el tipo de producción.  

## <a name="next-steps"></a>Pasos siguientes
Vaya a [planificar eventos en vivo de Teams](plan-for-teams-live-events.md).

### <a name="related-topics"></a>Temas relacionados
- [Eventos en directo de Microsoft 365 en Yammer, Microsoft Teams y Microsoft Stream](https://docs.microsoft.com/stream/live-event-m365)
- [Introducción a los eventos de Microsoft Teams Live](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [Eventos en directo en Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Eventos en directo de Microsoft Stream](https://docs.microsoft.com/stream/live-event-overview)

 
