---
title: Configure la característica llamarme para sus usuarios
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Aprenda a configurar la característica Llamarme en Teams para que los usuarios no puedan unirse a la parte de audio por teléfono cuando usan su PC para el audio.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821100"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configure la característica llamarme para sus usuarios

En Microsoft Teams, la característica **Llamarme** ofrece a los usuarios una forma de unirse a la parte de audio de una reunión por teléfono. Esto es útil en escenarios en los que es posible que no sea posible usar un equipo para audio. Los usuarios obtienen la parte de audio de la reunión a través de su teléfono móvil o línea fijo y la parte de contenido de la reunión, como cuando otro participante comparte su pantalla o reproduce un vídeo a través de su &mdash; &mdash; equipo.

> [!IMPORTANT]
> 
> Durante los períodos de alto volumen de reuniones (que hemos estado experimentando con el brote del COVID-19), se recomienda que los usuarios se unan a las reuniones al hacer clic en el botón <strong>Unirse a la reunión de Teams</strong> en lugar de usar los números de conferencia RTC o <strong>Llamarme al</strong>. Esto contribuye a garantizar la calidad del audio cuando el alto volumen de reuniones provoca congestión en la red RTC. 

> [!IMPORTANT]
> Mientras dure el brote de COVID-19, se recomienda a los usuarios que se unan a las reuniones mediante el botón **Unirse a la reunión de Teams** en lugar de usar los números de conferencia RTC o la opción **Llamarme al**</strong>. Esto se debe principalmente a la congestión de las infraestructuras de telefonía de países afectados por COVID-19. Si evita las llamadas RTC, es probable que experimente mayor calidad de audio. 

## <a name="the-user-experience"></a>La experiencia del usuario

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Unirse a una reunión mediante el teléfono para el audio

Haga **clic en** Unirse para unirse a una reunión y, a continuación, haga clic en Audio **del** teléfono en la pantalla Elegir la configuración de audio **y vídeo.** Desde aquí, los usuarios pueden realizar la llamada de reunión y unirse a ellos o llamar manualmente a la reunión.

![Captura de pantalla de la opción de audio del teléfono](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Dejar que se llame a la reunión de Teams**

En la **pantalla Usar teléfono para audio,** el usuario escribe su número de teléfono y hace clic en **Llamarme.** La reunión llama al usuario y lo une a la reunión.

![Captura de pantalla de la opción Llamarme en la pantalla Usar teléfono para audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Marcar manualmente**

Otra forma de unirse es llamar directamente a la reunión. En la pantalla Usar teléfono  para **el audio,** haga clic en Marcar manualmente para obtener una lista de números de teléfono que se usarán para llamar a la reunión.

![Captura de pantalla de la opción Marcar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Obtener una llamada cuando algo va mal con el audio durante una reunión

Si un usuario experimenta problemas de audio al usar su equipo durante una reunión, el usuario puede cambiar fácilmente al uso de su teléfono para el audio. Teams detecta cuando se produce un problema con el audio o dispositivo y redirige al usuario **para** que use su teléfono mostrando una opción Devolver la llamada.

Este es un ejemplo del  mensaje y la opción Volver a llamar que se muestra cuando Teams no detecta un micrófono.

![Captura de pantalla de la opción Volver a llamarme](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

El usuario hace clic **en Volver a** llamar, lo que abre la pantalla Usar teléfono para el **audio.** Desde aquí, pueden introducir su número de teléfono, hacer que se llame a la reunión de Teams y unirse a ella, o bien llamar manualmente a la reunión.

## <a name="set-up-the-call-me-feature"></a>Configurar la característica Llamarme

Para habilitar la característica Llamarme para los usuarios de su organización, es necesario configurar lo siguiente:

- La audioconferencia está habilitada para los usuarios de su organización que programan reuniones (organizadores de reuniones). Para obtener más información, consulte [Configurar Audioconferencia](set-up-audio-conferencing-in-teams.md) para Teams y Administrar la configuración de [Audioconferencia para un usuario en Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- Los usuarios pueden llamar desde las reuniones. Para obtener más información, [consulte Administrar la configuración de Audioconferencia para un usuario en Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

Si un usuario no tiene habilitada la opción Llamarme desde las reuniones, la opción **Llamarme** no está disponible y el usuario no recibirá una llamada para unirse a la reunión. En su lugar, el usuario ve una lista de números de teléfono en la pantalla Usar teléfono para **audio** que puede usar para llamar manualmente a la reunión en su teléfono.
