---
title: Usar NDI en Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Aprenda a usar NDI en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a1b756cfdb56de533d4dd170f301dc38e4b3b529
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308173"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Usar la tecnología de NDI® en Microsoft Teams

 La tecnología NewTek NDI® (interfaz de dispositivo de red) es una solución moderna para conectar dispositivos de medios (como una cámara de estudio y un mezclador). En lugar de usar conexiones físicas, la tecnología de® de NDI permite la conectividad en una Intranet local, incluso en un equipo local.

NDI® tecnología se ha convertido en una solución estándar de la industria para producir contenido en vivo para transmisiones por secuencias y ha obtenido un importante conocimiento y adopción en el mundo de la difusión profesional.

Skype añadió previamente la funcionalidad de® de salida de NDI a Skype a finales del 2018. Microsoft Teams usa esta funcionalidad para mejorar la experiencia de la reunión.

NDI® tecnología está limitada a una red local y solo se debe considerar parte del flujo de trabajo de producción, no de una solución de difusión.

## <a name="turn-on-ndi-technology"></a>Activar NDI® tecnología

NDI® tecnología requiere que se activen dos pasos para un usuario.

1. El administrador de inquilinos debe habilitar la propiedad ' AllowNDIStreaming ' en CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Después de completar este cambio, el usuario final debe activar NDI tecnología® para su cliente específico a partir **Settings**de  >  **los permisos**de configuración.

Cuando un usuario se une a una reunión, verá un mensaje en el que se le notifica que la reunión se está transmitiendo. Si los usuarios no desean que se incluyan en la difusión, tendrán que quitarlos de la reunión.

La imagen siguiente muestra el mensaje emergente que un usuario ve en una reunión de Teams.

![Una imagen del banner de tecnología de NDI® que se muestra en una reunión de Teams.](media/NDI-disclosure.png)

La pancarta tiene un vínculo a la [política de privacidad de Microsoft](https://aka.ms/teamsprivacy).

## <a name="supported-locales-and-user-types"></a>Configuraciones regionales y tipos de usuario admitidos

NDI® tecnología es compatible con todas las configuraciones regionales. Los siguientes usuarios están incluidos en un flujo tecnológico de NDI®, pero no todos los usuarios pueden acceder a la NDI tecnología de®:

- En el inquilino: soporte completo, entregado en función de ring/tenantId/userId (controlado por la Directiva de reuniones)
- Federado: sin acceso a secuencias (incluso cuando tiene activada la tecnología® NDI)<sup>1</sup>
- Freemium: sin acceso a la transmisión por secuencias
- Anónimo: sin acceso a secuencias
- Invitado: sin acceso a secuencias  

<sup>1</sup> los dispositivos tienen una configuración de tecnología de NDI® que está activada de forma predeterminada. Si un participante de la reunión usa un dispositivo con NDI tecnología®, tendrá que activar NDI tecnología de®.
