---
title: Asistente para directivas de Teams para Educación para aplicar fácilmente directivas de aprendizaje seguro
author: DaniEASmith
ms.author: danismith
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
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo usar el asistente de directivas de Teams para Educación para aplicar fácilmente directivas para que los alumnos y profesores mantengan seguro su entorno de aprendizaje.
f1keywords: ''
ms.openlocfilehash: 833e4b16ca617d06fcc3ace770e2548f6e05a0bb
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790235"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Usar el Asistente para directivas de Teams para Educación para aplicar fácilmente directivas para un entorno de aprendizaje seguro

## <a name="overview"></a>Información general

El Asistente para directivas de Microsoft Teams para Educación simplifica la administración de directivas para alumnos y profesores. Úselo para aplicar rápida y fácilmente el conjunto de directivas más importante relevante para crear una experiencia de aprendizaje segura y productiva.

Las directivas de Teams le permiten controlar cómo se comporta Teams en su entorno y qué características están disponibles para los usuarios. Por ejemplo, hay directivas de llamadas, directivas de reunión y directivas de mensajería, por nombrar algunas, y cada área de directiva se puede personalizar para satisfacer las necesidades de su organización.

Para mantener un entorno de aprendizaje seguro y centrado, es importante establecer directivas para controlar lo que los alumnos pueden hacer en Teams. Por ejemplo, puede usar directivas para controlar quién puede usar el chat privado y las llamadas privadas, quién puede programar reuniones y qué tipos de contenido se pueden compartir. También puede usar directivas para activar las características de Teams que enriquecen la experiencia de aprendizaje.

Es necesario ajustar las directivas tanto para los alumnos como para los formadores, con el fin de mantener la experiencia de aprendizaje segura. Las directivas para los alumnos deben ser más restrictivas para reducir el riesgo de recibir niveles de acceso inadecuados. Los formadores y el personal necesitan un conjunto independiente de directivas que puedan ser más permisivas para que puedan tener éxito. Por ejemplo, permita que los formadores programen reuniones y que los alumnos no lo puedan hacer.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de pantalla del asistente.":::

En este artículo se explica cómo ejecutar el asistente.

> [!IMPORTANT]
> Las directivas que aplique el asistente satisfarán las necesidades de la mayoría de Teams para Educación clientes. El asistente ajusta la definición global (predeterminada para toda la organización) de un conjunto principal de directivas con la configuración que recomendamos para la seguridad de los alumnos y la aplica a los alumnos. El asistente también crea y asigna un conjunto de directivas personalizadas a profesores y personal. La mayoría de Teams para Educación clientes no necesitarán usar otros métodos de asignación de directivas después de ejecutar este asistente. Use otros métodos de asignación de *directivas solo* si desea crear y administrar directivas manualmente para sus alumnos, educadores y personal.

## <a name="teams-for-education-policy-wizard"></a>Asistente para directivas de Teams para Educación

<a name="polwiz_intro"> </a>

El asistente aplica un conjunto de definiciones de directivas básicas a los alumnos y un conjunto independiente de definiciones de directivas básicas a los formadores y al personal, con una configuración adecuada para cada uno. Esto es lo que ocurre al ejecutar el asistente.

El asistente configura directivas según el tipo de institución educativa (**primaria o secundaria** o **superior**). Seleccione el tipo de institución y el asistente hará lo siguiente:

- **Alumnos**: El asistente ajusta la definición de directiva global (predeterminada para toda la organización) de cada área de directiva cubierta por el asistente con una nueva configuración predeterminada adecuada para proteger a los alumnos. Esto garantiza que los alumnos actuales y todos los nuevos alumnos obtengan el conjunto de directivas más restrictivo.
- **Profesores y personal**: el asistente crea un conjunto de definiciones de directivas personalizadas para cada área de directiva cubierta por el asistente con una configuración adaptada a las necesidades de los formadores y el personal. Después, asigna las definiciones de directiva al grupo de formadores y personal que elija. De esta forma, los profesores y el personal obtienen un conjunto más permisivo de directivas para que puedan tener éxito.

