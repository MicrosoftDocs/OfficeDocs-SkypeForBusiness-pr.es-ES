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
description: Obtenga información sobre cómo configurar la característica Llamarme en Teams para que los usuarios puedan unirse a la parte de audio por teléfono al usar su equipo para el audio podría no ser posible.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 04510a827e9343010c756b14590e9800354c71e9
ms.sourcegitcommit: f979c491af5210e6ceb1d1c00e000767f1a8311d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "51623138"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configure la característica llamarme para sus usuarios

En Microsoft Teams, la característica **Llamarme** ofrece a los usuarios una forma de unirse a la parte de audio de una reunión por teléfono. Esto es útil en escenarios en los que puede que no sea posible usar un equipo para audio. Los usuarios obtienen la parte de audio de la reunión a través de su teléfono móvil o línea terrestre y la parte de contenido de la reunión, como cuando otro participante de la reunión comparte su pantalla o reproduce un vídeo a través de &mdash; &mdash; su equipo.

> [!IMPORTANT]
> 
> Durante los períodos de alto volumen de reuniones (que hemos estado experimentando con el brote del COVID-19), se recomienda que los usuarios se unan a las reuniones al hacer clic en el botón <strong>Unirse a la reunión de Teams</strong> en lugar de usar los números de conferencia RTC o <strong>Llamarme al</strong>. Esto contribuye a garantizar la calidad del audio cuando el alto volumen de reuniones provoca congestión en la red RTC.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>La experiencia de usuario

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Unirse a una reunión usando el teléfono para el audio

Haga **clic en** Unirse para unirse a una reunión, Teléfono **audio** en la pantalla Elegir las opciones de vídeo y **audio** y haga clic **en Unirse ahora.** Desde aquí, los usuarios pueden hacer la llamada de reunión y unirse a ellas o llamar manualmente a la reunión.

![Captura de pantalla de la Teléfono de audio](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Permitir que la Teams llamada de reunión**

En la **pantalla Usar teléfono para audio,** el usuario escribe su número de teléfono y, a continuación, hace clic en **Llamarme.** La reunión llama al usuario y los une a la reunión.

![Captura de pantalla de la opción Llamarme en la pantalla Usar teléfono para audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Marcar manualmente**

Otra forma de unirse es llamar directamente a la reunión. En la pantalla Usar teléfono  **para audio,** haga clic en Marcar manualmente para obtener una lista de números de teléfono que se usarán para llamar a la reunión.

![Captura de pantalla de la opción Marcar manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Obtener una llamada cuando hay un problema con el audio durante una reunión

Si un usuario experimenta problemas de audio al usar su equipo durante una reunión, el usuario puede cambiar fácilmente al uso de su teléfono para el audio. Teams detecta cuando se produce un problema de audio o dispositivo y redirige al usuario para que use su teléfono mostrando una **opción Llamarme** de nuevo.

Este es un ejemplo del  mensaje y la opción Llamarme atrás que se muestra cuando Teams no detecta un micrófono.

![Captura de pantalla de la opción Llamarme atrás](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

El usuario hace clic **en Llamarme** de nuevo, que muestra la **pantalla Usar teléfono para audio.** Desde aquí, pueden escribir su número de teléfono y tener la llamada Teams reunión y unirse a la reunión o llamar manualmente a la reunión.

## <a name="set-up-the-call-me-feature"></a>Configurar la característica Llamarme

Para habilitar la característica Llamarme para los usuarios de su organización, debe configurarse lo siguiente:

- Las audioconferencias están habilitadas para los usuarios de su organización que programan reuniones (organizadores de reuniones). Para obtener más información, vea Configurar audioconferencias [para Teams](set-up-audio-conferencing-in-teams.md) y Administrar la configuración de [conferencias](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)de audio para un usuario en Teams .

- El organizador de la reunión puede llamar desde reuniones. Para obtener más información, vea [Administrar la configuración de audioconferencia](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)para un usuario en Teams .

Si el organizador de la reunión no tiene habilitada la opción de acceso telefónico de las reuniones, la opción de **audio de Teléfono** de la pantalla Elegir las opciones de vídeo y **audio** no está disponible para nadie y otros usuarios no pueden recibir una llamada para unirse a la reunión. Para los usuarios con acceso telefónico habilitado, una vez que se han unido a la reunión, pueden unirse a otros marcando su número desde el icono **Mostrar participantes.**
