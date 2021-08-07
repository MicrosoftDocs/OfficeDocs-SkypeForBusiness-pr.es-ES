---
title: Teams para Educación Asistente para directivas para aplicar fácilmente directivas para un aprendizaje seguro
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
description: Obtenga información sobre cómo usar el Teams para Educación de directivas de aprendizaje para aplicar fácilmente directivas a alumnos y profesores para mantener su entorno de aprendizaje seguro.
f1keywords: ''
ms.openlocfilehash: 2824ed511f1c2f5a5a7389760de9d50559e5da2a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772411"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Use el Asistente Teams para Educación directivas para aplicar fácilmente directivas para un entorno de aprendizaje seguro

## <a name="overview"></a>Información general

El Microsoft Teams para Educación de directivas simplifica la administración de directivas para los alumnos y los profesores. Úsese para aplicar fácilmente y rápidamente el conjunto más importante de directivas relevantes para crear una experiencia de aprendizaje segura y productiva.

Las directivas de Teams le permiten controlar cómo Teams se comporta en su entorno y qué características están disponibles para los usuarios. Por ejemplo, hay directivas de llamadas, directivas de reunión y directivas de mensajería, por nombrar algunas, y cada área de directiva se puede personalizar para satisfacer las necesidades de su organización.

Para mantener un entorno de aprendizaje seguro y centrado, es importante establecer directivas para controlar lo que los alumnos pueden hacer en Teams. Por ejemplo, puede usar directivas para controlar quién puede usar chat privado y llamadas privadas, quién puede programar reuniones y qué tipos de contenido se pueden compartir. También puede usar directivas para activar Teams características que enriquecen la experiencia de aprendizaje.

Las directivas deben ajustarse tanto para los alumnos como para los profesores para mantener la experiencia de aprendizaje segura. Las directivas para los alumnos deben ser más restrictivas para reducir el riesgo de recibir niveles de acceso inadecuados. Los profesores y el personal necesitan un conjunto independiente de directivas que puedan ser más permisivas para que puedan tener éxito. Por ejemplo, permita que los profesores programe reuniones y restrinja a los alumnos que lo hacen.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de pantalla del asistente":::

En este artículo se explica cómo ejecutar el asistente.

> [!IMPORTANT]
> Las directivas aplicadas por el asistente satisfarán las necesidades de la mayoría de Teams para Educación clientes. El asistente ajusta la definición global (predeterminada para toda la organización) de un conjunto principal de directivas con la configuración que se recomienda para la seguridad de los alumnos y se aplica a los alumnos. El asistente también crea y asigna un conjunto de directivas personalizadas a profesores y docentes. La mayoría Teams para Educación clientes no necesitarán usar otros métodos de asignación de directivas después de ejecutar este asistente. Use otros métodos de asignación *de directivas solo* si desea crear y administrar directivas manualmente para los alumnos, los profesores y el personal.

## <a name="teams-for-education-policy-wizard"></a>Teams para Educación Asistente para directivas

<a name="polwiz_intro"> </a>

El asistente aplica un conjunto de definiciones de directiva básicas a los alumnos y un conjunto independiente de definiciones de directiva básicas para los profesores y el personal, con configuraciones adecuadas para cada uno. Esto es lo que ocurre al ejecutar el asistente.

El asistente configura directivas basadas en el tipo de institución educativa **(Educación primaria o secundaria** **o educación superior).** Seleccione el tipo de institución y el asistente haga lo siguiente:

- **Alumnos:** el asistente ajusta la definición de directiva global (predeterminada para toda la organización) de cada área de directiva que cubre el asistente con una nueva configuración predeterminada que sea adecuada para mantener seguros a los alumnos. Esto garantiza que los alumnos actuales y todos los alumnos nuevos obtengan el conjunto de directivas más restrictivo.
- **Profesores y docentes:** el asistente crea un conjunto de definiciones de directiva personalizadas para cada área de directiva que cubre el asistente con una configuración adaptada a las necesidades de los profesores y el personal. Después, asigna las definiciones de directiva al grupo de profesores y docentes que elija. De esta forma, los profesores y el personal obtienen un conjunto más permisivo de directivas para que puedan tener éxito.

Solo necesita ejecutar el asistente una vez. Los nuevos alumnos obtienen automáticamente las definiciones de directiva global (predeterminada para toda la organización) aplicadas por el asistente y los nuevos docentes que agregue al grupo seleccionado se asignarán automáticamente a las directivas personalizadas.

