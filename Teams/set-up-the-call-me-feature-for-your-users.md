---
title: Configure la característica llamarme para sus usuarios
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo configurar la característica llamarme en Teams para que los usuarios puedan unirse a la parte de audio por teléfono cuando use su equipo para el audio puede no ser posible.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d29a517b8df194fe19b9e16554f7c57964177c90
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138020"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configure la característica llamarme para sus usuarios

En Microsoft Teams, la característica **llamarme** proporciona a los usuarios una manera de unirse a la parte de audio de una reunión por teléfono. Esto es útil en escenarios en los que es posible que no sea posible usar un equipo para el audio. Los usuarios obtienen la parte de audio de la reunión a través del teléfono móvil o la línea terrestre y la parte de contenido de la reunión &mdash; , como cuando otro participante de la reunión comparte su pantalla o reproduce un vídeo &mdash; a través de su equipo.

> [!IMPORTANT]
> 
> Durante los períodos de gran volumen de reunión (que hemos estado experimentando con el brote COVID-19), recomendamos que los usuarios se unan a las reuniones haciendo clic en el botón unirse a la <strong>reunión de Teams</strong> en lugar de llamar usando los números de la Conferencia RTC o llamando <strong>al</strong>. Esto ayuda a garantizar la calidad de audio en las ocasiones en que el volumen de las reuniones altas provoca congestión en la red PSTN. 

> [!IMPORTANT]
> Mientras dure el brote de COVID-19, se recomienda a los usuarios que se unan a las reuniones mediante el botón **Unirse a la reunión de Teams** en lugar de usar los números de conferencia RTC o la opción **Llamarme al**</strong>. Esto se debe principalmente a la congestión de las infraestructuras de telefonía de países afectados por COVID-19. Si evita las llamadas RTC, es probable que experimente mayor calidad de audio. 

## <a name="the-user-experience"></a>La experiencia del usuario

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Unirse a una reunión con el teléfono para el audio

Haga clic en **unirse** para unirse a una reunión y, a continuación, haga clic en **audio del teléfono** en la pantalla **elegir la configuración de audio y vídeo** . Desde aquí, los usuarios pueden tener la llamada de la reunión y unirse a la reunión de forma manual.

![Captura de pantalla de la opción audio del teléfono](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Permitir que los equipos de la reunión llamen**

En la pantalla **usar teléfono para audio** , el usuario escribe su número de teléfono y luego hace clic en **llamarme**. La reunión llama al usuario y lo une a la reunión.

![Captura de pantalla de la opción llamarme en la pantalla usar teléfono para audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Marcación manual**

Otra forma de unirse es llamar directamente a la reunión. En la pantalla **usar teléfono para audio** , haga clic en **marcar de forma manual** para obtener una lista de números de teléfono que usar para llamar a la reunión.

![Captura de pantalla de la opción de marcado manual](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Recuperar una llamada cuando algo sale mal con el audio durante una reunión

Si un usuario experimenta problemas de audio al usar su equipo durante una reunión, el usuario puede cambiar fácilmente a usar el teléfono para el audio. Teams detecta cuando se produce un problema de audio o dispositivo y redirige al usuario para que use su teléfono con una opción para **volver a llamarme** .

Este es un ejemplo del mensaje y la opción **llamarme atrás** que se muestra cuando Teams no detecta un micrófono.

![Captura de pantalla de la opción llamarme atrás](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

El usuario hace clic en **llamarme de nuevo**, que muestra la pantalla **usar teléfono para audio** . Desde aquí puede escribir su número de teléfono y hacer que los equipos de la reunión se llamen y se unan a la reunión o marquen de forma manual en la reunión.

## <a name="set-up-the-call-me-feature"></a>Configurar la característica llamarme

Para habilitar la característica llamar a los usuarios de su organización, debe configurar los siguientes elementos:

- La Conferencia de audio está habilitada para los usuarios de su organización que programan reuniones (organizadores de reuniones). Para obtener más información, vea [configurar las conferencias de audio para Teams](set-up-audio-conferencing-in-teams.md) y [administrar la configuración de audioconferencias para un usuario en Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- Los usuarios pueden llamar desde reuniones. Para obtener más información, vea [administrar la configuración de audioconferencias para un usuario en Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Si un usuario no tiene la opción de marcado de las reuniones habilitadas, la opción **llamar me** no está disponible y el usuario no recibirá una llamada para unirse a la reunión. En su lugar, el usuario verá una lista de números de teléfono en la pantalla **de uso de teléfono para audio** que pueden usar para llamar de forma manual a la reunión de su teléfono.
