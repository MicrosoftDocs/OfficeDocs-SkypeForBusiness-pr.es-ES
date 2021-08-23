---
title: Use NDI en Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar NDI en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a9eed33ba105584379f207697c27e8d6bd6cde5
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359187"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Use la tecnología ® NDI en Microsoft Teams

 La tecnología newtek NDI® (interfaz de dispositivo de red) es una solución moderna para conectar dispositivos multimedia (como una cámara de estudio y un mezclador). En lugar de usar conexiones físicas, la tecnología NDI® permite la conectividad a través de una intranet local, incluso en un equipo local.

La tecnología ® NDI se ha convertido en una solución estándar del sector para producir contenido en directo para transmisiones y ha adquirido una conciencia y adopción significativas en el mundo de la difusión profesional.

Skype funcionalidad de ® de salida a Skype a finales de 2018. Microsoft Teams esta funcionalidad para mejorar la experiencia de la reunión.

La tecnología ® NDI está limitada a una red local y solo debe considerarse una parte del flujo de trabajo de producción, no una solución de difusión.

## <a name="turn-on-ndi-technology"></a>Activar la tecnología ® NDI

La tecnología ® NDI requiere dos pasos para estar activado para un usuario.

1. El administrador de inquilinos debe permitir que el usuario final active NDI para su directiva de reunión. Esto se puede hacer de forma individual en el portal de administración de Teams o a través de Teams PowerShell mediante la propiedad _AllowNDIStreaming_ en CsTeamsMeetingPolicy.

    ```PowerShell
    Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
    ```

2. Una vez que se haya rellenado este cambio, el usuario final debe activar la tecnología NDI® para su cliente específico desde **Configuración**  >  **permisos.**

Después de activarse para un usuario y su cliente particular, el usuario puede activar NDI a través del menú desbordamiento y seleccionar "Difundir a través de NDI".

Después de iniciar el NDI y tener un punto de conexión suscrito a una fuente de NDI, verán un mensaje que les notifica que la reunión se está difundiendo. Si los usuarios no quieren incluirse en la difusión, necesitarán abandonar la reunión.

La siguiente imagen muestra el mensaje de banner que un usuario ve en una Teams reunión.

![he NDI® banner de tecnología que se muestra en una Teams reunión.](media/NDI-disclosure.png)

El banner tiene un vínculo a la directiva [de privacidad de Microsoft.](https://aka.ms/teamsprivacy)

> [!NOTE]
> NDI® se activa solo por sesión. En la siguiente reunión, el usuario debe activarlo antes de usar NDI®.

## <a name="supported-locales-and-user-types"></a>Configuraciones regionales y tipos de usuario compatibles

La tecnología ® NDI es compatible con todas las configuraciones regionales.

El acceso al uso de NDI está determinado por la directiva de reunión para el usuario que intenta activar la característica. Para la solución más segura, no active la directiva NDI como una configuración global.
