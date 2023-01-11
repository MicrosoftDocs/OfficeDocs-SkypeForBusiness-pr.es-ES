---
title: Información general sobre el codificador para el streaming en Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: En este artículo se ofrece información general sobre la configuración rtmp basada en codificadores para los eventos de streaming de Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d7ea21edb6677397785367cecd3daaf9bbe513f3
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767975"
---
# <a name="live-streaming-events-in-microsoft-teams"></a>Eventos de streaming en directo en Microsoft Teams

Puede crear eventos en directo con Microsoft Teams en toda la organización. Puede programar, producir y entregar eventos en directo para varios escenarios, como eventos de toda la empresa, actualizaciones de liderazgo y mucho más. Los eventos de streaming en directo permiten a los productores ajustar y controlar el contenido que se difunde a una audiencia.

Puede crear, programar y ejecutar eventos en directo con una única velocidad de bits RTMP o streaming RTMPS desde un codificador: nos ocuparemos de toda la transcodificación para que la velocidad de bits adaptable se entregue a los visores.

Al igual que con cualquier otro vídeo de Teams, puede hacer que el evento en directo esté abierto a toda la empresa o limitar el acceso a grupos específicos. Esto proporciona una experiencia de creación y visualización de un extremo a otro dentro de Teams.

Después del evento, el vídeo estará disponible a petición con características inteligentes que incluyen:

- Voz a texto y subtítulos.
- La búsqueda de transcripciones y los códigos de tiempo le permiten encontrar rápidamente momentos importantes en un vídeo.

## <a name="live-events-in-microsoft-365"></a>Eventos en directo en Microsoft 365

Puede crear un evento de vapor en directo en Teams o Yammer, dondequiera que resida su audiencia, equipo o comunidad. Los asistentes pueden ver el evento en vídeo de alta definición (HD) y enviar preguntas a través de una experiencia de preguntas&A moderada. La perfecta integración en Microsoft 365 significa que puede usar Teams para ofrecer eventos de alta producción y calidad de estudio.

## <a name="get-started"></a>Introducción

Asegúrese de que los usuarios que desea que puedan crear eventos en directo tengan los permisos concedidos necesarios para crear un evento en directo. De forma predeterminada, todos los usuarios de su organización pueden crear un evento en directo, pero un administrador de Teams puede restringir el acceso. Obtenga más información sobre la administración de eventos en directo.

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Directivas** de **eventos en directo** de Reuniones > la pestaña **Administrar directivas** > .
1. Si quiere:
    1. editar la directiva predeterminada existente, elija **Global (valor predeterminado para toda la organización).**
    1. cree una nueva directiva personalizada, elija **+Agregar**.
    1. editar una directiva personalizada, seleccione la directiva y, a continuación, elija **Editar**.

## <a name="monitor-your-event"></a>Supervisar el evento

Como productor, puede usar el cliente de Teams para ver la fuente de audiencia (visible en el lado derecho) y el número de asistentes que están viendo el evento.

## <a name="capabilities"></a>Capacidades

Las siguientes son funcionalidades de eventos de streaming en directo:

|Operación                                            |Límites                                                               |
|-----------------------------------------------------|---------------------------------------------------------------------|
|Crear eventos en directo en Teams (con codificador externo)  |Enterprise (E1, E3, E5), Educación (A3, A5)                          |
|Ver evento en directo                                     |Visores con permisos para ver el evento y una licencia válida de Teams (a menos que el evento sea público, no es necesaria una licencia para ver) |
|Resolución máxima                                   |720p                                                                 |
|Máximo de eventos en directo simultáneos (en directo o en directo) |15                                                                   |
|Visores simultáneos activos                            |10000                                                                |
|Duración máxima del evento en directo                         |4 horas                                                              |
|Compatibilidad con almacenamiento en caché de la red del partner                      |Urticaria, Kollective, Riverbed, Rampa, Microsoft                          |
|Otra compatibilidad con almacenamiento en caché de red                        |Puede funcionar, pero no es compatible                                        |
|Controles de ATTENDEE DVR                                |Pausa, velocidad de reproducción (2x ponerse al día, 1x en directo), buscar                |
|Subtítulos en tiempo real                                   |708 caption pass-through from encoder                                |
|Voz a texto y subtítulos automáticos                |Procesado después del evento                                            |
|Discusiones interactivas                              |Compatible con Yammer cuando se crea el evento desde Yammer           |
|Comentarios de Teams                                       |Disponible después de que finalice el evento                                       |
|Visualización a petición en un evento en directo (después del evento)        |Transición automática para directo a petición para la visualización e indexación inmediatas en Teams |
|Grabación descargable                               |Procesado y disponible después del evento en directo por los propietarios               |

Los eventos en directo en Teams son un servicio muy disponible y puede esperar un buen rendimiento a escala. En el escenario poco probable de que se requiera conmutación por error, los eventos en directo que usen codificación externa no tendrán redundancia y no se podrán recuperar.
