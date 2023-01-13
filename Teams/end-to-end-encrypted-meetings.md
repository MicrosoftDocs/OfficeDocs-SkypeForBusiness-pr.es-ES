---
title: Requerir cifrado de un extremo a otro para reuniones confidenciales de Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Obtenga información sobre cómo habilitar el cifrado de un extremo a otro para las reuniones de Teams.
ms.openlocfilehash: 091da268e8042707dd7e27094fde33d957a52d79
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800139"
---
# <a name="require-end-to-end-encryption-for-sensitive-teams-meetings"></a>Requerir cifrado de un extremo a otro para reuniones confidenciales de Teams

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

El cifrado de un extremo a otro es el cifrado de información en su origen y descifrado en su destino previsto sin la capacidad de los nodos intermedios para descifrar. Cuando las reuniones de Teams están cifradas de un extremo a otro, nadie excepto los participantes de la reunión pueden oír o ver la comunicación. Ninguna otra parte, incluido Microsoft, tiene acceso a la conversación descifrada.

Las reuniones cifradas de un extremo a otro se pueden realizar entre dos partes cuando: las partes usan la versión más reciente del cliente de escritorio de Teams para Windows o Mac, están en un dispositivo móvil con la actualización más reciente para iOS y Android, o están en una Salas de Teams en un dispositivo Windows con la actualización más reciente. No se admite el cifrado de un extremo a otro para las reuniones a las que se asiste a través del explorador.

> [!Note]
> El cifrado de reuniones de un extremo a otro requiere Teams Premium.

Si no habilita el cifrado de un extremo a otro, Teams aún protege las reuniones mediante cifrado en función de los estándares del sector. Los datos intercambiados durante las reuniones siempre son seguros mientras están en tránsito y en reposo. Para obtener más información, vea [Cifrado multimedia para Teams](teams-security-guide.md#media-encryption).

Durante una reunión cifrada de un extremo a otro, Teams protege las siguientes características:

- Audio

- Vídeo

- Pantalla compartida

[El cifrado en Microsoft 365](/microsoft-365/compliance/encryption) protege el chat, el uso compartido de archivos, la presencia y otros contenidos de la reunión. Las aplicaciones, avatares, reacciones, chat y Q&A no se cifran de un extremo a otro.

Las siguientes características no están disponibles durante una reunión cifrada de un extremo a otro:

- Subtítulos en directo y transcripción

- Grabación

- Modo conferencia, modo complementario, galería grande

- Salas para sesión de subgrupo

Si su organización usa la grabación de cumplimiento, el cifrado de un extremo a otro no está disponible. Para obtener más información sobre cómo Teams admite la grabación de cumplimiento, vea [Introducción a la grabación basada en directivas de Teams para llamadas y reuniones](teams-recording-policy.md).

## <a name="enable-end-to-end-encryption-for-meetings"></a>Habilitar el cifrado de un extremo a otro para las reuniones

De forma predeterminada, el cifrado de un extremo a otro para las reuniones no está habilitado. Puede habilitarla con una directiva de cifrado mejorada por el administrador de Teams.

Una vez habilitado el cifrado de un extremo a otro, los organizadores de la reunión tienen la opción de elegir el cifrado de un extremo a otro y, después, crear una reunión. También puede exigir el cifrado de un extremo a otro con una plantilla de reunión o una etiqueta de confidencialidad.

Para habilitar el cifrado de un extremo a otro para las reuniones

1. En el Centro de administración de Teams, seleccione **Directiva de cifrado mejorada**.

1. Seleccione la directiva que desea actualizar.

1. Establezca **el cifrado de reunión de un extremo a otro** en **No habilitado, pero los usuarios pueden invalidarlo**.

1. Seleccione **Guardar**.

## <a name="related-topics"></a>Temas relacionados

[Configurar reuniones de Teams con tres niveles de protección](configure-meetings-three-tiers-protection.md)

[Usar el cifrado de un extremo a otro para las llamadas de Microsoft Teams uno a uno](teams-end-to-end-encryption.md)
