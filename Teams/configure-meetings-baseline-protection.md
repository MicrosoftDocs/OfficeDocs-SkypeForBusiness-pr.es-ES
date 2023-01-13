---
title: Configurar reuniones de Teams con protección de línea base
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
description: Aprenda a configurar reuniones de Teams para un nivel de protección de línea base mediante plantillas y etiquetas de confidencialidad.
ms.openlocfilehash: 3770bb03c1986c4a6bbef72408340fd791b058f1
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800104"
---
# <a name="configure-teams-meetings-with-baseline-protection"></a>Configurar reuniones de Teams con protección de línea base

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Para el nivel de protección de *línea base* , restringiremos quién puede omitir la sala de espera con una etiqueta de confidencialidad y estableceremos un valor predeterminado para quién puede presentar una directiva de administrador de Teams. También puede restringir acciones adicionales si su organización lo requiere.

> [!Note]
> La configuración de reuniones en etiquetas de confidencialidad y plantillas de reunión personalizadas requieren Teams Premium.

En la tabla siguiente se describen las acciones que restringiremos para las reuniones de línea base y dónde se configurarán esas opciones.

|Característica|Setting|Ubicación|Forzada|
|:------|:------|:-------|:-------|
|Permitir cámara para los asistentes|**On**|Plantilla|No|
|Permitir micrófono para los asistentes|**On**|Plantilla|No|
|Aplicar una marca de agua a la fuente de vídeo de todos|**Desactivado**|Etiqueta|Sí|
|Aplicar una marca de agua al contenido compartido|**Desactivado**|Etiqueta|Sí|
|Cifrado de un extremo a otro|**Desactivado**|Etiqueta|Sí|
|Administrar lo que ven los asistentes|**Desactivado**|Plantilla|No|
|Chat de reunión|**On**|Plantilla|No|
|Personas marcación puede omitir la sala de espera|**Desactivado**|Plantilla|Sí|
|Impedir copiar el contenido del chat en el Portapapeles|**Desactivado**|Etiqueta|Sí|
|Grabar automáticamente|**Desactivado**|Plantilla|No|
|Quién puede omitir la sala de espera|**Personas en mi organización, personas de organizaciones de confianza e invitados**|Plantilla|No|
|Quién puede presentar|**Todos los miembros de la organización, pero el usuario puede invalidar**|Centro de administración de Teams|No|
|Quién puede grabar|**Organizadores y moderadores**|Plantilla|No|

La configuración que aparece como obligatoria se aplica mediante la etiqueta de confidencialidad o la plantilla de reunión. El organizador de la reunión puede cambiar las opciones que no se aplican.

## <a name="default-values-for-who-can-present"></a>Valores predeterminados de **Quién puede presentar**

El valor predeterminado de **Quién puede presentar** es **Todos**. Para el nivel de protección de línea base, estableceremos un valor predeterminado más seguro para **todos los usuarios de la organización** que los organizadores de la reunión pueden cambiar si lo desean.

Podemos establecer este valor con una etiqueta de confidencialidad, pero el valor se aplicará para cualquier reunión con esa etiqueta. Esta configuración no está disponible en las plantillas de reunión, por lo que la estableceremos en el Centro de administración de Teams.

Para configurar quién puede presentar en las reuniones
1. En el Centro de administración de Teams, expanda Reuniones y seleccione **Directivas de reunión**.
1. Seleccione la directiva que desea actualizar.
1. En **Participantes & invitados**, establezca **Quién puede presentar en reuniones en** **Todos los miembros de la organización, pero el usuario puede invalidarlo**.
1. Seleccione **Guardar**.

## <a name="watermarks-and-end-to-end-encryption"></a>Marcas de agua y cifrado de un extremo a otro

En el nivel de protección de *línea base* , deshabilitaremos las marcas de agua y el cifrado de un extremo a otro con una etiqueta de confidencialidad. Esto evitará que los organizadores de la reunión usen estas características. Las marcas de agua y el cifrado de un extremo a otro son más aplicables a las reuniones confidenciales.

El cifrado de un extremo a otro y las marcas de agua deshabilitan algunas otras características, como la grabación de reuniones. Desactivarlas para el nivel de protección de *línea base* puede evitar instancias en las que los organizadores de reuniones usen estas características sin darse cuenta de los límites que imponen.

Si trabaja en un sector altamente regulado, es posible que desee mantener estas características disponibles incluso *en el nivel* de protección previsto.

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Para el nivel de protección de *línea base* , usaremos una etiqueta de confidencialidad que puede usar directamente en una reunión o como parte de una plantilla de reunión. Según la configuración que elija, esta etiqueta también se puede usar para clasificar equipos y archivos individuales.

Si ya tiene etiquetas de confidencialidad implementadas en su organización, tenga en cuenta cómo se ajusta esta etiqueta a la estrategia general de etiquetas. Puede cambiar el nombre o la configuración que se muestra a continuación si es necesario para satisfacer las necesidades de su organización. Si ya tiene una etiqueta que usa para la protección general o de línea base, puede editarla y agregarle reuniones de Teams.

