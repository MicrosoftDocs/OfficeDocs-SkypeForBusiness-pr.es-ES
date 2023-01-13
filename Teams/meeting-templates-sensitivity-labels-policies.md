---
title: Usar plantillas de reunión de Teams, etiquetas de confidencialidad y directivas de administración juntas para reuniones confidenciales
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
description: Obtenga información sobre cómo usar las directivas de administración de Teams junto con etiquetas de confidencialidad y plantillas de reunión para mejorar la seguridad y el cumplimiento de las reuniones confidenciales.
ms.openlocfilehash: f0363a7e27df39da7270d9f492048b639f8a3d30
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800085"
---
# <a name="use-teams-meeting-templates-sensitivity-labels-and-admin-policies-together-for-sensitive-meetings"></a>Usar plantillas de reunión de Teams, etiquetas de confidencialidad y directivas de administración juntas para reuniones confidenciales

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

En las reuniones de Teams, los organizadores de la reunión pueden configurar [una variedad de opciones](https://support.microsoft.com/office/53261366-dbd5-45f9-aae9-a70e6354f88e) que determinan qué características están disponibles en la reunión. Como administrador, puede deshabilitar o exigir valores específicos para esta configuración mediante una combinación de directivas de administración, etiquetas de confidencialidad y plantillas de reunión.

[Las plantillas de reunión](custom-meeting-templates-overview.md) se crean y administran en el Centro de administración de Teams. Las etiquetas de confidencialidad se crean y se administran en el portal de cumplimiento Microsoft Purview. 

> [!Note]
> La configuración de reuniones en etiquetas de confidencialidad y plantillas de reunión personalizadas requieren Teams Premium.

Al usar directivas de administración, plantillas y etiquetas conjuntamente, puede hacer posible una variedad de escenarios de reunión para ayudar a satisfacer las necesidades empresariales y de cumplimiento de los diferentes departamentos de su organización.

## <a name="policies-labels-templates-and-meetings-settings"></a>Directivas, etiquetas, plantillas y configuración de reuniones

En la tabla siguiente se muestra una lista de las características de Teams que pueden resultar útiles para administrar reuniones con diferentes necesidades de cumplimiento en su organización y en las que se pueden configurar.

|Característica|Directiva de administración de Teams|Etiqueta de confidencialidad|Plantilla de reunión|Organizador de la reunión|
|:----|:----|:----|:----|:----|
|Permitir cámara para los asistentes|La configuración de directiva de administración de vídeo IP y modo para vídeo IP determina qué participantes pueden usar sus cámaras.|Sin configuración|Puede evitar o permitir la cámara para los asistentes. Se puede exigir la configuración o se puede permitir que el organizador de la reunión cambie.|Puede impedir o permitir la cámara para los asistentes si no está bloqueada por una plantilla.|
|Permitir micrófono para los asistentes|La configuración modo de audio IP determina qué participantes pueden usar sus micrófonos.|Sin configuración|Puede evitar o permitir el micrófono para los asistentes. Se puede exigir la configuración o se puede permitir que el organizador de la reunión cambie.|Puede evitar o permitir el micrófono para los asistentes si no está bloqueado por una plantilla.|
|Aplicar una marca de agua a la fuente de vídeo de todos|Puede establecerse en Activado o Desactivado. Si se establece en Desactivado, no estará disponible en etiquetas de confidencialidad, plantillas de reunión o configuración de reuniones.|Puede exigir o impedir marcas de agua en las fuentes de vídeo de los participantes o dejar la configuración descontrolada.|Puede exigir o impedir marcas de agua en las fuentes de vídeo de los participantes a menos que la configuración se controle mediante una etiqueta de confidencialidad.|El organizador de la reunión puede activarlo o desactivarlo a menos que la configuración esté deshabilitada por directiva de administrador o que se aplique o no mediante una plantilla de reunión o una etiqueta de confidencialidad.|
|Aplicar una marca de agua al contenido compartido|Puede establecerse en Activado o Desactivado. Si se establece en Desactivado, no estará disponible en etiquetas de confidencialidad, plantillas de reunión o configuración de reuniones.|Puede exigir o impedir marcas de agua en el contenido compartido en pantalla o dejar la configuración descontrolada.|Puede exigir o impedir marcas de agua en el contenido compartido en pantalla a menos que la configuración se controle mediante una etiqueta de confidencialidad.|El organizador de la reunión puede activarlo o desactivarlo a menos que la configuración esté deshabilitada por directiva de administrador o que se aplique o no mediante una plantilla de reunión o una etiqueta de confidencialidad.|
|Cifrado de un extremo a otro|Cuando está activado, el cifrado de un extremo a otro puede activarse mediante una etiqueta de confidencialidad, una plantilla de reunión o el organizador de la reunión.|Puede exigir o evitar el cifrado de un extremo a otro o dejar la configuración descontrolada.|Puede exigir o impedir el cifrado de un extremo a otro a menos que la configuración se controle mediante una etiqueta de confidencialidad.|El organizador de la reunión puede activarlo o desactivarlo a menos que la configuración esté deshabilitada por directiva de administrador o que se aplique o no mediante una plantilla de reunión o una etiqueta de confidencialidad.|
|Administrar lo que ven los asistentes|Sin configuración|Sin configuración|Puede establecerse en Activado o Desactivado y puede aplicar la configuración o permitir que el organizador de la reunión la cambie.|El organizador de la reunión puede activarlo o desactivarlo a menos que la configuración se aplique o desactive mediante una plantilla de reunión.|
|Chat de reunión|Puede establecerse en Activado, Desactivado o Activado para todos los usuarios excepto los participantes anónimos. Si se establece en Desactivado, la configuración del chat se deshabilitará en las etiquetas, las plantillas y la configuración de la reunión.|Puede exigir que el chat esté activado, desactivado o solo para reunión, o dejar la configuración descontrolada.|Si está habilitado en la directiva de administrador y no se controla mediante una etiqueta de confidencialidad, puede establecerse en Activado, Desactivado o solo para reunión. Se puede exigir la configuración o se puede permitir que el organizador de la reunión cambie.|Si la directiva de administrador la habilita y no se aplica mediante una etiqueta o plantilla de confidencialidad, el propietario de la reunión puede establecerlo en Activado, Desactivado o solo para reunión.|
|Personas marcación puede omitir la sala de espera|Establece la configuración predeterminada para las nuevas reuniones.|Si la etiqueta controla quién puede omitir la sala de espera, esta configuración se aplica Activado o Desactivado; de lo contrario, se descontrola.|Si no se controla mediante una etiqueta de confidencialidad, puede establecerse en Activado o Desactivado. Se puede exigir la configuración o se puede permitir que el organizador de la reunión cambie.|Si no se aplica mediante una plantilla o etiqueta de confidencialidad, el propietario de la reunión puede establecerlo en Activado o Desactivado.|
|Impedir copiar el contenido del chat en el Portapapeles|Sin configuración|Puede impedir que se copie el chat de la reunión. (No se aplica a los participantes anónimos).|Sin configuración|Sin configuración|
|Grabar automáticamente|Sin configuración|Puede exigir o impedir la grabación automática de la reunión o dejarla descontrolada.|Si no se controla mediante una etiqueta de confidencialidad, puede establecerse en Activado o Desactivado y puede aplicar la configuración o permitir que el organizador de la reunión la cambie.|El organizador de la reunión puede activarlo o desactivarlo a menos que se aplique o desactive mediante una plantilla de reunión o una etiqueta de confidencialidad.|
|Quién puede omitir la sala de espera|Establece la configuración predeterminada para las nuevas reuniones.|Puede exigir una determinada opción para quién puede omitir la sala de espera o puede dejarse sin control.|Si no se controla mediante una etiqueta de confidencialidad, selecciona una configuración para quién puede omitir la sala de espera. Se puede exigir la configuración o se puede permitir que el organizador de la reunión cambie.|El organizador de la reunión puede elegir quién puede omitir la sala de espera a menos que la configuración se aplique mediante una etiqueta o plantilla.|
|Quién puede presentar|Establece la configuración predeterminada para las nuevas reuniones. Los valores disponibles son Organizadores, Todos los usuarios de la organización y Todos.|Puede exigir la configuración de todos los usuarios, asistentes autenticados, organizadores o personas específicas, o puede dejarse sin control.|Sin configuración|El organizador de la reunión puede seleccionar quién puede presentar a menos que se aplique mediante una etiqueta de confidencialidad.|
|Quién puede grabar|Sin configuración|Puede exigir la configuración de los organizadores u organizadores y moderadores, o puede dejarse sin controlar.|Si no se controla mediante una etiqueta de confidencialidad, selecciona una configuración de organizadores u organizadores y moderadores.  Se puede exigir la configuración o se puede permitir que el organizador de la reunión cambie.|El organizador de la reunión puede elegir quién puede grabar (organizadores u organizadores y moderadores), a menos que la configuración se aplique mediante una etiqueta o plantilla.|

## <a name="admin-policies-effect-on-sensitivity-labels-and-meeting-templates"></a>Administración el efecto de las directivas en las etiquetas de confidencialidad y las plantillas de reunión

Aunque algunas directivas de administración (como la configuración de la sala de espera y quién puede presentar) especifican los valores predeterminados que puede cambiar el organizador de la reunión, la mayoría de las directivas de administrador determinan si una característica determinada está disponible para los usuarios en absoluto.

Si una característica no está disponible para un usuario determinado porque la directiva de administrador la ha desactivado, esa característica no se puede exigir con una etiqueta de confidencialidad o una plantilla de reunión.

Por ejemplo, si crea una etiqueta *altamente confidencial* y la configura para exigir la marca de agua y el cifrado de un extremo a otro, esa obligación solo se aplicará si la marca de agua y el cifrado de un extremo a otro están habilitados para el organizador de la reunión en la directiva de administrador.

Cuando planee las plantillas de reunión y las etiquetas de confidencialidad, asegúrese de que la configuración que desea controlar con ellas esté habilitada en las directivas de administración cuando sea necesario.

## <a name="sensitivity-labels-and-templates-together"></a>Etiquetas y plantillas de confidencialidad juntas

Algunas opciones de configuración solo están disponibles en etiquetas de confidencialidad y algunas solo están disponibles en plantillas. Hay varios disponibles en ambos casos:

- Chat
- Cifrado de un extremo a otro
- Configuración de la sala de espera
- Grabación de la reunión
- Marca de agua

Siempre que se usa una etiqueta de confidencialidad, la configuración configurada en la etiqueta tiene prioridad sobre cualquier configuración de plantilla o organizador de reuniones.

La configuración de una etiqueta de confidencialidad puede dejarse sin control cuando se crea la etiqueta, lo que permite que una plantilla o el organizador de la reunión controlen esta configuración.

Las etiquetas de confidencialidad se usan a menudo para varios fines: etiquetar documentos, sitios y correos electrónicos, así como reuniones. Puede evitar la creación de etiquetas adicionales solo para reuniones mediante plantillas junto con las etiquetas para tener en cuenta las variaciones de un tipo determinado de reunión.

Por ejemplo, el departamento de marketing podría tener requisitos diferentes para las reuniones confidenciales que el departamento de investigación. Puede configurar las opciones que son comunes a ambos en una etiqueta de confidencialidad y, a continuación, hacer plantillas independientes disponibles para los dos grupos que refinan aún más la configuración de la reunión para ese grupo. Ambas plantillas podrían usar la misma etiqueta.

## <a name="user-based-policies-and-meeting-based-policies"></a>Directivas basadas en usuarios y directivas basadas en reuniones

Las directivas de Teams , incluidas las directivas de reunión, se aplican en el nivel de usuario o grupo. La configuración de plantilla y etiqueta de confidencialidad se aplica en el nivel de reunión individual donde se usan esas etiquetas y plantillas. Tenga en cuenta dónde tiene sentido configurar las opciones en las directivas de administración de Teams frente a las etiquetas o plantillas de confidencialidad.

Estos son algunos ejemplos:

Si desea diferentes configuraciones de sala de espera predeterminadas para el departamento de investigación y el departamento de marketing, puede configurar estos valores predeterminados mediante directivas de administración y modificarlos aún más con etiquetas o plantillas.

Si desea que las marcas de agua solo estén disponibles para los funcionarios de gobierno, puede habilitarlas solo para aquellas personas que usen una directiva de administración. Después puede tener etiquetas o plantillas que exijan la marca de agua, pero la marca de agua solo se usará en las reuniones organizadas por los funcionarios de gobierno.

## <a name="different-meeting-types-with-the-same-sensitivity"></a>Diferentes tipos de reuniones con la misma sensibilidad

Usar plantillas y etiquetas juntas puede resultar útil si tiene diferentes tipos de reuniones que tienen la misma sensibilidad. Por ejemplo, si algunas de sus reuniones confidenciales son interactivas y otras son presentaciones en las que hay una interacción mínima de los asistentes, puede crear dos plantillas:
- Una que desactiva el vídeo y el audio de los asistentes para usarlos en las presentaciones
- Una que deja el vídeo y el audio a la discreción del organizador de la reunión para usarlo en reuniones interactivas

Ambas plantillas podrían usar la etiqueta *Confidencial* , que controlaría la configuración adicional, como quién puede omitir la sala de espera y quién puede presentar.

## <a name="specify-default-values-that-meeting-organizers-can-change"></a>Especificar valores predeterminados que los organizadores de la reunión pueden cambiar

Aunque las etiquetas suelen exigir una configuración determinada, las plantillas pueden exigir una configuración o permitir que el organizador de la reunión la cambie. Esto le permite implementar configuraciones predeterminadas que satisfacen sus necesidades de cumplimiento, a la vez que ofrece a los organizadores de la reunión la opción de invalidar la configuración si procede.

Por ejemplo, para un nivel de protección de línea base, es posible que desee usar una etiqueta de confidencialidad para desactivar la marca de agua. Al mismo tiempo, puede usar una plantilla para establecer el valor predeterminado para quién puede omitir la sala de espera, pero permitir que el organizador de la reunión cambie la configuración si es necesario.

Puede asignar la etiqueta de protección de línea base a la plantilla para que ambos se usen cuando un organizador de la reunión elija esa plantilla.

Algunas directivas de administración también se pueden usar para establecer un valor predeterminado que puede cambiar un organizador de la reunión. Entre ellos se incluyen los controles de la sala de espera y quién puede presentar.

## <a name="related-topics"></a>Temas relacionados

[Información general sobre las plantillas de reunión personalizadas en Microsoft Teams](custom-meeting-templates-overview.md)

[Configurar reuniones de Teams con tres niveles de protección](configure-meetings-three-tiers-protection.md)

[Usar etiquetas de confidencialidad para proteger los elementos del calendario, las reuniones y el chat de Teams](/microsoft-365/compliance/sensitivity-labels-meetings)