Solo necesita ejecutar el asistente una vez. Los nuevos alumnos obtienen automáticamente las definiciones de directiva global (predeterminada para toda la organización) aplicadas por el asistente y se asignan automáticamente las directivas personalizadas a los nuevos docentes que agregue al grupo seleccionado.

Además, siempre que se agregue una nueva característica a Teams, el valor predeterminado apropiado de edu relevante de la directiva para esa característica se agregará automáticamente a global (valor predeterminado para toda la organización) sin necesidad de intervención del administrador. Esto ayuda a garantizar que se aplican las directivas adecuadas para mantener a los alumnos seguros y comprometidos.

> [!NOTE]
> Vea [Directivas aplicadas por el asistente](#policies-applied-by-the-wizard) para obtener una lista detallada de las definiciones de directivas aplicadas por el asistente.

¡Comencemos!

## <a name="run-the-wizard"></a>Ejecutar el asistente

<a name="polwiz_run"> </a>

Siga estos pasos para ejecutar el asistente.

1. Si no está familiarizado con Teams, se iniciará automáticamente el asistente. En caso contrario, puede iniciar el asistente en cualquier momento desde el panel. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Inicio** y, a continuación, en el mosaico **Configuración de directivas sencilla para un entorno de aprendizaje seguro** , seleccione **Configuración rápida**.

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Captura de pantalla del asistente en el panel.":::

2. Seleccione el tipo de institución educativa (**Primaria o Secundaria** o **Educación superior**) y, a continuación, seleccione **Siguiente**.

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Captura de pantalla de la página del asistente para seleccionar el tipo de institución.":::

3. Busque y seleccione los grupos que contengan los profesores y el personal y, a continuación, seleccione **Siguiente**. Si aún no ha configurado ningún grupo para los profesores y el personal, [cree un grupo](/microsoft-365/admin/create-groups/create-groups) y vuelva a ejecutar el asistente. <br/><br/>Puede seleccionar hasta tres grupos. A los formadores y al personal de los grupos que seleccione se les asignará [un conjunto de directivas personalizadas](#policies-applied-by-the-wizard) adaptadas a sus necesidades. Recuerde que este conjunto de directivas es independiente de las directivas aplicadas a los alumnos.

    :::image type="content" source="media/edu-policy-wizard-add-3-groups.png" alt-text="Captura de pantalla de la página del asistente para seleccionar grupos de profesores y docentes.":::

4. Revise las selecciones.

    :::image type="content" source="media/edu-policy-wizard-3-groups-review.png" alt-text="Captura de pantalla de la página del asistente para revisar las selecciones.":::

5. Seleccione **Aplicar** para aplicar los cambios. Esto puede tardar unos minutos en completarse.<br/><br/>Las definiciones de directiva global (predeterminada para toda la organización) se aplican inmediatamente a los alumnos. Para los profesores y el personal, pueden pasar unas horas hasta que las directivas personalizadas se asignen a cada miembro de los grupos seleccionados, según el tamaño de los grupos. Esto ocurre en segundo plano, después de completar correctamente este paso.
6. Está en camino, pero aún no ha terminado. Hay algunas cosas más que tener en cuenta. A continuación, consulte los pasos de la sección [Qué hacer después de ejecutar el asistente](#what-to-do-after-running-the-wizard) de este artículo.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Captura de pantalla de la página del asistente para ver los pasos siguientes.":::

## <a name="what-to-do-after-running-the-wizard"></a>Qué hacer después de ejecutar el asistente

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Paso 1: Quitar las asignaciones de directiva existentes que entren en conflicto con las directivas aplicadas por el asistente

> [!IMPORTANT]
> **Complete este paso solo si tiene directivas existentes asignadas a alumnos, profesores y personal *antes* de ejecutar el asistente**. Si es la primera vez que usa Teams y no tiene otras directivas que las creadas por el asistente, omita esta opción y vaya al paso 2.

En Teams, para un área de directiva determinada, se puede aplicar una directiva a un usuario de las siguientes maneras:

- Asignación directa al usuario
- Asignación a un grupo del que el usuario es miembro
- Si el usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se le haya asignado una directiva, el usuario obtiene automáticamente la directiva Global (predeterminada para toda la organización).

Si hay más de una de estas asignaciones de directiva para un usuario, Teams usa el siguiente orden para determinar qué asignación de directiva surte efecto. Para obtener más información, vea [Qué directiva tiene prioridad](policy-assignment-overview.md#which-policy-takes-precedence) o [Reglas de prioridad para grupos](assign-policies-users-and-groups.md#precedence-rules).

|Asignaciones de directiva de un usuario|Directiva que surte efecto|
|---|---|
|Directiva asignada a un grupo: No <p> Directiva asignada directamente al usuario: No|Directiva predeterminada global (para toda la organización)|
|Directiva asignada a un grupo: No <p> Directiva asignada directamente al usuario: Sí|Directiva asignada directamente al usuario|
|Directiva asignada a un grupo: Sí <p> Directiva asignada directamente al usuario: Sí|Directiva asignada directamente al usuario|
|Directiva asignada a un grupo: Sí <p> Directiva asignada directamente al usuario: No|Directiva asignada a un grupo <p> Si el usuario es miembro de varios grupos y a cada grupo se le asigna una directiva del mismo área de directiva, se aplicará la directiva que tenga la [clasificación de asignaciones de grupo](assign-policies-users-and-groups.md#group-assignment-ranking) más alta.|

Debido a este orden, las directivas creadas por el asistente no se aplicarán si un usuario tiene asignaciones directas o asignaciones de grupo existentes. Esto significa que tendrá que quitar las asignaciones de directiva existentes del usuario para que la directiva aplicada por el asistente surta efecto.

Para cada [área de directiva aplicada por el asistente](#policies-applied-by-the-wizard), haga lo siguiente:

- Quite todas las tareas directas y las tareas de grupo existentes de los alumnos para que la definición de directiva global (predeterminada para toda la organización) aplicada por el asistente surta efecto.
- Quite las asignaciones directas en conflicto de los profesores y el personal para que la definición de directiva personalizada creada por el asistente surta efecto. Use la tabla anterior para determinar los escenarios que se aplican a su caso. <p> Tenga en cuenta que el asistente asigna directivas a los profesores y al grupo de docentes con una [clasificación de tareas de grupo](assign-policies-users-and-groups.md#group-assignment-ranking) de 1, que es la clasificación más alta. Si los profesores y el grupo de docentes tienen asignada una directiva existente del mismo área de directiva, esa directiva existente se mueve a una clasificación inferior y la directiva asignada por el asistente surte efecto.

[Obtenga más información](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) sobre cómo quitar directivas asignadas directamente a usuarios.

Por ejemplo, asignó una directiva de reunión directamente a los formadores y los alumnos tienen la directiva de reunión Global (predeterminada para toda la organización). En este escenario, quite la directiva de reunión que asignó directamente a los profesores para que la definición de directiva personalizada para la directiva de reunión creada por el asistente surta efecto. No tiene que hacer nada con la directiva de reuniones global (predeterminada para toda la organización) existente para los alumnos porque ninguna otra directiva de reunión entra en conflicto con ella.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Paso 2: Comprobar si hay medidas adicionales que puede tomar para la seguridad de los estudiantes

El asistente ajusta y aplica [automáticamente estas directivas](#policies-applied-by-the-wizard). Hay algunas medidas adicionales, que puede que desee tomar en función de las necesidades de su institución para mantenerse seguro.

Consulte [Mantener seguros a los alumnos mientras usan Teams para el aprendizaje a distancia](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) para obtener recomendaciones de seguridad adicionales.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Paso 3: Buscar actualizaciones de directivas en el Centro de mensajes

Actualmente, el asistente aplica nuestras directivas recomendadas al ejecutarlo. Es importante saber que, a medida que las nuevas directivas estén disponibles en Teams, el asistente actualizará automáticamente la configuración global (predeterminada para toda la organización) para la seguridad de los alumnos.

Pero compruebe con frecuencia el [Centro](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) de mensajes (en la Centro de administración de Microsoft 365) para estar al día de las nuevas características y sus directivas y configuración de directivas en Teams.

## <a name="make-changes-in-the-wizard"></a>Realizar cambios en el asistente

<a name="polwiz_change"> </a>

Si necesita realizar cambios después de ejecutar el asistente, puede volver a ejecutarlo y cambiar las selecciones.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Inicio** y, a continuación, en el icono **Configuración de directivas sencilla para un entorno de aprendizaje seguro** , seleccione **Cambiar**.
2. Desde aquí, continúe por cada página del asistente para realizar los cambios. Puede cambiar el tipo de institución, los grupos de educadores y docentes a los que desea asignar directivas, o ambos.

En la tabla siguiente se resume lo que sucede cuando se realiza un cambio en el asistente.

|Tipo de cambio|Comportamiento de la directiva|
|---|---|
|Cambiar tanto el tipo de institución educativa como los profesores y los grupos de docentes|<ul><li>**Estudiantes**: Las definiciones de directiva globales (predeterminadas para toda la organización) basadas en el nuevo tipo de institución educativa se aplican a los estudiantes.</li><li>**Formadores y personal**: se crea un conjunto de definiciones de directivas personalizadas basadas en el nuevo tipo de institución educativa y se asigna a los nuevos grupos de formadores y docentes. Las definiciones de directivas personalizadas anteriores se quitan de los profesores y grupos de docentes anteriores.</li></ul>|
|Cambiar solo el tipo de institución educativa|<ul><li>**Estudiantes**: Las definiciones de directiva globales (predeterminadas para toda la organización) basadas en el nuevo tipo de institución educativa se aplican a los estudiantes.</li><li>**Formadores y personal**: se crea un conjunto de definiciones de directivas personalizadas basadas en el nuevo tipo de institución educativa y se asigna a los formadores y grupos de personal. Las definiciones de directivas personalizadas creadas para el tipo de institución educativa anterior se quitan de los profesores y los grupos de personal.</li></ul>|
|Cambiar solo los profesores y los grupos de docentes|<ul><li>**Alumnos**: No hay cambios en las definiciones de directiva global (predeterminada para toda la organización) aplicadas a los alumnos.</li><li>**Profesores y personal**: las definiciones de directivas personalizadas se asignan a los nuevos formadores y grupos de docentes y se quitan de los anteriores formadores y grupos de personal.</li></ul>|

## <a name="policies-applied-by-the-wizard"></a>Directivas aplicadas por el asistente

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Áreas directivas

Estas son las áreas de directiva y los nombres de directiva correspondientes que cubre el asistente. Para encontrar estas directivas, vaya al Centro de administración de Microsoft Teams y, a continuación, en el panel de navegación izquierdo, vaya a cada página del área de directiva.

#### <a name="students"></a>[**Estudiantes**](#tab/students/)

|Área Directiva|Nombre de directiva principal o secundario|Nombre de la directiva de educación superior|
|---|---|---|
|Directiva de equipo|Global (valor predeterminado para toda la organización)|Global (valor predeterminado para toda la organización)|
|Directiva de reuniones|Global (valor predeterminado para toda la organización)|Global (valor predeterminado para toda la organización)|
|Directiva de eventos en directo|Global (valor predeterminado para toda la organización)|Global (valor predeterminado para toda la organización)|
|Directiva de configuración de aplicaciones|Global (valor predeterminado para toda la organización)|Global (valor predeterminado para toda la organización)|
|Directiva de permisos de aplicaciones|Global (valor predeterminado para toda la organización)|Global (valor predeterminado para toda la organización)|
|Directiva de mensajería|Global (valor predeterminado para toda la organización)|Global (valor predeterminado para toda la organización)|
|Directiva de llamadas|Global (valor predeterminado para toda la organización)|Global (valor predeterminado para toda la organización)|

#### <a name="educators-and-staff"></a>[**Educadores y personal**](#tab/educators/)

|Área Directiva|Nombre de directiva principal o secundario|Nombre de la directiva de educación superior|
|---|---|---|
|Directiva de equipo|Profesores y docentes principales o secundarios: Teams|Profesores y docentes de educación superior: Teams|
|Directiva de reuniones|Profesores y docentes primarios o secundarios: reunión|Profesores y personal de educación superior: reunión|
|Directiva de eventos en directo|Educadores y personal primarios o secundarios: eventos en directo|Educadores y personal de educación superior: eventos en directo|
|Directiva de mensajería|Profesores y docentes primarios o secundarios: mensajes|Profesores y personal de educación superior: mensajes|
|Directiva de llamadas|Profesores y docentes primarios o secundarios: llamadas|Profesores y personal de educación superior: llamadas|

### <a name="policy-settings"></a>Configuración de directiva

Este es un resumen de la configuración aplicada por el asistente para cada área de directiva.

> [!NOTE]
> Solo los propietarios de equipos pueden crear canales compartidos.<br><br>Los canales compartidos con otras organizaciones requieren la configuración de [Conexión directa B2B de Azure AD](/azure/active-directory/external-identities/b2b-direct-connect-overview) , que está deshabilitada de forma predeterminada. Vea [Colaborar con participantes externos en un canal](/microsoft-365/solutions/collaborate-teams-direct-connect) para habilitar esta característica.

#### <a name="students"></a>[**Estudiantes**](#tab/student-settings/)

Esta es una lista de las definiciones de directiva global (predeterminada para toda la organización) ajustadas por el asistente y aplicadas a los alumnos.

|Área Directiva|Sub-área|Configuración de directiva|Principal o secundario|Educación superior|
|---|---|---|---|---|
|Directiva de equipo||Crear canales privados|Desactivado|Activado|
|||Crear canales compartidos|Activado|Activado|
|||Compartir canal con participantes externos|Activado|Activado|
|||Participar en un canal compartido externo|Activado|Activado|
|Directiva de reuniones|General|Permitir la opción Reunirse ahora en canales|Desactivado|Activado|
|||Permitir el complemento de Outlook|Desactivado|Activado|
|||Permitir la programación de reuniones de canal|Desactivado|Activado|
|||Permitir la programación de reuniones privadas|Desactivado|Activado|
|||Permitir el registro de reuniones|Activado|Activado|
|||Quién puede registrarse|Todos los miembros de la organización|Todos los miembros de la organización|
||Audio & vídeo|Transcripción|Activado|Activado|
|||Grabación en la nube|Desactivado|Activado|
|||Modo de audio IP|Audio entrante y saliente activado|Audio entrante y saliente activado|
|||Modo de vídeo IP|Vídeo entrante y saliente activado|Vídeo entrante y saliente activado|
|||Vídeo IP|Activado|Activado|
|||Permitir el streaming NDI|Desactivado|Desactivado|
|||Velocidad de bits multimedia (kb/s)|50 000|50 000|
||Uso compartido de contenido|Modo de uso compartido de la pantalla|Toda la pantalla|Toda la pantalla|
|||Permitir a un participante ceder o solicitar el control|Activado|Activado|
|||Permitir a un participante externo ceder o solicitar el control|Activado|Activado|
|||Uso compartido de PowerPoint|Activado|Activado|
|||Whiteboard|Activado|Activado|
|||Notas compartidas|Activado|Activado|
||Participantes & invitados|Permitir que los usuarios anónimos inicien una reunión|Desactivado|Activado|
|||Roles que tienen derechos de moderador en las reuniones|EveryoneUserOverride|EveryoneUserOverride|
|||Admitir automáticamente usuarios|EveryoneInCompany|EveryoneInCompany|
|||Permitir que los usuarios de acceso telefónico omitan la sala de espera|Desactivado|Desactivado|
|||Reunirse ahora en reuniones privadas|Desactivado|Activado|
|||Subtítulos en directo|Deshabilitado, pero el usuario puede invalidar|Deshabilitado, pero el usuario puede invalidar|
|||Chatear en reuniones|Activado|Activado|
|Directiva de eventos en directo||Programación de eventos en directo|Desactivado|Desactivado|
|||Transcripción para los asistentes|Activado|Activado|
|||Quién puede unirse a eventos en directo programados|Todos los miembros de la organización|Todos los miembros de la organización|
|||Quién puede grabar un evento|Siempre|Siempre|
|Directiva de mensajería||Los propietarios pueden eliminar mensajes enviados|Desactivado|Activado|
|||Eliminar mensajes enviados|Desactivado|Activado|
|||Editar los mensajes enviados|Desactivado|Activado|
|||Confirmaciones de lectura|Controlado por el usuario|Controlado por el usuario|
|||Chat|Desactivado|Activado|
|||Giphy en conversaciones|Desactivado|Activado|
|||Clasificación de contenido de Giphy|Estricto|Estricto|
|||Memes en conversaciones|Activado|Activado|
|||Adhesivos en conversaciones|Activado|Activado|
|||Vistas previas de url|Activado|Activado|
|||Traducir mensajes|Activado|Activado|
|||Lector inmersivo para mensajes|Activado|Activado|
|||Enviar mensajes urgentes con notificaciones prioritarias|Desactivado|Activado|
|||Crear mensajes de voz|Permitido en chats y canales|Permitido en chats y canales|
|||En dispositivos móviles, mostrar los canales favoritos encima de los chats recientes|Habilitado|Habilitado|
|||Quitar usuarios de chats grupales|Desactivado|Activado|
|Directiva de permisos de aplicaciones||Aplicaciones de Microsoft|Bloquear aplicaciones específicas y permitir que todos los demás > Walkie Talkie bloqueado|Permitir todas las aplicaciones|
|||Aplicaciones de terceros|Permitir todas las aplicaciones|Permitir todas las aplicaciones|
|||Aplicaciones personalizadas|Permitir todas las aplicaciones|Permitir todas las aplicaciones|
|Directiva de configuración de aplicaciones||Cargar aplicaciones personalizadas|Desactivado|Desactivado|
|||Anclaje de usuario|Activado|Activado|
|||Aplicaciones instaladas|Ninguna|Ninguna|
|||Aplicaciones ancladas|Actividad, Calendario, Teams|Actividad, Chats, Teams, Calendario, Llamadas, Archivo
|Directiva de llamadas||Realizar llamadas privadas|Desactivado|Activado|
|||Desvío de llamadas y llamadas simultáneas a personas de su organización|Desactivado|Activado|
|||Desvío de llamadas y llamadas simultáneas a números de teléfono externos|Desactivado|Activado|
|||El correo de voz está disponible para enrutar llamadas entrantes|Controlado por el usuario|Controlado por el usuario|
|||Las llamadas entrantes se pueden enrutar a grupos de llamadas|Desactivado|Activado|
|||Permitir la delegación para llamadas entrantes y salientes|Desactivado|Activado|
|||Evitar la omisión de pago y enviar llamadas a través de la RTC|Desactivado|Desactivado|
|||Ocupado ocupado está disponible cuando está en una llamada|Desactivado|Desactivado|
|||Permitir llamadas RTC web|Desactivado|Activado|

#### <a name="educators-and-staff"></a>[**Educadores y personal**](#tab/educator-settings/)

Esta es una lista de las definiciones de directivas personalizadas asignadas a los formadores y grupos de docentes que elija en el asistente.  

|Área Directiva|Sub-área|Configuración de directiva|Principal o secundario|Educación superior|
|---|---|---|---|---|
|Directiva de equipo||Crear canales privados|Activado|Activado|
|||Crear canales compartidos|Activado|Activado|
|||Compartir canal con participantes externos|Activado|Activado|
|||Participar en un canal compartido externo|Activado|Activado|
|Directiva de reuniones|General|Permitir la opción Reunirse ahora en canales|Activado|Activado|
|||Permitir el complemento de Outlook|Activado|Activado|
|||Permitir la programación de reuniones de canal|Activado|Activado|
|||Permitir la programación de reuniones privadas|Activado|Activado|
|||Permitir el registro de reuniones|Activado|Activado|
|||Quién puede registrarse|Todos los miembros de la organización|Todos los miembros de la organización|
||Audio & vídeo|Transcripción|Activado|Activado|
|||Grabación en la nube|Activado|Activado|
|||Modo de audio IP|Audio entrante y saliente activado|Audio entrante y saliente activado|
|||Modo de vídeo IP|Vídeo entrante y saliente activado|Vídeo entrante y saliente activado|
|||Vídeo IP|Activado|Activado|
|||Permitir el streaming NDI|Desactivado|Desactivado|
|||Velocidad de bits multimedia (kb/s)|50 000|50 000|
||Uso compartido de contenido|Modo de uso compartido de la pantalla|Toda la pantalla|Toda la pantalla|
|||Permitir a un participante ceder o solicitar el control|Activado|Activado|
|||Permitir a un participante externo ceder o solicitar el control|Activado|Activado|
|||Uso compartido de PowerPoint|Activado|Activado|
|||Whiteboard|Activado|Activado|
|||Notas compartidas|Activado|Activado|
||Participantes & invitados|Permitir que los usuarios anónimos inicien una reunión|Activado|Activado|
|||Roles que tienen derechos de moderador en las reuniones|OrganizerOnlyUserOverride|OrganizerOnlyUserOverride|
|||Admitir automáticamente usuarios|OrganizadorOnly|OrganizadorOnly|
|||Permitir que los usuarios de acceso telefónico omitan la sala de espera|Desactivado|Desactivado|
|||Reunirse ahora en reuniones privadas|Activado|Activado|
|||Subtítulos en directo|Deshabilitado, pero el usuario puede invalidar|Deshabilitado, pero el usuario puede invalidar|
|||Chatear en reuniones|Activado|Activado|
|Directiva de eventos en directo||Programación de eventos en directo|Activado|Activado|
|||Transcripción para los asistentes|Activado|Activado|
|||Quién puede unirse a eventos en directo programados|Todos los miembros de la organización|Todos los miembros de la organización|
|||Quién puede grabar un evento|Grabar siempre|Grabar siempre|
|Directiva de mensajería||Los propietarios pueden eliminar mensajes enviados|Activado|Activado|
|||Eliminar mensajes enviados|Activado|Activado|
|||Editar los mensajes enviados|Activado|Activado|
|||Confirmaciones de lectura|Controlado por el usuario|Controlado por el usuario|
|||Chat|Activado|Activado
|||Giphy en conversaciones|Activado|Activado|
|||Clasificación de contenido de Giphy|Estricto|Estricto|
|||Memes en conversaciones|Activado|Activado|
|||Adhesivos en conversaciones|Activado|Activado|
|||Vistas previas de url|Activado|Activado|
|||Traducir mensajes|Activado|Activado|
|||Lector inmersivo para mensajes|Activado|Activado|
|||Enviar mensajes urgentes con notificaciones prioritarias|Activado|Activado|
|||Crear mensajes de voz|Permitido en chats y canales|Permitido en chats y canales|
|||En dispositivos móviles, mostrar los canales favoritos encima de los chats recientes|Habilitado|Habilitado|
|||Quitar usuarios de chats grupales|Activado|Activado|
|Directiva de llamadas||Realizar llamadas privadas|Activado|Activado|
|||Desvío de llamadas y llamadas simultáneas a personas de su organización|Activado|Activado|
|||Desvío de llamadas y llamadas simultáneas a números de teléfono externos|Activado|Activado|
|||El correo de voz está disponible para enrutar llamadas entrantes|Controlado por el usuario|Controlado por el usuario|
|||Las llamadas entrantes se pueden enrutar a grupos de llamadas|Activado|Activado|
|||Permitir la delegación para llamadas entrantes y salientes|Activado|Activado|
|||Evitar la omisión de pago y enviar llamadas a través de la RTC|Desactivado|Desactivado|
|||Ocupado ocupado está disponible cuando está en una llamada|Desactivado|Desactivado|
|||Permitir llamadas RTC web|Activado|Activado|

## <a name="related-topics"></a>Temas relacionados

- [Directivas de Teams y paquetes de directivas para educación](policy-packages-edu.md)
- [Asignar directivas a grandes conjuntos de usuarios de su centro educativo](batch-group-policy-assignment-edu.md)
- [Mantener a los alumnos seguros mientras usan Teams para el aprendizaje a distancia](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
