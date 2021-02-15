---
title: Sincronizar datos del Sistema de información de estudiantes (SIS) con Insights para Educación
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Sincronizar datos del Sistema de información de estudiantes (SIS) con Insights para Educación en Microsoft Teams
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f6d4a7dca340d297543abb3620a36cdd804ca9f
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196584"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>Sincronizar datos del Sistema de información de estudiantes (SIS) con Insights para Educación
Cuando más datos introduzca en [Insights para Educación](class-insights.md), mejor podrán los formadores ayudar a los alumnos y más fácil será para los líderes educativos ayudar a los formadores.

Para emplear Insights a nivel de la organización, es necesario usar [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) para conectarse al Sistema de información de estudiantes (SIS) de modo que Insights tenga la estructura jerárquica del sistema educativo asignada correctamente. 

Para ver Insights a nivel de clase como formador de clase *no* necesita esta sincronización, ya que usamos los permisos y la estructura de clase de Teams.

## <a name="plan-your-sis-integration"></a>Planear la integración del SIS
Los datos del SIS proporcionan la estructura jerárquica del sistema educativo y asignan adónde se destina a cada usuario.

Insights funciona mejor cuando se usa el [formato de archivo de SDS V2](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format), pero también es compatible con un formato de archivo [SDS V1](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds) con una funcionalidad *limitada*.

### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Diferencias entre los formatos de archivo SDS V1 y V2

| Tipo de datos |   V1 | V2 (recomendado para nuevos clientes) |
|:--- |:--- |:--- |
| **Usuarios** | El formato V1 contiene **solo formadores**, por lo que para establecer permisos a nivel de organización para los responsables del ámbito educativo, deberá buscarlos y definir manualmente los permisos de cada uno. | El formato V2 contiene **todos los roles** para que pueda asignar permisos basados en roles. |
| **Organizaciones** | El formato V1 contiene **solo escuelas**, por lo que verá únicamente un nivel de agregación (todas las escuelas). Aunque una lista plana le permite centrarse en una escuela específica, es posible que esta lista tenga un gran número de escuelas o que contenga diferentes tipos de escuelas que sean difíciles de comparar (como la escuela primaria y la secundaria o la escuela de ciencias y la de artes).<br/><br/> Con una jerarquía, puede crear niveles lógicos, como un departamento de ciencias o de arte.| El formato V2 contiene **la jerarquía completa de su distrito o institución**, incluidas universidades, facultades, campus, regiones, programas, etc.<br/><br/> Con una jerarquía, puede ver la agregación relevante por cada nivel de la jerarquía, comparar rápidamente entre unidades de la organización a cada nivel, asignar permisos a niveles específicos, establecer objetivos por nivel de la organización y así sucesivamente.|

### <a name="type-of-data-required"></a>Tipos de datos necesarios
En la tabla siguiente le mostramos el tipo de datos necesario para sacar el mayor provecho de Insights.

