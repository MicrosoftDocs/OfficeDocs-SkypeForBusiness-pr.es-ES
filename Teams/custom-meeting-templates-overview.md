---
title: Información general sobre plantillas de reunión personalizadas en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
appliesto:
- Microsoft Teams
description: Obtenga más información sobre las plantillas de reunión personalizadas en Microsoft Teams Premium.
ms.openlocfilehash: 0ed766141e09b9c26d8e8c6f5e8fdd12195ddb78
ms.sourcegitcommit: 4fdbd93aacb52a4fca68e31eb04d0495d4e27a10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/27/2022
ms.locfileid: "69672920"
---
# <a name="overview-of-custom-meeting-templates-in-microsoft-teams"></a>Información general sobre plantillas de reunión personalizadas en Microsoft Teams

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Microsoft Teams Premium incluye la capacidad de crear plantillas de reunión personalizadas. Las plantillas de reunión se pueden usar para controlar la configuración de reuniones que controla normalmente el organizador de la reunión. Con las plantillas, puede crear experiencias de reunión coherentes en su organización y ayudar a aplicar requisitos de cumplimiento y reglas empresariales.

Las plantillas de reunión se pueden usar para aplicar la configuración o establecer valores predeterminados. La configuración de cada plantilla se puede bloquear para que el organizador de la reunión no pueda cambiarla o se pueda desbloquear para que el organizador de la reunión la cambie si es necesario.

Las siguientes opciones de configuración de reunión se pueden controlar con una plantilla de reunión:

|Setting|Descripción|
|:------|:----------|
|Chat|Especifica si el chat de la reunión está disponible. También se puede usar para evitar el chat antes y después de la reunión.|
|Cifrado de un extremo a otro|Especifica si la reunión está cifrada.|
|Vestíbulo|Especifica quién puede omitir la sala de espera y unirse a la reunión directamente.|
|Administrar lo que ven los asistentes|Especifica si los organizadores de la reunión pueden obtener una vista previa y aprobar el contenido que se comparte en pantalla antes de que otros participantes puedan verlo.|
|Micrófono y cámara para los asistentes|Especifica si los asistentes pueden reactivar y usar su cámara.|
|Notificar cuando los autores de llamadas se unan y se vayan|Especifica si se reproduce un sonido cuando las personas que llaman por teléfono se unen o abandonan la reunión.|
|Q&A|Especifica si los asistentes pueden usar la característica Q&A para realizar preguntas durante la reunión.|
|Reacciones|Especifica si los asistentes pueden usar reacciones o levantar la mano en la reunión.|
|Grabación|Especifica quién puede grabar y si la reunión se graba automáticamente.|
|Etiqueta de confidencialidad|Especifica la etiqueta de confidencialidad que se usará para la reunión.|
|Filigranas|Especifica si las marcas de agua se usan para las fuentes de la cámara y el contenido que se comparte en la pantalla en la reunión.|

Algunos ejemplos de cuándo una plantilla puede ser útil son:

- Aplicar la grabación automática de reuniones para determinados tipos de reuniones.
- Restringir el chat y la cámara y el audio de los asistentes y usar la característica Q&A para las reuniones de estilo de presentación.
- Usar un valor predeterminado más estricto para quién puede omitir la sala de espera, pero permitir que el organizador de la reunión cambie la configuración si es necesario.

Para obtener información sobre cómo crear plantillas de reunión, vea [Crear una plantilla de reunión personalizada en Microsoft Teams](create-custom-meeting-template.md).

## <a name="templates-with-sensitivity-labels"></a>Plantillas con etiquetas de confidencialidad

Las plantillas tienen la opción de especificar una etiqueta de confidencialidad. Las etiquetas también se pueden aplicar directamente a las reuniones, independientemente de las plantillas. Las etiquetas de confidencialidad pueden controlar algunas de las mismas opciones de configuración que las plantillas:

- Cifrado de un extremo a otro
- Chat de reunión
- Grabar automáticamente
- Quién puede omitir la sala de espera
- Quién puede presentar
- Quién puede grabar
- Filigranas

Si alguna de estas opciones está configurada en la etiqueta, invalidará esta configuración en la plantilla.

## <a name="templates-included-with-teams"></a>Plantillas incluidas con Teams

Teams Premium incluye varias plantillas de reuniones predeterminadas que puede poner a disposición de los usuarios:

- Reunión grande
- Reunión protegida
- Ayuntamiento
- [Cita virtual](virtual-appointment-meeting-template.md)
- Webinar

Además, estas plantillas están disponibles en Teams para Educación:

- Clase
- Grupo Discusión
- Conferencia
- Conferencia de padres y profesores

Puede actualizar la configuración de estas plantillas si es necesario.

## <a name="related-topics"></a>Temas relacionados

[Configurar reuniones de Teams con tres niveles de protección](configure-meetings-three-tiers-protection.md)

[Usar plantillas de reunión de Teams, etiquetas de confidencialidad y directivas de administración juntas](meeting-templates-sensitivity-labels-policies.md)
