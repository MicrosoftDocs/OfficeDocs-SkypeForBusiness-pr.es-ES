---
title: Uso de informes de actividad para Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 04/17/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: chenle
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
description: Obtenga información sobre cómo utilizar los informes de actividad para ver cómo los usuarios de su organización usa Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9868c63de06f56fcebd8a3457e048c91a86e2b72
ms.sourcegitcommit: 58934985891818fa505ae742b1e750edccadd870
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "25576530"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Uso de informes de actividad para Microsoft Teams 
========================================

Puede usar informes de actividad para ver cómo los usuarios de su organización usa Microsoft Teams. Por ejemplo, si algunas no usan equipos aún, es posible que no saben cómo empezar a trabajar o comprender cómo pueden usar los equipos sean más productivos y colaboración. Su organización puede usar los informes de actividad para decidir dónde asignar prioridades a los esfuerzos de aprendizaje y la comunicación.

## <a name="how-to-get-to-the-reports-dashboard"></a>Cómo obtener al panel de informes

1. En el [Centro de administración de Office 365](https://portal.office.com/adminportal/home), seleccione **informes** > **uso**.
 
2. En la página de **uso** , elija **Seleccionar un informe** para seleccionar de una lista de los informes disponibles. 

## <a name="teams-activity-reports-that-are-available"></a>Informes de actividad de los equipos que están disponibles

Actualmente hay dos informes de actividad, puede ver:

- Informe de actividad de usuario de Microsoft Teams 
- Informe de uso de dispositivos de Microsoft Teams 

### <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe de actividad de usuario de Microsoft Teams le ofrece una vista de las actividades más comunes que los usuarios realizan en Microsoft Teams. Esto incluye cuántas personas participar en una charla en un canal, ¿cuántas comunican a través de mensajes de chat privado y cuántos participan en llamadas o reuniones. Puede ver esta información tanto en el nivel de inquilino, así como para cada usuario individual.

![Captura de pantalla del informe de actividad de usuario de los equipos en el centro de administración de Office 365.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar el informe de actividad de usuario de Microsoft Teams

Puede obtener una vista en la actividad de usuario de Microsoft Teams mirando en los gráficos de **los usuarios** y la **actividad** .

![Captura de pantalla del informe de actividad de usuario de los equipos en el centro de administración de Office 365 con llamadas numerada.](media/teams-user-activity-report-with-callouts.png)

|Llamada |Descripción  |
|--------|-------------|
|**1**   |Puede verse el informe de actividad de usuario de Microsoft Teams para las tendencias durante los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si hace clic en un día determinado en el informe, en la tabla (7) mostrará datos durante 30 días, hasta la fecha (2) para cuando se generó el informe. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |La vista de **actividades** muestra el número de actividades de Microsoft Teams por tipo de actividad. Los tipos de actividad son el número de mensajes de chat, mensajes de chat privado, las llamadas o reuniones de los equipos. |
|**4**   |La vista de **los usuarios** muestra el número de usuarios por tipo de actividad. Los tipos de actividad son el número de mensajes de chat, mensajes de chat privado, las llamadas o reuniones de los equipos. |
|**5**   |El eje X en los gráficos es el intervalo de fechas seleccionado para el informe específico. <ul><li>En el diagrama de **actividad** , el eje Y es el número de actividades especificado.</ul></li> <ul><li>En el gráfico de **los archivos** , el eje Y es el número de usuarios que participan en los equipos chats, chats privadas, llamadas o reuniones.</ul></li> |
|**6**   |Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, en el diagrama de **actividad** , haga clic en o puntee en los **mensajes del canal**, **los mensajes de Chat**, **las llamadas**o **reuniones** para ver sólo la información relacionada con cada uno de ellos. Cambiar esta selección no cambia la información de la tabla de la cuadrícula. |
|**7**   |La lista de grupos que se muestra está determinada por el conjunto de todos los grupos que existía (no se han eliminado) entre el marco de tiempo informes de más grueso (180 días).  El recuento de actividad variará según la selección de fecha. <ul><li>**Nombre de usuario** es la dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo anónimo.</ul></li> <ul><li>**Fecha de última actividad (UTC)** hace referencia a la última fecha en que el usuario participó en una actividad de Microsoft Teams.</ul></li> <ul><li>**Mensajes del canal** es el número de mensajes únicos que el usuario ha realizado en una charla de equipo durante el período de tiempo especificado.</ul></li> <ul><li>**Mensajes de chat** es el número de mensajes únicos que el usuario registrado en privado chat durante el período de tiempo especificado.</ul></li> <ul><li>**Las llamadas** es el número de llamadas que el usuario participó en durante el período de tiempo especificado.</ul></li> <ul><li>**Las reuniones** es el número de reuniones en línea que el usuario participó en durante el período de tiempo especificado.</ul></li> <ul><li>**Otra actividad** es el número de otras actividades en el equipo por el usuario algunas de las cuales incluyen y no se limitan a: mensajes de gusto, aplicaciones, trabajar en archivos, búsqueda, siguiente los equipos y canal y favoriting.</ul></li> <ul><li>**Deleted** indica si se elimina el equipo. Si el equipo se elimina, pero tenía actividad en el período del informe, que se muestra en la cuadrícula con eliminado establecido en true.</ul></li> <ul><li>**Fecha de Deleted** es la fecha en que se eliminó el equipo.</ul></li> <ul><li>**Producto asignado** es la lista de productos que están asignados al usuario.</ul></li> <ui>**Nota:** No es posible que vea todos los elementos en la lista debajo de las columnas hasta que agregue a ellos. </ul><br><br> <ui>Si las directivas de su organización impide la visualización de informes donde es identificable información de usuario, puede cambiar la configuración de privacidad para todos estos informes. Desproteger el **¿cómo ocultar detalles a nivel de usuario?** sección en los [Informes de actividad en la vista previa centro de administración de Office 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Haga clic o toque pulse en **Columnas** para agregar o quitar columnas de un informe. |
|**9**   |También puede exportar los datos del informe en un archivo .csv de Excel, haciendo clic o punteando el vínculo de exportación. De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2.000 usuarios, puede ordenar y filtrar dentro de la tabla en el informe de sí mismo. Si tiene más de 2.000 usuarios, en orden para filtrar y ordenar, debe exportar los datos. |

### <a name="microsoft-teams-device-usage-report"></a>Informe de uso de dispositivos de Microsoft Teams

El informe de uso de la aplicación de Microsoft Teams proporciona información acerca de cómo los usuarios se conectan a Microsoft Teams, incluidas las aplicaciones móviles. El informe le ayudará a comprender qué dispositivos son populares en la organización y cómo varios usuarios trabajan fuera de la oficina.

![Captura de pantalla del informe de uso de dispositivos de los equipos en el centro de administración de Office 365.](media/teams-device-usage-report.png)

## <a name="who-can-access-the-teams-activity-reports"></a>Quién puede tener acceso a los informes de actividad de los equipos

Pueden tener acceso a los informes de actividad por los usuarios que están asignados:

- Rol de administrador global de Office 365
- Rol de administrador de específicos del producto (Exchange, Skype para empresas o SharePoint)
- Función de lector de informes

### <a name="reports-reader-role"></a>Función de lector de informes

Puede asignar la función de *lector de informes* al personal de TI que no sean que desea que tengan acceso a estos informes. Mediante la asignación de esta función a los administradores de recursos de aprendizaje o partes interesadas del negocio, puede asegurarse de que tienen acceso a toda la información que son útiles para la adopción de unidad y realizar el seguimiento de los equipos.

## <a name="other-information-on-the-reports-dashboard"></a>Otra información en el panel de informes

### <a name="at-a-glance-activity-widget"></a>Widget de actividad de un vistazo

El panel de informes incluye los datos de uso de Microsoft Teams en el widget de actividad de un vistazo, lo que ofrece una vista de producto cruzado de cómo los usuarios comunicarán y colaboran con los distintos servicios de Office 365.

![Captura de pantalla del widget de actividad de un vistazo los equipos en el panel de informes.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Tarjeta de actividad de los equipos

El panel de informes también incluye una nueva tarjeta para Microsoft Teams. La tarjeta le ofrece una visión general de la actividad en los equipos, incluido el número de usuarios activos, por lo que comprender rápidamente cuántos usuarios usa el servicio.

![Captura de pantalla de la tarjeta de actividad de los equipos en el panel de informes.](media/teams-activity-card.png)
