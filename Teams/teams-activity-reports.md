---
title: Utilizar informes de actividad para Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 04/17/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: chenle
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
description: Obtenga información sobre cómo utilizar los informes de actividad para ver cómo los usuarios de su organización utiliza Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d9a999781163042d41a30d1b0d0412d36367f50
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
<a name="use-activity-reports-for-microsoft-teams"></a>Utilizar informes de actividad para Microsoft Teams 
========================================

Puede utilizar informes de actividad para ver cómo los usuarios de su organización utiliza Microsoft Teams. Por ejemplo, si algunos no utilizan equipos aún, podría no saben cómo empezar o entender cómo pueden usar los equipos sean más productivos y colaboración. Su organización puede utilizar los informes de actividad para decidir dónde establecer prioridades de esfuerzos de formación y comunicación.

## <a name="how-to-get-to-the-reports-dashboard"></a>Cómo llegar al tablero de mandos de informes

1. En el [Centro de administración de Office 365](https://portal.office.com/adminportal/home), seleccione **informes** > **uso**.
 
2. En la página de **uso** , elija **Seleccionar un informe** para seleccionar de una lista de los informes disponibles. 

## <a name="teams-activity-reports-that-are-available"></a>Informes de actividad de los equipos que están disponibles

Actualmente hay dos informes de actividad que se puede ver:

- Informe de actividad de usuario de Microsoft Teams 
- Informe de uso de dispositivos de Microsoft Teams 

### <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe de actividad de usuario de Microsoft Teams ofrece una vista de las actividades más comunes que realizan los usuarios en Microsoft Teams. Esto incluye cuántas personas participar en una charla en un canal, cuántos comunican mediante mensajes de chat privado y cuántos participan en reuniones o llamadas. Puede ver esta información tanto en el nivel de inquilinos, así como para cada usuario individual.

![Captura de pantalla del informe de actividad de usuario de equipos en el centro de administración de Office 365.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar el informe de actividad de usuario de Microsoft Teams

Puede obtener una vista en la actividad de usuario de Microsoft Teams mirando en las tablas de **actividad** y **los usuarios** .

![Captura de pantalla del informe de actividad de usuario equipos en el centro de administración de Office 365 con llamadas numeradas.](media/teams-user-activity-report-with-callouts.png)

|Llamada |Descripción  |
|--------|-------------|
|**1**   |El informe de actividad de usuario de Microsoft Teams puede verse las tendencias en los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si hace clic en un día determinado en el informe, la tabla (7) mostrará datos durante 30 días, hasta la fecha (2) para cuando se generó el informe. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |La vista de **actividad** muestra el número de actividades de Teams de Microsoft por tipo de actividad. Los tipos de actividad son el número de mensajes de chat, mensajes de chat privado, llamadas o las reuniones de los equipos. |
|**4**   |La vista de **los usuarios** muestra el número de usuarios por tipo de actividad. Los tipos de actividad son el número de mensajes de chat, mensajes de chat privado, llamadas o las reuniones de los equipos. |
|**5**   |El eje X de los gráficos es el intervalo de fechas seleccionado para el informe específico. <ul><li>En el diagrama de **actividad** , el eje Y es el número de actividades especificado.</ul></li> <ul><li>En el gráfico de **archivos** , el eje Y es el número de usuarios, participar en charlas de equipos, charlas privadas, llamadas o reuniones.</ul></li> |
|**6**   |Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, en el diagrama de **actividad** , haga clic o puntee en **mensajes del canal**, **mensajes de Chat**, **llamadas**o **reuniones** para ver sólo la información relacionada con cada uno de ellos. Cambiar esta selección, no cambia la información en la tabla de la cuadrícula. |
|**7**   |La lista de grupos que se muestra está determinada por el conjunto de todos los grupos que existían (no se han eliminado) en el marco de tiempo informes de mayor (180 días).  El recuento de actividad varían según la selección de fecha. <ul><li>**Nombre de usuario** es la dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o que este campo sea anónimo.</ul></li> <ul><li>**Fecha de última actividad (UTC)** hace referencia a la última fecha en la que el usuario participó en una actividad de Microsoft Teams.</ul></li> <ul><li>**Mensajes del canal** es el número de mensajes únicos a los que el usuario registrado en un chat de equipo durante el período de tiempo especificado.</ul></li> <ul><li>**Mensajes de chat** es el número de mensajes únicos que el usuario registrado en una privada charla durante el período de tiempo especificado.</ul></li> <ul><li>**Llamadas** es el número de llamadas que el usuario participó en durante el período de tiempo especificado.</ul></li> <ul><li>**Reuniones** es el número de reuniones en línea que el usuario participó en durante el período de tiempo especificado.</ul></li> <ul><li>**Otra actividad** es el número de otras actividades del equipo por parte del usuario.</ul></li> <ul><li>**Deleted** indica si el equipo se elimina. Si el equipo se elimina, pero tenía actividad en el período de notificación, aparecerá en la cuadrícula con eliminado establecido en true.</ul></li> <ul><li>**Deleted fecha** es la fecha en que el equipo se ha eliminado.</ul></li> <ul><li>**Producto asignado** es la lista de productos que se asignan al usuario.</ul></li> <ui>**Nota:** Puede que no vea todos los elementos de la lista siguiente en las columnas hasta que los agrega. </ul><br><br> <ui>Si las directivas de su organización le impide ver informes donde la información de usuario es identificable, puede cambiar la configuración de privacidad para todos estos informes. Retirar el **¿cómo ocultar detalles a nivel de usuario?** sección en los [Informes de actividad en la vista previa centro de administración de Office 365](https://support.office.com/en-us/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Haga clic o toque pulse en **Columnas** para agregar o quitar columnas de un informe. |
|**9**   |También puede exportar los datos del informe a un archivo .csv de Excel, haciendo clic o punteando el vínculo de exportación. De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2.000 usuarios, puede ordenar y filtrar dentro de la tabla en el informe. Si tiene más de 2.000 usuarios, con el fin de filtrar y ordenar, debe exportar los datos. |

### <a name="microsoft-teams-device-usage-report"></a>Informe de uso de dispositivos de Microsoft Teams

El informe de uso de la aplicación Teams de Microsoft proporciona información acerca de cómo los usuarios se conectan a Microsoft Teams, incluyendo aplicaciones móviles. El informe le ayuda a comprender qué dispositivos son populares en la organización y cuántos usuarios trabajan sobre la marcha.

![Captura de pantalla del informe de uso de dispositivos de equipos en el centro de administración de Office 365.](media/teams-device-usage-report.png)

## <a name="who-can-access-the-teams-activity-reports"></a>Quién puede tener acceso a los informes de actividad de los equipos

Pueden tener acceso a los informes de actividad por usuarios que tienen asignados:

- Función de administrador global de Office 365
- Función de administrador de productos específicos (Exchange, Skype para negocios o SharePoint)
- Función de lector de informes

### <a name="reports-reader-role"></a>Función de lector de informes

Puede asignar la función de *lector de informes* a personal ajeno a TI que deseen tener acceso a estos informes. Al asignar este rol a los responsables de formación o partes interesadas del negocio, puede asegurarse de que tienen acceso a la información que son útiles para la adopción de unidad y realizar el seguimiento de los equipos.

## <a name="other-information-on-the-reports-dashboard"></a>Otra información en el panel de informes

### <a name="at-a-glance-activity-widget"></a>Widget de actividad de un vistazo

El tablero de informes incluye los datos de uso de Teams de Microsoft en el widget de actividad de un vistazo, que ofrece una vista de producto cruzado de cómo los usuarios comunicarán y colaboran con los distintos servicios de Office 365.

![Captura de pantalla de un widget de actividad de un vistazo los equipos en el tablero de mandos de informes.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Tarjeta de la actividad de los equipos

El tablero de mandos de informes también incluye una nueva tarjeta de Teams de Microsoft. La tarjeta le ofrece una visión general de la actividad en equipos, incluido el número de usuarios activos, por lo que puede saber rápidamente cuántos usuarios usan el servicio.

![Captura de pantalla de la tarjeta de la actividad de equipos en el tablero de mandos de informes.](media/teams-activity-card.png)
