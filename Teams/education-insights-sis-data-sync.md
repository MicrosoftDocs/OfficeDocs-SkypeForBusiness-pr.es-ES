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
ms.openlocfilehash: 5d5ba5c2c5179d5c333472450fd9b2e9c270a4e9
ms.sourcegitcommit: 7579dda8018691eb1a724cb0311b53333dc3ae5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "53142846"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>Sincronizar datos del Sistema de información de estudiantes (SIS) con Insights para Educación
Cuando más datos introduzca en [Insights para Educación](class-insights.md), mejor podrán los formadores ayudar a los alumnos y más fácil será para los líderes educativos ayudar a los formadores.

Para emplear Insights a nivel de la organización, es necesario usar [School Data Sync (SDS)](/SchoolDataSync) para conectarse al Sistema de información de estudiantes (SIS) de modo que Insights tenga la estructura jerárquica del sistema educativo asignada correctamente. 

Para ver Insights a nivel de clase como formador de clase *no* necesita esta sincronización, ya que usamos los permisos y la estructura de clase de Teams.

## <a name="plan-your-school-data-sync-integration"></a>Planear la integración de School Data Sync
Microsoft School Data Sync (o SDS) proporciona datos del Sistema de información escolar (o SIS) y su estructura jerárquica del sistema educativo y determina adónde se asigna un usuario particular. También ofrece datos adicionales sobre la jerarquía de alumnos y organizaciones.

Insights funciona mejor cuando se usa el [formato de archivo de SDS V2.1](/schooldatasync/sds-v2.1-csv-file-format), pero también es compatible con un [formato de archivo SDS V2](/schooldatasync/sds-v2-csv-file-format) y [formato de archivo SDS V1](/schooldatasync/school-data-sync-format-csv-files-for-sds) *con una funcionalidad limitada*.


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Diferencias entre los formatos de archivo SDS V1 y V2

| Tipo de datos | V1 | V2 y V2.1 |
|:--- |:--- |:--- |
| **Usuarios** |Solo admite el rol de "formador", como resultado, los permisos de nivel de organización para los líderes educativos deben establecerse manualmente.|Admite varios roles para que se puedan establecer permisos basados en roles|
| **Organizaciones** | Solo admite "escuelas", nivel de agregación.<br><br>Como resultado, no proporciona varios niveles de agregación y proporciona una capacidad limitada para comparar diferentes tipos de escuelas (por ejemplo, primaria frente a secundaria, ciencias frente a escuela de arte).|Admite jerarquías de varias capas, como distrito o institución, universidades, facultades, profesores, campus, regiones, programas, etc.<br><br>Permite varios niveles de agregación y comparar fácilmente entre unidades organizativas en cada nivel, asignar permisos a niveles específicos, establecer objetivos por nivel de organización, etc.|
| **Información opcional adicional** |Ninguna|**Solo formato de archivo V2.1**<br><br>*Sesiones académicas*: períodos de tiempo de sesiones (semestres, años académicos, etc.)<br><br>Datos demográficos y banderas de estudiantes*: datos como la raza,	etnia y género, así como programas especiales (IEP, 504)|

> [!NOTE]
> Los clientes no podrán incorporar el formato de archivo v2 a partir del 15 de julio de 2021 y tendrán que usar el formato v2.1 en su lugar. Todas las actualizaciones y capacidades futuras se realizarán en el formato v2.1 con retrocompatibilidad con el formato de archivo v1.

### <a name="best-practices"></a>Procedimientos recomendados

Una jerarquía con las asignaciones adecuadas y en la que todos los miembros pertenecen al nivel correcto permite que Insights ofrezca datos precisos y conclusiones relevantes para los distintos tipos de líderes educativos.

Cuantos más detalle proporcione, mejores y más relevantes serán los informes y los datos destacados.

#### <a name="file-format-version-to-use-adn-data-to-sync"></a>Versión del formato de archivo que se va a usar y datos para sincronizar
*   Use el formato de archivo V2.1 y sincronice los datos opcionales que use Insights para Educación como se indica [aquí](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv).

#### <a name="users-and-roles"></a>Usuarios y roles
*   Asegúrese de que **todos los usuarios** aparecen listados en los archivos que proporciona y sincroniza. Esto incluye todos los alumnos y el personal que necesite ver datos para las unidades de organización que abarquen.
*   Si actualmente solo tiene profesores listados en el SIS, agregue todos los demás usuarios manualmente antes de cargar los archivos al SDS y sincronizar los datos. Las estadísticas recopiladas por Insights serán solo de los alumnos registrados, si faltan algunos alumnos, los datos y las conclusiones no representarán al conjunto.
    
*   Si también usa SDS para el aprovisionamiento, asegúrese de **proporcionar el nombre y los apellidos de cada usuario**. De lo contrario, se hará referencia a los alumnos mediante su dirección de correo electrónico, lo que dará lugar a una experiencia poco óptima.

