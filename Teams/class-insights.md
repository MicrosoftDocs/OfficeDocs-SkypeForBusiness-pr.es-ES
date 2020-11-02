---
title: Guía de Insights en Teams para el ámbito educativo para administradores de TI
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Una guía para administradores de TI de Insights para Microsoft Teams para el ámbito educativo.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b63ea1a1a09a55d9a51fb2a110c024960f23f6f4
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803528"
---
# <a name="it-admin-guide-to-insights-in-teams-for-education"></a>Guía de Insights en Teams para el ámbito educativo para administradores de TI

Con Insights en Microsoft Teams para el ámbito educativo, los formadores y líderes pueden acceder a los datos de análisis sobre la participación digital, la carga de trabajo asignada, las calificaciones, las comunicaciones y más. El motor de Insights son los principios éticos por los cuales los formadores y los alumnos están primero. Insights cumple con los estándares de privacidad y garantiza el cumplimiento continuo con la institución.

Insights está activa en los SKU A1, A3 y A5 de Office 365 Educación.

> [!NOTE]
> Formadores, pueden encontrar información sobre el uso de Insights aquí: [Guía de Insights en Microsoft Teams para formadores](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181).

## <a name="use-insights"></a>Usar Insights

### <a name="user-types"></a>Tipos de usuario
- Los **alumnos** se pueden identificar por sus licencias y  _no tienen_ acceso a la pestaña Insights (incluso si son los propietarios de un equipo). 
- Los **formadores** se pueden identificar por sus licencias para profesores. Los formadores deben tener una licencia para profesores y ser los propietarios de un equipo de clase para agregar y ver los datos en la pestaña Insights. 
- Asimismo, se identifica a los **líderes** según su licencia de facultad, pero además necesitan permisos específicos de los administradores globales de TI para ver los informes en la aplicación Insights.
- Las cuentas de invitado _no tienen_ acceso a Insights.

### <a name="entry-points"></a>Puntos de entrada
Los formadores y los líderes tienen diferentes puntos de entrada, en los que pueden descubrir y usar Insights.

