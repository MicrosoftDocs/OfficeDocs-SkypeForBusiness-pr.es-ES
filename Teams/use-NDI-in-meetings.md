---
title: Difundir contenido de reunión
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar NDI y SDI para difundir el contenido de la reunión en Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc185a22c7ea4d849008989da29f50a8f98ebb9d
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706817"
---
# <a name="broadcast-meeting-content"></a>Difundir contenido de reunión 



Teams ofrece dos opciones para difundir el contenido de las reuniones de Teams: Network Device Interface (NewTek NDI®) y Serial Digital Interface (SDI):

- La nueva tecnología NDI® deTek es una solución moderna para conectar dispositivos multimedia (como una cámara de estudio y una mezcladora). En lugar de usar conexiones físicas, la tecnología NDI® permite la conectividad a través de una intranet local, incluso en un equipo local.

  La tecnología NDI® se ha convertido en una solución estándar de la industria para la producción de contenido en vivo para transmisiones y ha ganado una importante conciencia y adopción en el mundo de la difusión profesional.

- SDI se ha utilizado en las producciones de difusión desde 1989 y es compatible con la mayoría de los dispositivos de hardware de estudio heredados. Los dispositivos de hardware de AJA Video Systems y Blackmagic Design proporcionan conectividad a dispositivos de difusión heredados que usan SDI.

> [!NOTE]
> La característica Salida de hardware de vídeo que admite SDI se encuentra actualmente en versión preliminar.

La tecnología NDI® y SDI es compatible con todas las configuraciones regionales.

El acceso al uso de NDI y SDI viene determinada por la directiva de reunión del usuario que intenta activar la característica. Para obtener la solución más segura, no active el parámetro de streaming local como una configuración global.


## <a name="enable-broadcast-features"></a>Habilitar características de difusión

Para habilitar las características de difusión NDI® y SDI para un usuario:

1. El administrador de inquilinos debe habilitar al usuario final para que tenga activado el streaming local para su directiva de reunión. 

2. El usuario final debe activar el streaming local para su cliente específico.


Para habilitar al usuario final, puede usar el Centro de Administración de Teams o PowerShell de Teams como se indica a continuación.

En el Centro de administración de Teams, vaya a **Directivas de reunión > Audio & vídeo** y seleccione **Difusión local**.

Para usar PowerShell, use el cmdlet de Set-CsTeamsMeetingPolicy como se indica a continuación:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

Una vez completado este cambio, el usuario final debe activar el streaming local para su cliente específico desde **Permisos de configuración** > . Para obtener más información, consulte [Difundir audio y vídeo desde Teams](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3).





