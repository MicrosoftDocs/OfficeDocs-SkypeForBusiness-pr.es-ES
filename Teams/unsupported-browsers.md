---
title: Reuniones de Microsoft Teams en exploradores no admitidos
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 5f2fc7ee97a5172a849c14d9ede6d93ffc08d302
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837260"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>Reuniones de Microsoft Teams en exploradores no admitidos

Algunos exploradores, como Internet Explorer 11, Safari y Firefox, admiten la aplicación Web de Microsoft Teams, pero no admiten algunas de las características de llamadas y reuniones de Teams. Para evitar esta limitación, Team Web App permite a los usuarios recibir audio a través de una conexión RTC y les permite ver el contenido presentado (compartir pantalla) a una velocidad de visualización reducida.

Cuando Teams detecta un explorador no compatible, muestra automáticamente un mensaje que explica el problema y las limitaciones de la sesión. El mensaje proporciona más instrucciones para obtener acceso al audio de la reunión, como, por ejemplo, aconsejar al usuario que deje un número de devolución de llamada para que los equipos puedan llamar al usuario, o bien instruir al usuario para que llame al número de conferencia incluido en la invitación a la reunión. El mensaje también anima al usuario a descargar y usar el cliente de [escritorio de Teams](https://teams.microsoft.com/downloads) para la experiencia de todos los equipos.

Si la RTC no está disponible, el usuario no verá las instrucciones para acceder a la reunión y no podrá unirse a la reunión.

## <a name="browser-limitations"></a>Limitaciones del explorador

Los usuarios que usen la aplicación Teams Web en exploradores no admitidos experimentarán las siguientes limitaciones:

- El audio solo está disponible a través de una conexión RTC. Los usuarios no pueden usar el micrófono.
- Los usuarios no pueden compartir sus cámaras ni ver los vídeos de otros participantes, pero pueden ver el contenido presentado mediante la pantalla compartida basada en imágenes.
- Los usuarios no pueden compartir su pantalla, aunque pueden ver una pantalla compartida por otro participante de la reunión.
- Los usuarios no pueden tomar el control durante una sesión compartida de pantalla.
- Los usuarios no recibirán notificaciones de llamadas entrantes.
- Si la llamada se interrumpe, la reunión no se volverá a conectar automáticamente.
- Los usuarios no pueden iniciar reuniones.

## <a name="related-topics"></a>Temas relacionados

- [Unirse a una reunión de Teams en un explorador no admitido](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
- [Especificaciones y límites de Teams](/microsoftteams/limits-specifications-teams#browsers)