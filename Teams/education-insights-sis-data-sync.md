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
ms.openlocfilehash: 9b0d9ae3788be09e4a66724e6122791a91b6879f
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997739"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>Sincronizar datos del Sistema de información de estudiantes (SIS) con Insights para Educación
Cuando más datos introduzca en [Insights para Educación](class-insights.md), mejor podrán los formadores ayudar a los alumnos y más fácil será para los líderes educativos ayudar a los formadores.

Para emplear Insights a nivel de la organización, es necesario usar [School Data Sync (SDS)](/SchoolDataSync) para conectarse al Sistema de información de estudiantes (SIS) de modo que Insights tenga la estructura jerárquica del sistema educativo asignada correctamente. 

Para ver Insights a nivel de clase como formador de clase *no* necesita esta sincronización, ya que usamos los permisos y la estructura de clase de Teams.

## <a name="plan-your-school-data-sync-integration"></a>Planear la integración de School Data Sync
Microsoft School Data Sync (o SDS) proporciona datos del Sistema de información escolar (o SIS) y su estructura jerárquica del sistema educativo y determina adónde se asigna un usuario particular. También ofrece datos adicionales sobre la jerarquía de alumnos y organizaciones.

Insights funciona mejor cuando se usa el [formato de archivo de SDS V2](/schooldatasync/sds-v2-csv-file-format) y superiores, pero también es compatible con un formato de archivo [SDS V1](/schooldatasync/school-data-sync-format-csv-files-for-sds) *con una funcionalidad limitada*.


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Diferencias entre los formatos de archivo SDS V1 y V2

Para sacar el máximo partido de Insights, se recomienda usar el formato de archivo v2 o v2.1 (próximamente)

| Tipo de datos | V1 | V2 (recomendado) |
|:--- |:--- |:--- |
| **Usuarios** | El formato V1 contiene **solo formadores**, por lo que para establecer permisos a nivel de organización para los responsables del ámbito educativo, deberá buscarlos y definir manualmente los permisos de cada uno. | El formato V2 contiene **todos los roles** para que pueda asignar permisos basados en roles. |
| **Organizaciones** | El formato V1 contiene **solo escuelas**, por lo que verá únicamente un nivel de agregación (todas las escuelas). Aunque una lista plana le permite centrarse en una escuela específica, es posible que esta lista tenga un gran número de escuelas o que contenga diferentes tipos de escuelas que sean difíciles de comparar (como la escuela primaria y la secundaria o la escuela de ciencias y la de artes).<br/><br/> Con una jerarquía, puede crear niveles lógicos, como un departamento de ciencias o de arte.| El formato V2 contiene **la jerarquía completa de su distrito o institución**, incluidas universidades, facultades, campus, regiones, programas, etc.<br/><br/> Con una jerarquía, puede ver la agregación relevante por cada nivel de la jerarquía, comparar rápidamente entre unidades de la organización a cada nivel, asignar permisos a niveles específicos, establecer objetivos por nivel de la organización y así sucesivamente.|

> [!NOTE]
> Los clientes no podrán incorporar el formato de archivo v2 a partir del 15 de julio de 2021 y tendrán que usar el formato v2.1 en su lugar. Todas las actualizaciones y capacidades futuras se realizarán en el formato v2.1 con retrocompatibilidad con el formato de archivo v1.

## <a name="best-practices"></a>Procedimientos recomendados
Una jerarquía con las asignaciones adecuadas y en la que todos los miembros pertenecen al nivel correcto permite que Insights ofrezca datos precisos y conclusiones relevantes para los distintos tipos de líderes educativos.

Cuantos más detalle proporcione, mejores y más relevantes serán los informes y los datos destacados.

Estos son algunos procedimientos recomendados para garantizar una implementación sencilla de SDS con la que los usuarios puedan sacar el máximo partido a Insights.

### <a name="file-format-version-to-ue"></a>Versión de formato de archivo a ue
*   Use el formato de archivo V2.1 (próximamente) y sincronice los datos opcionales que use Insights para Educación

### <a name="users-and-roles"></a>Usuarios y roles
*   Asegúrese de que **todos los usuarios** aparecen listados en los archivos que proporciona y sincroniza. Esto incluye todos los alumnos y el personal que necesite ver datos para las unidades de organización que abarquen.
    Si actualmente solo tiene profesores listados en el SIS, agregue los demás usuarios manualmente antes de cargar los archivos al SDS y sincronizar los datos.
    Las estadísticas recopiladas por Insights son solo de los alumnos registrados, si faltan algunos alumnos, los datos y las conclusiones no representarán al conjunto.
    
*   Asegúrese de **proporcionar el nombre y los apellidos de cada usuario**. De lo contrario, se hará referencia a ellos mediante su dirección de correo electrónico, lo que no proporciona una experiencia óptima en los informes y contenidos destacados (tarjetas con Insights sobre la actividad o el rendimiento de los alumnos).

*   El nivel de curso o año debe basarse en esta [lista de asignaciones](#supported-grade-level-values). 

*   Es importante **agregar el nivel de año o curso a todos los alumnos** para que los datos de actividad se puedan agregar y filtrar por ellos.    

*   Asegúrese de **asignar cada usuario a su unidad organizativa**. De este modo, Insights para Educación no mostrará datos engañosos en los contenidos destacados de Insights para Educación.

    *   Un alumno se puede asociar a más de una unidad organizativa, por ejemplo, alumnos registrados en un programa especial o en dos facultades. En caso de que el alumno tenga más de una unidad organizativa, proporcione una línea para cada uno en el archivo de usuarios para ese alumno.
    
    *   El administrador de TI puede conceder permisos en función de la unidad organizativa para el personal. **Asegúrese de que los miembros del personal estén asociados con el nivel de unidad correcto**, para que reciban los permisos que necesitan. Por ejemplo, un orientador asignado a cuatro escuelas necesita ver todos los cursos de estas escuelas, mientras que un director debe poder ver todas las clases de su escuela. 
    
*   **El rol es fundamental**. Aunque se trata de una lista cerrada, intente hacer coincidir el rol de [la lista](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) con el rol real de cada usuario que cargue. De esta forma, puede asignar permisos basados en roles en consecuencia. Por ejemplo, proporcione permisos para que todos los directores vean las clases de su escuela, o para que todos los profesores vean su facultad. 

### <a name="organizations"></a>Organizaciones

* Asegúrese de **reflejar la jerarquía real y completa de la organización**. Esto puede lograrse agregando el archivo manualmente. En algunos casos, esta jerarquía no se refleja en el SIS. Aun así, puede que necesite ver la agregación relevante por cada nivel de la jerarquía, asignar permisos a niveles específicos, establecer objetivos por nivel de organización, etc. 

* Asegúrese de que **todas las unidades de organización en el árbol de organización incluyan alumnos o clases** para agregar datos de alumnos para ellas. Le recomendamos que los alumnos estén en la rama más baja del árbol.

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

