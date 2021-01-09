---
title: Asistente para directivas de Teams para el sector educativo para aplicar fácilmente directivas de aprendizaje seguro
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre cómo usar el asistente para directivas de Teams para el educación para aplicar fácilmente directivas para que los alumnos y profesores mantengan seguro su entorno de aprendizaje.
f1keywords: ''
ms.openlocfilehash: 1ea7fb684bce3d59063f1a258d0db37fb75a4681
ms.sourcegitcommit: 95b85926d67cbf3159f58d9083d5813cc29074f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790424"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Usar el Asistente para directivas de Teams para el aprendizaje para aplicar fácilmente directivas para un entorno de aprendizaje seguro

## <a name="overview"></a>Descripción general

El Asistente para directivas de Microsoft Teams para el sector educativo simplifica la administración de las directivas para los alumnos y profesores. Úselo para aplicar rápida y fácilmente el conjunto de directivas más importante relevante para crear una experiencia de aprendizaje segura y productiva.

Las directivas de Teams le permiten controlar el comportamiento de Teams en su entorno y qué características están disponibles para los usuarios. Por ejemplo, hay directivas de llamadas, directivas de reuniones y directivas de mensajería, entre otras, y cada área de directiva se puede personalizar para satisfacer las necesidades de su organización.

Para mantener un entorno de aprendizaje seguro y centrado, es importante establecer directivas para controlar lo que los alumnos pueden hacer en Teams. Por ejemplo, puede usar directivas para controlar quién puede usar el chat privado y las llamadas privadas, quién puede programar reuniones y qué tipos de contenido se pueden compartir. También puede usar directivas para activar las características de Teams que enriquecen la experiencia de aprendizaje.

Es necesario ajustar las directivas tanto para alumnos como para profesores para mantener segura la experiencia de aprendizaje. Las directivas para los alumnos deben ser más restrictivas para reducir el riesgo de recibir niveles de acceso inadecuados. Los formadores y el personal necesitan un conjunto independiente de directivas que pueden ser más permisivas para que puedan tener éxito. Por ejemplo, permita que los profesores programe reuniones y restrinja que los alumnos lo hacen.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de pantalla del asistente":::

Este artículo le guiará por la ejecución del asistente.

> [!IMPORTANT]
> Las directivas que aplique el asistente se cumplirán con las necesidades de la mayoría de los clientes de Teams para el sector educativo. El asistente ajusta la definición global (predeterminada para toda la organización) de un conjunto principal de directivas con opciones de configuración que se recomiendan para la seguridad de los alumnos y se aplica a los alumnos. El asistente también crea y asigna un conjunto de directivas personalizadas a profesores y docentes. La mayoría de los clientes de Teams para el sector educativo no necesitarán usar otros métodos de asignación de directivas después de ejecutar este asistente. Use otros métodos de asignación *de directivas* solo si quiere crear y administrar manualmente directivas para los alumnos, los educadores y el personal.

## <a name="teams-for-education-policy-wizard"></a>Asistente para directivas de Teams para el sector educativo

<a name="polwiz_intro"> </a>

El asistente aplica un conjunto de definiciones de directiva básicas a los alumnos y un conjunto independiente de definiciones de directiva básicas para los formadores y el personal, con una configuración adecuada para cada uno. Esto es lo que ocurre al ejecutar el asistente.

El asistente configura directivas según el tipo de institución educativa **(educación primaria, secundaria** **o superior).** Seleccione el tipo de institución y el asistente podrá hacer lo siguiente:

- **Alumnos:** el asistente ajusta la definición de directiva global (predeterminada para toda la organización) de cada área de directiva cubierta por el asistente con una nueva configuración predeterminada adecuada para mantener a sus alumnos seguros. Esto garantiza que los alumnos actuales y todos los nuevos alumnos obtengan el conjunto de directivas más restrictivo.
- **Formadores y personal:** el asistente crea un conjunto de definiciones de directiva personalizadas para cada área de directiva cubierta por el asistente con una configuración adaptada a las necesidades de los formadores y el personal. Después, asigna las definiciones de directiva al grupo de formadores y docentes que elija. De esta forma, los profesores y el personal obtienen un conjunto más permisivo de directivas para que puedan tener éxito.

