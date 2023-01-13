---
title: Configurar reuniones de Teams con protección para datos altamente confidenciales
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
description: Aprenda a configurar reuniones de Teams para proteger la información altamente confidencial mediante plantillas y etiquetas de confidencialidad.
ms.openlocfilehash: 0d49cc4305f77b4b4208cc0f7418d5506155d0d6
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800262"
---
# <a name="configure-teams-meetings-with-protection-for-highly-sensitive-data"></a>Configurar reuniones de Teams con protección para datos altamente confidenciales

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Para obtener el nivel de protección *altamente sensible* , veremos dos escenarios diferentes:
- Reuniones altamente confidenciales en las que los asistentes participan e interactúan con los moderadores
- Presentaciones altamente confidenciales donde los asistentes no interactúan y solo están viendo la presentación

> [!Note]
> La configuración de reuniones en etiquetas de confidencialidad y plantillas de reunión personalizadas requieren Teams Premium.

#### <a name="highly-sensitive-meetings"></a>Reuniones altamente confidenciales

Para las reuniones altamente confidenciales, restringiremos quién puede omitir la sala de espera, quién puede presentar, cuándo los participantes pueden chatear y bloquearemos la copia desde el chat de la reunión. También habilitaremos el cifrado de un extremo a otro y la marca de agua para el vídeo y el contenido compartidos. Dado que usamos marcas de agua, la grabación de la reunión se deshabilitará.

En la tabla siguiente se describen las acciones que restringiremos para las reuniones altamente confidenciales y dónde se configurarán esas opciones.

|Característica|Setting|Ubicación|Forzada|
|:------|:------|:-------|:-------|
|Permitir cámara para los asistentes|**On**|Plantilla|No|
|Permitir micrófono para los asistentes|**On**|Plantilla|No|
|Aplicar una marca de agua a la fuente de vídeo de todos|**On**|Etiqueta|Sí|
|Aplicar una marca de agua al contenido compartido|**On**|Etiqueta|Sí|
|Cifrado de un extremo a otro|**On**|Etiqueta|Sí|
|Administrar lo que ven los asistentes|**On**|Plantilla|Sí|
|Chat de reunión|**Solo en reunión**|Plantilla|Sí|
|Personas marcación puede omitir la sala de espera|**Desactivado**|Etiqueta|Sí|
|Impedir copiar el contenido del chat en el Portapapeles|**On**|Etiqueta|Sí|
|Grabar automáticamente|(Deshabilitada debido a la marca de agua y el cifrado)|N/D|N/D|
|Quién puede omitir la sala de espera|**Solo los organizadores y co-organizadores**|Etiqueta|Sí|
|Quién puede presentar|**Solo los organizadores y co-organizadores**|Etiqueta|Sí|
|Quién puede grabar|(Deshabilitada debido a la marca de agua y el cifrado)|N/D|N/D|

La configuración que aparece como obligatoria se aplica mediante la etiqueta de confidencialidad o la plantilla de reunión. El organizador de la reunión puede cambiar las opciones que no se aplican.

#### <a name="highly-sensitive-presentations"></a>Presentaciones altamente confidenciales

Para presentaciones altamente confidenciales (donde no esperamos la interacción con los asistentes a la reunión), desactivaremos los micrófonos y las cámaras de los asistentes y desactivaremos el chat de la reunión.

Si desea permitir que los asistentes hagan preguntas al moderador, los organizadores de la reunión pueden activar la característica Q&A. (Asegúrese de que está habilitado en las directivas de reunión de administración de Teams).

En la tabla siguiente se describen qué acciones restringiremos para presentaciones altamente confidenciales y dónde se configurarán esas opciones.