Para crear una etiqueta de confidencialidad
1. Abra el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com).
1. En **Soluciones**, haga clic en **Protección de información**.
1. Haga clic en **Crear una etiqueta**.
1. Asigne un nombre a la etiqueta. Le sugerimos **Confidencial**, pero puede elegir un nombre diferente si ya está en uso.
1. Agregue un nombre para mostrar y una descripción y, a continuación, haga clic en **Siguiente**.
1. En la página **Definir el ámbito de esta etiqueta** , seleccione **Elementos** e **Incluir reuniones**. (Tenga en cuenta que puede seleccionar otras opciones si desea usar esta etiqueta para otros fines).
1. Seleccione **Siguiente**.
1. Continúe seleccionando las opciones que desea usar con esta etiqueta y, a continuación, en la página **Configuración para reuniones y chats de Teams** , elija los siguientes valores:
    1. Seleccione **Controlar el cifrado de un extremo a otro para el vídeo y el audio** de la reunión y establezca **Aplicar cifrado de un extremo a otro** en **Desactivado**.
    1. Seleccione **Controlar marcas de agua** y establezca **Aplicar marcas de agua al contenido compartido** y **Aplicar marcas de agua a la fuente de vídeo de todos** los usuarios en **Desactivado**.
    1. Configure otras opciones de configuración que necesite para su organización.
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-baseline-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-baseline-large.png":::-->
1. Seleccione **Siguiente**.
1. Complete el asistente con cualquier configuración adicional que desee usar y, a continuación, seleccione **Crear etiqueta** y, a continuación, seleccione **Listo**.

Una vez que haya creado la etiqueta, deberá publicarla para los usuarios que la usarán. Para la protección de línea base, la etiqueta estará disponible para todos los usuarios. La etiqueta se publica en la portal de cumplimiento Microsoft Purview, en la pestaña **Directivas de etiqueta** de la página **Protección de información**. Si tiene una directiva existente que se aplique a todos los usuarios, agregue esta etiqueta a esa directiva. Si necesita crear una nueva directiva, vea [Publicar etiquetas de confidencialidad creando una directiva de etiqueta](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

Para obtener más información sobre el uso de etiquetas de confidencialidad con reuniones, vea [Usar etiquetas de confidencialidad para proteger elementos de calendario, reuniones de Teams y chat](/microsoft-365/compliance/sensitivity-labels-meetings).

## <a name="meeting-templates"></a>Plantillas de reunión

En el nivel de protección de *línea base* , usaremos la plantilla para establecer un valor predeterminado para quién puede omitir la sala de espera que incluye participantes externos de dominios de confianza.

También evitaremos que las personas que llaman por teléfono omitan la sala de espera. Puede omitir esta configuración si su organización mantiene reuniones con frecuencia en las que los participantes de acceso telefónico local deben poder unirse directamente. Si hay ciertos tipos de reuniones en los que esto es cierto, considere la posibilidad de usar una plantilla independiente para esas reuniones.

Si ha elegido deshabilitar las marcas de agua y el cifrado de un extremo a otro en la confidencialidad, también puede usar la plantilla para ocultar esa configuración al organizador de la reunión.

Para crear una plantilla de reunión personalizada

1. En el Centro de administración de Teams, expanda **Reuniones** y seleccione **Plantillas de reunión**.
1. Seleccione **Agregar.**
1. Escriba un nombre y una descripción para la plantilla.
1. En la sección **Aplicar etiqueta de confidencialidad** , elija la etiqueta que creó anteriormente.
1. Selecciona **Aplicar etiqueta de confidencialidad** y, a continuación, **bloquear**.
1. En la lista desplegable **Sala de espera** , seleccione **Todos los miembros de mi organización, las organizaciones de confianza y los invitados**.
1. Asegúrese de que **Personas llamada en el teléfono puede omitir la sala de espera** está establecida en **Desactivado**, selecciónela y seleccione **Bloquear**.
1. Si ha deshabilitado las marcas de agua y el cifrado de un extremo a otro con la etiqueta de confidencialidad, considere la posibilidad de seleccionar estas opciones aquí y seleccionar **Ocultar** para que los organizadores de la reunión no las vean.
1. Cambia las opciones de configuración adicionales si lo deseas.
1. Para evitar que el organizador de la reunión cambie una configuración, seleccione la configuración y, a continuación, seleccione **Bloquear**.
1. Para evitar que el organizador de la reunión vea una configuración, seleccione la configuración y, a continuación, seleccione **Ocultar**.
1. Seleccione **Guardar**.

## <a name="related-topics"></a>Temas relacionados

[Configurar reuniones de Teams con tres niveles de protección](configure-meetings-three-tiers-protection.md)

[Información general sobre las plantillas de reunión personalizadas en Microsoft Teams](custom-meeting-templates-overview.md)

[Usar plantillas de reunión de Teams, etiquetas de confidencialidad y directivas de administración juntas para reuniones confidenciales](meeting-templates-sensitivity-labels-policies.md)
