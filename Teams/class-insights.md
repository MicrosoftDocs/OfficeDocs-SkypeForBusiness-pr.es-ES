---
title: Class Insights de Microsoft Teams para administradores de TI
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Una guía para administradores de TI de Class Insights para Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbf535c73bd1b23b22f368707bcbabe44c0cdf2d
ms.sourcegitcommit: 2cc36c954200f50de33b909856b33fe0a9a6b7a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126200"
---
# <a name="class-insights-for-it-admins"></a>Class Insights para administradores de TI

Con Class Insights de Microsoft Teams, los formadores pueden acceder a los datos de análisis sobre el compromiso y el rendimiento de los estudiantes. Class Insights recopila la actividad de los alumnos en Teams, como, por ejemplo, las calificaciones, la entrega de tareas y la colaboración en archivos, y crea un panel de análisis donde se muestran elementos visuales de datos accionables.

Class Insights está activa en los SKU A1, A3 y A5 de Office 365 Educación

> [!NOTE]
> Formadores, [aquí](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc) hay más información sobre cómo usar Class Insights.

## <a name="permissions"></a>Permisos

Los formadores pueden agregar la clase Insights a un canal público de un equipo de clase yendo a Aplicaciones en la barra aplicaciones de Teams y buscando Insights.

- Las licencias para profesores definen a los profesores. Los formadores deben tener una licencia para profesores y ser los propietarios de un equipo de clase para agregar y ver la pestaña Insights.
- Los estudiantes se definen por sus licencias y **no tienen acceso a la pestaña Insights** (incluso si son los propietarios de un equipo).
- La pestaña refleja la actividad de todos los miembros del equipo de clase que no son propietarios (incluidos los formadores que no son propietarios del equipo).

## <a name="compliance"></a>Cumplimiento

Class Insights tiene compromisos de cumplimiento líderes en el sector y se clasifica como un servicio de nivel C dentro del marco de cumplimiento de Office 365.