|Característica|Setting|Ubicación|Forzada|
|:------|:------|:-------|:-------|
|Permitir cámara para los asistentes|**Desactivado**|Plantilla|Sí|
|Permitir micrófono para los asistentes|**Desactivado**|Plantilla|Sí|
|Aplicar una marca de agua a la fuente de vídeo de todos|**On**|Etiqueta|Sí|
|Aplicar una marca de agua al contenido compartido|**On**|Etiqueta|Sí|
|Cifrado de un extremo a otro|**On**|Etiqueta|Sí|
|Administrar lo que ven los asistentes|**On**|Plantilla|Sí|
|Chat de reunión|**Desactivado**|Plantilla|Sí|
|Personas marcación puede omitir la sala de espera|**Desactivado**|Etiqueta|Sí|
|Impedir copiar el contenido del chat en el Portapapeles|**On**|Etiqueta|Sí|
|Grabar automáticamente|(Deshabilitada debido a la marca de agua y el cifrado)|N/D|N/D|
|Quién puede omitir la sala de espera|**Solo los organizadores y co-organizadores**|Etiqueta|Sí|
|Quién puede presentar|**Solo los organizadores y co-organizadores**|Etiqueta|Sí|
|Quién puede grabar|(Deshabilitada debido a la marca de agua y el cifrado)|N/D|N/D|

La configuración que aparece como obligatoria se aplica mediante la etiqueta de confidencialidad o la plantilla de reunión. El organizador de la reunión puede cambiar las opciones que no se aplican.

## <a name="options-for-recording-meetings"></a>Opciones para grabar reuniones

Para el nivel de protección *altamente confidencial* , usamos la marca de agua y el cifrado de un extremo a otro para las reuniones y las presentaciones. Sin embargo, el uso de estas características impide la grabación de la reunión. Si necesita grabar reuniones altamente confidenciales, le recomendamos que no configure las marcas de agua ni el cifrado de un extremo a otro como parte de la etiqueta de confidencialidad. Los organizadores de reuniones pueden seguir usándolas para las reuniones que no necesiten grabar.

## <a name="presentation-options-for-highly-sensitive-meetings"></a>Opciones de presentación para reuniones altamente confidenciales

Para las reuniones *altamente confidenciales* , aplicamos una configuración específica para quién puede presentar, así como cómo se comparte el contenido.

Al activar **Administrar lo que los asistentes pueden ver**, nos aseguramos de que los organizadores de la reunión puedan controlar el contenido compartido antes de que aparezca en la pantalla para los participantes. En este ejemplo, usamos una plantilla para activarla de forma predeterminada, pero también puede exigirla en la plantilla si lo necesita.

Al establecer **Quién puede presentar** en **Solo los organizadores y co-organizadores** en la etiqueta de confidencialidad, nos aseguramos de que solo las personas que pueden presentar sean aquellas que el organizador de la reunión desee.

## <a name="lobby-options-for-sensitive-meetings"></a>Opciones de sala de espera para reuniones confidenciales

Usaremos la etiqueta de confidencialidad para evitar que nadie más que los organizadores de la reunión omita la sala de espera. Esto permite a los organizadores consultar a cada asistente y asegurarse de que deben ser admitidos.

## <a name="participation-options-for-highly-sensitive-meetings"></a>Opciones de participación para reuniones altamente confidenciales

Aunque el chat se puede controlar con la etiqueta de confidencialidad, usaremos plantillas en este caso para que las plantillas de reunión y presentación puedan compartir la misma etiqueta. Restringiremos el chat solo durante la reunión para las reuniones y lo desactivaremos por completo para las presentaciones. (Los organizadores pueden usar la característica Q&A en las presentaciones para permitir comentarios o preguntas del público).

Para las reuniones y presentaciones, también evitaremos copiar el contenido del chat en el Portapapeles.

Aunque dejaremos habilitados el micrófono y la cámara de los asistentes para las reuniones, los desactivaremos para las presentaciones.

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Para el nivel de protección confidencial, usaremos una etiqueta de confidencialidad que puede usar directamente en una reunión o como parte de una plantilla de reunión. Según la configuración que elija, esta etiqueta también se puede usar para clasificar equipos y archivos individuales.

