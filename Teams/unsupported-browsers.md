---
title: Microsoft Teams reuniones en exploradores no compatibles
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
description: Obtenga información sobre Teams audio y vídeo en exploradores no compatibles.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83617628fe04140c45b005e993d95eac34c6f8bd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121318"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>Microsoft Teams reuniones en exploradores no compatibles

Algunos exploradores, como Internet Explorer 11, Safari y Firefox, admiten la aplicación web Microsoft Teams pero no admiten algunas de las características de Teams llamadas y reuniones. Para evitar esta limitación, la aplicación web Teams permite a los usuarios recibir audio a través de una conexión RTC y les permite ver el contenido presentado (uso compartido de pantalla) a una velocidad de visualización reducida.

> [!Note]
> Microsoft 365 aplicaciones y servicios no admitirán Internet Explorer 11 a partir del 17 de agosto de 2021 (Microsoft Teams no admitirá Internet Explorer 11 anteriormente, a partir del 30 de noviembre de 2020). [Más información](https://aka.ms/AA97tsw). Tenga en cuenta que Internet Explorer 11 seguirá siendo un navegador compatible. Internet Explorer 11 es un componente del [](/lifecycle/faq/internet-explorer-microsoft-edge) Windows operativo y sigue la directiva de ciclo de vida del producto en el que está instalado.

Cuando Teams un explorador no compatible, muestra automáticamente un mensaje que explica el problema y las limitaciones de la sesión. El mensaje proporciona instrucciones adicionales para obtener acceso al audio de la reunión, como aconsejar al usuario que deje un número de llamada para que Teams pueda llamar al usuario, o indicar al usuario que llame al número de conferencia incluido en la invitación a la reunión. El mensaje también anima al usuario a descargar y usar el Teams de escritorio [para](https://teams.microsoft.com/downloads) disfrutar de la experiencia Teams usuario.

Si rtc no está disponible, el usuario no verá las instrucciones para acceder a la reunión y no podrá unirse a la reunión.

## <a name="browser-limitations"></a>Limitaciones del explorador

Las personas que usan la Teams web en exploradores no admitidos experimentarán las siguientes limitaciones:

- El audio solo está disponible a través de una conexión RTC. Los usuarios no pueden usar el micrófono.
- Los usuarios no pueden compartir su cámara ni ver vídeos de otros participantes, pero pueden ver el contenido presentado mediante el uso compartido de pantalla basado en imágenes.
- Los usuarios no pueden compartir su pantalla, aunque pueden ver una pantalla que comparte otro participante de la reunión.
- Los usuarios no pueden tomar el control durante una sesión de uso compartido de pantalla.
- Los usuarios no recibirán notificaciones de llamadas entrantes.
- Si la llamada se interrumpe, la reunión no se volverá a conectar automáticamente.
- Los usuarios no pueden iniciar reuniones.

Para obtener más información sobre el soporte del explorador en Teams, vea [Límites y especificaciones para Teams](./limits-specifications-teams.md#browsers).

## <a name="related-topics"></a>Temas relacionados

- [Unirse a Teams reunión en un explorador no compatible](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)