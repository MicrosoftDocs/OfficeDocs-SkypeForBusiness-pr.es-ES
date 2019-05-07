---
title: ¿Qué son los eventos en directo de Microsoft Teams?
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: tonysmit
search.appverid: MET150
description: Obtenga información sobre cómo live eventos permiten a los usuarios difundir vídeo y contenido a grandes audiencias en línea en Microsoft Teams, Yammer y Microsoft Stream.
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01dfa91c13625e1f1f18fdce5840cf6ba2baeb79
ms.sourcegitcommit: 47e5f6a0440f646d67bc3ca7c232df9558f78040
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "33641496"
---
# <a name="what-are-microsoft-teams-live-events"></a>¿Qué son los eventos en directo de Microsoft Teams?

## <a name="overview"></a>Información general

Con Microsoft Teams eventos en directo, los usuarios de su organización pueden difundir contenido de vídeo y convocatorias de reunión a grandes audiencias en línea. 

Eventos en directo Microsoft 365 traer la transmisión por secuencias a un nuevo nivel, fomentar la conexión a lo largo del ciclo de vida de compromiso completo con los asistentes antes, durante y después de eventos en directo de vídeo en directo. Puede crear un evento en directo donde reside la audiencia, equipo o la Comunidad, utilizando Microsoft Stream, Microsoft Teams, o Yammer.  

Los equipos ofrece una colaboración basada en chat, llamada, las reuniones y con eventos en directo, por lo que puede ampliar el público de sus reuniones. Eventos en directo equipos es una extensión de las reuniones de los equipos, permitir a los usuarios difundir contenido de reuniones y vídeo a una audiencia en línea de gran tamaño. Estos están diseñados para las comunicaciones de uno a varios donde el host del evento es líder las interacciones y participación de la audiencia es principalmente ver el contenido compartido por host. Los asistentes pueden verla el evento grabado o en vivo en Yammer, los equipos o Microsoft Stream y pueden interactuar con los moderadores uso moderado Q & A o una conversación de Yammer. 

Eventos en directo se consideran la próxima versión de Difundir presentación de reunión de Skype y finalmente a los equipos de reemplazan las funciones proporcionadas en Difundir presentación de reunión de Skype. En este momento, Microsoft seguirá admitir la reunión Difundir presentación de Skype para usuarios que utilizan Skype para la empresa en sus organizaciones, sin interrupciones en el servicio de eventos nuevo o futuros. Sin embargo, le recomendamos que pruebe los equipos de eventos en directo para poder aprovechar todas las características nuevas y apasionantes incluidos compatibilidad con codificadores de hardware y software externos y el uso compartido de la pantalla. 

Por lo tanto, vamos a empezar. En primer lugar, eche un vistazo en el siguiente diagrama que muestra los componentes de nivel alto necesarios para Microsoft 365 eventos en directo y cómo se conectan. 

![Certificación de diagrama que muestra los componentes clave de eventos en directo, programación, de producción, secuencia de Microsoft plataforma, proveedores de terceros eCDN] (../media/teams-live-events.png  "Certificación de diagrama que muestra los componentes clave de eventos en directo, programación, de producción, secuencia de Microsoft plataforma, proveedores de terceros eCDN")

### <a name="event-group-roles"></a>Roles de grupo (evento)
Eventos en directo en los equipos permite a varios roles (Organizador, productor, moderador y attendee) para difundir correctamente y participar en un evento. Para obtener más información, consulte [roles de grupo de eventos](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles).

## <a name="key-components"></a>Componentes clave
Por lo tanto, se puede ver en la imagen anterior, hay cuatro componentes principales que se usan con eventos en directo en los equipos.

### <a name="scheduling"></a>Programación
Los equipos proporciona la capacidad para los organizadores crear un evento con el asistente apropiado de permisos, designar los integrantes del grupo de eventos, seleccione el método de producción e invitar a los asistentes. Si se creó el evento en directo desde dentro de un grupo de Yammer, los asistentes de evento live podrán usar Yammer conversación para interactuar con otras personas en el evento. 

![Captura de pantalla que muestra el nuevo live pantalla de eventos para crear y programar un evento en directo nuevo] (../media/teams-live-events-schedule.png "Captura de pantalla que muestra el nuevo live pantalla de eventos para crear y programar un evento en directo nuevo")

### <a name="production"></a>Producción
La entrada de vídeo es la base de los eventos en directo y puede variar de una cámara Web único a una producción de vídeo profesional de varias cámara. Los eventos live en Microsoft 365 admite una gran variedad de escenarios de producción, incluir un evento de inicio rápido con cámaras web o un evento que tiene lugar en un dispositivo externo o una aplicación. Puede elegir estas opciones según sus requisitos de proyecto y el presupuesto. Hay dos formas para producir eventos:

