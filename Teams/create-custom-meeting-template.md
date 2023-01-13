---
title: Crear una plantilla de reunión personalizada en Microsoft Teams
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
- highpri
appliesto:
- Microsoft Teams
description: Obtenga información sobre cómo los administradores de Microsoft Teams pueden crear una plantilla de reunión personalizada para establecer o aplicar la configuración del organizador de la reunión para mejorar la seguridad y el cumplimiento de las reuniones.
ms.openlocfilehash: ec9e836474032d5bb9fde0aed6c81a231788d1bf
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800270"
---
# <a name="create-a-custom-meeting-template-in-microsoft-teams"></a>Crear una plantilla de reunión personalizada en Microsoft Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

Las plantillas de reunión personalizadas de Microsoft Teams (una característica Teams Premium) le permiten especificar valores para muchas de las opciones de configuración de reunión disponibles para los organizadores de la reunión. Las plantillas pueden configurar opciones que los organizadores de reuniones pueden cambiar o pueden bloquear la configuración para que los organizadores de la reunión no puedan cambiarlas. Para obtener más información sobre las plantillas de reunión personalizadas, vea [Información general sobre las plantillas de reunión personalizadas en Microsoft Teams](custom-meeting-templates-overview.md).

Puede crear hasta 50 plantillas personalizadas. Vea [Administrar plantillas de reunión en Microsoft Teams](manage-meeting-templates.md) para obtener información sobre cómo administrar las plantillas que están disponibles para los usuarios.

Para cada opción de la plantilla, puede definir lo siguiente:

- **Valor predeterminado** : es el valor que se aplica a una reunión cuando se usa la plantilla.
- **Visible** : determina si el organizador de la reunión puede ver esta configuración en las opciones de la reunión. 
- **Estado de bloqueo** : determina si el organizador de la reunión puede cambiar la configuración establecida por la plantilla. Si la configuración está bloqueada, el organizador de la reunión no puede cambiarla.

Para crear una plantilla de reunión personalizada

1. En el Centro de administración de Teams, expanda **Reuniones** y seleccione **Plantillas de reunión**.
1. Seleccione **Agregar.**
1. Escriba un nombre y una descripción para la plantilla.
1. Elija la configuración que desea usar para esta plantilla. (Consulte las secciones siguientes para obtener descripciones de cada configuración).
1. Para evitar que el organizador de la reunión cambie una configuración, seleccione la configuración y, a continuación, seleccione **Bloquear**.
1. Para evitar que el organizador de la reunión vea una configuración, seleccione la configuración y, a continuación, seleccione **Ocultar**.
1. Seleccione **Guardar**.

Una vez creada la plantilla, puede tardar hasta 24 horas en estar disponible para los usuarios.

#### <a name="security"></a>Seguridad

|Setting|Descripción|
|:------|:----------|
|Etiqueta de confidencialidad|Especifica la etiqueta de confidencialidad de la reunión que se usará para la reunión. Tenga en cuenta que la etiqueta de confidencialidad puede invalidar cierta configuración de la plantilla.|
|¿Quién puede evitar la sala de espera?|Especifica quién puede omitir la sala de espera y unirse a la reunión directamente.|
|Personas marcación puede omitir la sala de espera|Especifica si las personas que llaman por teléfono pueden omitir la sala de espera y unirse a la reunión directamente.|
|Notificar cuando los autores de llamadas se unan y se vayan|Especifique si quiere que se reproduzca un sonido cuando las personas que llaman por teléfono se unan o abandonen la reunión.|
|Habilitar el cifrado de un extremo a otro de la reunión|Especifique si quiere que la reunión use el cifrado de un extremo a otro. La grabación y la transcripción no funcionarán si está activada.|
|Aplicar una marca de agua al contenido compartido|Especifica si una marca de agua está superpuesto en el contenido que se comparte en pantalla en la reunión.|
|Aplicar una marca de agua a la fuente de vídeo de todos|Especifica si una marca de agua se superpone en las fuentes de vídeo de los asistentes en la reunión.|

#### <a name="audio-and-video"></a>Audio y vídeo

|Setting|Descripción|
|:------|:----------|
|Permitir micrófono para los asistentes|Cuando **está activado**, los asistentes pueden reactivar el audio.|
|Permitir cámara para los asistentes|Cuando **están activados**, los asistentes pueden activar sus cámaras.|

#### <a name="recording-and-transcription"></a>Grabación y transcripción

|Setting|Descripción|
|:------|:----------|
|Grabar reuniones automáticamente|Cuando **las** reuniones se graban automáticamente.|
|¿Quién puede grabar reuniones?|Especifica si solo los organizadores o los moderadores pueden grabar las reuniones.|

#### <a name="meeting-engagement"></a>Participación en la reunión

|Setting|Descripción|
|:------|:----------|
|Los asistentes pueden chatear|Especifica si el chat de la reunión está disponible. También se puede usar para evitar el chat antes y después de la reunión.|
|Los asistentes pueden usar reacciones|Especifica si los asistentes pueden usar reacciones en la reunión. Debe estar **Activado** para que la característica levantar la mano funcione.|
|Habilitar Q&A|Especifica si los asistentes pueden usar la característica Q&A para realizar preguntas durante la reunión.|
|Administrar lo que ven los asistentes|Cuando **están activados**, los organizadores de la reunión pueden ver y aprobar el contenido compartido en pantalla antes de que otros participantes puedan verlo.|

## <a name="related-topics"></a>Temas relacionados

[Información general sobre las plantillas de reunión personalizadas en Microsoft Teams](custom-meeting-templates-overview.md)

[Usar plantillas de reunión de Teams, etiquetas de confidencialidad y directivas de administración juntas](meeting-templates-sensitivity-labels-policies.md)

[Configurar reuniones de Teams con tres niveles de protección](configure-meetings-three-tiers-protection.md)
