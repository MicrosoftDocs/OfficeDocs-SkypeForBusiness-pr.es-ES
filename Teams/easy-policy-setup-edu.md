---
title: Asistente para directivas de Teams para la educación para aplicar directivas fácilmente para un aprendizaje seguro
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: shajohri, angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar el Asistente de directivas de Teams para el ámbito educativo para aplicar directivas a estudiantes y educadores de forma sencilla para mantener el entorno de aprendizaje en seguridad.
f1keywords: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d72ef20a8ae56fba67534944d229d01468531207
ms.sourcegitcommit: 80c1ec1d5a43b9259a4da6db3e462f6d4257bfa7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "49564263"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Use el Asistente para directivas de Teams para el ámbito educativo para aplicar directivas fácilmente para un entorno de aprendizaje seguro.

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Información general

El Asistente para directivas de Microsoft Teams para el ámbito educativo simplifica la administración de directivas para los estudiantes y los educadores. Utilícelo para aplicar de forma rápida y sencilla el conjunto más importante de directivas relevante para crear una experiencia de aprendizaje segura y productiva.

Las directivas de Teams permiten controlar cómo se comparan los equipos y qué características están disponibles para los usuarios. Por ejemplo, hay directivas de llamada, directivas de reunión y directivas de mensajería, por nombrar algunas, y cada área de Directiva se puede personalizar para satisfacer las necesidades de la organización.

Para mantener un entorno de aprendizaje seguro y centrado, es importante establecer directivas para controlar lo que los alumnos pueden hacer en Teams. Por ejemplo, puede usar directivas para controlar quién puede usar chats privados y llamadas privadas, quién puede programar reuniones y qué tipos de contenido se pueden compartir. También puede usar directivas para activar las características de teams que enriquecen la experiencia de aprendizaje.

Para que los estudiantes y educadores puedan mantener la seguridad de la experiencia de aprendizaje, deben ajustarse las directivas. Las directivas para alumnos deben ser más restrictivas para reducir el riesgo de recibir niveles inapropiados de acceso. Los educadores y el personal necesitan un conjunto independiente de directivas que puedan ser más permisivos para permitir que funcionen correctamente. Por ejemplo, permita que los educadores programen reuniones y restrinjan que los alumnos la hagan.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de pantalla del asistente":::

En este artículo se explica cómo ejecutar el asistente.

> [!IMPORTANT]
> Las directivas aplicadas por el asistente satisfarán las necesidades de la mayoría de los equipos para los clientes educativos. El asistente ajusta la definición global (predeterminada para toda la organización) de un conjunto de directivas básicas con la configuración que recomendamos para la seguridad de los alumnos y la aplica a los alumnos. El Asistente también crea y asigna un conjunto de directivas personalizadas a educadores y personal. La mayoría de los equipos de los clientes educativos no necesitan usar otros métodos de asignación de directivas después de ejecutar este asistente. Use otros métodos de asignación de directivas *solo* si desea crear y administrar manualmente las directivas para los estudiantes, los educadores y el personal.

## <a name="teams-for-education-policy-wizard"></a>Asistente para directivas de Teams para el ámbito educativo

<a name="polwiz_intro"> </a>

El asistente aplica un conjunto de definiciones de directivas básicas a los alumnos y un conjunto independiente de definiciones de directivas básicas para educadores y personal, con la configuración adecuada para cada uno de ellos. Esto es lo que sucede al ejecutar el asistente.

El asistente configura las directivas según el tipo de institución educativa (**principal o secundaria** o de **educación superior**). Selecciona el tipo de institución y el asistente hace lo siguiente:

- **Alumnos**: el asistente ajusta la definición de directiva global (predeterminada para toda la organización) de cada área de directiva cubierta por el asistente con la nueva configuración predeterminada que es adecuada para mantener a los alumnos seguros. Esto garantiza que los alumnos actuales y todos los nuevos alumnos obtengan el conjunto de directivas más restrictivo.
- **Educadores y personal**: el asistente crea un conjunto de definiciones de directiva personalizadas para cada área de directiva cubierta por el asistente con configuraciones adaptadas a las necesidades de educadores y personal. A continuación, asigna las definiciones de directiva al grupo de educadores y personal que elija. De esta manera, los formadores y el personal obtienen un conjunto de directivas más permisivo para permitir que se realicen correctamente.

