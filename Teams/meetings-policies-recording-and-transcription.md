---
title: Administrar las directivas de reunión para la grabación y la transcripción
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: Aprenda a administrar la configuración de la directiva de reunión en Teams para la grabación y la transcripción.
ms.openlocfilehash: da7a5d43231abcb00339f2ffc2c57c7e90ff2d2e
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646369"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Configuración de la directiva de reunión para grabar & transcripción

En este artículo se describen las opciones de configuración de la directiva de reunión específicas para la grabación y la transcripción, incluidas las siguientes:

- [Permitir transcripción](#allow-transcription)
- [Permitir la grabación en la nube](#allow-cloud-recording)
- [Almacenar grabaciones fuera de su país o región](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>Permitir transcripción

Esta es una combinación de directiva por organizador y por usuario. Esta configuración controla si se pueden usar las características de subtítulos y transcripción durante la reproducción de las grabaciones de la reunión. La persona que inició la grabación necesita esta configuración activada para que estas características funcionen con su grabación.

Al activar esta opción, se crea una copia de la transcripción que se almacena con la grabación de la reunión, lo que habilita **Búsqueda**, **CC** y **transcripciones** en la grabación de la reunión.

La transcripción para las reuniones grabadas actualmente solo se admite para los usuarios que establecen su idioma o hablan inglés en Teams reuniones.

## <a name="allow-cloud-recording"></a>Permitir la grabación en la nube

Esta configuración es una combinación de una directiva por organizador y por usuario, y controla si se pueden grabar las reuniones. La grabación la puede iniciar el organizador de la reunión u otro participante de la reunión si la configuración de directiva está activada para el participante y si es un usuario autenticado de la misma organización.

Las personas de fuera de su organización, como los usuarios federados y anónimos, no pueden iniciar la grabación. Los usuarios invitados no pueden iniciar o detener la grabación.

![Captura de pantalla que muestra las opciones de grabación](media/meeting-policies-recording.png)

Veamos el ejemplo siguiente.

|Usuario |Directiva de reuniones  |Permitir la grabación en la nube |
|---------|---------|---------|
|Daniela | Global   | Desactivado |
|Amanda | Location1MeetingPolicy | Activado|
|John (usuarios externos) | No aplicable | No aplicable|

- Las reuniones organizadas por Daniela no se pueden grabar.
- Amanda no puede grabar reuniones organizadas por Daniela.
- Las reuniones organizadas por Amanda se pueden grabar.
- Daniela no puede grabar reuniones organizadas por Amanda.
- John no puede grabar reuniones organizadas por Amanda.

Para más información sobre la grabación de reuniones en la nube, consulte [Grabación de reuniones en la nube de Teams](cloud-recording.md).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Almacenar grabaciones fuera de su país o región

Esta directiva controla si los registros de reunión se pueden almacenar de forma permanente en otro país o región. Si está habilitada, las grabaciones no se pueden migrar. Para obtener más información sobre las reuniones en la nube y dónde se almacenan las grabaciones, vea [Teams grabación de reuniones](cloud-recording.md) en la nube.

## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a usuarios en Teams](policy-assignment-overview.md)
- [Grabación de reuniones en la nube](cloud-recording.md)
