---
title: Configurar reuniones de Teams con protección para datos confidenciales
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
description: Obtenga información sobre cómo configurar reuniones de Teams para proteger la información confidencial mediante plantillas y etiquetas de confidencialidad.
ms.openlocfilehash: 3aae927f29464f3e5d8a9e695c170ded06d3dd1f
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800091"
---
# <a name="configure-teams-meetings-with-protection-for-sensitive-data"></a>Configurar reuniones de Teams con protección para datos confidenciales

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Para el nivel *de protección confidencial* , restringiremos quién puede omitir la sala de espera, quién puede presentar y quién puede registrar. También puede restringir acciones adicionales si su organización lo requiere.

En la tabla siguiente se describen las acciones que restringiremos para las reuniones confidenciales y dónde se configurarán esas opciones.

|Característica|Setting|Ubicación|Forzada|
|:------|:------|:-------|:-------|
|Permitir cámara para los asistentes|**On**|Plantilla|No|
|Permitir micrófono para los asistentes|**On**|Plantilla|No|
|Aplicar una marca de agua a la fuente de vídeo de todos|**Desactivado**|Plantilla|No|
|Aplicar una marca de agua al contenido compartido|**Desactivado**|Plantilla|No|
|Cifrado de un extremo a otro|**Desactivado**|Plantilla|No|
|Administrar lo que ven los asistentes|**On**|Plantilla|No|
|Chat de reunión|**On**|Plantilla|No|
|Personas marcación puede omitir la sala de espera|**Desactivado**|Plantilla|Sí|
|Impedir copiar el contenido del chat en el Portapapeles|**Desactivado**|Etiqueta|No|
|Grabar automáticamente|**Desactivado**|Plantilla|No|
|Quién puede omitir la sala de espera|**Solo las personas invitadas**|Etiqueta|Sí|
|Quién puede presentar|**Usuarios en mi organización e invitados**|Etiqueta|Sí|
|Quién puede grabar|**Organizador y co-organizador**|Etiqueta|Sí|

La configuración que aparece como obligatoria se aplica mediante la etiqueta de confidencialidad o la plantilla de reunión. El organizador de la reunión puede cambiar las opciones que no se aplican.

> [!Note]
> La configuración de reuniones en etiquetas de confidencialidad y plantillas de reunión personalizadas requieren Teams Premium.

## <a name="presentation-options-for-sensitive-meetings"></a>Opciones de presentación para reuniones confidenciales

Para el nivel *de protección confidencial* , estamos imponiendo una configuración específica para quién puede presentar, así como cómo se comparte el contenido.

Al activar **Administrar lo que los asistentes pueden ver**, nos aseguramos de que los organizadores de la reunión puedan controlar el contenido compartido antes de que aparezca en la pantalla para los participantes. En este ejemplo, usamos una plantilla para activarla de forma predeterminada, pero también puede exigirla en la plantilla si lo necesita.

Al establecer **Quién puede presentar** **en Personas de mi organización e invitados** en la etiqueta de confidencialidad, eliminamos la posibilidad de que participantes anónimos presenten en la reunión. Puede restringir esta opción a **Solo los organizadores y co-organizadores** si es necesario. (Lo haremos para el nivel de protección *altamente sensible* ).

También restringiremos la grabación a los organizadores y co-organizadores mediante la etiqueta de confidencialidad.

## <a name="lobby-options-for-sensitive-meetings"></a>Opciones de sala de espera para reuniones confidenciales

Usaremos la etiqueta de confidencialidad para impedir que nadie más que los asistentes invitados (personas invitadas directamente por el organizador o a quienes se reenvió una invitación) pasen por alto la sala de espera. Esto proporciona un nivel adicional de protección al permitir que el organizador veta a cualquier persona que no haya enviado directamente una invitación antes de admitirla a la reunión. Puede restringir aún más esta configuración seleccionando **Solo los organizadores y los co-organizadores**. (Lo haremos para el nivel de protección *altamente sensible* ).


## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Para el nivel de protección confidencial, usaremos una etiqueta de confidencialidad que puede usar directamente en una reunión o como parte de una plantilla de reunión. Según la configuración que elija, esta etiqueta también se puede usar para clasificar equipos y archivos individuales.

Si ya tiene etiquetas de confidencialidad implementadas en su organización, tenga en cuenta cómo se ajusta esta etiqueta a la estrategia general de etiquetas. Puede cambiar el nombre o la configuración si es necesario para satisfacer las necesidades de su organización. Si ya tiene una etiqueta que usa para información confidencial, puede editarla y agregar reuniones de Teams.