Solo necesita ejecutar el asistente una vez. Los alumnos nuevos obtienen automáticamente las definiciones de directiva global (predeterminada para toda la organización) aplicadas por el asistente y a los nuevos docentes que agregue al grupo seleccionado se les asignarán automáticamente las directivas personalizadas.

> [!NOTE]
> Vea [las directivas aplicadas por el asistente](#policies-applied-by-the-wizard) para obtener una lista detallada de las definiciones de directiva que ha aplicado el asistente.

Empecemos.

## <a name="run-the-wizard"></a>Ejecutar el asistente

<a name="polwiz_run"> </a>

Siga estos pasos para ejecutar el asistente.

1. Si es la primera vez que trabaja en Teams, el asistente se inicia automáticamente. En caso contrario, puede iniciar el asistente en cualquier momento desde el panel. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya al panel **y,** **a** continuación, en el mosaico Configuración fácil de directivas de un entorno de aprendizaje seguro, seleccione **Configuración rápida.**

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Captura de pantalla del asistente en el panel":::

2. Selecciona el tipo de institución educativa **(educación primaria,** secundaria o **superior)** y, a continuación, **selecciona Siguiente.**

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de pantalla de la página del asistente para seleccionar el tipo de institución":::

3. Busque y seleccione un grupo que contenga a sus profesores y docentes y, a continuación, seleccione **Siguiente.** Si aún no tiene ningún grupo configurado para los profesores y el personal, cree un grupo y vuelva [a](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)ejecutar el asistente. <br/><br/>Actualmente, solo puede seleccionar un grupo. A los formadores y al personal del grupo que seleccione se les asignará un conjunto de directivas personalizadas adaptadas [a](#policies-applied-by-the-wizard) sus necesidades. Recuerde que este conjunto de directivas es independiente de las directivas aplicadas a los alumnos.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Captura de pantalla de la página del asistente para seleccionar un educador y un grupo de docentes":::

4. Revise las selecciones.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Captura de pantalla de la página del asistente para revisar selecciones":::

5. Seleccione **Aplicar** para aplicar los cambios. Esto puede tardar unos minutos en completarse.<br/><br/>Las definiciones de directiva global (predeterminada para toda la organización) se aplican inmediatamente a los alumnos. Para los formadores y el personal, puede que las directivas personalizadas tarden unas horas en asignarse a cada miembro del grupo que haya seleccionado, según el tamaño del grupo. Esto ocurre en segundo plano, después de completar correctamente este paso.
6. Está de camino, pero aún no ha terminado. Hay algunas cosas más que tener en cuenta. A continuación, consulte los pasos de la sección Qué hacer después de [ejecutar la sección](#what-to-do-after-running-the-wizard) del asistente de este artículo.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Captura de pantalla de la página del asistente para los pasos siguientes":::

## <a name="what-to-do-after-running-the-wizard"></a>Qué hacer después de ejecutar el asistente

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Paso 1: Quitar las asignaciones de directivas existentes que entren en conflicto con las directivas aplicadas por el asistente

> [!IMPORTANT]
> **Complete este paso solo si tiene directivas existentes asignadas a alumnos, educadores y personal *antes* de que ejecutó el asistente.** Si es nuevo en Teams y no tiene directivas existentes distintas de las directivas creadas por el asistente, omita este paso y vaya al paso 2.

En Teams, para un área de directiva determinada, una directiva se puede aplicar a un usuario de las siguientes maneras:

- Asignación directa al usuario
- Asignación a un grupo del que el usuario es miembro
- Si el usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se ha asignado una directiva, el usuario obtiene automáticamente la directiva Global (predeterminada para toda la organización).

Si hay más de una de estas asignaciones de directiva para un usuario, Teams usa el siguiente orden para determinar qué asignación de directiva tiene efecto. Para obtener más información, vea [¿Qué directiva tiene prioridad?](assign-policies.md#which-policy-takes-precedence) y [reglas de prioridad.](assign-policies.md#precedence-rules)

|Asignaciones de directivas de un usuario|Directiva que entra en vigor |
|---------|---------|
|Directiva asignada al grupo: No<br/>Directiva asignada directamente al usuario: No    |Directiva predeterminada global (para toda la organización)      |
|Directiva asignada al grupo: No<br/>Directiva asignada directamente al usuario: Sí    |Directiva asignada directamente al usuario         |
|Directiva asignada al grupo: Sí<br/>Directiva asignada directamente al usuario: Sí     |Directiva asignada directamente al usuario         |
|Directiva asignada al grupo: Sí<br/>Directiva asignada directamente al usuario: No     |Directiva asignada al grupo<br/><br/>Si el usuario es miembro de varios grupos y a cada grupo se le asigna una directiva de la misma área de directiva, se hace efectiva la directiva que tenga la clasificación de asignación [de](assign-policies.md#group-assignment-ranking) grupo más alta.       |

Debido a este orden, las directivas creadas por el asistente no se verán efectivas si un usuario tiene asignaciones directas o asignaciones de grupo existentes. Esto significa que tendrá que quitar las asignaciones de directiva existentes del usuario para que la directiva aplicada por el asistente suba a efecto.

Para cada [área de directiva aplicada por el asistente,](#policies-applied-by-the-wizard)haga lo siguiente:

- Quite todas las asignaciones directas y tareas de grupo existentes de los alumnos para que la definición de directiva Global (predeterminada para toda la organización) aplicada por el asistente se haga efectiva.
- Quite las asignaciones directas en conflicto para los profesores y el personal para que la definición de directiva personalizada creada por el asistente suba a efecto. Use la tabla anterior para determinar los escenarios que le aplican. <br/><br/>Tenga en cuenta que el asistente asigna directivas [a](assign-policies.md#group-assignment-ranking) los profesores y al grupo de docentes con una clasificación de asignación de grupo de 1, que es la clasificación más alta. Si los profesores y el grupo de docentes tienen asignada una directiva de la misma área de directiva, esa directiva existente se mueve a una posición más baja y la directiva asignada por el asistente entra en vigor.

[Obtenga más](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) información sobre cómo quitar directivas que estén asignadas directamente a los usuarios.

Por ejemplo, asignó una directiva de reunión directamente a los profesores y los alumnos tienen la directiva de reunión global (predeterminada para toda la organización). En este escenario, quite la directiva de reunión que asignó directamente a los profesores para que se haga efectiva la definición de directiva personalizada para la directiva de reunión creada por el asistente. No tiene que hacer nada con la directiva de reunión global (predeterminada para toda la organización) existente para los alumnos porque ninguna otra directiva de reunión entra en conflicto con ella.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Paso 2: Comprobar si hay medidas adicionales que puede tomar para la seguridad de los alumnos

El asistente ajusta y aplica automáticamente [estas directivas.](#policies-applied-by-the-wizard) Hay algunas medidas adicionales que quizás quiera tomar en función de las necesidades de su institución para mantenerse seguro.

Vea [Mantener a los alumnos seguros mientras usan Teams para el aprendizaje a distancia](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) para obtener recomendaciones de seguridad adicionales.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Paso 3: Buscar actualizaciones de directivas en el Centro de mensajes

Actualmente, el asistente aplica nuestras directivas recomendadas al ejecutarlo. Es importante saber que, a medida que las nuevas directivas estén disponibles en Teams, el asistente no agregará automáticamente la configuración global (predeterminada para toda la organización) para la seguridad de los alumnos. Esta función estará disponible en una versión futura.

Hasta que esta función esté disponible, consulte el Centro de mensajes [(en](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) el Centro de administración de Microsoft 365) con frecuencia para mantenerse al día sobre las nuevas directivas y la configuración de directivas en Teams. Cuando haya nuevas características disponibles, es posible que tenga que actualizar manualmente las directivas para mantener seguro su entorno de aprendizaje.

## <a name="make-changes-in-the-wizard"></a>Realizar cambios en el asistente

<a name="polwiz_change"> </a>

Si necesita realizar cambios después de ejecutar el asistente, puede volver a ejecutarlo y cambiar las selecciones.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya al panel **y,** **a** continuación, en la configuración de directivas sencilla para un icono de entorno de aprendizaje seguro, **seleccione Cambiar.**
2. Desde aquí, continúe por cada página del asistente para realizar los cambios. Puede cambiar el tipo de institución, el grupo de educadores y personal al que desea asignar directivas o ambos.

En la tabla siguiente se resume lo que ocurre cuando se realiza un cambio en el asistente.

|Tipo de cambio  |Comportamiento de la directiva  |
|---------|---------|
|Cambiar el tipo de institución educativa y los profesores y el grupo de docentes    |<ul><li>**Alumnos:** las definiciones de directivas globales (predeterminadas para toda la organización) basadas en el nuevo tipo de institución educativa se aplican a los alumnos.</li><li>**Formadores y personal:** se crea y se asigna al nuevo profesor y al grupo de docentes un conjunto de definiciones de directivas personalizadas basadas en el nuevo tipo de institución educativa. Las definiciones de directivas personalizadas anteriores se quitan de los profesores y el grupo de personal anteriores.</li></ul>    |
|Cambiar solo el tipo de institución educativa    |<ul><li>**Alumnos:** las definiciones de directivas globales (predeterminadas para toda la organización) basadas en el nuevo tipo de institución educativa se aplican a los alumnos.</li><li>**Formadores y personal:** se crea y asigna a los profesores y al grupo de docentes un conjunto de definiciones de directivas personalizadas basadas en el nuevo tipo de institución educativa. Las definiciones de directivas personalizadas creadas para el tipo de institución educativa anterior se quitan de los profesores y del grupo de personal.</li></ul>         |
|Cambiar solo los profesores y el grupo de docentes   |<ul><li>**Alumnos:** no hay ningún cambio en las definiciones de directiva globales (predeterminadas para toda la organización) aplicadas a los alumnos.</li><li>**Formadores y personal:** las definiciones de directiva personalizadas se asignan a los nuevos formadores y al grupo de personal y se quitan de los profesores y el grupo de personal anteriores.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Directivas aplicadas por el asistente

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Áreas de directiva

Estas son las áreas de directiva y los nombres de directiva correspondientes que trata el asistente. Para buscar estas directivas, vaya al Centro de administración de Microsoft Teams y, a continuación, en el panel de navegación izquierdo, vaya a cada página del área de directiva.

#### <a name="students"></a>[**Alumnos**](#tab/students/)

|Área de directiva  |Nombre de directiva principal o secundaria |Nombre de la directiva de educación superior  |
|---------|---------|---------|
|Directiva de equipo    |Global (predeterminado para toda la organización)         |Global (predeterminado para toda la organización)           |
|Directiva de reuniones    |Global (predeterminado para toda la organización)           |Global (predeterminado para toda la organización)           |
|Directiva de eventos en directo     |Global (predeterminado para toda la organización)          |  Global (predeterminado para toda la organización)          |
|Directiva de configuración de aplicaciones     |Global (predeterminado para toda la organización)           |Global (predeterminado para toda la organización)           |
|Directiva de permisos de aplicación    |Global (predeterminado para toda la organización)           |Global (predeterminado para toda la organización)           |
|Directiva de mensajería     |Global (predeterminado para toda la organización)           |Global (predeterminado para toda la organización)           |
|Directiva de llamadas    |Global (predeterminado para toda la organización)           |Global (predeterminado para toda la organización)           |

#### <a name="educators-and-staff"></a>[**Educadores y personal**](#tab/educators/)

|Área de directiva  |Nombre de directiva principal o secundaria |Nombre de la directiva de educación superior |
|---------|---------|---------|
|Directiva de equipo   |Profesores y docentes primarios o secundarios: equipos         |Profesores y docentes de educación superior: Equipos         |
|Directiva de reuniones    |Profesores y docentes primarios o secundarios: reunión         |Profesores de educación superior y personal: reunión         |
|Directiva de eventos en directo   | Profesores y docentes primarios o secundarios: eventos en directo         |Profesores y docentes de educación superior: eventos en directo         |
|Directiva de mensajería    |Profesores y docentes primarios o secundarios: mensajería         | Profesores de educación superior y personal: mensajería         |
|Directiva de llamadas    |Profesores y docentes primarios o secundarios: llamadas         |Profesores de educación superior y personal: llamadas         |

* * *

### <a name="policy-settings"></a>Configuración de la directiva

Este es un resumen de la configuración aplicada por el asistente para cada área de directiva.

#### <a name="students"></a>[**Alumnos**](#tab/student-settings/)

Aquí tiene una lista de las definiciones de directivas globales (predeterminadas para toda la organización) ajustadas por el asistente y aplicadas a los alumnos.

|Área de directiva |Subsádes  |Configuración de directiva  |Principal o secundario |Educación superior |
|---------|---------|---------|---------|---------|
|Directiva de equipo   |         |Crear canales privados         |Desactivado       |Activado|
|Directiva de reuniones    |General         |Permitir la opción Reunirse ahora en canales         |Desactivado      |Activado|
|  |        |Permitir el complemento de Outlook         |Desactivado       |Activado|
|  |        |Permitir la programación de reuniones de canal        |Desactivado      |Activado|
|  |        |Permitir la programación de reuniones privadas       |Desactivado      |Activado|
|  |Audio & vídeo        |Permitir transcripción        |Activado       |Activado|
|  |        |Permitir la grabación en la nube         |Desactivado      |Activado|
|  |        |Modo de audio IP       |Audio entrante y saliente activado        |Audio entrante y saliente activado|
|  |        |Modo de vídeo IP         |Vídeo entrante y saliente activado     |Vídeo entrante y saliente activado|
|  |       |Permitir vídeo IP         |Activado         |Activado|
|  |       |Permitir el streaming NDI         |Desactivado         |Desactivado|
|  |       |Velocidad de bits multimedia (kb/s)         |50 000         |50 000|
|  |Uso compartido de contenido       |Modo de uso compartido de pantalla         |Toda la pantalla         |Toda la pantalla|
|  |       |Permitir a un participante ceder o solicitar el control         |Activado         |Activado|
|  |       |Permitir a un participante externo ceder o solicitar el control         |Activado         |Activado|
|  |       |Permitir uso compartido de PowerPoint        |Activado         |Activado|
|  |       |Permitir pizarra         |Activado         |Activado|
|  |       |Permitir notas compartidas         |Activado        |Activado|
|  |Participantes & invitados       |Permitir que los usuarios anónimos inicien una reunión       |Desactivado         |Activado|
|  |       |Roles que tienen derechos de moderador en las reuniones        |EveryoneUserOverride         |EveryoneUserOverride|
|  |       |Admitir automáticamente usuarios        |EveryoneInCompany|EveryoneInCompany|
|  |       |Permitir que los usuarios de acceso telefónico omitan la sala de espera        |Desactivado         |Desactivado|
|  |       |Permitir la opción Reunirse ahora en las reuniones privadas        |Desactivado         |Activado|
|  |       |Activar subtítulos en directo       |Deshabilitado, pero el usuario puede invalidar         |Deshabilitado, pero el usuario puede invalidar|
|  |       |Permitir el chat en las reuniones         |Activado         |Activado|
|Directiva de eventos en directo  |       |Permitir la programación         |Desactivado         |Desactivado|
|  |       |Permitir la transcripción para los asistentes          |Activado       |Activado|
|  |       |Quién puede unirse a eventos en directo programados        |Todos los usuarios de la organización        |Todos los usuarios de la organización|
|  |       |Quién puede grabar un evento         |Siempre         |Siempre|
|Directiva de mensajería  |       |Los propietarios pueden eliminar los mensajes enviados         |Desactivado|Activado|
|  |       |Eliminar mensajes enviados         |Desactivado         |Activado|
|  |       |Editar los mensajes enviados         |Desactivado         |Activado|
|  |       |Confirmaciones de lectura         |Usuario controlado         |Usuario controlado|
|  |       |Chat         |Desactivado         |Activado|
|  |       |Usar Imágenes de Giphy en conversaciones         |Desactivado         |Activado|
|  |       |Clasificación de contenido de Giphy         |Estricto        |Estricto|
|  |       |Usar memes en conversaciones         |Activado         |Activado|
|  |       |Usar adhesivos en conversaciones         |Activado         |Activado|
|  |       |Permitir vistas previas de URL        |Activado         |Activado|
|  |       |Traducir mensajes         |Activado         |Activado|
|  |       |Permitir que el lector inmersivo pueda ver mensajes        |Activado      |Activado|
|  |       |Enviar mensajes urgentes con notificaciones de prioridad  |Desactivado         |Activado|
|  |       |Crear mensajes de voz         |Permitido en chats y canales         |Permitido en chats y canales|
|  |       |En dispositivos móviles, mostrar canales favoritos encima de chats recientes     |Habilitado         |Habilitado|
|  |       |Quitar usuarios de chats grupales         |Desactivado         |Activado|
|Directiva de permisos de aplicación  |       |Aplicaciones de Microsoft         |Bloquear aplicaciones específicas y permitir que todos los demás > Walkie-talkie bloqueado         |Permitir todas las aplicaciones|
|  |       |Aplicaciones de terceros         |Permitir todas las aplicaciones         |Permitir todas las aplicaciones|
|  |       |Aplicaciones personalizadas         |Permitir todas las aplicaciones         |Permitir todas las aplicaciones|
|Directiva de configuración de aplicaciones  |           |Cargar aplicaciones personalizadas           |Desactivado         |Desactivado|
|  |       |Permitir anclar usuarios |Activado         |Activado|
|  |       |Aplicaciones instaladas         |Ninguna         |Ninguna|
|  |       |Aplicaciones ancladas         |Actividad, Calendario, Teams         |Actividad, chats, equipos, calendario, llamadas, archivo
|Directiva de llamadas  |       |Realizar llamadas privadas         |Desactivado        |Activado|
|  |       |Call forwarding and simultaneousing to people in your organization         |Desactivado         |Activado|
|  |       |Reenvío de llamadas y llamadas simultáneas a números de teléfono externos         |Desactivado         |Activado|
|  |       |El correo de voz está disponible para enrutar llamadas entrantes         |Usuario controlado         |Usuario controlado|
|  |       |Las llamadas entrantes se pueden enrutar a grupos de llamadas         |Desactivado        |Activado|
|  |       |Permitir la delegación para llamadas entrantes y salientes         |Desactivado         |Activado|
|  |       |Evitar la omisión de pago y enviar llamadas a través de RTC        |Desactivado         |Desactivado|
|  |       |Ocupado está disponible durante una llamada         |Desactivado         |Desactivado|
|  |       |Permitir llamadas RTC web         |Desactivado         |Activado|

#### <a name="educators-and-staff"></a>[**Educadores y personal**](#tab/educator-settings/)

Aquí tiene una lista de las definiciones de directiva personalizadas asignadas a los profesores y al grupo de docentes que elija en el asistente.  

|Área de directiva |Subsádes  |Configuración de directiva  |Principal o secundario |Educación superior |
|---------|---------|---------|---------|---------|
|Directiva de equipo   |         |Crear canales privados         |Activado       |Activado|
|Directiva de reuniones    |General         |Permitir la opción Reunirse ahora en canales         |Activado      |Activado|
|  |        |Permitir el complemento de Outlook         |Activado       |Activado|
|  |        |Permitir la programación de reuniones de canal        |Activado      |Activado|
|  |        |Permitir la programación de reuniones privadas       |Activado      |Activado|
|  |Audio & vídeo        |Permitir transcripción        |Activado       |Activado|
|  |        |Permitir la grabación en la nube         |Activado      |Activado|
|  |        |Modo de audio IP       |Audio entrante y saliente activado        |Audio entrante y saliente activado|
|  |        |Modo de vídeo IP         |Vídeo entrante y saliente activado     |Vídeo entrante y saliente activado|
|  |       |Permitir vídeo IP         |Activado         |Activado|
|  |       |Permitir el streaming NDI         |Desactivado         |Desactivado|
|  |       |Velocidad de bits multimedia (kb/s)         |50 000         |50 000|
|  |Uso compartido de contenido       |Modo de uso compartido de pantalla         |Toda la pantalla         |Toda la pantalla|
|  |       |Permitir a un participante ceder o solicitar el control         |Activado         |Activado|
|  |       |Permitir a un participante externo ceder o solicitar el control         |Activado         |Activado|
|  |       |Permitir uso compartido de PowerPoint        |Activado         |Activado|
|  |       |Permitir pizarra         |Activado         |Activado|
|  |       |Permitir notas compartidas         |Activado        |Activado|
|  |Participantes & invitados       |Permitir que los usuarios anónimos inicien una reunión       |Activado        |Activado|
|  |       |Roles que tienen derechos de moderador en las reuniones        |OrganizerOnlyUserOverride         |OrganizerOnlyUserOverride|
|  |       |Admitir automáticamente usuarios        |OrganizerOnly|OrganizerOnly|
|  |       |Permitir que los usuarios de acceso telefónico omitan la sala de espera        |Desactivado         |Desactivado|
|  |       |Permitir la opción Reunirse ahora en las reuniones privadas        |Activado         |Activado|
|  |       |Activar subtítulos en directo       |Deshabilitado, pero el usuario puede invalidar         |Deshabilitado, pero el usuario puede invalidar|
|  |       |Permitir el chat en las reuniones         |Activado         |Activado|
|Directiva de eventos en directo  |       |Permitir la programación         |Activado         |Activado|
|  |       |Permitir la transcripción para los asistentes          |Activado       |Activado|
|  |       |Quién puede unirse a eventos en directo programados        |Todos los usuarios de la organización        |Todos los usuarios de la organización|
|  |       |Quién puede grabar un evento         |Grabar siempre         |Grabar siempre|
|Directiva de mensajería  |       |Los propietarios pueden eliminar los mensajes enviados         |Activado|Activado|
|  |       |Eliminar mensajes enviados         |Activado         |Activado|
|  |       |Editar los mensajes enviados         |Activado         |Activado|
|  |       |Confirmaciones de lectura         |Usuario controlado         |Usuario controlado|
|  |       |Chat         |Activado         |Activado
|  |       |Usar Imágenes de Giphy en conversaciones         |Activado        |Activado|
|  |       |Clasificación de contenido de Giphy         |Estricto        |Estricto|
|  |       |Usar memes en conversaciones         |Activado         |Activado|
|  |       |Usar adhesivos en conversaciones         |Activado         |Activado|
|  |       |Permitir vistas previas de URL        |Activado         |Activado|
|  |       |Traducir mensajes         |Activado         |Activado|
|  |       |Permitir que el lector inmersivo pueda ver mensajes        |Activado      |Activado|
|  |       |Enviar mensajes urgentes con notificaciones de prioridad  |Activado         |Activado|
|  |       |Crear mensajes de voz         |Permitido en chats y canales         |Permitido en chats y canales|
|  |       |En dispositivos móviles, mostrar canales favoritos encima de chats recientes     |Habilitado         |Habilitado|
|  |       |Quitar usuarios de chats grupales         |Activado        |Activado|
|Directiva de llamadas  |       |Realizar llamadas privadas         |Activado       |Activado|
|  |       |Call forwarding and simultaneousing to people in your organization         |Activado        |Activado|
|  |       |Reenvío de llamadas y llamadas simultáneas a números de teléfono externos         |Activado        |Activado|
|  |       |El correo de voz está disponible para enrutar llamadas entrantes         |Usuario controlado         |Usuario controlado|
|  |       |Las llamadas entrantes se pueden enrutar a grupos de llamadas         |Activado        |Activado|
|  |       |Permitir la delegación para llamadas entrantes y salientes         |Activado         |Activado|
|  |       |Evitar la omisión de pago y enviar llamadas a través de RTC        |Desactivado         |Desactivado|
|  |       |Ocupado está disponible durante una llamada         |Desactivado         |Desactivado|
|  |       |Permitir llamadas RTC web         |Activado      |Activado|

* * *

## <a name="related-topics"></a>Temas relacionados

- [Directivas de Teams y paquetes de directivas para el sector educativo](policy-packages-edu.md)
- [Asignar directivas a grandes conjuntos de usuarios de la escuela](batch-group-policy-assignment-edu.md)
- [Mantener a los alumnos seguros mientras usan Teams para el aprendizaje a distancia](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
