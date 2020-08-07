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
ms.openlocfilehash: 86c0908b04b2eece835a747d9f57625878c15a99
ms.sourcegitcommit: 95989f1a93524a2025feeb50b8635da332961ea3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588294"
---
# <a name="use-ndi-in-microsoft-teams"></a>Usar NDI en Microsoft Teams

[!INCLUDE [template](includes/preview-feature.md)]

La interfaz de dispositivo de red (NDI) es una solución moderna para conectar dispositivos de medios (como una cámara de estudio y un mezclador). En lugar de usar conexiones físicas, NDI permite la conectividad en una Intranet local, incluido en un equipo local.

NewTek NDI® se ha convertido en una solución estándar de la industria para producir contenido en vivo para transmisiones por secuencias y ha obtenido un importante conocimiento y adopción en el mundo de la difusión profesional.

Skype agregó previamente la funcionalidad de NDI-out a Skype a finales del 2018. Microsoft Teams aprovecha esta funcionalidad para mejorar la experiencia de la reunión.

NDI está limitado a una red local y solo se debe considerar parte del flujo de trabajo de producción, no de una solución de difusión.

## <a name="turn-on-ndi"></a>Activar NDI

NDI requiere que se activen dos pasos para un usuario.

1. El administrador de inquilinos debe habilitar la propiedad ' AllowNDIStreaming ' en CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Después de completar este cambio, el usuario final debe activar NDI para su cliente específico a partir **Settings**de  >  **los permisos**de configuración.

Cuando un usuario se une a una reunión, verá un mensaje en el que se le notifica que la reunión se está transmitiendo. Si los usuarios no desean que se incluyan en la difusión, tendrán que quitarlos de la reunión.

La imagen siguiente muestra el mensaje emergente que un usuario ve en una reunión de Teams.

![Una imagen del banner NDI que se muestra en una reunión de Teams.](media/NDI-disclosure.png)

La pancarta tiene un vínculo a la [política de privacidad de Microsoft](https://aka.ms/teamsprivacy).

## <a name="supported-locales-and-user-types"></a>Configuraciones regionales y tipos de usuario admitidos

NDI es compatible con todas las configuraciones regionales. Los siguientes usuarios son compatibles con una reunión de NDI:

- En el inquilino: soporte completo, entregado en función de ring/tenantId/userId (controlado por la Directiva de reuniones)
- Federado: no (incluso cuando se NDI)<sup>1</sup>
- Freemium: no (valor predeterminado)
- Anonymous: no (valor predeterminado)
- Invitado: no (valor predeterminado)

<sup>1</sup> los dispositivos tienen una configuración NDI que está activada de forma predeterminada. Si un participante de la reunión usa un dispositivo con NDI desactivado, tendrá que activar NDI.
