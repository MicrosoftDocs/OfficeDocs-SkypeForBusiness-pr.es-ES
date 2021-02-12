---
title: Reuniones de Microsoft Teams en exploradores no compatibles
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo Teams admite audio y vídeo en exploradores no compatibles.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4aca1592a89e36e7a26a9a22b111968e4b44a302
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804530"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>Reuniones de Microsoft Teams en exploradores no compatibles

Algunos exploradores, como Internet Explorer 11, Safari y Firefox, admiten la aplicación web de Microsoft Teams, pero no admiten algunas de las características de llamadas y reuniones de Teams. Para evitar esta limitación, la aplicación web de Teams permite a los usuarios recibir audio a través de una conexión RTC y les permite ver el contenido presentado (uso compartido de pantalla) a una velocidad de visualización reducida.

> [!Note]
> Las aplicaciones y servicios de Microsoft 365 no admitirán Internet Explorer 11 a partir del 17 de agosto de 2021 (Microsoft Teams no admitirá Internet Explorer 11 antes, a partir del 30 de noviembre de 2020). [Más información](https://aka.ms/AA97tsw). Tenga en cuenta que Internet Explorer 11 seguirá siendo un navegador compatible. Internet Explorer 11 es un componente [](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) del sistema operativo Windows y sigue la directiva del ciclo de vida del producto en el que está instalado.

Cuando Teams detecta un explorador no compatible, muestra automáticamente un mensaje que explica el problema y las limitaciones de la sesión. El mensaje proporciona instrucciones adicionales para acceder al audio de la reunión, como aconsejar al usuario que deje un número de detrás de la llamada para que Teams pueda llamar al usuario o indicar al usuario que llame al número de conferencia incluido en la invitación a la reunión. El mensaje también anima al usuario a descargar y usar el cliente de escritorio [de Teams](https://teams.microsoft.com/downloads) para disfrutar de la experiencia completa de Teams.

Si RTC no está disponible, el usuario no verá las instrucciones para acceder a la reunión y no podrá unirse a ella.

## <a name="browser-limitations"></a>Limitaciones del explorador

Los usuarios de la aplicación web de Teams en exploradores no compatibles experimentarán las siguientes limitaciones:

- El audio solo está disponible a través de una conexión RTC. Los usuarios no pueden usar el micrófono.
- Los usuarios no pueden compartir su cámara ni ver vídeos de otros participantes, pero pueden ver contenido presentado mediante pantalla compartida basada en imágenes.
- Los usuarios no pueden compartir su pantalla, aunque pueden ver una pantalla que otro participante de la reunión comparte.
- Los usuarios no pueden tomar el control durante una sesión de pantalla compartida.
- Los usuarios no recibirán notificaciones de llamadas entrantes.
- Si se interrumpe la llamada, la reunión no volverá a conectarse automáticamente.
- Los usuarios no pueden iniciar reuniones.

Para obtener más información sobre la compatibilidad de exploradores en Teams, vea [Límites y especificaciones para Teams.](/microsoftteams/limits-specifications-teams#browsers)

## <a name="related-topics"></a>Temas relacionados

- [Unirse a una reunión de Teams en un explorador no compatible](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