> [!NOTE]
> Visite el [Centro de Confianza de Microsoft](https://www.microsoft.com/trust-center) para obtener más información sobre cómo Microsoft protege sus datos. 

## <a name="privacy"></a>Privacidad

La información que se recopila y se muestra a través de la clase Insights cumple con más de 90 estándares normativos y del sector, incluidos RGPD y los derechos educativos de la familia y ley de privacidad (FERPA) para la seguridad de los estudiantes y niños y otras normas similares y orientadas a la privacidad. Es importante que los administradores de TI sepan que la información recopilada para cada estudiante está pensada para usarse solo en un contexto de clase, para permitir que los formadores determinen el comportamiento de la clase. La información se recopila para actividades de aprendizaje significativas, como la asistencia a las reuniones de clase, la publicación de mensajes, las respuestas a las publicaciones de los compañeros, las tareas hechas, la edición de archivos y mucho más. Por ejemplo, no se muestra información sobre chats privado o un inicio de sesión de Teams.

Nuestro objetivo es ayudar a los formadores a entender el compromiso y centrar la atención en el aprendizaje de los estudiantes. Aunque estas actividades de clase se pueden enfocar en acciones a nivel de los estudiantes, Microsoft Teams no asigna un valor positivo o negativo a estas acciones y no hay una identificación crítica de cada alumno basada en criterios. La información en la clase Insights le informa a un formador, por ejemplo, si un estudiante no ha estado activo en la herramienta durante cierto período de tiempo o si ha completado todas sus tareas de la semana pasada a tiempo. Es responsabilidad del formador interactuar con el estudiante y con su familia o tutores para determinar el motivo subyacente de cualquier actividad o inactividad detectada.

## <a name="data-collection"></a>Recopilación de datos

Recopilamos datos para clase la Insights cuando se activa Education Analytics para el inquilino. Los datos se recopilan a partir de la actividad de Teams para presentar recomendaciones accionables sobre formación y aprendizaje.

Education Analytics está **activado** de manera predeterminada.

Actualmente, estos datos se extraen de las siguientes áreas de actividad de los estudiantes y formadores en los equipos de clase:

|Componente de los equipos  |Datos recopilados  |
|-----------------|------------------------|------------------------|
|Tareas |La apertura, la entrega y las calificaciones de las tareas. |
|El compromiso con el canal |Visitar un canal, crear una publicación, responder y dar me gusta a una publicación (sin incluir el contenido del chat). |
|Archivos |Cargar, descargar, acceder, modificar, comentar y compartir un archivo (sin incluir el contenido del archivo). |
|Reuniones |Asistencia (sin incluir el contenido de la reunión). |

## <a name="data-location"></a>Ubicación de datos

Los datos de Class Insights para inquilinos ubicados en Europa se almacenan en servidores en Europa. Los datos de los inquilinos ubicados en Estados Unidos se almacenan en servidores en Estados Unidos. Si usa Class Insights y su inquilino de Office 365 se encuentra en una región fuera de Europa o Estados Unidos, los datos se almacenarán en la región geográfica adecuada.

## <a name="performance-and-reliability"></a>Rendimiento y confiabilidad

Class Insights está diseñada para controlar un gran volumen de datos recopilados de la actividad de Teams con un rendimiento y confiabilidad óptimos.

El proceso de recopilación de datos se lleva a cabo en servidores independientes, independientemente de la instalación de la pestaña Insights en Teams. La pestaña de Class Insights no afecta al rendimiento de la aplicación o al ancho de banda de red de los formadores y alumnos que usan el resto de la funcionalidad de Teams.

> [!TIP]
> Lea [aquí](edu-remote-low-bandwidth.md) cómo usar Teams para el ámbito educativo cuando la banda ancha está lenta.

## <a name="how-to-delete-your-data"></a>Cómo eliminar sus datos

Los servicios educativos almacenan las acciones de los alumnos y los formadores efectuadas en el contexto de un equipo de clase. Estos datos se consideran un conjunto de datos mezclados y, por lo tanto, no se eliminan automáticamente del servicio una vez que se eliminan las cuentas de usuario de los alumnos o el formador de su organización.

> [!NOTE]
> La eliminación de los datos tiene una impacto negativo en la capacidad de Insights de analizar el compromiso del equipo de clase a lo largo del tiempo.

- Abra una incidencia de soporte técnico [aquí](https://edusupport.microsoft.com/support). La incidencia de soporte técnico debe indicar claramente la solicitud de una operación RGPD para eliminar DSR y contener el ID. de objeto de usuario que se eliminará. No es posible limitar el conjunto de datos o la ventana de tiempo de la eliminación.
- Una vez que se archivó, la incidencia de soporte técnico permanece en cola por una semana para cumplir con la directiva de retención mínima  Tendrá la oportunidad de cancelar la operación durante este tiempo.
- Después de una semana, el equipo de Education Analytics toma medidas para asegurarse de que todos los datos relacionados con el ID. de usuario se eliminan del servicio. El soporte técnico de Microsoft supervisa el vale de ICM y le notificará una vez que se haya completado el proceso de eliminación en un máximo de 28 días.

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>Desactivar y activar Insights con School Data Sync (SDS)

School Data Sync ayuda a automatizar el proceso de sincronización e importación de los datos del sistema de información de estudiantes (SIS) con Office 365.

El uso de Class Insights no requiere el uso de SDS. Sin embargo, puede desactivar Education Analytics en cualquier momento desactivando la alternancia en el centro de administración de SDS en **Configuración** > **Administrar Education Analytics**.

:::image type="content" source="media/class-insights-on-off.png" alt-text="El botón de encendido/apagado para habilitar o deshabilitar la clase Insights":::

De forma predeterminada, Education Analytics y, por lo tanto, Class Insights están activados. Cuando desactiva Analytics, se eliminarán todos los datos recopilados para la pestaña de la clase Insights. Vuelva a activar Analytics y empezaremos a recopilar datos desde el momento en que se vuelva a habilitar.

Más información: [Class Insights para formadores](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)