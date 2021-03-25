---
title: Directivas de grabación de eventos en directo
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Obtenga información sobre las directivas de grabación de eventos en directo.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7a5f793230798c68f0a39e2d9a3500eab9791065
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119169"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Directivas de grabación de eventos en directo en Microsoft Teams

Tiene varias opciones para grabar un evento en directo de Microsoft Teams. Las opciones de grabación se establecen con directivas de grabación. En este artículo se describen las distintas opciones de configuración.

Las opciones de grabación se establecen con el comando de PowerShell [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)

## <a name="scheduling-and-option-behaviors"></a>Programación y comportamientos de opciones

Hay dos opciones de organizador al programar una grabación de eventos en directo:

- Grabación disponible para productores y presentadores

  - Archivo de grabación: Proporciona un archivo de grabación que los productores y los presentadores pueden descargar una vez que haya terminado el evento.

- Grabación disponible para los asistentes

  - DVR: Una grabadora de vídeo digital (DVR) permite a los asistentes rebobinar y pausar durante el evento

  - VOD: Un vídeo a petición (VOD) permite a los asistentes ver una vez que el evento ha terminado

## <a name="broadcast-recording-policy-setting"></a>Configuración de directiva de grabación de difusión

Como parte de la directiva de difusión, hay una configuración que puede activar o desactivar para activar o desactivar la grabación de un evento en directo.

|                                 | Grabación disponible para productores y presentadores | Grabación disponible para los asistentes |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Grabar siempre               | Deshabilitado y seleccionado                                | Deshabilitado y seleccionado         |
| Organizador puede grabar o no | Habilitado y no seleccionado de forma predeterminada                  | Habilitado y no seleccionado de forma predeterminada   |
| Nunca grabar               | Deshabilitado y no seleccionado                            | Deshabilitado y no seleccionado      |

Cuando la directiva se establece en **Registro siempre,** la página de directiva tiene las siguientes opciones seleccionadas:

![configuración de directiva de eventos en directo](../media/live-event-recording-policy.png "Captura de pantalla de la configuración de la directiva de eventos en directo en el centro de administración de Microsoft Teams")

## <a name="storage-and-persistence-behavior"></a>Comportamiento de almacenamiento y persistencia

| Opción                                       | Estado   | DVR                                                   | VOD                                                     | Grabación                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| Grabación disponible para productores y presentadores | Seleccionado     | DVR está disponible y el activo de Azure Media Services (AMS) se almacena durante 180 días | Los asistentes pueden acceder al evento y verlo                     |                              |
|                                                  | No seleccionado | DVR está disponible y el activo de AMS se almacena durante 180 días | Los asistentes no án acceso al evento una vez que se ha terminado |                              |
||Deshabilitado (no seleccionado)|DVR está disponible y el activo de AMS se elimina después del evento|Los asistentes no án acceso al evento una vez que se ha terminado||
| Grabación disponible para productores y presentadores | Seleccionado     |                                                           |                                                             | Se crea y almacena un MP4 |
|                                                  | No seleccionado |                                                           |                                                             | No se crea ningún archivo           |

### <a name="related-topics"></a>Temas relacionados

- [¿Qué son los eventos en directo de Teams?](what-are-teams-live-events.md)
- [Planear eventos en directo en Teams](plan-for-teams-live-events.md)
- [Establecer la configuración de eventos en directo de Microsoft Teams](configure-teams-live-events.md)
- [Grabación de reuniones en la nube de Teams](../cloud-recording.md)