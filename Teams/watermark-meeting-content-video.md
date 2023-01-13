---
title: Requerir una marca de agua para reuniones confidenciales de Teams
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
description: Obtenga información sobre cómo habilitar o requerir marcas de agua en el vídeo de los asistentes y el contenido compartido en reuniones confidenciales de Teams.
ms.openlocfilehash: 199ba2d84ca4187a7d8e3c4f9a4d471bb9251598
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800238"
---
# <a name="require-a-watermark-for-sensitive-teams-meetings"></a>Requerir una marca de agua para reuniones confidenciales de Teams

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Puede habilitar que una marca de agua se muestre en las reuniones de Teams tanto para el contenido compartido en pantalla como para el vídeo de los asistentes. La marca de agua muestra la dirección de correo electrónico del participante de la reunión. Los participantes de la reunión no pueden desactivar la marca de agua. 

Las marcas de agua son compatibles con equipos de escritorio de Teams, Teams Mobile, Salas de Microsoft Teams en Windows y Salas de Microsoft Teams en Surface Hub. (Las marcas de agua no son compatibles con Salas de Microsoft Teams en Android). Personas unirse a reuniones desde plataformas no compatibles, incluida [la interoperabilidad de vídeo en la nube (CVI),](cloud-video-interop.md) podrá ver contenido sin marcas de agua.

Los siguientes participantes tienen una experiencia de solo audio cuando se está usando una marca de agua:

- Participantes que usan el cliente web de Teams
- participantes de Infraestructura de escritorio virtual (VDI)
- Participantes anónimos
- Participantes de desbordamiento

> [!Note]
> La configuración de reunión en etiquetas de confidencialidad, plantillas de reunión personalizadas y marcas de agua requieren Teams Premium.

Las marcas de agua de reunión están habilitadas en el Centro de administración de Teams. Después, el organizador de la reunión puede agregarlas o exigirlas mediante una plantilla o una etiqueta de confidencialidad.

En la tabla siguiente se muestra dónde están configuradas las marcas de agua:

|Setting|directiva de Administración|Etiqueta de confidencialidad|Plantilla|Organizador de la reunión|
|:------|:----------:|:---------------:|:------:|:---------------:|
|Aplicar una marca de agua al contenido compartido|Sí|Sí|Sí|Sí|
|Aplicar una marca de agua a la fuente de vídeo de todos|Sí|Sí|Sí|Sí|

Cuando se usa una marca de agua en una reunión, se desactivan las siguientes características:

- Grabación de la reunión, incluida la grabación automática

- Galería grande

- Modo conjunto

- PowerPoint Live

- Whiteboard

- Contenido de la cámara

## <a name="watermarks-for-sensitive-and-highly-sensitive-meetings"></a>Marcas de agua para reuniones confidenciales y altamente confidenciales

Las marcas de agua pueden ser útiles para proteger la información confidencial compartida en reuniones. Esto es muy útil al compartir información con personas que normalmente no tienen acceso a la información. Por ejemplo, un miembro de la organización financiera podría usar marcas de agua al compartir estimaciones trimestrales con administradores de diferentes divisiones.

Puesto que las marcas de agua están diseñadas para reducir las posibilidades de que se exfiltre la información confidencial, es posible que no se agreguen a la seguridad usarlas en reuniones en las que todos los participantes tengan acceso directo al contenido compartido.

Para obtener información sobre el uso de marcas de agua con otras características de reuniones para ayudar a proteger la información confidencial de las reuniones, vea [Configurar reuniones de Teams con protección para datos altamente confidenciales](/microsoftteams/configure-meetings-highly-sensitive-protection).

## <a name="enable-watermarks"></a>Habilitar marcas de agua

Para que las marcas de agua estén disponibles en plantillas y etiquetas de confidencialidad, y para el organizador de la reunión, deben estar habilitadas en el Centro de administración de Teams.

Para habilitar la marca de agua para reuniones

1. En el Centro de administración de Teams, expanda Reuniones y seleccione **Directivas de reunión**.

1. Seleccione la directiva que desea actualizar.

1. Para habilitar la marca de agua en el vídeo de los asistentes, establezca **Vídeos de marca de agua** **en Activado**.

1. Para habilitar la marca de agua en el contenido compartido en pantalla en una reunión, establezca **Contenido compartido de la marca de agua** en **Activado**.

    ![Captura de pantalla de la directiva de administración de Teams para marcas de agua](media/watermark-admin-policy.png)

1. Para ver el aspecto que tendrá la marca de agua en dispositivos móviles y de escritorio, seleccione **Vista previa**.

1. Seleccione **Guardar**.

También puede habilitar o deshabilitar las marcas de agua mediante PowerShell. Use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) con los `-AllowWatermarkForCameraVideo` parámetros y `-AllowWatermarkForScreenSharing` .

Por ejemplo:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForCameraVideo $True 

Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForScreenSharing $True 
```

## <a name="related-topics"></a>Temas relacionados

[Configurar reuniones de Teams con tres niveles de protección](configure-meetings-three-tiers-protection.md)

[Usar plantillas de reunión de Teams, etiquetas de confidencialidad y directivas de administración juntas para reuniones confidenciales](meeting-templates-sensitivity-labels-policies.md)
