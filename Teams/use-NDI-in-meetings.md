---
title: Difundir contenido de la reunión
author: CarolynRowe
ms.author: crowe
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar NDI y SDI para difundir contenido de reunión en Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65e47ccfa1963e8e95e13a1c8b94e1e051ff709c
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2021
ms.locfileid: "59941885"
---
# <a name="broadcast-meeting-content"></a>Difundir contenido de la reunión 



Teams ofrece dos opciones para difundir contenido Teams reunión: Interfaz de dispositivo de red (NewTek NDI®) e Interfaz digital serial (SDI):

- NewTek NDI® es una solución moderna para conectar dispositivos multimedia (como una cámara de estudio y un mezclador). En lugar de usar conexiones físicas, la tecnología NDI® permite la conectividad a través de una intranet local, incluso en un equipo local.

  La tecnología ® NDI se ha convertido en una solución estándar del sector para producir contenido en directo para transmisiones y ha adquirido una conciencia y adopción significativas en el mundo de la difusión profesional.

- SDI se ha usado en producciones de difusión desde 1989 y es compatible con la mayoría de los dispositivos de hardware de estudio heredados. Los dispositivos de hardware de AJA Video Systems y Blackmagic Design proporcionan conectividad a dispositivos de difusión heredados que usan SDI.

> [!NOTE]
> La característica Salida de hardware de vídeo compatible con SDI se encuentra actualmente en versión preliminar.

La tecnología ® NDI y SDI es compatible con todas las configuraciones regionales.

El acceso al uso de NDI y SDI está determinado por la directiva de reunión para el usuario que intenta activar la característica. Para la solución más segura, no active el parámetro de streaming local como una configuración global.


## <a name="enable-broadcast-features"></a>Habilitar características de difusión

Para habilitar las características de difusión ® NDI y SDI para un usuario:

1. El administrador de inquilinos debe habilitar al usuario final para que el streaming local esté activado para su directiva de reunión. 

2. El usuario final debe activar la transmisión local para su cliente específico.


Para habilitar al usuario final, puede usar el Teams de administración o Teams PowerShell como se muestra a continuación.

En el Teams de administración, vaya a Directivas de **reunión > audio & vídeo** y seleccione Permitir streaming de **NDI.**

Para usar PowerShell, use el cmdlet Set-CsTeamsMeetingPolicy siguiente:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

Una vez que se haya rellenado este cambio, el usuario final debe activar el streaming local para su cliente específico Configuración  >  **permisos.** Para obtener más información, vea [Difundir audio y vídeo desde Teams](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3).





