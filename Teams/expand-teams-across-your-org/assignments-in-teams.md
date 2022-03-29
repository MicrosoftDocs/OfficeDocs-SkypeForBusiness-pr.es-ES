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
description: Obtenga información sobre cómo administrar tareas en el centro Microsoft Teams administración en Teams para Educación.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 529240db27824ce8bf872d23636b904198ef7db1
ms.sourcegitcommit: ecc67b7b9378cc72f85517f30c32680045056fda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2022
ms.locfileid: "64504140"
---
# <a name="assignments-in-teams-for-education"></a>Tareas en Teams para educación

Las características Tareas y calificaciones de Teams para Educación permiten a los profesores asignar tareas, trabajos o cuestionarios a sus alumnos. Los formadores pueden administrar las escalas de tiempo de las tareas, las instrucciones, agregar recursos para entregar, calificar con las indicaciones y mucho más. También pueden realizar un seguimiento del progreso de clase y de alumno individual en la pestaña Calificaciones.

[Obtenga más información sobre Tareas y calificaciones en Teams para Educación](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Para obtener más información Teams tareas en distintas plataformas, [vea Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integraciones de asignaciones en el centro Microsoft Teams administración

Con la configuración de administración del centro Microsoft Teams administración, puede activar o desactivar las características para los profesores de su organización y sus alumnos. A continuación se muestra la configuración relacionada con Tareas:

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>Resumen de correo electrónico de tutor semanal

Los correos electrónicos de los tutores se envían cada fin de semana a los padres o tutores. El correo electrónico contiene información sobre las tareas de la semana anterior y de la semana siguiente. La sincronización de padres y tutores se puede configurar con [School Data Sync](/schooldatasync/parent-contact-sync).

1. Importar la información de contacto de los padres a través de La sincronización de padres y tutores en SDS. Para obtener instrucciones sobre cómo habilitar la sincronización entre padres y tutores, vea [Habilitar la sincronización entre padres y tutores](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. Active la configuración del tutor en el centro Microsoft Teams administrador, ya que la configuración está desactivada de forma predeterminada. Esto permitirá a los profesores enviar un resumen semanal.

   > [!NOTE]
   > Los profesores pueden optar por no participar en el resumen anulando la selección de la configuración dentro de su propio equipo personal de clase (tareas Configuración > correo electrónico de padres **o tutores**).

Para comprobar que los padres recibirán el correo electrónico, deben cumplirse los tres elementos siguientes:

- Dirección de correo electrónico adjunta al perfil de alumno en SDS y etiquetada como _Padres_ o _Tutores_. Para obtener más información, vea [Formato de archivo de sincronización de padres y tutores](/schooldatasync/parent-contact-sync-file-format).

- Los alumnos pertenecen al menos a una clase en la que el profesor no deshabilita el correo electrónico en la configuración [de la tarea](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).

- Los correos electrónicos contendrán información sobre las tareas que tienen una fecha de vencimiento de la semana anterior o de la semana próxima.

La configuración predeterminada para esta característica es - **Desactivado**.

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode es una plataforma de codificación basada en bloques que da vida a la informática para todos los alumnos.

MakeCode es un producto de Microsoft que está sujeto a las condiciones [de uso y](https://go.microsoft.com/fwlink/?LinkID=206977) las directivas [de privacidad de](https://go.microsoft.com/fwlink/?LinkId=521839) Microsoft.

La configuración predeterminada para esta característica es - **Desactivado**.

Para habilitar las asignaciones de MakeCode en Teams, vaya al Centro de administración de Teams, vaya **a** la sección Tareas y  active la opción de alternancia MakeCode a **Activar**. Seleccione **Guardar**. Espere unas horas para que esta configuración suba a efecto.

Para obtener más información sobre cómo funciona esta característica, vea esta [demostración en vídeo](https://makecode.com/blog/teams/teams-assignments).

[Obtenga más información sobre MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin es](https://www.turnitin.com/) un servicio de integridad académica. Este es un servicio de terceros que está sujeto a sus propios términos y política de privacidad. Usted es responsable del uso de los productos y servicios de terceros.

La configuración predeterminada para esta característica es - **Desactivado**.

Para habilitar Turnitin para su organización, necesitará una suscripción a Turnitin. A continuación, puede introducir la siguiente información, que se puede encontrar en la consola de administración de Turnitin:

- **TurnitinApiKey**: se trata de un GUID de 32 caracteres que se encuentra en la consola de administración en Integraciones.
- **TurnitinApiUrl**: esta es la dirección URL HTTPS de la consola de administración de Turnitin.

Estas son algunas instrucciones para ayudarle a obtener esta información.

**TurnitinApiUrl** es la dirección de host de la consola de administración.
Ejemplo: `https://your-tenant-name.turnitin.com`

La consola de administración es donde puede crear una integración y una clave de API asociada a la integración.

Seleccione **Integraciones en** el menú lateral, seleccione **Agregar integración** y asigne un nombre a la integración.

![Captura de pantalla que muestra cómo agregar una nueva integración.](./educationImages/Assignments_mopo_turnitin2.png)

El **TurnitinApiKey** se le dará después de seguir las indicaciones.
Copie la clave de API y péguela en el Microsoft Teams de administración.  Esta es la única vez que puede ver la clave.

![Captura de pantalla que muestra cómo copiar la clave de API.](./educationImages/Assignments_mopo_turnitin3.png)

Al hacer clic en **el botón** Guardar del Centro de administración para esta configuración, espere unas horas para que esta configuración suba a efecto.

## <a name="assignments-data"></a>Datos de asignaciones

Las tareas almacenan información generada tanto por profesores como por alumnos. Todos los datos se comparten de forma compartida entre el profesor y el alumno específico para el que está destinada la información en clase. Hay dos almacenes de estos datos, SharePoint y fuera de SharePoint.

>[!NOTE]
>Las mismas reglas también se aplican a las integraciones de terceros, como progreso de lectura.

### <a name="assignments-data-in-sharepoint-document-libraries"></a>Datos de asignaciones en SharePoint de documentos

Los archivos de los alumnos asociados con un envío para la tarea se almacenan en una biblioteca de documentos (denominada: *Trabajo del alumno*). Los archivos asociados con tareas creadas por profesores y accesibles por los alumnos se almacenan en otra biblioteca de documentos (*denominada: Archivos* de clase) en el sitio de SharePoint clase correspondiente. Las integraciones de primera parte también pueden almacenar datos de asignaciones en el mismo sitio de grupo de SharePoint clase correspondiente (denominado: Título *de tareas + marca de tiempo*).

#### <a name="files-associated-with-the-student"></a>Archivos asociados con el alumno

Los administradores de TI pueden usar la herramienta búsqueda de contenido para buscar archivos de *alumno (trabajo* del *alumno, archivos* de clase u otros archivos de integración de terceros) relacionados con envíos de tareas y archivos relacionados con tareas. Por ejemplo, un administrador podría buscar en todos los sitios SharePoint de la organización y usar el nombre y el nombre de clase o tarea del alumno en la consulta de búsqueda para buscar datos relevantes para una solicitud de interesado (DSR).

#### <a name="files-associated-with-the-teacher"></a>Archivos asociados con el profesor

Los administradores de TI pueden usar la herramienta búsqueda de contenido para buscar archivos de *profesor (trabajo* del *alumno, archivos* de clase u otros archivos de integración de terceros) relacionados con tareas y archivos distribuidos a los alumnos por los profesores dentro de una clase en tareas. Por ejemplo, un administrador podría buscar en todos los sitios SharePoint de la organización y usar el nombre del profesor y el nombre de clase o tarea en la consulta de búsqueda para buscar datos relevantes para un DSR.

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>Asigna datos fuera de SharePoint bibliotecas de documentos

Algunos datos relacionados con Tareas no se almacenan en el equipo de clase SharePoint sitio, lo que significa que no se pueden detectar con la búsqueda de contenido. Esto incluye:

- Calificaciones de los alumnos y comentarios del profesor
- La lista de documentos enviados para una tarea por cada alumno
- Detalles de la tarea como Fecha de vencimiento, etc.
- Datos de integración de primera, como pasajes de progreso de lectura o datos de pronunciación de alumnos

Para este tipo de datos, un administrador de TI o un propietario de datos, como un profesor, pueden tener que ir a la tarea en el equipo de clase para buscar datos relevantes para un DSR. El administrador puede agregarse como propietario a la clase y ver todas las tareas de ese equipo de clase.

>[!NOTE]
>Si un alumno ya no forma parte de la clase, es posible que sus datos aún están presentes en la clase, ya *que ya no están inscritos*. El alumno tendrá que proporcionar al administrador de inquilinos la lista de las clases de las que formaron parte.

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>Exportar datos de asignación en masa fuera SharePoint bibliotecas de documentos

#### <a name="for-a-student"></a>Para un alumno

Para exportar en masa los datos de un solo alumno, antes de quitar al alumno de las clases de las que forman parte, ejecute el  [script](/microsoft-365/education/deploy/configure-assignments-for-teams) y proporcione el ``userId``archivo . Si el alumno se ha quitado del sitio, el administrador puede volver a agregar el alumno a la clase antes de ejecutar el script, ``userId`` ``classId`` o el administrador puede proporcionar el y el del que el alumno formaba parte alguna vez.

Los datos sobre los envíos de los alumnos se exportarán.

#### <a name="for-a-teacher"></a>Para un profesor

Los datos de tareas de exportación en masa funcionan del mismo modo para un alumno, pero todos los envíos a los que tiene acceso el profesor se exportarán.

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>Eliminar datos de asignación en masa fuera de SharePoint bibliotecas de documentos

#### <a name="for-a-student"></a>Para un alumno

Para eliminar en masa los datos de un solo alumno, antes de quitar al alumno de las clases de las que forman parte, ejecute el [script](/microsoft-365/education/deploy/configure-assignments-for-teams) y proporcione el ``userId``archivo . Si el alumno se ha quitado del sitio, el administrador puede volver a agregar el alumno a la clase antes de ejecutar el script, ``userId`` ``classId`` o el administrador puede proporcionar el y el del que el alumno formaba parte alguna vez.

Al proporcionar una ``ClassId`` , el administrador solo podrá eliminar información sobre el alumno de una clase específica.

#### <a name="for-a-teacher"></a>Para un profesor

Puesto que los datos de una tarea para un profesor se comparten en toda la clase, no hay ninguna opción de eliminación masiva. En su lugar, el administrador puede agregarse a la clase, ir a la aplicación y eliminar la tarea.

Para obtener más información,  [veaConfigurar tareas para Teams](/microsoft-365/education/deploy/configure-assignments-for-teams).

## <a name="removing-assignments-and-grades"></a>Quitar tareas y calificaciones

También puede usar directivas Teams para quitar tareas y calificaciones para un usuario específico o para todo el espacio empresarial.

Para quitar tareas y calificaciones para un usuario individual, vaya al Centro de administración de Teams y vaya **a** Teams aplicaciones  > directivas de permisos para crear una nueva definición de directiva de permisos de aplicación.  Al crear la nueva definición de directiva, establezca la directiva de  aplicaciones de **Microsoft** en Bloquear aplicaciones específicas, permitir  a todos los demás y agregar Asignaciones a la lista de aplicaciones bloqueadas. Una vez guardada la nueva definición de directiva, asígnela a los usuarios adecuados.

Para quitar tareas y calificaciones para todo el espacio empresarial, vaya al Centro de administración de Teams, vaya  **a Teams aplicaciones >** Administrar aplicaciones y busque y seleccione Tareas en la lista de aplicaciones. Cambie la configuración de estado de la página Configuración de la aplicación de asignación a _Bloqueado_.

## <a name="assignments-diagnostic-tool-for-users"></a>Herramienta de diagnóstico de asignaciones para usuarios

El soporte técnico de Microsoft ha creado una herramienta para recopilar datos de diagnóstico para el equipo de ingeniería de Microsoft para investigar los problemas relacionados con la característica Tareas.

Se puede acceder a esta herramienta dentro de Tareas en cualquier pantalla en la que los usuarios experimente un problema.

Para extraer la herramienta de diagnóstico en Teams, los usuarios pueden:

- **En escritorio y web:**
  - Seleccione Ctrl+/
- **En dispositivos móviles:**
  - Toca la pantalla con dos dedos y gira los dedos 45 grados, o
  - Pulse en la pantalla con tres dedos durante 15 segundos

Una vez que la herramienta de diagnóstico aparece, los usuarios verán una lista de datos que pueden ser necesarios por el soporte técnico de Microsoft.

Los datos que se extrayes pueden incluir:

- Id. de grupo
- ID. del espacio empresarial
- Id. de sesión
- Id. de asignación
- Id. de envío
- Id. de usuario

Estos datos no se envían automáticamente a Microsoft. Los usuarios deben copiar y pegar los datos en un agente de soporte técnico de Microsoft con respecto a un vale de soporte técnico.

Si un usuario extrae la herramienta de diagnóstico y la cierra, no se envían datos.

Cuando los datos se envían a un agente de soporte técnico de Microsoft, se administran como datos de soporte técnico en los contratos de servicio Microsoft 365 organización.

Para obtener instrucciones sobre el uso de esta herramienta de diagnóstico que puede compartir con profesores y alumnos, vea Obtener datos [de diagnóstico para solucionar problemas de tareas](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e).
