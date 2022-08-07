---
title: Reuniones de Microsoft Teams en exploradores no compatibles
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: nakulm
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo Teams admite audio y vídeo en exploradores no compatibles.
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 71fb02fae88f2f61d2d6435e126e20093a5a3baf
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267831"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>Reuniones de Microsoft Teams en exploradores no compatibles

Algunos exploradores, como Internet Explorer 11, Safari y Firefox, admiten la aplicación web de Microsoft Teams, pero no algunas de las características de llamadas y reuniones de Teams. Para evitar esta limitación, la aplicación web de Teams permite a los usuarios recibir audio a través de una conexión RTC y les permite ver el contenido presentado (uso compartido de la pantalla) a una velocidad de visualización reducida.

> [!Note]
> Las aplicaciones y servicios de Microsoft 365 no serán compatibles con Internet Explorer 11 a partir del 17 de agosto de 2021 (Microsoft Teams no admitirá Internet Explorer 11 anteriormente, a partir del 30 de noviembre de 2020). [Más información](https://aka.ms/AA97tsw). Tenga en cuenta que Internet Explorer 11 seguirá siendo un navegador compatible. Internet Explorer 11 es un componente del sistema operativo Windows y [sigue la directiva de ciclo de vida](/lifecycle/faq/internet-explorer-microsoft-edge) del producto en el que está instalado.

Cuando Teams detecta un explorador no compatible, muestra automáticamente un mensaje en el que se explica el problema y las limitaciones de sesión. El mensaje proporciona instrucciones adicionales para acceder al audio de la reunión, como aconsejar al usuario que deje un número de devolución de llamada para que Teams pueda llamar al usuario o indicar al usuario que llame al número de conferencia incluido en la invitación a la reunión. El mensaje también anima al usuario a descargar y usar el [cliente de escritorio de Teams](https://teams.microsoft.com/downloads) para disfrutar de toda la experiencia de Teams.

Si RTC no está disponible, el usuario no verá las instrucciones para acceder a la reunión y no podrá unirse a ella.

## <a name="browser-limitations"></a>Limitaciones del explorador

Los usuarios que usen la aplicación web de Teams en exploradores no compatibles experimentarán las siguientes limitaciones:

- El audio solo está disponible a través de una conexión RTC. Los usuarios no pueden usar su micrófono.
- Los usuarios no pueden compartir su cámara ni ver los vídeos de otros participantes, pero pueden ver el contenido presentado mediante la pantalla compartida basada en imágenes.
- Los usuarios no pueden compartir su pantalla, aunque pueden ver una pantalla que comparte otro participante de la reunión.
- Los usuarios no pueden tomar el control durante una sesión de uso compartido de la pantalla.
- Los usuarios no recibirán notificaciones de llamadas entrantes.
- Si se interrumpe la llamada, la reunión no volverá a conectarse automáticamente.
- Los usuarios no pueden iniciar reuniones.

Para obtener más información sobre la compatibilidad con exploradores en Teams, consulte [Límites y especificaciones para Teams](./limits-specifications-teams.md#browsers).

## <a name="related-topics"></a>Temas relacionados

- [Unirse a una reunión de Teams en un explorador no compatible](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)