- **Los equipos de Microsoft**: este método de producción permite a los usuarios producir sus eventos en directo en Microsoft Teams utilizando su cámara Web o un / V una entrada de sistemas de la sala de equipos. Esta opción es mejor y más rápida opción si desea usar los dispositivos de audio y vídeos conectado a su PC o invita a los moderadores remotos por participar en el evento. Esta opción permite a los usuarios usar sus cámaras web fácilmente y compartir su pantalla como entrada en el evento. 

    ![Captura de pantalla que muestra un evento en directo producido mediante el uso de rápido inicia el método de producción] (../media/teams-live-events-quick-start.png "Captura de pantalla que muestra un evento en directo que se genera utilizando el rápido inicia el método de producción")

- **Aplicación externa o dispositivo**: codificadores externos permiten a los usuarios producir sus eventos en directo directamente desde un codificador basada en software con la [Secuencia de Microsoft](https://stream.microsoft.com)o un hardware externo. Esta opción es mejor si ya dispone de equipamiento de calidad studio (por ejemplo, mezcladores de medios) qué compatibilidad con transmisión por secuencias a un servicio de protocolo de mensajería en tiempo real (RTMP). Este tipo de producción se utiliza normalmente en los eventos de gran escala, como salas de ciudad ejecutivos – donde la difusión de una única secuencia de un mezclador de medios a la audiencia. 

    ![Captura de pantalla que muestra un evento en directo producido mediante el método de producción codificador externo] (../media/teams-live-events-external-encoder.png "Captura de pantalla que muestra un evento en directo que se genera utilizando el método de producción codificador externo")

### <a name="streaming-platform"></a>Plataforma de transmisión por secuencias
La plataforma de transmisión por secuencias del evento en directo se compone de las siguientes partes:

- **Servicios de medios de Azure**: [Servicios de medios de Azure](https://docs.microsoft.com/azure/media-services/previous/) proporciona servicios de transmisión por secuencias vídeo de calidad de difusión para llegar a más grandes audiencias en dispositivos móviles más populares de hoy. Servicios de medios mejora la accesibilidad, la distribución y la escalabilidad y de manera fácil y rentable para transmitir contenido a su público local o en todo el mundo, al mismo tiempo que protege su contenido.
- **Azure Content Delivery Network (CDN)**: una vez que entre la secuencia, se entrega a través de la [Red de entrega de contenido (CDN) de Azure](https://docs.microsoft.com/azure/cdn/). Servicios de medios Azure proporciona CDN integrada para transmitir los extremos. Esto permite que las secuencias para que se vean en todo el mundo con ningún almacenamiento en búfer.

### <a name="enterprise-content-delivery-network-ecdn"></a>Red de entrega de contenido empresarial (eCDN)
El objetivo de la red eCDN es tomar el contenido de vídeo de internet y distribuir el contenido en toda la empresa sin afectar el rendimiento de la red. Puede usar uno de estos partners de eCDN para optimizar la red para eventos en directo mantenidos dentro de la organización:
- [Subárbol](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](http://www.kollective.com)
- [Pendiente](http://www.ramp.com)

### <a name="attendee-experience"></a>Experiencia del Asistente 
La experiencia del asistente es el aspecto más importante de eventos en directo y es muy importante que los asistentes pueden participar en el evento en directo sin necesidad de los problemas. La experiencia del asistente usa Azure Media Player (para los eventos generados en Microsoft Teams) y Stream Player (para los eventos producidos en un enccoder externo) funciona a través de escritorio, explorador y mobile (iOS, Android). Office 365 proporciona Yammer y los equipos como dos concentradores de colaboración y el Asistente live experiencia se integra en estas herramientas de colaboración. 

![Experiencia de captura de pantalla que muestra al Asistente de eventos en directo] (../media/teams-live-events-attendee.png "Experiencia de captura de pantalla que muestra al Asistente de eventos en directo")

## <a name="next-steps"></a>Pasos siguientes
Vaya al [Plan para los equipos eventos en directo](plan-for-teams-live-events.md).

### <a name="related-topics"></a>Temas relacionados
- [Eventos en directo a través de Microsoft 365 en Yammer, Microsoft Teams y Stream de Microsoft](https://docs.microsoft.com/stream/live-event-m365)
- [Eventos en directo en Microsoft Teams](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Eventos en directo de Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Eventos en directo en Microsoft Stream](https://docs.microsoft.com/stream/live-event-overview)

 
