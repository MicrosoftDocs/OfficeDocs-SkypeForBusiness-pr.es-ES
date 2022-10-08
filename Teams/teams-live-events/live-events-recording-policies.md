---
title: Directivas de grabación de eventos en directo
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Obtenga información sobre las directivas de grabación de eventos en directo.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: abe4cb004ada98021e74823495e6208fc31c28fb
ms.sourcegitcommit: fcedb958bf555d870215ae84fb83752304944716
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2022
ms.locfileid: "68486560"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Directivas de grabación de eventos en directo en Microsoft Teams

Tiene varias opciones para grabar un evento en directo de Microsoft Teams. Las opciones de grabación se establecen mediante directivas de grabación. En este artículo se describen las distintas opciones de configuración.

Las opciones de grabación se establecen mediante el comando de PowerShell [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy).

## <a name="scheduling-and-option-behaviors"></a>Programación y comportamientos de opciones

Hay dos opciones de organizador mientras se programa una grabación de un evento en directo:

- Grabación disponible para productores y moderadores

  - Archivo de grabación: proporciona un archivo de grabación que los productores y moderadores pueden descargar después de que finalice el evento.

- Grabación disponible para los asistentes

  - DVR: una grabadora de vídeo digital (DVR) permite a los asistentes rebobinar y pausar durante el evento

  - VOD: un vídeo a petición (VOD) permite a los asistentes ver una vez finalizado el evento

## <a name="broadcast-recording-policy-setting"></a>Configuración de directiva de grabación de difusión

Como parte de la directiva de difusión, hay una configuración que puede activar o desactivar para activar o desactivar la grabación de un evento en directo.

| &nbsp;| Grabación disponible para productores y moderadores | Grabación disponible para los asistentes |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Grabar siempre               | Deshabilitado y seleccionado                                | Habilitado y seleccionado         |
| El organizador puede grabar o no | Habilitado y seleccionado de forma predeterminada                  | Habilitado y seleccionado de forma predeterminada   |
| No grabar nunca               | Deshabilitado y no seleccionado                            | Deshabilitado y no seleccionado      |

## <a name="storage-and-persistence-behavior"></a>Comportamiento de almacenamiento y persistencia

| Opción                                       | Estado   | Dvr                                                   | Vod                                                     | Grabación                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| Grabación disponible para los asistentes | Seleccionado     | DVR está disponible y el activo de Azure Media Services (AMS) se almacena durante 180 días | El asistente puede acceder al evento y verlo                     |                              |
|                                                  | No seleccionado | DVR está disponible y el activo de AMS se almacena durante 180 días | Los asistentes no obtendrán acceso al evento después de que se termine |                              |
||Deshabilitado (no seleccionado)|DVR está disponible y el activo de AMS se elimina después del evento|Los asistentes no obtendrán acceso al evento después de que se termine||
| Grabación disponible para productores y moderadores | Seleccionado     |                                                           |                                                             | Se crea un MP4 y se almacena durante 180 días |
|                                                  | No seleccionado |                                                           |                                                             | No se crea ningún archivo           |

### <a name="related-topics"></a>Temas relacionados

- [¿Qué son los eventos en directo de Teams?](what-are-teams-live-events.md)
- [Planear eventos en directo en Teams](plan-for-teams-live-events.md)
- [Establecer la configuración de eventos en directo de Microsoft Teams](configure-teams-live-events.md)
- [Grabación de reuniones en la nube de Teams](../cloud-recording.md)
