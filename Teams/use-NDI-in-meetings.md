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
ms.openlocfilehash: eebbea6ce5d632d38e94465f05fd9f60a3300a4e060106e7ba2f6218433c5e8b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335820"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Use la tecnología ® NDI en Microsoft Teams

 La tecnología newtek NDI® (interfaz de dispositivo de red) es una solución moderna para conectar dispositivos multimedia (como una cámara de estudio y un mezclador). En lugar de usar conexiones físicas, la tecnología NDI® permite la conectividad a través de una intranet local, incluso en un equipo local.

La tecnología ® NDI se ha convertido en una solución estándar del sector para producir contenido en directo para transmisiones y ha adquirido una conciencia y adopción significativas en el mundo de la difusión profesional.

Skype funcionalidad de ® de salida a Skype a finales de 2018. Microsoft Teams esta funcionalidad para mejorar la experiencia de la reunión.

La tecnología ® NDI está limitada a una red local y solo debe considerarse una parte del flujo de trabajo de producción, no una solución de difusión.

## <a name="turn-on-ndi-technology"></a>Activar la tecnología ® NDI

La tecnología ® NDI requiere dos pasos para estar activado para un usuario.

1. El administrador de inquilinos debe habilitar la propiedad "AllowNDIStreaming" en CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Una vez que se haya rellenado este cambio, el usuario final debe activar la tecnología NDI® para su cliente específico desde **Configuración**  >  **permisos.**

Cuando un usuario se une a una reunión, verá un mensaje que le notifica que la reunión se está difundiendo. Si los usuarios no quieren incluirse en la difusión, necesitarán abandonar la reunión.

La siguiente imagen muestra el mensaje de banner que un usuario ve en una Teams reunión.

![he NDI® banner de tecnología que se muestra en una Teams reunión.](media/NDI-disclosure.png)

El banner tiene un vínculo a la directiva [de privacidad de Microsoft.](https://aka.ms/teamsprivacy)

> [!NOTE]
> NDI® se activa solo por sesión. En el siguiente inicio de sesión, el usuario debe activarlo antes de usar NDI®.

## <a name="supported-locales-and-user-types"></a>Configuraciones regionales y tipos de usuario compatibles

La tecnología ® NDI es compatible con todas las configuraciones regionales. Los siguientes usuarios se incluyen en una transmisión de tecnología NDI®, pero no todos los usuarios pueden acceder a la transmisión de tecnología ® NDI:

- In-tenant: soporte completo, entregado en función de ring/tenantId/userId (controlado por la directiva de reuniones)
- Federado: no hay acceso de transmisión (incluso cuando tienen NDI® tecnología en)<sup>1</sup>
- Premium: sin acceso de transmisión
- Anónimo: sin acceso de transmisión
- Invitado: sin acceso de transmisión  

<sup>1</sup> Los dispositivos tienen una configuración de tecnología ® NDI que está predeterminada. Si un participante de la reunión usa un dispositivo con la tecnología NDI® desactivada, tendrá que activar la tecnología ® NDI.