Si ya tiene etiquetas de confidencialidad implementadas en su organización, tenga en cuenta cómo se ajusta esta etiqueta a la estrategia general de etiquetas. Puede cambiar el nombre o la configuración si es necesario para satisfacer las necesidades de su organización. Si ya tiene una etiqueta que usa para información confidencial, puede editarla y agregar reuniones de Teams.

> [!IMPORTANT]
> Si se especifica una etiqueta de confidencialidad que restringe la copia desde el chat como etiqueta de canal predeterminada en una etiqueta de contenedor, los equipos con esa etiqueta de contenedor restringirán la copia del chat para todos los canales del equipo, tanto dentro como fuera de las reuniones del canal.

Para crear una etiqueta de confidencialidad
1. Abra el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com).
1. En **Soluciones**, haga clic en **Protección de información**.
1. Haga clic en **Crear una etiqueta**.
1. Asigne un nombre a la etiqueta. Le sugerimos **Altamente confidencial**, pero puede elegir un nombre diferente si ese ya está en uso.
1. Agregue un nombre para mostrar y una descripción y, a continuación, haga clic en **Siguiente**.
1. En la página **Definir el ámbito de esta etiqueta** , seleccione **Elementos** e **Incluir reuniones**. (Tenga en cuenta que puede seleccionar otras opciones si desea usar esta etiqueta para otros fines).
1. Seleccione **Siguiente**.
1. Continúe seleccionando las opciones que desea usar con esta etiqueta y, a continuación, en la página **Configuración para reuniones y chats de Teams** , elija los siguientes valores:
    1. Seleccione **Controlar quién puede omitir la sala de espera** y seleccione **Solo los organizadores y co-organizadores** en la lista desplegable.
    1. Asegúrese **de que la opción Permitir que los usuarios de acceso telefónico local omita la sala de espera** está desactivada
    1. Seleccione **Controlar quién puede presentar** y seleccione **Solo los organizadores y co-organizadores** en la lista desplegable.
    1. Seleccione **Controlar el cifrado de un extremo a otro para el vídeo y el audio** de la reunión y, después, establezca **Aplicar cifrado de un extremo a otro** en **Activado**.
    1. Seleccione **Controlar marcas de agua** y, después, establezca **Aplicar marca de agua a contenido compartido** y **Aplicar marca de agua a la fuente de vídeo de todos** los usuarios en **Activado**.
    1. Seleccione **Impedir la copia del contenido del chat en el Portapapeles**.
    1. Configure otras opciones de configuración que necesite para su organización.
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-highly-sensitive-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-highly-sensitive-large.png":::-->
1. Seleccione **Siguiente**.
1. Complete el asistente con cualquier configuración adicional que desee usar y, a continuación, seleccione **Crear etiqueta** y, a continuación, seleccione **Listo**.