*   El nivel de curso o año debe basarse en esta [lista de asignaciones](#supported-grade-level-values). 

*   Asegúrese de **agregar el nivel de curso o año a todos los alumnos** .    

*   Asegúrese de **asignar cada usuario a su unidad organizativa**.

    *   Un alumno se puede asociar a más de una unidad organizativa, por ejemplo, alumnos registrados en un programa especial o en dos facultades. En caso de que el alumno tenga más de una unidad organizativa, proporcione una línea para cada una en el archivo de usuarios para ese alumno.
    
    *   El administrador de TI puede conceder permisos en función de la unidad organizativa para el personal. **Asegúrese de que los miembros del personal estén asociados con el nivel de unidad correcto**, para que reciban los permisos que necesitan. Por ejemplo, un orientador asignado a cuatro escuelas necesita ver todos los cursos de estas escuelas, mientras que un director debe poder ver todas las clases de su escuela. 
    
*   **El rol es fundamental**. Aunque se trata de una lista cerrada, intente hacer coincidir el rol de [la lista](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) con el rol real de cada usuario que cargue. De esta forma, puede asignar permisos basados en roles en consecuencia. Por ejemplo, proporcione permisos para que todos los directores vean las clases de su escuela, o para que todos los profesores vean su facultad. 

#### <a name="organizations"></a>Organizaciones

* Asegúrese de **reflejar la jerarquía real y completa de la organización**. En algunos casos, esta jerarquía no se refleja en el SIS, en cuyo caso debe agregarse manualmente al archivo CSV antes de la sincronización.

* Asegúrese de que **todas las unidades organizativas del árbol de organización incluyan alumnos o clases**. Le recomendamos que los alumnos estén en la rama más baja del árbol.

> [!NOTE]
> Para obtener más información sobre la implementación de SDS, visite [SDS](/schooldatasync/planning-school-data-sync).

## <a name="integrate-sis-data-using-sds"></a>Integrar SIS con SDS

School Data Sync (SDS) se proporciona con Microsoft Office 365 para el ámbito educativo. SDS lee los datos del Sistema de Información de Estudiantes (SIS) de una institución educativa y los integra con aplicaciones de Microsoft como Teams para habilitar la creación automática de aulas y usuarios en línea.

También sincroniza los datos del SIS con Insights.

Como administrador de TI, puede elegir usar SDS solo para el aprovisionamiento, solo para Insights o para ambos.

Para sincronizar la información de SIS con Insights para Educación, siga las instrucciones en [Cómo implementar SDS para Insights](/schooldatasync/how-to-deploy-sds-for-insights).

### <a name="deploy-sds"></a>Implementar SDS
**Si ya usa SDS**, le recomendamos que siga nuestros [procedimientos recomendados](#best-practices). 

**Si aún no usa SDS**, ahora necesitará [implementarlo](/schooldatasync/deploying-school-data-sync).

Durante el proceso de implementación, podrá decidir si desea usar SDS para aprovisionar usuarios y clases en Teams o solo para proporcionar una jerarquía de usuarios y organizaciones a Insights.

> [!NOTE]
> Si está a mitad del año y ya ha creado equipos manualmente, use SDS solo para proporcionar los datos de la jerarquía organizativa y los usuarios a Insights, y el próximo año considere la posibilidad de usar SDS también para aprovisionar usuarios y clases para Teams.

### <a name="verify-the-sync-process"></a>Comprobar el proceso de sincronización
Para comprobar el progreso del estado de sincronización, siga las instrucciones de [SDS para el estado de los datos y el seguimiento de Insights](/schooldatasync/sds-for-insights-data-health-and-monitoring).

> [!IMPORTANT]
> Si tiene algún problema, nuestra [atención al cliente](https://aka.ms/edusupport) estará encantada de ayudarle.

## <a name="supported-grade-level-values"></a>Valores admitidos en el nivel de la curso

En los archivos SDS, el nivel de curso/año se define como valores enumerados, lo que significa que solo puede proporcionar un conjunto seleccionado de valores dentro del archivo .CSV. Cualquier valor distinto de los valores especificados producirá un error durante el proceso de sincronización.

En la sección siguiente se definen los valores admitidos en el archivo de usuarios.

### <a name="united-states--worldwide-grade-levels"></a>Niveles de la curso de Estados Unidos y el mundo
|Valor en archivo (columna Curso) | Etiqueta en Insights|
|:---|:---| 
|TI|Infantil|
|PR|Preescolar|
|PK|Pre-kindergarten|
|TK|Preescolar de transición|
|KG|Jardín de infancia|
|01 o 1|Primer curso|
|02 o 2|Segundo curso|
|03 o 3|Tercer curso|
|04 o 4|Cuarto curso|
|05 o 5|Quinto curso|
|06 o 6|Sexto curso|
|07 o 7|Séptimo curso|
|08 o 8|Octavo curso|
|09 o 9|Noveno curso|
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
|01 o 1|Infantil (tercer curso)|
|02 o 2|1.º de Primaria|
|03 o 3|2.º de Primaria|
|04 o 4|3.º de Primaria|
|05 o 5|4.º de Primaria|
|06 o 6|5.º de Primaria|
|07 o 7|6.º de Primaria|
|08 o 8|1.º de ESO|
|09 o 9|2.º de ESO|
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