Los **formadores** pueden usar estos dos puntos de entrada:
- [Pestañas](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181): En una pestaña agregada desde el menú de navegación superior, se puede encontrar información disponible para cada clase de la que son propietarios. Insights mostrará los datos de actividad de todos los canales de los equipos de clase, pero solo se puede agregar como una pestaña en los canales públicos. La pestaña refleja la actividad de todos los miembros del equipo de clase que no son propietarios (incluidos los formadores que no son propietarios del equipo).
- [Aplicación personal](https://support.microsoft.com/article/747fd8d9-00b0-43e6-bacc-a1bf030b1867): Un resumen de todas las clases activas está disponible en la barra de la aplicaciones de la izquierda en Teams.

Los **líderes** pueden usar Insights como [aplicación personal](https://support.microsoft.com/article/8738d1b1-4e1c-49bd-9e8d-b5292474c347).

### <a name="manage-setup-policy"></a>Administrar la directiva de configuración
Como administrador, puede usar la [directiva de configuración de la aplicación](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies) para instalar Insights de forma predeterminada para los formadores y líderes cuando inicien Teams.
Con esa directiva, puede personalizar Temas para que muestre Insights, y anclar esta última en la barra de aplicaciones.

> [!TIP]
> Lea el documento de[Directivas de Teams y los paquetes de directivas para la educación](https://docs.microsoft.com/microsoftteams/policy-packages-edu), que abarca este tema.



## <a name="compliance"></a>Cumplimiento

Insights tiene compromisos de cumplimiento líderes en el sector y se clasifica como un servicio de nivel C dentro del marco de cumplimiento de Office 365.

> [!NOTE]
> Visite el [Centro de Confianza de Microsoft](https://www.microsoft.com/trust-center) para obtener más información sobre cómo Microsoft protege sus datos. 

## <a name="privacy"></a>Privacidad

La información que se recopila y se muestra a través de Insights cumple con más de 90 estándares normativos y del sector, incluidos RGPD y la Ley de Derechos Educativos y Privacidad de la Familia (FERPA) para la seguridad de los estudiantes y niños, así como otras normas similares y orientadas a la privacidad. Es importante que los administradores de TI sepan que la información recopilada para cada estudiante está pensada para usarse solo en un contexto de clase, para permitir que los formadores y líderes determinen el comportamiento de los estudiantes. La información se recopila para actividades de aprendizaje significativas, como la asistencia a las reuniones de clase, la publicación de mensajes, las respuestas a las publicaciones de los compañeros, las tareas hechas, la edición de archivos y mucho más. Por ejemplo, no se muestra información sobre chats privado o un inicio de sesión de Teams.

Nuestro objetivo es ayudar a los formadores a entender el compromiso y centrar la atención en el aprendizaje de los estudiantes. Aunque estas actividades de clase se pueden enfocar en acciones a nivel de los estudiantes, Microsoft Teams no asigna un valor positivo o negativo a estas acciones y no hay una identificación crítica para cada alumno basada en criterios. La información en Insights informa a un profesor de que, por ejemplo, un estudiante no ha estado activo en la herramienta durante cierto período de tiempo o ha completado todas sus tareas de la semana pasada a tiempo. Es responsabilidad del formador interactuar con el estudiante y con su familia o tutores para determinar el motivo subyacente de cualquier actividad o inactividad detectada.

## <a name="data-collection"></a>Recopilación de datos

- Recopilamos datos para Insights cuando se activa Education Analytics para el espacio empresarial. Los datos se recopilan a partir de la actividad de Teams para presentar recomendaciones accionables sobre formación y aprendizaje.
- Los datos de los invitados _no_ se recopilan en Insights.
- Education Analytics está **activado** de manera predeterminada.

Actualmente, estos datos se extraen de las siguientes áreas de actividad de los estudiantes y formadores en los equipos de clase:

|Componente de los equipos  |Datos recopilados  |
|-----------------|------------------------|------------------------|
|Tareas |La apertura, la entrega y las calificaciones de las tareas. |
|El compromiso con el canal |Visitar un canal, crear una publicación, responder y dar me gusta a una publicación (sin incluir el contenido del chat). |
|Archivos |Cargar, descargar, acceder, modificar, comentar y compartir un archivo (sin incluir el contenido del archivo). |
|Reuniones |Asistencia (sin incluir el contenido de la reunión). |

## <a name="data-location"></a>Ubicación de datos

Los datos de Insights para espacios empresariales ubicados en Europa se almacenan en servidores en Europa. Los datos de los espacios empresariales ubicados en Estados Unidos se almacenan en servidores en Estados Unidos. Si usa Insights y su espacio empresarial de Office 365 se encuentra en una región fuera de Europa o Estados Unidos, los datos se almacenarán en la región geográfica adecuada.

## <a name="performance-and-reliability"></a>Rendimiento y confiabilidad

Insights está diseñado para controlar un gran volumen de datos recopilados de la actividad de Teams con un rendimiento y confiabilidad óptimos.

El proceso de recopilación de datos se lleva a cabo en servidores separados, independientemente de la instalación de la pestaña Insights en Teams. La pestaña de Insights no afecta al rendimiento de la aplicación o al ancho de banda de red de los profesores y alumnos que usan el resto de la funcionalidad de Teams.

> [!TIP]
> Lea [Ayuda para los casos que presentan poco ancho de banda para Teams para el ámbito educativo](edu-remote-low-bandwidth.md) acerca de cómo usar Teams para el ámbito educativo cuando existe poco ancho de banda.

## <a name="how-to-delete-your-data"></a>Cómo eliminar sus datos

Los servicios educativos almacenan las acciones de los alumnos y los formadores efectuadas en el contexto de un equipo de clase. Estos datos se consideran un conjunto de datos mezclados y, por lo tanto, no se eliminan automáticamente del servicio una vez que se eliminan las cuentas de usuario de los alumnos o el formador de su organización.

> [!NOTE]
> La eliminación de los datos tiene una impacto negativo en la capacidad de Insights de analizar el compromiso del equipo de clase a lo largo del tiempo.

- Abra una incidencia de soporte técnico en [https://edusupport.microsoft.com/support](https://edusupport.microsoft.com/support). La incidencia de soporte técnico debe indicar claramente la solicitud de una operación RGPD para eliminar DSR y contener el ID. de objeto de usuario que se eliminará. No es posible limitar el conjunto de datos o la ventana de tiempo de la eliminación.
- Una vez que se archivó, la incidencia de soporte técnico permanece en cola por una semana para cumplir con la directiva de retención mínima  Tendrá la oportunidad de cancelar la operación durante este tiempo.
- Después de una semana, el equipo de Education Analytics toma medidas para asegurarse de que todos los datos relacionados con el ID. de usuario se eliminan del servicio. El soporte técnico de Microsoft supervisa el vale de ICM y le notificará una vez que se haya completado el proceso de eliminación en un máximo de 28 días.

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>Desactivar y activar Insights con School Data Sync (SDS)

School Data Sync ayuda a automatizar el proceso de sincronización e importación de los datos del sistema de información de estudiantes (SIS) con Office 365.

El uso de Insights no requiere el uso de SDS. Sin embargo, puede desactivar Education Analytics en cualquier momento desactivando la alternancia en el centro de administración de SDS en **Configuración** > **Administrar Education Analytics** .

:::image type="content" source="media/class-insights-on-off.png" alt-text="El botón de encendido y apagado para habilitar o deshabilitar Insights":::

De forma predeterminada, Education Analytics y, por lo tanto, Insights están activados. Cuando desactiva Analytics, se eliminan todos los datos recopilados para la pestaña de Insights. Vuelva a activar Analytics y empezaremos a recopilar datos desde el momento en que se vuelve a habilitar.

## <a name="additional-resources"></a>Recursos adicionales
- [Guía de Insights para formadores](https://support.microsoft.com/office/27b56255-90c0-47aa-bac3-1c9f50157181)
