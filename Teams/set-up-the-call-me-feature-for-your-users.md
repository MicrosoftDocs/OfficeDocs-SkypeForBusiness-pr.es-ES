---
title: Configure la característica llamarme para sus usuarios
author: CarolynRowe
ms.author: crowe
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo configurar la característica Llamarme en Teams para que los usuarios puedan unirse a la parte de audio por teléfono al usar su equipo para el audio no sea posible.
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a144e6a751f44ff520ee0317dbbcb390f30abbfd
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794538"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configure la característica llamarme para sus usuarios

En Microsoft Teams, la característica **Llamarme** ofrece a los usuarios una forma de unirse a la parte de audio de una reunión por teléfono. Esto es útil en escenarios en los que es posible que no sea posible usar un equipo con audio. Los usuarios obtienen la parte de audio de la reunión a través de su teléfono móvil o línea terrestre y la parte de contenido de la reunión&mdash;, como cuando otro participante comparte su pantalla o reproduce un vídeo&mdash;a través de su equipo.

> [!IMPORTANT]
> 
> Durante los períodos de alto volumen de reuniones (que hemos estado experimentando con el brote del COVID-19), se recomienda que los usuarios se unan a las reuniones al hacer clic en el botón <strong>Unirse a la reunión de Teams</strong> en lugar de usar los números de conferencia RTC o <strong>Llamarme al</strong>. Esto contribuye a garantizar la calidad del audio cuando el alto volumen de reuniones provoca congestión en la red RTC.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>La experiencia de usuario

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Unirse a una reunión con el teléfono para el audio

Haga clic en **Unirse** para unirse a una reunión, luego Audio **del teléfono** en la pantalla **Elegir las opciones de audio y vídeo** y haga clic en **Unirse ahora**. Desde aquí, los usuarios pueden realizar la llamada de reunión y unirse a ellos o llamar manualmente a la reunión.

![Captura de pantalla de la opción de audio Teléfono.](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Permitir la llamada a la reunión de Teams**

En la pantalla **Usar teléfono para audio** , el usuario escribe su número de teléfono y, a continuación, hace clic en **Llamarme**. La reunión llama al usuario y se une a ella.

![Captura de pantalla de la opción Llamarme en la pantalla Usar teléfono para audio.](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Marcar manualmente**

Otra forma de unirse es llamar directamente a la reunión. En la pantalla **Usar teléfono para audio** , haga clic **en Marcar de forma manual** para obtener una lista de los números de teléfono que se usarán para llamar a la reunión.

![Captura de pantalla de la opción Marcar manualmente.](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Recuperar una llamada cuando se produce un problema con el audio durante una reunión

Si un usuario experimenta problemas de audio al usar su equipo durante una reunión, el usuario puede cambiar fácilmente al uso de su teléfono para el audio. Teams detecta cuándo se produce un problema de audio o dispositivo y redirige al usuario para que use su teléfono mostrando una opción **Llamarme de vuelta** .

Este es un ejemplo del mensaje y la opción **Devolverme la llamada** que se muestra cuando Teams no detecta un micrófono.

![Captura de pantalla de la opción Volver a llamarme.](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

El usuario hace clic en **Llamarme**, lo que hace que aparezca la pantalla **Usar teléfono para audio** . Desde aquí, pueden introducir su número de teléfono y hacer que la llamada de reunión de Teams se una a la reunión o llamar manualmente a la reunión.

## <a name="set-up-the-call-me-feature"></a>Configurar la característica Llamarme

Para habilitar la característica Llamarme para los usuarios de su organización, debe configurar lo siguiente:

- Audioconferencia está habilitado para los usuarios de su organización que programan reuniones (organizadores de reuniones). Para obtener más información, consulte [Configurar Audioconferencia para Teams](set-up-audio-conferencing-in-teams.md) y [Administrar la configuración de Audioconferencia para un usuario en Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- El organizador de la reunión puede llamar desde las reuniones. Para obtener más información, consulte [Administrar la configuración de Audioconferencia para un usuario en Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Si el organizador de la reunión no tiene habilitada la opción Llamada de salida desde reuniones, la opción **Audio del teléfono** de la pantalla **Elegir las opciones de audio y vídeo** no está disponible para nadie y los demás usuarios no pueden recibir una llamada para unirse a ella. Para los usuarios con llamadas entrantes habilitadas, una vez que se hayan unido a la reunión, pueden unirse a otras personas marcando su número desde el icono **Mostrar participantes** .