Para crear una etiqueta de confidencialidad
1. Abra el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com).
1. En **Soluciones**, haga clic en **Protección de información**.
1. Haga clic en **Crear una etiqueta**.
1. Asigne un nombre a la etiqueta. Le sugerimos **Confidencial**, pero puede elegir un nombre diferente si ya está en uso.
1. Agregue un nombre para mostrar y una descripción y, a continuación, haga clic en **Siguiente**.
1. En la página **Definir el ámbito de esta etiqueta** , seleccione **Elementos** e **Incluir reuniones**. (Tenga en cuenta que puede seleccionar otras opciones si desea usar esta etiqueta para otros fines).
1. Seleccione **Siguiente**.
1. Continúe seleccionando las opciones que desea usar con esta etiqueta y, a continuación, en la página **Configuración para reuniones y chats de Teams** , elija los siguientes valores:
    1. Seleccione **Controlar quién puede omitir la sala de espera** y elija **Solo las personas invitadas** en la lista desplegable.
    1. Seleccione **Controlar quién puede presentar** y elija **Personas de mi organización e invitados en** la lista desplegable.
    1. Seleccione **Quién puede grabar** y elija **Organizadores y co-organizadores** en la lista desplegable.
    1. Configure otras opciones de configuración que necesite para su organización.
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-sensitive-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-sensitive-large.png":::-->
1. Seleccione **Siguiente**.
1. Complete el asistente con cualquier configuración adicional que desee usar y, a continuación, seleccione **Crear etiqueta** y, a continuación, seleccione **Listo**.

Una vez que haya creado la etiqueta, deberá publicarla para los usuarios que la usarán. Para la protección confidencial, haremos que la etiqueta esté disponible para todos los usuarios. La etiqueta se publica en la portal de cumplimiento Microsoft Purview, en la pestaña **Directivas de etiqueta** de la página **Protección de información**. Si tiene una directiva existente que se aplique a todos los usuarios, agregue esta etiqueta a esa directiva. Si necesita crear una nueva directiva, vea [Publicar etiquetas de confidencialidad creando una directiva de etiqueta](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

Para obtener más información sobre el uso de etiquetas de confidencialidad con reuniones, vea [Usar etiquetas de confidencialidad para proteger elementos de calendario, reuniones de Teams y chat](/microsoft-365/compliance/sensitivity-labels-meetings).

## <a name="meeting-templates"></a>Plantillas de reunión

Una ventaja de usar plantillas es que puede crear varias plantillas con la misma etiqueta de confidencialidad que bloquean diferentes configuraciones. Por ejemplo, si algunas de sus reuniones confidenciales son presentaciones en las que hay una interacción mínima de los asistentes, puede crear una plantilla que desactive el vídeo de los asistentes e incluso el chat, y otra plantilla que deje esas opciones al organizador de la reunión. Ambas plantillas usarían la etiqueta *Confidencial* .

En el nivel *de protección confidencial* , usaremos la plantilla para evitar que los usuarios que llaman por teléfono omitan la sala de espera. Si hay ciertos tipos de reuniones en las que quiere permitir que los autores de llamadas por teléfono omitan la sala de espera, considere la posibilidad de usar una plantilla independiente con la misma etiqueta para esas reuniones.

Para crear una plantilla de reunión personalizada

1. En el Centro de administración de Teams, expanda **Reuniones** y seleccione **Plantillas de reunión**.
1. Seleccione **Agregar.**
1. Escriba un nombre y una descripción para la plantilla.
1. En la sección **Aplicar etiqueta de confidencialidad** , elija la etiqueta que creó anteriormente.
1. Selecciona **Aplicar etiqueta de confidencialidad** y, a continuación, **bloquear**.
1. Asegúrese de que **Personas llamada en el teléfono puede omitir la sala de espera** está establecida en **Desactivado**, selecciónela y seleccione **Bloquear**.
1. Cambia las opciones de configuración adicionales si lo deseas.
1. Para evitar que el organizador de la reunión cambie una configuración, seleccione la configuración y, a continuación, seleccione **Bloquear**.
1. Para evitar que el organizador de la reunión vea una configuración, seleccione la configuración y, a continuación, seleccione **Ocultar**.
1. Seleccione **Guardar**.

## <a name="related-topics"></a>Temas relacionados

[Configurar reuniones de Teams con tres niveles de protección](configure-meetings-three-tiers-protection.md)

[Información general sobre las plantillas de reunión personalizadas en Microsoft Teams](custom-meeting-templates-overview.md)

[Usar plantillas de reunión de Teams, etiquetas de confidencialidad y directivas de administración juntas para reuniones confidenciales](meeting-templates-sensitivity-labels-policies.md)