| Tipo de datos | Ejemplos de lo que necesita proporcionar|¿Por qué es importante?|
|:--- |:--- |:--- |
| **Usuarios** |   Rol (por ejemplo, alumno)<br/> [Curso](#supported-grade-level-values) (por ejemplo, 6.º)<br/> Organización (nombre) | Asignar correctamente cada persona a su rol, curso y organización, nos asegura que los resúmenes y agregaciones sean los correctos.|
| **Organizaciones** | Tipo de organización (por ejemplo, la universidad) |   La jerarquía es importante aquí. Por ejemplo, las escuelas pueden pertenecer a un distrito y ese distrito puede pertenecer a un estado.<br/> A un líder educativo del distrito solo se le permite ver datos para las escuelas de ese distrito.|
| **Clases** | Título (por ejemplo, Informática I) | En esta tabla se destacan las clases impartidas en la organización. Esta tabla deben incluir las asignaciones correctas para que podamos asignar la clase apropiada al alumno. |
| **Inscripción** | Rol (por ejemplo, alumno) | Esta tabla está disponible para alumnos y formadores y nos permite conocer en qué clase están inscritos. |

> [!NOTE]
> Durante el proceso de implementación, puede decidir si quiere usar SDS para aprovisionar usuarios y clases en Teams o solo para proporcionar datos a Insights.

## <a name="best-practices"></a>Procedimientos recomendados
Una jerarquía con las asignaciones adecuadas y en la que todos los miembros pertenecen al nivel correcto permite que Insights ofrezca datos precisos y conclusiones relevantes para los distintos tipos de líderes educativos.

Cuantos más detalle proporcione aquí, mejores y más relevantes serán los informes y los datos destacados.
Estos son algunos procedimientos recomendados para garantizar una implementación sencilla de SDS con la que los usuarios puedan sacar el máximo partido a Insights.

### <a name="users"></a>Usuarios
*   Asegúrese de que *todos los usuarios* aparecen listados en los archivos que proporciona y sincroniza. Esto incluye todos los alumnos y el personal que necesite ver datos para las unidades de organización que abarquen.

    Si actualmente solo tiene profesores listados en el SIS, agregue los demás usuarios manualmente antes de cargar los archivos al SIS y sincronizar los datos.

    Si faltan algunos alumnos, las estadísticas que recopile Insights no los incluirán, por lo que los datos y las conclusiones pueden ser equívocas.
    
*   Asegúrese de *proporcionar el nombre y los apellidos de cada usuario*. Si no es así, se hará referencia a ellos con su dirección de correo electrónico, lo que proporciona una experiencia menos positiva en los informes y datos destacados (tarjetas con Insights en la actividad o el rendimiento de los alumnos).

*   El *curso debe introducirse con 2 dígitos* (por ejemplo, 07 para el séptimo curso). Vea los detalles de [Asignación de lista](#supported-grade-level-values). 

*   Es importante *agregar el curso de todos los alumnos* para poder filtrar los datos por curso.    

*   Asegúrese de *asignar cada usuario a su unidad organizativa*. De esta forma, no mostraremos datos acumulados erróneos en nuestros datos destacados basados en datos agregados para cada unidad.

    *   Un alumno se puede asociar con más de una unidad organizativa, por ejemplo, alumnos registrados en un programa especial o en dos facultades. En este caso, proporcione dos líneas en el archivo de usuarios para ese alumno, una para cada organización.
    
    *   Podrá definir los permisos relevantes en función de la unidad de organización para el personal. Asegúrese de que están asociados con el nivel de unidad correcto para que reciban los permisos que necesitan. Por ejemplo, un orientador asignado a cuatro escuelas necesita ver todas las clases de estas escuelas, mientras que un director debe poder ver todas las clases de su escuela. 
    
*   El rol es fundamental. Aunque se trata de una lista cerrada, intente hacer coincidir el rol de [la lista](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) con el rol real de cada usuario que cargue. De esta forma, puede asignar permisos basados en roles en consecuencia. Por ejemplo, proporcione permisos para que todos los directores vean las clases de su escuela, o para que todos los profesores vean su facultad. 

### <a name="organizations"></a>Organizaciones

* Asegúrese de reflejar la *jerarquía real de la organización*. Esto puede lograrse agregando el archivo manualmente. En algunos casos, esta jerarquía no se refleja en el SIS. Aun así, puede que necesite ver la agregación relevante por cada nivel de la jerarquía, asignar permisos a niveles específicos, establecer objetivos por nivel de organización, etc. 

* Asegúrese de que *todas las unidades de organización en el árbol de organización incluyan alumnos o clases* para agregar datos de alumnos para ellas. Le recomendamos que los alumnos estén en la rama más baja del árbol.

> [!NOTE]
> Para obtener más información sobre la implementación de SDS, visite [SDS](https://docs.microsoft.com/schooldatasync/planning-school-data-sync).

## <a name="integrate-sis-using-sds"></a>Integrar SIS con SDS

School Data Sync (SDS) se proporciona con Microsoft Office 365 para el ámbito educativo. SDS lee los datos del Sistema de Información de Estudiantes (SIS) de una institución educativa y los integra con Teams para habilitar la creación automática de aulas y usuarios en línea.

También sincroniza los datos del SIS con Insights.

### <a name="sync-with-insights"></a>Sincronización con Insights

En primer lugar, debe activar el botón de alternancia de Insights para iniciar el proceso de sincronización.

* En el [**portal de SDS**](https://sds.microsoft.com), vaya a **Configuración**, desplácese hacia abajo hasta **Recopilar datos para Insights** y compruebe que está habilitado (está *activado* de forma predeterminada).

* Desplácese hacia abajo hasta el botón siguiente, llamado **Sincronizar datos de la organización desde SDS (versión preliminar)** y actívelo.

Si no ve la opción de *Sincronizar datos de la organización desde SDS (versión preliminar)* en la página Configuración, vaya a la [página de registro](https://aka.ms/insights/join) para proporcionar su información y un miembro del equipo se pondrá en contacto con usted.

:::image type="content" source="media/insights-sds-settings.png" alt-text="Sincronización con los botones de alternancia de Insights":::

### <a name="deploy-sds"></a>Implementar SDS
**Si ya usa SDS**, le recomendamos que siga nuestros [procedimientos recomendados](#best-practices). 

Para sincronizar los perfiles actuales con Insights, vaya a **Sincronizar perfiles**, haga clic en **Editar** y seleccione **Sincronizar con Insights**. Para la sincronización inicial, se recomienda esperar 24 horas a que los informes estén disponibles tras la actualización de los datos desde su SIS.  

:::image type="content" source="media/insights-sds-profile-sync.png" alt-text="Perfil de sincronización con botones de alternancia de Insights":::

**Si aún no usa SDS**, ahora necesitará [implementarlo](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync).

Durante el proceso de implementación, puede decidir si quiere usar SDS para aprovisionar usuarios y clases en Teams o solo para proporcionar datos a Insights.

> [!NOTE]
> Si está a mitades del año y ya creó los equipos manualmente, use SDS solo para proporcionar los datos a Insights y el año que viene considere la posibilidad de usar SDS para aprovisionar usuarios y clases en Teams.

### <a name="verify-the-sync-process"></a>Comprobar el proceso de sincronización
Ahora en la página Configuración debería aparecer una nueva área de estado junto a Sincronizar datos de SDS (versión preliminar).
 
*   Si el estado es **En curso**, espere hasta 24 horas después de la implementación del perfil de SDS.

*   Si el estado es **Completado**, ¡enhorabuena! Ya puede ver Insights a nivel de organización y continuar con el paso siguiente.

*   Si el estado es **Completado con errores**, **Completado con advertencias** o **Cancelado**, descargue el archivo de registro que contiene los errores y advertencias para la última sincronización y compruebe si puede corregir estos errores. 

> [!IMPORTANT]
> Si tiene algún problema, nuestra [atención al cliente](https://aka.ms/edusupport) estará encantada de ayudarle.

## <a name="supported-grade-level-values"></a>Valores admitidos en el nivel de la curso

En los archivos SDS, el nivel de curso/año se define como valores enumerados, lo que significa que solo puede proporcionar un conjunto seleccionado de valores dentro del archivo .CSV. Cualquier valor distinto de los valores especificados producirá un error durante el proceso de sincronización.

> [!NOTE]
> El *curso/año debe introducirse con 2 dígitos* (por ejemplo, 07 para el séptimo curso).

En la sección siguiente se definen los valores admitidos en el archivo de usuarios.

### <a name="united-states--worldwide-grade-levels"></a>Niveles de la curso de Estados Unidos y el mundo
|Valor en archivo (columna Curso) | Etiqueta en Insights|
|:---|:---| 
|TI|Infantil|
|PR|Preescolar|
|PK|Pre-kindergarten|
|TK|Preescolar de transición|
|KG|Jardín de infancia|
|01|Primer curso|
|02|Segundo curso|
|03|Tercer curso|
|04|Cuarto curso|
|05|Quinto curso|
|06|Sexto curso|
|07|Séptimo curso|
|08|Octavo curso|
|09|Noveno curso|
|10|Décimo curso|
|11|Undécimo curso|
|12|Duodécimo curso|
|PS|Estudios superiores|
|PS1|Estudios superiores primer año|
|PS2|Estudios superiores segundo año|
|PS3|Estudios superiores tercer año|
|PS4|Puesto último año|
|pregrado|Pregrado|
|graduado|Graduado|
|postgrado|Postgrado (graduado con énfasis en investigación)|
|alumnos|Alumnos|
|educación adulta|Educación adulta|
|UG|Sin calificar|
|Otros|Otros|

### <a name="united-kingdom-year-groups"></a>Grupos de años del Reino Unido
|Valor en archivo (columna Curso) | Etiqueta en Insights|
|:---|:---| 
|TI|Infantil|
|PR|Preescolar|
|PK|Infantil (segundo ciclo)|
|01|Infantil (tercer curso)|
|02|1.º de Primaria|
|03|2.º de Primaria|
|04|3.º de Primaria|
|05|4.º de Primaria|
|06|5.º de Primaria|
|07|6.º de Primaria|
|08|1.º de ESO|
|09|2.º de ESO|
|10|3.º de ESO|
|11|4.º de ESO|
|12|1.º de Bachillerato|
|13|2.º de Bachillerato|
|PS|Estudios superiores|
|PS1|Estudios superiores primer año|
|PS2|Estudios superiores segundo año|
|PS3|Estudios superiores tercer año|
|PS4|Estudios superiores cuarto año|
|pregrado|Pregrado|
|graduado|Graduado|
|postgrado|Postgrado (graduado con énfasis en investigación)|
|alumnos|Alumnos|
|educación adulta|Educación adulta|
|UG|Sin calificar|
|Otros|Otros|
