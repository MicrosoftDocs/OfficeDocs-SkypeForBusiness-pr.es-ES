---
title: Configurar la característica llamarme para los usuarios
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo configurar la característica llamarme en Teams para que los usuarios puedan unirse a la parte de audio por teléfono en escenarios en los que es posible que no se pueda usar el equipo para el audio.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f1ffee416b1d5674e831fda4c5bb15a89c510f4
ms.sourcegitcommit: 1ddd29e3839e50387efb4ec7b9d2154991bb2642
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "35432150"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configurar la característica llamarme para los usuarios

En Microsoft Teams, **** la característica llamarme proporciona a los usuarios una manera de unirse a la parte de audio de una reunión por teléfono. Esto es útil en escenarios en los que es posible que no sea posible usar un equipo para el audio. Los usuarios obtienen la parte de audio de la reunión a través del teléfono móvil o la línea terrestre y la parte&mdash;de contenido de la reunión, cuando otro participante de la reunión&mdash;comparte su pantalla o reproduce un vídeo a través de su equipo.

## <a name="the-user-experience"></a>La experiencia del usuario

Haga clic en **unirse** para unirse a una reunión y, a continuación, haga clic en **audio del teléfono** en la pantalla **elegir la configuración de audio y vídeo** . Desde aquí, los usuarios pueden tener la llamada de la reunión y unirse a la reunión de forma manual.

![Captura de pantalla de la opción audio del teléfono](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Permitir que los equipos de la reunión llamen**

En la pantalla **usar teléfono para audio** , el usuario escribe su número de teléfono y luego hace clic en **llamarme**. La reunión llama al usuario y lo une a la reunión.

![Captura de pantalla de la opción llamarme en la pantalla usar teléfono para audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Marcación manual**

Otra forma de unirse es llamar directamente a la reunión. En la pantalla **usar teléfono para audio** , haga clic en **marcar de forma manual** para obtener una lista de números de teléfono que usar para llamar a la reunión.

![Captura de pantalla de la opción de marcado manual](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

## <a name="set-up-the-call-me-feature"></a>Configurar la característica llamarme

Para habilitar la característica llamar a los usuarios de su organización, debe configurar los siguientes elementos:

- La Conferencia de audio está habilitada para los usuarios de su organización que programan reuniones (organizadores de reuniones). Para obtener más información, vea [configurar las conferencias de audio para Teams](set-up-audio-conferencing-in-teams.md) y [administrar la configuración de audioconferencias para un usuario en Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- Los usuarios pueden llamar desde reuniones. Para obtener más información, vea [administrar la configuración de audioconferencias para un usuario en Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Si un usuario no tiene la opción de marcado de las reuniones habilitadas, la opción **llamar me** no está disponible y el usuario no recibirá una llamada para unirse a la reunión. En su lugar, el usuario verá una lista de números de teléfono en la pantalla **de uso de teléfono para audio** que pueden usar para llamar de forma manual a la reunión de su teléfono.