Además, siempre que se agrega una nueva característica a Teams, el valor predeterminado correspondiente de EDU correspondiente de la directiva para esa característica se agregará automáticamente al global (predeterminado para toda la organización) sin requerir ninguna intervención del administrador. Esto ayuda a garantizar que se han puesto en marcha las directivas adecuadas para mantener a los alumnos seguros y comprometidos.

> [!NOTE]
> Vea [Directivas aplicadas por el asistente](#policies-applied-by-the-wizard) para obtener una lista detallada de las definiciones de directiva aplicadas por el asistente.

Ahora, empecemos.

## <a name="run-the-wizard"></a>Ejecutar el asistente

<a name="polwiz_run"> </a>

Siga estos pasos para ejecutar el asistente.

1. Si no es nuevo en Teams, el asistente se iniciará automáticamente. En caso contrario, puede iniciar el asistente en cualquier momento desde el panel. En la navegación izquierda del centro de administración de Microsoft Teams, vaya a Panel y, **a** continuación, en el icono Configuración de directivas fácil para un entorno de aprendizaje seguro, seleccione **Configuración rápida.**

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Captura de pantalla del asistente en el panel":::

2. Seleccione el tipo de institución educativa **(Educación primaria o secundaria** o educación **superior)** y, a continuación, **seleccione Siguiente.**

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de pantalla de la página del asistente para seleccionar el tipo de institución":::

3. Busque y seleccione un grupo que contenga a los profesores y al personal y, a continuación, seleccione **Siguiente**. Si aún no tiene ningún grupo configurado para los profesores y el personal, cree un grupo y vuelva [a](/microsoft-365/admin/create-groups/create-groups)ejecutar el asistente. <br/><br/>Actualmente, solo puede seleccionar un grupo. A los formadores y al personal del grupo que seleccione se les asignará [un conjunto](#policies-applied-by-the-wizard) de directivas personalizadas adaptadas a sus necesidades. Recuerde que este conjunto de directivas es independiente de las directivas aplicadas a los alumnos.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Captura de pantalla de la página en el asistente para seleccionar el grupo de profesores y docentes":::

4. Revise las selecciones.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Captura de pantalla de página en el asistente para revisar selecciones":::

5. Seleccione **Aplicar** para aplicar los cambios. Esto puede tardar unos minutos en completarse.<br/><br/>Las definiciones de directiva global (predeterminada para toda la organización) se aplican inmediatamente a los alumnos. Para los profesores y el personal, las directivas personalizadas podrían tardar varias horas en asignarse a cada miembro del grupo seleccionado, según el tamaño del grupo. Esto ocurre en segundo plano, después de completar correctamente este paso.
6. Estás en camino, pero aún no has terminado. Hay algunas cosas más que tener en cuenta. A continuación, consulte los pasos de la [sección Qué hacer después](#what-to-do-after-running-the-wizard) de ejecutar el asistente de este artículo.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Captura de pantalla de la página en el asistente para los pasos siguientes":::

## <a name="what-to-do-after-running-the-wizard"></a>Qué hacer después de ejecutar el asistente

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Paso 1: Quitar las asignaciones de directivas existentes que entren en conflicto con las directivas aplicadas por el asistente

> [!IMPORTANT]
> **Complete este paso solo si tiene directivas existentes  asignadas** a alumnos, profesores y personal antes de que se haya ejecutado el asistente. Si es nuevo en Teams y no tiene ninguna directivas existentes que no sea las directivas creadas por el asistente, omita esto y vaya al paso 2.

En Teams, para un área de directiva determinada, una directiva se puede aplicar a un usuario de las siguientes maneras:

- Asignación directa al usuario
- Asignación a un grupo del que el usuario es miembro
- Si el usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se ha asignado una directiva, el usuario obtiene automáticamente la directiva Global (predeterminada para toda la organización)

Si existen más de una de estas asignaciones de directivas para un usuario, Teams el siguiente orden para determinar qué asignación de directiva entra en vigor. Para obtener más información, vea [¿Qué directiva tiene prioridad?](assign-policies.md#which-policy-takes-precedence) y [Reglas de prioridad.](assign-policies.md#precedence-rules)

|Asignaciones de directivas de un usuario|Directiva que entra en vigor |
|---------|---------|
|Directiva asignada al grupo: No<br/>Directiva asignada directamente al usuario: No    |Directiva predeterminada global (para toda la organización)      |
|Directiva asignada al grupo: No<br/>Directiva asignada directamente al usuario: Sí    |Directiva asignada directamente al usuario         |
|Directiva asignada al grupo: Sí<br/>Directiva asignada directamente al usuario: Sí     |Directiva asignada directamente al usuario         |
|Directiva asignada al grupo: Sí<br/>Directiva asignada directamente al usuario: No     |Directiva asignada al grupo<br/><br/>Si el usuario es miembro de varios grupos y a cada grupo se le asigna una directiva del mismo área de directiva, la directiva que tiene la clasificación de asignaciones de [grupo](assign-policies.md#group-assignment-ranking) más alta entra en vigor.       |

Debido a este orden, las directivas creadas por el asistente no se verán efectivas si un usuario tiene asignaciones directas o asignaciones de grupo existentes. Esto significa que tendrá que quitar las asignaciones de directivas existentes del usuario para que la directiva aplicada por el asistente suba a efecto.

Para cada [área de directiva aplicada por el asistente,](#policies-applied-by-the-wizard)haga lo siguiente:

- Quite todas las asignaciones directas y las asignaciones de grupo existentes de los alumnos para que la definición de directiva global (predeterminada para toda la organización) aplicada por el asistente suba a efecto.
- Quite las asignaciones directas en conflicto para los profesores y el personal para que la definición de directiva personalizada creada por el asistente suba a efecto. Use la tabla anterior para determinar los escenarios que se le aplican. <br/><br/>Tenga en cuenta que el asistente asigna directivas [a](assign-policies.md#group-assignment-ranking) los profesores y al grupo de docentes con una clasificación de tareas de grupo de 1, que es la clasificación más alta. Si el grupo de profesores y docentes tiene asignada una directiva existente del mismo área de directiva, esa directiva existente se mueve a una clasificación inferior y la directiva asignada por el asistente entra en vigor.

[Obtenga más información](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) sobre cómo quitar directivas que están asignadas directamente a los usuarios.

Por ejemplo, asignó una directiva de reunión directamente a los profesores y los alumnos tienen la directiva de reunión global (predeterminada para toda la organización). En este escenario, quite la directiva de reunión que asignó directamente a los profesores para que la definición de directiva personalizada para la directiva de reunión creada por el asistente se haga efectiva. No tiene que hacer nada con la directiva de reunión global (predeterminada para toda la organización) existente para los alumnos porque ninguna otra directiva de reunión entra en conflicto con ella.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Paso 2: Comprobar si hay medidas adicionales que puede tomar para la seguridad de los alumnos

El asistente ajusta y aplica automáticamente [estas directivas.](#policies-applied-by-the-wizard) Hay pocas medidas adicionales, que es posible que desee tomar en función de las necesidades de su institución para mantenerse seguro.

Vea [Mantener a los alumnos seguros mientras usan Teams aprendizaje a distancia](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) para obtener recomendaciones de seguridad adicionales.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Paso 3: Buscar actualizaciones de directivas en el Centro de mensajes

Actualmente, el asistente aplica nuestras directivas recomendadas al ejecutarlo. Es importante saber que a medida que las nuevas directivas están disponibles en Teams, el asistente actualiza automáticamente la configuración global (predeterminada para toda la organización) para la seguridad de los alumnos. 

Pero compruebe el [Centro](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) de mensajes (en el Centro de administración de Microsoft 365) con frecuencia para mantenerse al día sobre las nuevas características y sus directivas y la configuración de directivas en Teams. 

## <a name="make-changes-in-the-wizard"></a>Realizar cambios en el asistente

<a name="polwiz_change"> </a>

Si necesita realizar cambios después de ejecutar el asistente, puede volver a ejecutarlo y cambiar las selecciones.

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a Panel y, **a** continuación, en el icono Configuración de directivas fácil para un entorno de aprendizaje seguro, seleccione **Cambiar.**
2. Desde aquí, continúe por cada página del asistente para realizar los cambios. Puede cambiar el tipo de institución, el grupo de profesores y el personal al que desea asignar directivas, o ambos.

En la tabla siguiente se resume lo que ocurre al realizar un cambio en el asistente.

|Tipo de cambio  |Comportamiento de la directiva  |
|---------|---------|
|Cambiar tanto el tipo de institución educativa como el grupo de profesores y docentes    |<ul><li>**Alumnos:** las definiciones de directiva globales (predeterminadas para toda la organización) basadas en el nuevo tipo de institución educativa se aplican a los alumnos.</li><li>**Profesores y docentes:** se crea un conjunto de definiciones de directiva personalizadas basadas en el nuevo tipo de institución educativa y se asigna al nuevo grupo de profesores y docentes. Las definiciones de directiva personalizadas anteriores se quitan del grupo de profesores y docentes anteriores.</li></ul>    |
|Cambiar solo el tipo de institución educativa    |<ul><li>**Alumnos:** las definiciones de directiva globales (predeterminadas para toda la organización) basadas en el nuevo tipo de institución educativa se aplican a los alumnos.</li><li>**Profesores y docentes:** se crea un conjunto de definiciones de directivas personalizadas basadas en el nuevo tipo de institución educativa y se asigna al grupo de profesores y docentes. Las definiciones de directiva personalizadas creadas para el tipo de institución educativa anterior se quitan del grupo de profesores y docentes.</li></ul>         |
|Cambiar solo el grupo de profesores y docentes   |<ul><li>**Alumnos:** no hay ningún cambio en las definiciones de directiva globales (predeterminadas para toda la organización) aplicadas a los alumnos.</li><li>**Educadores y docentes:** las definiciones de directiva personalizadas se asignan al nuevo grupo de profesores y docentes y se quitan del grupo de profesores y docentes anteriores.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Directivas aplicadas por el asistente

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Áreas de directiva

Estas son las áreas de directiva y los nombres de directiva correspondientes cubiertos por el asistente. Para buscar estas directivas, vaya al centro de administración Microsoft Teams y, a continuación, en el panel de navegación izquierdo, vaya a cada página del área de directiva.

#### <a name="students"></a>[**Estudiantes**](#tab/students/)

|Área de directiva  |Nombre de directiva principal o secundaria |Nombre de la directiva de educación superior  |
|---------|---------|---------|
|Directiva de equipo    |Global (de forma predeterminada para toda la organización)         |Global (de forma predeterminada para toda la organización)           |
|Directiva de reuniones    |Global (de forma predeterminada para toda la organización)           |Global (de forma predeterminada para toda la organización)           |
|Directiva de eventos en directo     |Global (de forma predeterminada para toda la organización)          |  Global (de forma predeterminada para toda la organización)          |
|Directiva de configuración de aplicaciones     |Global (de forma predeterminada para toda la organización)           |Global (de forma predeterminada para toda la organización)           |
|Directiva de permisos de aplicación    |Global (de forma predeterminada para toda la organización)           |Global (de forma predeterminada para toda la organización)           |
|Directiva de mensajería     |Global (de forma predeterminada para toda la organización)           |Global (de forma predeterminada para toda la organización)           |
|Directiva de llamadas    |Global (de forma predeterminada para toda la organización)           |Global (de forma predeterminada para toda la organización)           |

#### <a name="educators-and-staff"></a>[**Educadores y personal**](#tab/educators/)

|Área de directiva  |Nombre de directiva principal o secundaria |Nombre de la directiva de educación superior |
|---------|---------|---------|
|Directiva de equipo   |Profesores y docentes de primaria o secundaria: Teams         |Profesores y docentes de educación superior: Teams         |
|Directiva de reuniones    |Profesores y docentes de primaria o secundaria: reunión         |Profesores y docentes de educación superior: reunión         |
|Directiva de eventos en directo   | Profesores y docentes de primaria o secundaria: eventos en directo         |Profesores y docentes de educación superior: eventos en directo         |
|Directiva de mensajería    |Profesores y docentes de primaria o secundaria: mensajería         | Profesores y docentes de educación superior: mensajería         |
|Directiva de llamadas    |Profesores y docentes de primaria o secundaria: llamadas         |Profesores y docentes de educación superior: llamadas         |

* * *

### <a name="policy-settings"></a>Configuración de directiva

Este es un resumen de la configuración aplicada por el asistente para cada área de directiva.

#### <a name="students"></a>[**Estudiantes**](#tab/student-settings/)

Esta es una lista de las definiciones de directivas globales (predeterminadas para toda la organización) ajustadas por el asistente y aplicadas a los alumnos.

|Área de directiva |Sub-área  |Configuración de directiva  |Principal o Secundario |Educación superior |
|---------|---------|---------|---------|---------|
|Directiva de equipo   |         |Crear canales privados         |Desactivado       |Activado|
|Directiva de reuniones    |General         |Permitir la opción Reunirse ahora en canales         |Desactivado      |Activado|
|  |        |Permitir el complemento de Outlook         |Desactivado       |Activado|
|  |        |Permitir la programación de reuniones de canal        |Desactivado      |Activado|
|  |        |Permitir la programación de reuniones privadas       |Desactivado      |Activado|
|  |Vídeo & audio        |Permitir transcripción        |Activado       |Activado|
|  |        |Permitir la grabación en la nube         |Desactivado      |Activado|
|  |        |Modo de audio IP       |Audio entrante y saliente activado        |Audio entrante y saliente activado|
|  |        |Modo de vídeo IP         |Vídeo entrante y saliente activado     |Vídeo entrante y saliente activado|
|  |       |Permitir vídeo IP         |Activado         |Activado|
|  |       |Permitir la transmisión NDI         |Desactivado         |Desactivado|
|  |       |Velocidad de bits multimedia (kb/s)         |50 000         |50 000|
|  |Uso compartido de contenido       |Modo de uso compartido de la pantalla         |Toda la pantalla         |Toda la pantalla|
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
|  |       |Quién puede unirse a eventos en directo programados        |Todos los miembros de la organización        |Todos los miembros de la organización|
|  |       |Quién puede grabar un evento         |Siempre         |Siempre|
|Directiva de mensajería  |       |Los propietarios pueden eliminar los mensajes enviados         |Desactivado|Activado|
|  |       |Eliminar mensajes enviados         |Desactivado         |Activado|
|  |       |Editar los mensajes enviados         |Desactivado         |Activado|
|  |       |Confirmaciones de lectura         |Controlado por el usuario         |Controlado por el usuario|
|  |       |Chat         |Desactivado         |Activado|
|  |       |Usar Giphys en conversaciones         |Desactivado         |Activado|
|  |       |Clasificación de contenido de Giphy         |Estricto        |Estricto|
|  |       |Usar memes en conversaciones         |Activado         |Activado|
|  |       |Usar adhesivos en conversaciones         |Activado         |Activado|
|  |       |Permitir vistas previas de URL        |Activado         |Activado|
|  |       |Traducir mensajes         |Activado         |Activado|
|  |       |Permitir lector inmersivo para ver mensajes        |Activado      |Activado|
|  |       |Enviar mensajes urgentes con notificaciones prioritarias  |Desactivado         |Activado|
|  |       |Crear mensajes de voz         |Permitido en chats y canales         |Permitido en chats y canales|
|  |       |En dispositivos móviles, mostrar canales favoritos por encima de chats recientes     |Habilitado         |Habilitado|
|  |       |Quitar usuarios de chats grupales         |Desactivado         |Activado|
|Directiva de permisos de aplicación  |       |Aplicaciones de Microsoft         |Bloquear aplicaciones específicas y permitir que todos los demás > Walkie Talkie bloqueado         |Permitir todas las aplicaciones|
|  |       |Aplicaciones de terceros         |Permitir todas las aplicaciones         |Permitir todas las aplicaciones|
|  |       |Aplicaciones personalizadas         |Permitir todas las aplicaciones         |Permitir todas las aplicaciones|
|Directiva de configuración de aplicaciones  |           |Upload aplicaciones personalizadas           |Desactivado         |Desactivado|
|  |       |Permitir la anclación de usuario |Activado         |Activado|
|  |       |Aplicaciones instaladas         |Ninguna         |Ninguna|
|  |       |Aplicaciones ancladas         |Actividad, Calendario, Teams         |Actividad, Chats, Teams, Calendario, Llamadas, Archivo
|Directiva de llamadas  |       |Realizar llamadas privadas         |Desactivado        |Activado|
|  |       |Reenvío de llamadas y llamadas simultáneas a personas de su organización         |Desactivado         |Activado|
|  |       |Reenvío de llamadas y llamadas simultáneas a números de teléfono externos         |Desactivado         |Activado|
|  |       |El correo de voz está disponible para el enrutamiento de llamadas entrantes         |Controlado por el usuario         |Controlado por el usuario|
|  |       |Las llamadas entrantes se pueden enrutar a grupos de llamadas         |Desactivado        |Activado|
|  |       |Permitir la delegación de llamadas entrantes y salientes         |Desactivado         |Activado|
|  |       |Evitar la omisión de pago y enviar llamadas a través de la RTC        |Desactivado         |Desactivado|
|  |       |Ocupado en ocupado está disponible cuando se está en una llamada         |Desactivado         |Desactivado|
|  |       |Permitir llamadas RTC web         |Desactivado         |Activado|

#### <a name="educators-and-staff"></a>[**Educadores y personal**](#tab/educator-settings/)

Esta es una lista de las definiciones de directiva personalizadas asignadas al grupo de profesores y docentes que elija en el asistente.  

|Área de directiva |Sub-área  |Configuración de directiva  |Principal o Secundario |Educación superior |
|---------|---------|---------|---------|---------|
|Directiva de equipo   |         |Crear canales privados         |Activado       |Activado|
|Directiva de reuniones    |General         |Permitir la opción Reunirse ahora en canales         |Activado      |Activado|
|  |        |Permitir el complemento de Outlook         |Activado       |Activado|
|  |        |Permitir la programación de reuniones de canal        |Activado      |Activado|
|  |        |Permitir la programación de reuniones privadas       |Activado      |Activado|
|  |Vídeo & audio        |Permitir transcripción        |Activado       |Activado|
|  |        |Permitir la grabación en la nube         |Activado      |Activado|
|  |        |Modo de audio IP       |Audio entrante y saliente activado        |Audio entrante y saliente activado|
|  |        |Modo de vídeo IP         |Vídeo entrante y saliente activado     |Vídeo entrante y saliente activado|
|  |       |Permitir vídeo IP         |Activado         |Activado|
|  |       |Permitir la transmisión NDI         |Desactivado         |Desactivado|
|  |       |Velocidad de bits multimedia (kb/s)         |50 000         |50 000|
|  |Uso compartido de contenido       |Modo de uso compartido de la pantalla         |Toda la pantalla         |Toda la pantalla|
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
|  |       |Quién puede unirse a eventos en directo programados        |Todos los miembros de la organización        |Todos los miembros de la organización|
|  |       |Quién puede grabar un evento         |Grabar siempre         |Grabar siempre|
|Directiva de mensajería  |       |Los propietarios pueden eliminar los mensajes enviados         |Activado|Activado|
|  |       |Eliminar mensajes enviados         |Activado         |Activado|
|  |       |Editar los mensajes enviados         |Activado         |Activado|
|  |       |Confirmaciones de lectura         |Controlado por el usuario         |Controlado por el usuario|
|  |       |Chat         |Activado         |Activado
|  |       |Usar Giphys en conversaciones         |Activado        |Activado|
|  |       |Clasificación de contenido de Giphy         |Estricto        |Estricto|
|  |       |Usar memes en conversaciones         |Activado         |Activado|
|  |       |Usar adhesivos en conversaciones         |Activado         |Activado|
|  |       |Permitir vistas previas de URL        |Activado         |Activado|
|  |       |Traducir mensajes         |Activado         |Activado|
|  |       |Permitir lector inmersivo para ver mensajes        |Activado      |Activado|
|  |       |Enviar mensajes urgentes con notificaciones prioritarias  |Activado         |Activado|
|  |       |Crear mensajes de voz         |Permitido en chats y canales         |Permitido en chats y canales|
|  |       |En dispositivos móviles, mostrar canales favoritos por encima de chats recientes     |Habilitado         |Habilitado|
|  |       |Quitar usuarios de chats grupales         |Activado        |Activado|
|Directiva de llamadas  |       |Realizar llamadas privadas         |Activado       |Activado|
|  |       |Reenvío de llamadas y llamadas simultáneas a personas de su organización         |Activado        |Activado|
|  |       |Reenvío de llamadas y llamadas simultáneas a números de teléfono externos         |Activado        |Activado|
|  |       |El correo de voz está disponible para el enrutamiento de llamadas entrantes         |Controlado por el usuario         |Controlado por el usuario|
|  |       |Las llamadas entrantes se pueden enrutar a grupos de llamadas         |Activado        |Activado|
|  |       |Permitir la delegación de llamadas entrantes y salientes         |Activado         |Activado|
|  |       |Evitar la omisión de pago y enviar llamadas a través de la RTC        |Desactivado         |Desactivado|
|  |       |Ocupado en ocupado está disponible cuando se está en una llamada         |Desactivado         |Desactivado|
|  |       |Permitir llamadas RTC web         |Activado      |Activado|

* * *

## <a name="related-topics"></a>Temas relacionados

- [Directivas de Teams y paquetes de directivas para educación](policy-packages-edu.md)
- [Asignar directivas a grandes conjuntos de usuarios de la escuela](batch-group-policy-assignment-edu.md)
- [Mantener a los alumnos seguros mientras usan Teams aprendizaje a distancia](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
