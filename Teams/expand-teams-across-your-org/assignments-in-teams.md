---
title: Tareas de Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Obtenga información sobre cómo administrar tareas en el centro de administración de Microsoft Teams de Teams para Educación.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed8b01b683d201bc26dec3d220c94fbc12e76f1c
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674672"
---
# <a name="assignments-in-teams-for-education"></a>Tareas en Teams para educación

Las características Tareas y calificaciones de Teams para Educación permiten a los profesores asignar tareas, trabajos o cuestionarios a sus alumnos. Los formadores pueden administrar escalas de tiempo de tareas, instrucciones, agregar recursos para entregar, calificar con pautas y mucho más. También pueden realizar un seguimiento del progreso de alumnos individuales y de clase en la pestaña Calificaciones.

[Obtenga más información sobre Tareas y calificaciones en Teams para Educación](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Para obtener más información sobre Teams tareas en distintas plataformas, vea [Teams características por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integraciones de tareas en el centro de administración de Microsoft Teams

Con la configuración de administrador del centro de administración de Microsoft Teams, puede activar o desactivar las características para los formadores de su organización y sus alumnos. A continuación, se muestran las opciones relacionadas con las tareas:

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>Resumen semanal del correo electrónico de tutor

Los correos electrónicos de tutores se envían cada fin de semana a los padres o tutores. El correo electrónico contiene información sobre las tareas de la semana anterior y de la semana próxima. La sincronización de padres y tutores se puede configurar con [School Data Sync](/schooldatasync/parent-contact-sync).

1. Importe la información de contacto de los padres a través de Parent and Guardian Sync en SDS. Para obtener instrucciones sobre cómo habilitar la sincronización de padres y tutores, consulte [Habilitar la sincronización de padres y tutores](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. Activa la configuración de tutor en el centro de administración de Microsoft Teams, ya que la configuración está desactivada de manera predeterminada. Esto permitirá a los profesores enviar un resumen semanal.

   > [!NOTE]
   > Los profesores pueden optar por no participar en el resumen anulando la selección de la configuración dentro de su propio equipo de clase personal (**tareas Configuración > correos electrónicos de padres o tutores**).

Para comprobar que los padres recibirán el correo electrónico, deben cumplirse los tres elementos siguientes:

- Dirección de correo electrónico adjunta al perfil de alumno en SDS y etiquetada como _padre_ o _tutor_. Para obtener más información, consulte [Formato de archivo de sincronización de padres y tutores](/schooldatasync/parent-contact-sync-file-format).

- Los alumnos pertenecen al menos a una clase en la que el profesor no ha deshabilitado el correo electrónico en la [configuración de la tarea](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).

- Los correos electrónicos contendrán información sobre las tareas que tienen una fecha de vencimiento de la semana anterior o de la próxima semana.

La configuración predeterminada para esta característica es - **Desactivado**.

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode es una plataforma de codificación basada en bloques que da vida a la informática para todos los estudiantes.

MakeCode es un producto de Microsoft que está sujeto a los [términos de uso y las directivas de](https://go.microsoft.com/fwlink/?LinkID=206977) [privacidad](https://go.microsoft.com/fwlink/?LinkId=521839) de Microsoft.

La configuración predeterminada para esta característica es - **Desactivado**.

Para habilitar las tareas de MakeCode en Teams, vaya al **Centro de Teams Administración**, vaya a la sección **Tareas** y cambie la opción de alternancia de MakeCode a **Activado**. Seleccione **Guardar**. Espere unas horas para que esta configuración surta efecto.

Para obtener más información sobre cómo funciona esta característica, vea esta [demostración en vídeo](https://makecode.com/blog/teams/teams-assignments).

[Más información sobre MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) es un servicio de integridad académica. Se trata de un servicio de terceros que está sujeto a sus propios términos y directivas de privacidad. Usted es responsable del uso que haga de los productos y servicios de terceros.

La configuración predeterminada para esta característica es - **Desactivado**.

Para habilitar Turnitin para su organización, necesitará una suscripción de Turnitin. A continuación, puede introducir la siguiente información, que puede encontrarse en la consola de administración de Turnitin:

- **TurnitinApiKey**: Este es un GUID de 32 caracteres que se encuentra en la consola de administración en Integraciones.
- **TurnitinApiUrl**: esta es la dirección URL HTTPS de la consola de administración de Turnitin.

Estas son algunas instrucciones que te ayudarán a obtener esta información.

**TurnitinApiUrl** es la dirección host de la consola de administración.
Ejemplo: `https://your-tenant-name.turnitin.com`

La consola de administración es donde puede crear una integración y una clave de API asociada con la integración.

Seleccione **Integraciones** en el menú lateral, seleccione **Agregar integración** y asigne un nombre a la integración.

![Captura de pantalla que muestra cómo agregar una nueva integración.](./educationImages/Assignments_mopo_turnitin2.png)

La **TurnitinApiKey** se le proporcionará después de seguir las indicaciones.
Copie la clave de API y péguela en el centro de administración de Microsoft Teams.  Esta es la única vez que puede ver la clave.

![Captura de pantalla que muestra cómo copiar la clave de API.](./educationImages/Assignments_mopo_turnitin3.png)

Al hacer clic en el botón **Guardar** en el centro de administración para esta configuración, espere unas horas para que esta configuración surta efecto.

## <a name="assignments-data"></a>Datos de asignaciones

Las tareas almacenan información generada tanto por profesores como por alumnos. Todos los datos se comparten entre el profesor y el alumno específico para el que la información está destinada en clase. Existen dos almacenes de estos datos, SharePoint y fuera de SharePoint.

>[!NOTE]
>Las mismas reglas también se aplican a integraciones de origen, como Progreso de lectura.

### <a name="assignments-data-in-sharepoint-document-libraries"></a>Datos de asignaciones en bibliotecas de documentos de SharePoint

Los archivos de los alumnos asociados a un envío de tarea se almacenan en una biblioteca de documentos (denominada: *Trabajo del alumno*). Los archivos asociados a tareas creadas por profesores y accesibles por los alumnos se almacenan en otra biblioteca de documentos (denominada Archivos de *clase*) en el sitio de SharePoint del equipo de clase correspondiente. Las integraciones de origen también pueden almacenar datos de tareas en el mismo sitio de SharePoint del equipo de clase correspondiente (denominado: *Título de las tareas + marca de tiempo*).

#### <a name="files-associated-with-the-student"></a>Archivos asociados con el alumno

Los administradores de TI pueden usar la herramienta de búsqueda de contenido para buscar archivos de alumnos (*trabajo* de estudiantes, *archivos de clase* u otros archivos de integración de terceros) relacionados con envíos de tareas y archivos relacionados con tareas. Por ejemplo, un administrador podría buscar en todos los sitios de SharePoint de la organización y usar el nombre del alumno y el nombre de la clase o tarea en la consulta de búsqueda para buscar datos relevantes para una solicitud del interesado (DSR).

#### <a name="files-associated-with-the-teacher"></a>Archivos asociados con el profesor

Los administradores de TI pueden usar la herramienta de búsqueda de contenido para buscar archivos de profesores (*Trabajo* de alumnos, *Archivos de clase* u otros archivos de integración de terceros) relacionados con tareas y archivos distribuidos a los alumnos por los profesores dentro de una clase sobre tareas. Por ejemplo, un administrador podría buscar en todos los sitios de SharePoint de la organización y usar el nombre del profesor y el nombre de la clase o tarea en la consulta de búsqueda para buscar datos relevantes para un DSR.

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>Asignaciones de datos fuera de SharePoint bibliotecas de documentos

Algunos datos relacionados con tareas no se almacenan en el sitio SharePoint equipo de clase, lo que significa que no se pueden detectar con la búsqueda de contenido. Esto incluye:

- Calificaciones y comentarios de los alumnos del profesor
- Lista de documentos enviados para una tarea por cada alumno
- Detalles de tareas, como la fecha de vencimiento, etc.
- Datos de integración de origen, como pasajes de Progreso de lectura o datos de pronunciación de alumnos

Para este tipo de datos, es posible que un administrador de TI o el propietario de los datos, como un profesor, tenga que ir a la tarea del equipo de clase para buscar datos relevantes para un DSR. El administrador puede agregarse a sí mismo como propietario de la clase y ver todas las tareas de ese equipo de clase.

>[!NOTE]
>Si un alumno ya no forma parte de la clase, es posible que sus datos sigan estando presentes en la clase *, ya que ya no están inscritos*. El estudiante tendrá que proporcionar al administrador de inquilinos la lista de clases de las que alguna vez formaron parte.

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>Exportar datos de asignación en masa fuera de las bibliotecas de documentos de SharePoint

#### <a name="for-a-student"></a>Para un alumno

Para exportar en masa los datos de un solo alumno, antes de quitar al alumno de las clases de las que forma parte, [ejecute el script](/microsoft-365/education/deploy/configure-assignments-for-teams) y proporcione el ``userId``. Si el alumno se ha quitado del sitio, el administrador puede volver a agregar al alumno a la clase antes de ejecutar el script, o bien el administrador puede proporcionar la ``userId`` y la ``classId`` que el alumno ha formado parte en alguna ocasión.

Se exportarán los datos sobre los envíos de alumnos.

#### <a name="for-a-teacher"></a>Para un profesor

Los datos de las tareas de exportación en masa funcionan del mismo modo para un alumno, pero se exportarán todos los envíos a los que el profesor tenga acceso.

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>Eliminar en masa datos de asignación fuera de SharePoint bibliotecas de documentos

#### <a name="for-a-student"></a>Para un alumno

Para eliminar en masa los datos de un solo alumno, antes de quitar al alumno de las clases a las que pertenece, [ejecute el script](/microsoft-365/education/deploy/configure-assignments-for-teams) y proporcione el ``userId``. Si el alumno se ha quitado del sitio, el administrador puede volver a agregar al alumno a la clase antes de ejecutar el script, o bien el administrador puede proporcionar la ``userId`` y la ``classId`` que el alumno ha formado parte en alguna ocasión.

Al proporcionar una ``ClassId`` , el administrador solo podrá eliminar información sobre el alumno de una clase específica.

#### <a name="for-a-teacher"></a>Para un profesor

Dado que los datos de una tarea para un profesor se comparten en toda la clase, no hay ninguna opción de eliminación masiva. En su lugar, el administrador puede agregarse a sí mismo a la clase, ir a la aplicación y eliminar la tarea.

Para obtener más información, vea [Configurar tareas para Teams](/microsoft-365/education/deploy/configure-assignments-for-teams).

## <a name="removing-assignments-and-grades"></a>Quitar tareas y calificaciones

También puede usar directivas de Teams para quitar tareas y calificaciones de un usuario específico o de todo el espacio empresarial.

Para quitar tareas y calificaciones de un usuario individual, vaya a **Teams Administración Centro** y vaya a **Teams aplicaciones > Directivas** de permisos para crear una nueva definición de directiva de permisos de aplicación.  Al crear la nueva definición de directiva, establezca la directiva de **aplicaciones de Microsoft** en _Bloquear aplicaciones específicas y permitir el resto_ y agregar tareas a la lista de aplicaciones **bloqueadas** . Una vez guardada la nueva definición de directiva, asígnela a los usuarios adecuados.

Para quitar tareas y calificaciones de todo el inquilino, vaya a **Teams Administración Centro**, vaya a **Teams aplicaciones > Administrar aplicaciones** y busque y seleccione **Tareas** en la lista de aplicaciones. Cambie la configuración de estado de la página de configuración de la aplicación de asignación a _Bloqueada_.

## <a name="assignments-diagnostic-tool-for-users"></a>Herramienta de diagnóstico de asignaciones para usuarios

Soporte técnico de Microsoft ha creado una herramienta para recopilar datos de diagnóstico para que el equipo de ingeniería de Microsoft investigue los problemas relacionados con la característica Tareas.

Se puede acceder a esta herramienta dentro de Tareas en cualquier pantalla en la que los usuarios experimentan un problema.

Para extraer la herramienta de diagnóstico en Teams, los usuarios pueden:

- **En el escritorio y en la Web:**
  - Seleccione Ctrl+/
- **En dispositivos móviles:**
  - Toque la pantalla con dos dedos y gire los dedos 45 grados, o
  - Pulsar en la pantalla con tres dedos durante 15 segundos

Una vez que aparezca la herramienta de diagnóstico, los usuarios verán una lista de datos que puede necesitar el soporte técnico de Microsoft.

Los datos extraídos pueden incluir:

- Id. de grupo
- ID. del espacio empresarial
- Id. de sesión
- Id. de tarea
- Id. de envío
- Id. de usuario

Estos datos no se envían automáticamente a Microsoft. Los usuarios deben copiar y pegar los datos a un agente de soporte técnico de Microsoft en relación con una incidencia de soporte técnico.

Si un usuario extrae la herramienta de diagnóstico y la cierra, no se envía ningún dato.

Cuando los datos se envían a un agente de soporte técnico de Microsoft, se tratan como Datos de soporte técnico en virtud de los contratos de servicio Microsoft 365 de su organización.

Para obtener instrucciones sobre el uso de esta herramienta de diagnóstico que puede compartir con profesores y alumnos, vea [Obtener datos de diagnóstico para solucionar problemas de tareas](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e).
