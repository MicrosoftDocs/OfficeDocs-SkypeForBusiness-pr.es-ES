---
title: Use los informes de actividades de Microsoft Teams
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
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre cómo utilizar los informes de actividad para ver cómo los usuarios de su organización usa Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff7104a6991ad940ad4082e1b3d24c36c3392582
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632309"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Use los informes de actividades de Microsoft Teams 
========================================

Puede usar informes de actividad en el centro de administración de Microsoft 365 para ver cómo los usuarios de su organización usa Microsoft Teams. Por ejemplo, si aún algunas no usan Microsoft Teams, es posible que no saben cómo empezar a trabajar o comprender cómo pueden usar los equipos sean más productivos y colaboración. Su organización puede usar los informes de actividad para decidir dónde debe dar prioridad a los esfuerzos de aprendizaje y comunicación.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Cómo ver los informes de los equipos en el panel de informes

1. En el [Centro de administración de Microsoft 365](https://portal.office.com/adminportal/home), seleccione **informes** > **uso**.
 
2. En la página de **uso** , elija **Seleccionar un informe**y, a continuación, en **Los equipos de Microsoft** en la lista de informes, seleccione el informe que desea ver.

## <a name="teams-activity-reports-that-are-available"></a>Informes de actividad de los equipos que están disponibles

Actualmente hay dos informes de actividad, puede ver:

- [Informe de actividad de usuario de Microsoft Teams](#microsoft-teams-user-activity-report) 
- [Informe de uso de dispositivos de Microsoft Teams](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe de actividad de usuario de los equipos le ofrece una vista de las actividades más comunes que los usuarios realizan en los equipos. Esto incluye cuántas personas participar en una charla en un canal, ¿cuántas comunican a través de mensajes de chat privado y cuántos participan en llamadas o reuniones. Puede ver esta información para toda la organización, así como para cada usuario individual.

![Captura de pantalla del informe de actividad de usuario de los equipos en el centro de administración de Office 365.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar el informe de actividad de usuario de Microsoft Teams

Puede obtener una vista en la actividad de usuario de los equipos mirando en los gráficos de **los usuarios** y la **actividad** .

![Captura de pantalla del informe de actividad de usuario de los equipos en el centro de administración de Office 365 con llamadas numerada.](media/teams-user-activity-report-with-callouts.png)

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe de actividad de usuario de los equipos se puede ver para las tendencias durante los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si hace clic en un intervalo de tiempo concreto en el informe, en la tabla (7) mostrará datos durante 30 días, hasta la fecha (2) para cuando se generó el informe. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |La vista de **actividades** muestra el número de actividades de Microsoft Teams por tipo de actividad. Los tipos de actividad son el números de mensajes de chat de equipo, los mensajes de chat privado, las llamadas y las reuniones. |
|**4**   |La vista de **los usuarios** muestra el número de usuarios por tipo de actividad. Los tipos de actividad son el números de mensajes de chat de equipo, los mensajes de chat privado, las llamadas y las reuniones. |
|**5**   |El eje X en los gráficos es el intervalo de fechas seleccionado para el informe específico. <ul><li>En el diagrama de **actividad** , el eje Y es el número de la actividad especificada.</ul></li> <ul><li>En el gráfico de **los usuarios** , el eje Y es el número de usuarios que participan en los equipos chats, chats privadas, llamadas o reuniones.</ul></li> |
|**6**   |Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, en el diagrama de **actividad** , haga clic en o puntee en los **mensajes del canal**, **los mensajes de Chat**, **las llamadas**o **reuniones** para ver sólo la información relacionada con cada uno de ellos. Cambiar esta selección no cambia la información de la tabla de la cuadrícula. |
|**7**   |La lista de los equipos de activos en el plazo de tiempo informes de más grueso (180 días).  El recuento de actividad variará según la selección de fecha. <br><br> Para ver la siguiente información en la tabla, asegúrese de que agregar las columnas a la tabla. <ul><li>**Nombre de usuario** es la dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo anónimo.</ul></li> <ul><li>**Fecha de última actividad (UTC)** hace referencia a la última fecha en que el usuario participó en una actividad de Microsoft Teams.</ul></li> <ul><li>**Mensajes del canal** es el número de mensajes únicos que el usuario ha realizado en una charla de equipo durante el período de tiempo especificado.</ul></li> <ul><li>**Mensajes de chat** es el número de mensajes únicos que el usuario registrado en privado chat durante el período de tiempo especificado.</ul></li> <ul><li>**Las llamadas** es el número de llamadas que el usuario participó en durante el período de tiempo especificado.</ul></li> <ul><li>**Las reuniones** es el número de reuniones en línea que el usuario participó en durante el período de tiempo especificado.</ul></li> <ul><li>**Otra actividad** es el número de otras actividades en el equipo por el usuario algunas de las cuales incluyen y no se limitan a: mensajes de gusto, aplicaciones, trabajar en archivos, búsqueda, siguiente los equipos y canal y favoriting.</ul></li> <ul><li>**Deleted** indica si se elimina el equipo. Si el equipo se elimina, pero tenía actividad en el período del informe, que se muestra en la cuadrícula con eliminado establecido en true.</ul></li> <ul><li>**Fecha de Deleted** es la fecha en que el usuario se ha eliminado.</ul></li> <ul><li>**Producto asignado** es la lista de productos que están asignados al usuario.</ul></li>Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Desproteger el **¿cómo ocultar detalles a nivel de usuario?** sección en los [Informes de actividad en la vista previa de Microsoft 365 Admin Center](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Haga clic o puntee en **columnas** para agregar o quitar columnas de la tabla. |
|**9**   |Haga clic o puntee en **Exportar** para exportar datos de informe a un archivo .csv de Excel. De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2.000 usuarios, puede ordenar y filtrar dentro de la tabla en el informe de sí mismo. Si tiene más de 2.000 usuarios, debe exportar los datos para filtrar y ordenar el informe. 

### <a name="microsoft-teams-device-usage-report"></a>Informe de uso de dispositivos de Microsoft Teams

El informe de uso de dispositivos de los equipos proporciona información acerca de cómo los usuarios se conectan a los equipos, incluidas las aplicaciones móviles. El informe le ayudará a comprender qué dispositivos son populares en la organización y cómo varios usuarios trabajan fuera de la oficina.

![Captura de pantalla del informe de uso de dispositivos de los equipos en el centro de administración de Office 365.](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretar el informe de uso de dispositivos de Microsoft Teams

Puede obtener una vista en el uso de dispositivos de los equipos mirando en los gráficos de **usuarios** y **distribución** .

![Captura de pantalla del informe de uso de dispositivos de los equipos en el centro de administración de Office 365 con llamadas numerada.](media/teams-device-usage-report-with-callouts.png)

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe de dispositivos de los equipos se puede ver para las tendencias durante los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si hace clic en un intervalo de tiempo concreto en el informe, en la tabla (7) mostrará datos durante 30 días, hasta la fecha (2) para cuando se generó el informe. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |La vista de **los usuarios** muestra el número de usuarios diarios por tipo de dispositivo. |
|**4**   |La vista de **distribución** muestra el número de usuarios por dispositivo durante el período de tiempo seleccionado.  |
|**5**   | <ul><li>En el gráfico de **los usuarios** , el eje X es el intervalo de fechas seleccionado para el informe y el eje Y es el número de usuarios por tipo de dispositivo.</ul></li> <ul><li>En el gráfico de **distribución** , el eje X muestra los distintos dispositivos que se usa para conectarse a los equipos y el eje Y es el número de usuarios con el dispositivo.</ul></li> |
|**6**   |Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, en el gráfico de **distribución** , haga clic en o puntee en **Windows**, **Mac**, **Web**, **iOS**o **Android** para ver sólo la información relacionada con cada uno de ellos. Cambiar esta selección no cambia la información de la tabla de la cuadrícula. |
|**7**   |La lista de los equipos de activos en el plazo de tiempo informes de más grueso (180 días).  El recuento de actividad variará según la selección de fecha. <br><br> Para ver la siguiente información en la tabla, asegúrese de que agregar las columnas a la tabla. <ul><li>**Nombre de usuario** es la dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo anónimo.</ul></li> <ul><li>**Fecha de última actividad (UTC)** hace referencia a la última fecha en que el usuario participó en una actividad de los equipos.</ul></li> <ul><li>**Deleted** indica si se elimina el equipo. Si el equipo se elimina, pero tenía actividad en el período del informe, que se muestra en la cuadrícula con eliminado establecido en true.</ul></li><ul><li>**Fecha de Deleted** es la fecha en que el usuario se ha eliminado.</ul></li> <ul><li>**Windows** está seleccionada si el usuario estaba activo en el cliente de escritorio de los equipos en un equipo basado en Windows.</ul></li> <ul><li>**Mac** se selecciona si el usuario estaba activo en el cliente de escritorio de los equipos en un equipo Mac OS.</ul></li>  <ul><li>**Web** está seleccionada si el usuario estaba activo en el cliente web de los equipos.</ul></li> <ul><li>**iOS** se selecciona si el usuario estaba activo en el cliente móvil de los equipos para iOS.</ul></li> <ul><li>**Teléfono Android** se selecciona si el usuario estaba activo en el cliente móvil de los equipos para Android.</ul></li></li> <ui>Si las directivas de su organización impide la visualización de informes donde es identificable información de usuario, puede cambiar la configuración de privacidad para todos estos informes. Desproteger el **¿cómo ocultar detalles a nivel de usuario?** sección en los [Informes de actividad en la vista previa de Microsoft 365 Admin Center](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Haga clic o puntee en **columnas** para agregar o quitar columnas de la tabla. |
|**9**   |Haga clic o puntee en **Exportar** para exportar datos de informe a un archivo .csv de Excel. De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2.000 usuarios, puede ordenar y filtrar dentro de la tabla en el informe de sí mismo. Si tiene más de 2.000 usuarios, debe exportar los datos para filtrar y ordenar el informe. 

## <a name="who-can-access-the-teams-activity-reports"></a>Quién puede tener acceso a los informes de actividad de los equipos

Pueden tener acceso a los informes de actividad por los usuarios que están asignados:

- Rol de administrador global de Office 365
- Rol de administrador de específicos del producto (Exchange, Skype para empresas o SharePoint)
- Función de lector de informes

### <a name="reports-reader-role"></a>Función de lector de informes

Puede asignar la función de *lector de informes* al personal de TI que no sean que desea que tengan acceso a estos informes. Mediante la asignación de esta función a los administradores de recursos de aprendizaje o partes interesadas del negocio, puede asegurarse de que tienen acceso a toda la información que son útiles para la adopción de unidad y realizar el seguimiento de los equipos.

## <a name="other-information-on-the-reports-dashboard"></a>Otra información en el panel de informes

### <a name="at-a-glance-activity-widget"></a>Widget de actividad de un vistazo

El panel de informes incluye los datos de uso de los equipos en el widget de actividad de un vistazo, lo que ofrece una vista de producto cruzado de cómo los usuarios comunicarán y colaboran con los distintos servicios de Office 365.

![Captura de pantalla del widget de actividad de un vistazo los equipos en el panel de informes.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Tarjeta de actividad de los equipos

La tarjeta de actividad de los equipos en el panel informes proporciona una visión general de la actividad en los equipos, incluido el número de usuarios activos, por lo que puede comprender rápidamente cuántos usuarios usa el servicio de. Al hacer clic en la tarjeta de actividad en el panel abre el informe de actividad de usuario de los equipos. 

![Captura de pantalla de la tarjeta de actividad de los equipos en el panel de informes.](media/teams-activity-card.png)