Solo tiene que ejecutar el Asistente una vez. Los nuevos alumnos obtienen automáticamente la definición de directiva global (predeterminada para toda la organización) aplicada por el asistente y el nuevo personal que agregue al grupo que seleccionó se asignan automáticamente a las directivas personalizadas.

> [!NOTE]
> Consulte [directivas aplicadas por el asistente](#policies-applied-by-the-wizard) para obtener una lista detallada de las definiciones de directivas aplicadas por el asistente.

¡ Ya puedes comenzar!

## <a name="run-the-wizard"></a>Ejecutar el asistente

<a name="polwiz_run"> </a>

Siga estos pasos para ejecutar el asistente. 

1. Si no está familiarizado con Teams, el asistente se iniciará automáticamente. En caso contrario, puede iniciar el asistente en cualquier momento desde el panel. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Panel** y, a continuación, en el icono **configuración de directiva sencilla para un entorno de aprendizaje seguro** , seleccione **Configuración rápida**.

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Captura de pantalla del asistente en el panel":::

2. Seleccione el tipo de institución educativa (**principal o secundaria** o **educación superior**) y, a continuación, haga clic en **siguiente**.

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de pantalla de la página del Asistente para seleccionar el tipo de institución":::

3. Busque y seleccione un grupo que contenga los educadores y el personal y, a continuación, haga clic en **siguiente**. Si aún no tiene ningún grupo configurado para los educadores y el personal, [cree un grupo](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)y vuelva a ejecutar el asistente. <br/><br/>En este momento, solo puede seleccionar un grupo. Los educadores y el personal del grupo que seleccione se asignarán a [un conjunto de políticas personalizadas](#policies-applied-by-the-wizard) adaptadas a sus necesidades. Recuerde que este conjunto de directivas es independiente de las directivas que se aplican a los alumnos.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Captura de pantalla de la página del Asistente para seleccionar el educador y el grupo de docentes":::

4. Revise las selecciones.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Captura de pantalla de la página en el Asistente para revisar las selecciones":::

5. Seleccione **aplicar** para aplicar los cambios. Esto puede demorar unos minutos en completarse.<br/><br/>Las definiciones de directiva globales (predeterminada para toda la organización) se aplican inmediatamente a los alumnos. Los educadores y el personal pueden tardar hasta 48 horas en asignar las directivas personalizadas a cada miembro del grupo que seleccionó, según el tamaño del grupo. Esto sucede en segundo plano, después de completar este paso correctamente.
6. Ya está en camino pero aún no lo ha hecho. Hay algunas cosas más que hay que tener en cuenta. Después, consulte los pasos de la sección [Qué hacer después de ejecutar el asistente](#what-to-do-after-running-the-wizard) de este artículo.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Captura de pantalla de la página del Asistente para los pasos siguientes":::

## <a name="what-to-do-after-running-the-wizard"></a>Qué hacer después de ejecutar el asistente

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Paso 1: quitar las asignaciones de directiva existentes que entran en conflicto con las directivas aplicadas por el asistente

> [!IMPORTANT]
> **Complete este paso solo si tiene directivas existentes asignadas a alumnos o educadores y personal *antes* de ejecutar el asistente**. Si no está familiarizado con Teams y no tiene directivas existentes distintas de las creadas por el asistente, omita este paso y vaya al paso 2.

En Teams, para una zona de directiva determinada, se puede aplicar una directiva a un usuario de las siguientes maneras:

- Asignación directa al usuario
- Asignación a un grupo del que el usuario es miembro
- Si el usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se haya asignado una directiva, el usuario obtiene automáticamente la directiva global (opción predeterminada para toda la organización).

Si hay más de una de estas asignaciones de directivas para un usuario, Teams usa el siguiente orden para determinar qué asignación de directiva surte efecto. Para obtener más información, consulte [¿qué directiva tiene prioridad?](assign-policies.md#which-policy-takes-precedence) y [las reglas de prioridad](assign-policies.md#precedence-rules).

|Asignaciones de directivas de un usuario|Directiva que se aplica |
|---------|---------|
|Directiva asignada al Grupo: no<br/>Directiva asignada directamente al usuario: no    |Directiva predeterminada global (toda la organización)      |
|Directiva asignada al Grupo: no<br/>Directiva asignada directamente al usuario: sí    |Directiva asignada directamente al usuario         |
|Directiva asignada al Grupo: sí<br/>Directiva asignada directamente al usuario: sí     |Directiva asignada directamente al usuario         |
|Directiva asignada al Grupo: sí<br/>Directiva asignada directamente al usuario: no     |Directiva asignada al grupo<br/><br/>Si el usuario es miembro de varios grupos y a cada grupo se le asigna una directiva del mismo área de Directiva, la Directiva que tiene la [clasificación de asignación de grupo](assign-policies.md#group-assignment-ranking) más alta tiene efecto.       |

Por este orden, las directivas creadas por el asistente no se aplicarán si un usuario ya tiene asignaciones directas o asignaciones de grupo. Esto significa que tendrá que quitar las asignaciones de directivas existentes del usuario para que la Directiva aplicada por el asistente surta efecto.

Para cada [área de directiva aplicada por el asistente](#policies-applied-by-the-wizard), haga lo siguiente:

- Quite todas las asignaciones directas y de grupos de los alumnos para que la definición de directiva global (predeterminada para toda la organización) aplicada por el asistente surta efecto.
- Quite las asignaciones directas conflictivas de los formadores y el personal para que la definición de directiva personalizada creada por el asistente surta efecto. Use la tabla anterior para determinar los escenarios que se aplican a su usuario. <br/><br/>Tenga en cuenta que el asistente asigna directivas a los formadores y al grupo de personal con una [clasificación de asignación de grupo](assign-policies.md#group-assignment-ranking) de 1, que es la mayor clasificación. Si el grupo educadores y personal tiene una directiva existente de la misma área de directiva asignada, esa directiva existente se mueve a una clasificación inferior y la directiva asignada por el asistente entrará en vigor.

[Obtenga más información](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) sobre cómo quitar directivas que se asignan directamente a los usuarios.

Por ejemplo, ha asignado una directiva de reunión directamente a los educadores y los alumnos tienen la Directiva de reunión global (opción predeterminada para toda la organización). En este caso, quite la Directiva de reunión que asignó directamente a los formadores para que la definición de directiva personalizada para la Directiva de reunión creada por el asistente surta efecto. No tiene que hacer nada con la Directiva de reuniones global (predeterminada para organigramas) existente para los alumnos porque ninguna otra política de la reunión entra en conflicto con ella.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Paso 2: comprobar las medidas adicionales que puede tomar para la seguridad de los alumnos

El asistente ajusta automáticamente [estas directivas y las](#policies-applied-by-the-wizard)aplica. Hay algunas medidas adicionales que quizás quieras tomar en función de las necesidades de tu institución para mantener la seguridad.

Vea [mantener a los alumnos seguros mientras usa Teams para](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) obtener recomendaciones de seguridad adicionales.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Paso 3: comprobar si hay actualizaciones de directiva en el centro de mensajes

En este momento, el asistente aplica las directivas recomendadas cuando la ejecuta. Es importante saber que, a medida que las nuevas directivas estén disponibles en Teams, el asistente no agrega automáticamente la configuración global (la organización predeterminada para toda la organización) para la seguridad de los alumnos. Esta capacidad estará disponible en una versión futura.

Hasta que esta capacidad esté disponible, compruebe el [centro de mensajes](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) (en el centro de administración de Microsoft 365) con frecuencia para mantenerse al día de las nuevas directivas y la configuración de directivas de Teams. A medida que estén disponibles nuevas características, es posible que tenga que actualizar manualmente las directivas para mantener el entorno de aprendizaje en seguridad.

## <a name="make-changes-in-the-wizard"></a>Realizar cambios en el asistente

<a name="polwiz_change"> </a>

Si necesita realizar cambios después de ejecutar el asistente, puede volver a ejecutarlo y cambiar las selecciones.

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Panel** y, a continuación, en el icono **configuración de directiva sencilla para un entorno de aprendizaje seguro** , seleccione **cambiar**.
2. Desde aquí, continúe con cada página del Asistente para realizar los cambios. Puede cambiar el tipo de institución, el grupo de educadores y el personal al que desea asignar directivas o ambos.

En la tabla siguiente se resume lo que sucede cuando realiza un cambio en el asistente.

|Tipo de cambio  |Comportamiento de la Directiva  |
|---------|---------|
|Cambiar el tipo de institución educativa y los formadores y el grupo personal    |<ul><li>**Alumnos**: las definiciones de directiva globales (predeterminada para toda la organización) basadas en el nuevo tipo de institución educativa se aplican a los alumnos.</li><li>**Educadores y personal**: un conjunto de definiciones de políticas personalizadas basadas en el nuevo tipo de institución educativa se crea y se asigna al nuevo educador y grupo de personal. Las definiciones de directiva personalizadas anteriores se quitan del grupo educadores y personal anterior.</li></ul>    |
|Cambiar solo el tipo de institución educativa    |<ul><li>**Alumnos**: las definiciones de directiva globales (predeterminada para toda la organización) basadas en el nuevo tipo de institución educativa se aplican a los alumnos.</li><li>**Educadores y personal**: un conjunto de definiciones de políticas personalizadas basadas en el nuevo tipo de institución educativa se crea y se asigna al grupo educadores y personal. Las definiciones de directiva personalizadas creadas para el tipo de institución educativa anterior se quitan del grupo educadores y personal.</li></ul>         |
|Cambiar solo el grupo educadores y personal   |<ul><li>**Alumnos**: sin cambiar las definiciones de directiva globales (predeterminada para toda la organización) que se aplican a los alumnos.</li><li>**Educadores y personal**: las definiciones de directiva personalizadas se asignan al nuevo grupo de educadores y personal y se quitan del grupo de educadores y personal anterior.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Directivas aplicadas por el asistente

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Áreas de directivas

Estas son las áreas de directivas y los nombres de directiva correspondientes que cubre el asistente. Para buscar estas directivas, vaya al centro de administración de Microsoft Teams y, a continuación, en el navegación de la izquierda, vaya a la página de cada área de directivas.

#### <a name="students"></a>[**Pida**](#tab/students/)

|Área de directivas  |Nombre de directiva principal o secundaria |Nombre de la política de educación superior  |
|---------|---------|---------|
|Directiva de equipo    |Global (valor predeterminado para toda la organización)         |Global (valor predeterminado para toda la organización)           |
|Directiva de reuniones    |Global (valor predeterminado para toda la organización)           |Global (valor predeterminado para toda la organización)           |
|Directiva de eventos en directo     |Global (valor predeterminado para toda la organización)          |  Global (valor predeterminado para toda la organización)          |
|Directiva de configuración de la aplicación     |Global (valor predeterminado para toda la organización)           |Global (valor predeterminado para toda la organización)           |
|Directiva de permisos de aplicaciones    |Global (valor predeterminado para toda la organización)           |Global (valor predeterminado para toda la organización)           |
|Directiva de mensajería     |Global (valor predeterminado para toda la organización)           |Global (valor predeterminado para toda la organización)           |
|Directiva de llamadas    |Global (valor predeterminado para toda la organización)           |Global (valor predeterminado para toda la organización)           |

#### <a name="educators-and-staff"></a>[**Educadores y personal**](#tab/educators/)

|Área de directivas  |Nombre de directiva principal o secundaria |Nombre de la política de educación superior |
|---------|---------|---------|
|Directiva de equipo   |Educadores y personal primarios o secundarios         |Educadores y personal de educación superior         |
|Directiva de reuniones    |Formadores primarios o secundarios y personal de la reunión         |Educadores y profesores de educación superior         |
|Directiva de eventos en directo   | Formadores primarios o secundarios y personal de eventos en vivo         |Educadores de educación superior y eventos en vivo         |
|Directiva de mensajería    |Educadores primarios o secundarios y mensajería de personal         | Educadores de educación superior y mensajería de personal         |
|Directiva de llamadas    |Educadores primarios o secundarios y llamadas de personal         |Educadores de educación superior y llamadas al personal         |

* * *

### <a name="policy-settings"></a>Configuración de la Directiva

A continuación se muestra un resumen de la configuración aplicada por el Asistente para cada área de directiva.

#### <a name="students"></a>[**Pida**](#tab/student-settings/)

A continuación se ofrece una lista de las definiciones de directiva globales (predeterminada para toda la organización) ajustadas por el asistente y aplicadas a los alumnos.

|Área de directivas |Área Secundaria  |Configuración de Directiva  |Principal o secundario |Educación superior |
|---------|---------|---------|---------|---------|
|Directiva de equipo   |         |Crear canales privados         |Desactivado       |Activado|
|Directiva de reuniones    |General         |Permitir reunirse ahora en los canales         |Desactivado      |Activado|
|  |        |Permitir el complemento de Outlook         |Desactivado       |Activado|
|  |        |Permitir programación de reuniones de canal        |Desactivado      |Activado|
|  |        |Permitir la programación de reuniones privadas       |Desactivado      |Activado|
|  |Audio & vídeo        |Permitir la transcripción        |Activado       |Activado|
|  |        |Permitir la grabación en la nube         |Desactivado      |Activado|
|  |        |Modo para audio IP       |Audio entrante y saliente habilitado        |Audio entrante y saliente habilitado|
|  |        |Modo para video IP         |Video entrante y saliente habilitado     |Video entrante y saliente habilitado|
|  |       |Permitir vídeo IP         |Activado         |Activado|
|  |       |Permitir transmisión por secuencias de NDI         |Desactivado         |Desactivado|
|  |       |Velocidad de bits multimedia (KB)         |50 000         |50 000|
|  |Uso compartido de contenido       |Modo de uso compartido de pantalla         |Pantalla completa         |Pantalla completa|
|  |       |Permitir que un participante pueda ceder o solicitar el control         |Activado         |Activado|
|  |       |Permitir que un participante externo pueda ceder o solicitar el control         |Activado         |Activado|
|  |       |Permitir el uso compartido de PowerPoint        |Activado         |Activado|
|  |       |Permitir pizarra         |Activado         |Activado|
|  |       |Permitir notas compartidas         |Activado        |Activado|
|  |Participantes & invitados       |Permitir a personas anónimas iniciar una reunión       |Desactivado         |Activado|
|  |       |Roles que tienen derechos de moderador en las reuniones        |EveryoneUserOverride         |EveryoneUserOverride|
|  |       |Admitir automáticamente personas        |EveryoneInCompany|EveryoneInCompany|
|  |       |Permitir que los usuarios de acceso telefónico omitan la sala de recepción        |Desactivado         |Desactivado|
|  |       |Permitir reunirse ahora en reuniones privadas        |Desactivado         |Activado|
|  |       |Habilitar títulos en vivo       |Deshabilitado pero el usuario puede invalidar         |Deshabilitado pero el usuario puede invalidar|
|  |       |Permitir la conversación en reuniones         |Activado         |Activado|
|  |Modo filtros de vídeo       |VideoFiltersMode         |BlurandDefaultBackgrounds|AllFilters|
|  |Informe de asistencia a reuniones       |AllowEngagementReport         |Desactivado         |Activado|
|Directiva de eventos en directo  |       |Permitir la programación         |Desactivado         |Desactivado|
|  |       |Permitir la transcripción para los asistentes          |Activado       |Activado|
|  |       |Quién puede unirse a eventos en directo programados        |Todas las personas en la organización        |Todas las personas en la organización|
|  |       |Quién puede grabar un evento         |Constantemente         |Constantemente|
|Directiva de mensajería  |       |Los propietarios pueden eliminar los mensajes enviados         |Desactivado|Activado|
|  |       |Eliminar mensajes enviados         |Desactivado         |Activado|
|  |       |Editar los mensajes enviados         |Desactivado         |Activado|
|  |       |Confirmaciones de lectura         |Controlado por el usuario         |Controlado por el usuario|
|  |       |Chat         |Desactivado         |Activado|
|  |       |Usar imágenes giphy en conversaciones         |Desactivado         |Activado|
|  |       |Clasificación de contenido de Giphy         |Estricto        |Estricto|
|  |       |Usar memes en las conversaciones         |Activado         |Activado|
|  |       |Usar adhesivos en las conversaciones         |Activado         |Activado|
|  |       |Permitir vistas previas de direcciones URL        |Activado         |Activado|
|  |       |Traducir mensajes         |Activado         |Activado|
|  |       |Permitir el lector inmersivo para ver mensajes        |Activado      |Activado|
|  |       |Enviar mensajes urgentes con notificaciones prioritarias  |Desactivado         |Activado|
|  |       |Crear mensajes de voz         |Permitido en chats y canales         |Permitido en chats y canales|
|  |       |En dispositivos móviles, Mostrar canales favoritos por encima de los chats recientes     |Habilitado         |Habilitado|
|  |       |Quitar usuarios de chats grupales         |Desactivado         |Activado|
|  |       |Respuestas sugeridas         |Activado         |Activado|
|Directiva de permisos de aplicaciones  |       |Aplicaciones de Microsoft         |Bloquear aplicaciones específicas y permitir a todos los demás > walkie talkie bloqueado         |Permitir todas las aplicaciones|
|  |       |Aplicaciones de terceros         |Permitir todas las aplicaciones         |Permitir todas las aplicaciones|
|  |       |Aplicaciones personalizadas         |Permitir todas las aplicaciones         |Permitir todas las aplicaciones|
|Directiva de configuración de la aplicación  |           |Cargar aplicaciones personalizadas           |Desactivado         |Desactivado|
|  |       |Permitir el anclaje de usuarios |Activado         |Activado|
|  |       |Aplicaciones instaladas         |Ninguna         |Ninguna|
|  |       |Aplicaciones ancladas         |Actividad, calendario, equipos         |Actividad, chats, equipos, calendario, llamadas, archivo
|Directiva de llamadas  |       |Realizar llamadas privadas         |Desactivado        |Activado|
|  |       |Desvío de llamadas y llamadas simultáneas a las personas de su organización         |Desactivado         |Activado|
|  |       |Desvío de llamadas y llamadas simultáneas a números de teléfono externos         |Desactivado         |Activado|
|  |       |El buzón de voz está disponible para enrutar llamadas entrantes         |Controlado por el usuario         |Controlado por el usuario|
|  |       |Las llamadas entrantes se pueden enrutar a grupos de llamadas         |Desactivado        |Activado|
|  |       |Permitir la delegación de llamadas entrantes y salientes         |Desactivado         |Activado|
|  |       |Evitar la omisión de peajes y enviar llamadas a través de la RTC        |Desactivado         |Desactivado|
|  |       |El ocupado en ocupado está disponible cuando se encuentra en una llamada         |Desactivado         |Desactivado|
|  |       |Permitir llamadas RTC en Web         |Desactivado         |Activado|

#### <a name="educators-and-staff"></a>[**Educadores y personal**](#tab/educator-settings/)

Esta es una lista de las definiciones de directiva personalizada asignadas al educador y al grupo de personal que usted elige en el asistente.  

|Área de directivas |Área Secundaria  |Configuración de Directiva  |Principal o secundario |Educación superior |
|---------|---------|---------|---------|---------|
|Directiva de equipo   |         |Crear canales privados         |Activado       |Activado|
|Directiva de reuniones    |General         |Permitir reunirse ahora en los canales         |Activado      |Activado|
|  |        |Permitir el complemento de Outlook         |Activado       |Activado|
|  |        |Permitir programación de reuniones de canal        |Activado      |Activado|
|  |        |Permitir la programación de reuniones privadas       |Activado      |Activado|
|  |Audio & vídeo        |Permitir la transcripción        |Activado       |Activado|
|  |        |Permitir la grabación en la nube         |Activado      |Activado|
|  |        |Modo para audio IP       |Audio entrante y saliente habilitado        |Audio entrante y saliente habilitado|
|  |        |Modo para video IP         |Video entrante y saliente habilitado     |Video entrante y saliente habilitado|
|  |       |Permitir vídeo IP         |Activado         |Activado|
|  |       |Permitir transmisión por secuencias de NDI         |Desactivado         |Desactivado|
|  |       |Velocidad de bits multimedia (KB)         |50 000         |50 000|
|  |Uso compartido de contenido       |Modo de uso compartido de pantalla         |Pantalla completa         |Pantalla completa|
|  |       |Permitir que un participante pueda ceder o solicitar el control         |Activado         |Activado|
|  |       |Permitir que un participante externo pueda ceder o solicitar el control         |Activado         |Activado|
|  |       |Permitir el uso compartido de PowerPoint        |Activado         |Activado|
|  |       |Permitir pizarra         |Activado         |Activado|
|  |       |Permitir notas compartidas         |Activado        |Activado|
|  |Participantes & invitados       |Permitir a personas anónimas iniciar una reunión       |Activado        |Activado|
|  |       |Roles que tienen derechos de moderador en las reuniones        |OrganizerOnlyUserOverride         |OrganizerOnlyUserOverride|
|  |       |Admitir automáticamente personas        |Organizadorsolo|Organizadorsolo|
|  |       |Permitir que los usuarios de acceso telefónico omitan la sala de recepción        |Desactivado         |Desactivado|
|  |       |Permitir reunirse ahora en reuniones privadas        |Activado         |Activado|
|  |       |Habilitar títulos en vivo       |Deshabilitado pero el usuario puede invalidar         |Deshabilitado pero el usuario puede invalidar|
|  |       |Permitir la conversación en reuniones         |Activado         |Activado|
|  |Modo filtros de vídeo       |VideoFiltersMode         |AllFilters|AllFilters|
|  |Informe de asistencia a reuniones       |AllowEngagementReport         |Activado         |Activado|
|Directiva de eventos en directo  |       |Permitir la programación         |Activado         |Activado|
|  |       |Permitir la transcripción para los asistentes          |Activado       |Activado|
|  |       |Quién puede unirse a eventos en directo programados        |Todas las personas en la organización        |Todas las personas en la organización|
|  |       |Quién puede grabar un evento         |Grabar siempre         |Grabar siempre|
|Directiva de mensajería  |       |Los propietarios pueden eliminar los mensajes enviados         |Activado|Activado|
|  |       |Eliminar mensajes enviados         |Activado         |Activado|
|  |       |Editar los mensajes enviados         |Activado         |Activado|
|  |       |Confirmaciones de lectura         |Controlado por el usuario         |Controlado por el usuario|
|  |       |Chat         |Activado         |Activado
|  |       |Usar imágenes giphy en conversaciones         |Activado        |Activado|
|  |       |Clasificación de contenido de Giphy         |Estricto        |Estricto|
|  |       |Usar memes en las conversaciones         |Activado         |Activado|
|  |       |Usar adhesivos en las conversaciones         |Activado         |Activado|
|  |       |Permitir vistas previas de direcciones URL        |Activado         |Activado|
|  |       |Traducir mensajes         |Activado         |Activado|
|  |       |Permitir el lector inmersivo para ver mensajes        |Activado      |Activado|
|  |       |Enviar mensajes urgentes con notificaciones prioritarias  |Activado         |Activado|
|  |       |Crear mensajes de voz         |Permitido en chats y canales         |Permitido en chats y canales|
|  |       |En dispositivos móviles, Mostrar canales favoritos por encima de los chats recientes     |Habilitado         |Habilitado|
|  |       |Quitar usuarios de chats grupales         |Activado        |Activado|
|  |       |Respuestas sugeridas         |Activado         |Activado|
|Directiva de llamadas  |       |Realizar llamadas privadas         |Activado       |Activado|
|  |       |Desvío de llamadas y llamadas simultáneas a las personas de su organización         |Activado        |Activado|
|  |       |Desvío de llamadas y llamadas simultáneas a números de teléfono externos         |Activado        |Activado|
|  |       |El buzón de voz está disponible para enrutar llamadas entrantes         |Controlado por el usuario         |Controlado por el usuario|
|  |       |Las llamadas entrantes se pueden enrutar a grupos de llamadas         |Activado        |Activado|
|  |       |Permitir la delegación de llamadas entrantes y salientes         |Activado         |Activado|
|  |       |Evitar la omisión de peajes y enviar llamadas a través de la RTC        |Desactivado         |Desactivado|
|  |       |El ocupado en ocupado está disponible cuando se encuentra en una llamada         |Desactivado         |Desactivado|
|  |       |Permitir llamadas RTC en Web         |Activado      |Activado|

* * *

## <a name="related-topics"></a>Temas relacionados

- [Directivas y paquetes de directivas de Teams para el ámbito educativo](policy-packages-edu.md)
- [Asignar directivas a grandes conjuntos de usuarios de la escuela](batch-group-policy-assignment-edu.md)
- [Proteger a los alumnos al utilizar Teams para el aprendizaje a distancia](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
