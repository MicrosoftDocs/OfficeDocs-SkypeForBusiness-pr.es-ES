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
description: Obtenga información sobre cómo usar NDI en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1ad11000de2ae0dac7563d785dfaea8c34978ed
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337019"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Usar tecnología NDI® en Microsoft Teams

 La tecnología newTek NDI® (Interfaz de dispositivos de red) es una solución moderna para conectar dispositivos multimedia (como una cámara de estudio y un mixer). En lugar de usar conexiones físicas, la tecnología de ® NDI habilita la conectividad a través de una intranet local, incluso en un equipo local.

La tecnología ® NDI se ha convertido en una solución estándar del sector para producir contenido en directo durante las transmisiones y ha adquirido un conocimiento y adopción significativos en el mundo de las difusiones profesionales.

Skype agregó anteriormente la funcionalidad de ® a Skype a finales de 2018. Microsoft Teams usa esta función para mejorar la experiencia de reunión.

La tecnología ® NDI está limitada a una red local y solo debe considerarse una parte del flujo de trabajo de producción, no una solución de difusión.

## <a name="turn-on-ndi-technology"></a>Activar la tecnología de ® NDI

La tecnología ® NDI requiere que se deben haber activado dos pasos para un usuario.

1. El administrador de inquilinos debe habilitar la propiedad 'AllowNDIStreaming' en CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Una vez que se haya rellenado este cambio, el usuario final debe activar la tecnología NDI® para su cliente específico desde Permisos  >  **de configuración.**

Cuando un usuario se une a una reunión, verá un mensaje que le notifica que la reunión se está difundiendo. Si los usuarios no quieren que se incluyan en la difusión, deben abandonar la reunión.

La imagen siguiente muestra el mensaje de banner que ve un usuario en una reunión de Teams.

![he NDI® de tecnología que se muestra en una reunión de Teams.](media/NDI-disclosure.png)

El banner tiene un vínculo a la directiva [de privacidad de Microsoft.](https://aka.ms/teamsprivacy)

## <a name="supported-locales-and-user-types"></a>Configuraciones regionales y tipos de usuario admitidos

La tecnología ® NDI es compatible con todas las configuraciones regionales. Los siguientes usuarios se incluyen en una transmisión de tecnología NDI® pero no todos los usuarios pueden acceder a la transmisión de tecnología NDI®:

- In-tenant – soporte completo, entregado según el ring/tenantId/userId (controlado por la directiva de reuniones)
- Federado: sin acceso a la transmisión (incluso cuando tienen tecnología NDI®)<sup>1</sup>
- Premium: sin acceso a la transmisión
- Anónimo: sin acceso a la transmisión
- Invitado: sin acceso a la transmisión  

<sup>1</sup> Los dispositivos tienen una configuración de ® NDI predeterminada. Si un participante de la reunión usa un dispositivo con tecnología NDI® desactivada, tendrá que activar la tecnología ® NDI.