Una vez que haya creado la etiqueta, deberá publicarla para los usuarios que la usarán. Para una protección altamente confidencial, haremos que la etiqueta esté disponible para todos los usuarios. La etiqueta se publica en la portal de cumplimiento Microsoft Purview, en la pestaña **Directivas de etiqueta** de la página **Protección de información**. Si tiene una directiva existente que se aplique a todos los usuarios, agregue esta etiqueta a esa directiva. Si necesita crear una nueva directiva, vea [Publicar etiquetas de confidencialidad creando una directiva de etiqueta](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

Para obtener más información sobre el uso de etiquetas de confidencialidad con reuniones, vea [Usar etiquetas de confidencialidad para proteger elementos de calendario, reuniones de Teams y chat](/microsoft-365/compliance/sensitivity-labels-meetings).

## <a name="meeting-templates"></a>Plantillas de reunión

En el nivel de protección *altamente confidencial* , estamos configurando las siguientes opciones con una plantilla de reunión:

- **Permitir cámara para los asistentes** -  **Activado**, pero no obligatorio para las reuniones y aplicado **Desactivado** para las presentaciones.
- **Permitir micrófono para los asistentes** -  **Activado**, pero no obligatorio para las reuniones y aplicado **Desactivado** para las presentaciones.
- **Administrar lo que pueden ver los asistentes** : obligatorio **para** las reuniones y las presentaciones.
- **Chat de reunión** : se aplica **a Solo en reunión** para reuniones y se aplica a **Desactivado** para presentaciones.

Dado que estas opciones de configuración difieren entre reuniones y presentaciones, crearemos una plantilla para cada una de las cuales compartiremos la misma etiqueta de confidencialidad.

#### <a name="highly-sensitive-meetings-template"></a>Plantilla de reuniones altamente confidenciales

Para crear una plantilla de reunión para reuniones altamente confidenciales

1. En el Centro de administración de Teams, expanda **Reuniones** y seleccione **Plantillas de reunión**.
1. Seleccione **Agregar.**
1. Escriba un nombre y una descripción para la plantilla.
1. En la sección **Aplicar etiqueta de confidencialidad** , elija la etiqueta que creó anteriormente.
1. Selecciona **Aplicar etiqueta de confidencialidad** y, a continuación, **bloquear**.
1. Establezca **Chat** de la **reunión en Solo en la reunión** y, a continuación, seleccione la configuración y seleccione **Bloquear**.
1. Establezca **Administrar lo que los asistentes ven** **en Activado** y, a continuación, seleccione la configuración y seleccione **Bloquear**.
1. Cambia las opciones de configuración adicionales si lo deseas.
1. Para evitar que el organizador de la reunión cambie una configuración, seleccione la configuración y, a continuación, seleccione **Bloquear**.
1. Para evitar que el organizador de la reunión vea una configuración, seleccione la configuración y, a continuación, seleccione **Ocultar**.
1. Seleccione **Guardar**.

#### <a name="highly-sensitive-presentations-template"></a>Plantilla de presentaciones altamente confidenciales

Para crear una plantilla de reunión para presentaciones altamente confidenciales

1. En el Centro de administración de Teams, expanda **Reuniones** y seleccione **Plantillas de reunión**.
1. Seleccione **Agregar.**
1. Escriba un nombre y una descripción para la plantilla.
1. En la sección **Aplicar etiqueta de confidencialidad** , elija la etiqueta que creó anteriormente.
1. Selecciona **Aplicar etiqueta de confidencialidad** y, a continuación, **bloquear**.
1. Establezca **Permitir micrófono para los asistentes** en **Activado** , seleccione la configuración y seleccione **Bloquear**.
1. Establezca **Permitir cámara para los asistentes** en **Activado** y, a continuación, seleccione la configuración y seleccione **Bloquear**.
1. Establezca **Chat de la reunión** en **Desactivado** y, a continuación, seleccione la configuración y seleccione **Bloquear**.
1. Establezca **Administrar lo que los asistentes ven** **en Activado** y, a continuación, seleccione la configuración y seleccione **Bloquear**.
1. Cambia las opciones de configuración adicionales si lo deseas.
1. Para evitar que el organizador de la reunión cambie una configuración, seleccione la configuración y, a continuación, seleccione **Bloquear**.
1. Para evitar que el organizador de la reunión vea una configuración, seleccione la configuración y, a continuación, seleccione **Ocultar**.
1. Seleccione **Guardar**.

## <a name="related-topics"></a>Temas relacionados

[Configurar reuniones de Teams con tres niveles de protección](configure-meetings-three-tiers-protection.md)

[Información general sobre las plantillas de reunión personalizadas en Microsoft Teams](custom-meeting-templates-overview.md)

[Usar plantillas de reunión de Teams, etiquetas de confidencialidad y directivas de administración juntas para reuniones confidenciales](meeting-templates-sensitivity-labels-policies.md)

[Usar etiquetas de confidencialidad para proteger los elementos del calendario, las reuniones y el chat de Teams](/microsoft-365/compliance/sensitivity-labels-meetings)
