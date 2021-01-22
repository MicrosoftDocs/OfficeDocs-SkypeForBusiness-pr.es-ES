---
title: Use los informes de actividades de Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 04/17/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: chenle
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar los informes de actividades para ver cómo usan los usuarios de su organización Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8428135d2d4baa40fd1957f6f5d02eb658732a6c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918676"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Use los informes de actividades de Microsoft Teams 
========================================

Puede usar los informes de actividades en el Centro de administración de Microsoft 365 para ver cómo usan los usuarios de su organización Microsoft Teams. Por ejemplo, si algunos todavía no usan Microsoft Teams, es posible que no sepan cómo empezar o comprendan cómo pueden usar Teams para ser más productivos y colaborativos. Su organización puede usar los informes de actividad para decidir dónde debe dar prioridad a los esfuerzos de aprendizaje y comunicación.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Cómo ver los informes de Teams en el panel Informes

1. En el [Centro de administración de Microsoft 365,](https://portal.office.com/adminportal/home)seleccione Uso **de**  >  **informes.**
 
2. En la **página** Uso, elija Seleccionar un informe y, **a** continuación, en **Microsoft Teams** en la lista de informes, elija el informe que desea ver.

## <a name="teams-activity-reports-that-are-available"></a>Informes de actividad de Teams que están disponibles

Actualmente hay dos informes de actividad que puede ver:

- [Informe de actividad de usuario de Microsoft Teams](#microsoft-teams-user-activity-report) 
- [Informe de uso de dispositivos de Microsoft Teams](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe de actividad de los usuarios de Teams le proporciona una vista de las actividades más comunes que realizan los usuarios en Teams. Esto incluye cuántas personas participan en un chat en un canal, cuántas se comunican a través de un mensaje de chat privado y cuántas participan en llamadas o reuniones. Puede ver esta información para toda la organización, así como para cada usuario individual.

![Captura de pantalla del informe de actividad de usuario en el centro de administración.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar el informe de actividad de los usuarios de Microsoft Teams

Puede obtener una vista de la actividad de los usuarios de Teams consultando los **gráficos** Actividad **y** Usuarios.

![Captura de pantalla del informe de actividad de usuario con llamadas numeradas.](media/teams-user-activity-report-with-callouts.png)

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe de actividad de los usuarios de Teams para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si hace clic en un intervalo de tiempo determinado en el informe, la tabla (7) mostrará los datos de 30 días, hasta la fecha (2) en la que se generó el informe. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |La **vista** Actividad muestra el número de actividades de Microsoft Teams por tipo de actividad. Los tipos de actividad incluyen los mensajes de chat del equipo, los mensajes de chat privados, las llamadas y las reuniones. |
|**4**   |La **vista** Usuarios muestra el número de usuarios por tipo de actividad. Los tipos de actividad incluyen los mensajes de chat del equipo, los mensajes de chat privados, las llamadas y las reuniones. |
|**5**   |El eje X de los gráficos es el intervalo de fechas seleccionado para el informe específico. <ul><li>En el **gráfico** de actividad, el eje Y es el recuento de la actividad especificada.</ul></li> <ul><li>En el **gráfico Usuarios,** el eje Y es el número de usuarios que participan en chats de equipos, chats privados, llamadas o reuniones.</ul></li> |
|**6**   |Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo,  en el gráfico de actividades, haga clic  o pulse en mensajes de **canal,** mensajes de **chat,** llamadas o reuniones para ver solo la información relacionada con cada uno de ellos. Cambiar esta selección no cambia la información de la tabla de cuadrícula. |
|**7**   |La lista de equipos activos a lo largo del plazo para los informes más amplio (180 días).  El recuento de actividades variará según la selección de fecha. <br><br> Para ver la siguiente información de la tabla, asegúrese de agregar las columnas a la tabla. <ul><li>**Nombre de** usuario es la dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.</ul></li> <ul><li>**Fecha de última actividad (UTC)** hace referencia a la última fecha en la que el usuario ha participado en una actividad de Microsoft Teams.</ul></li> <ul><li>**Mensajes de canal** es el número de mensajes únicos que el usuario publicó en un chat de equipo durante el período de tiempo especificado.</ul></li> <ul><li>**Mensajes de** chat es el número de mensajes únicos que el usuario publicó en un chat privado durante el período de tiempo especificado.</ul></li> <ul><li>**Llamadas** es el número de llamadas en las que el usuario ha participado durante el período de tiempo especificado.</ul></li> <ul><li>**Reuniones es** el número de reuniones en línea en las que el usuario ha participado durante el período de tiempo especificado.</ul></li> <ul><li>**Otra actividad** es el número de actividades de equipo que ha hecho el usuario, entre las que se incluyen, entre otras: mensajes que le gustan, aplicaciones, trabajando en archivos, buscando, siguiendo equipos y canales y favoreciendo.</ul></li> <ul><li>**"Eliminado"** indica si el equipo se ha eliminado. Si el equipo se elimina, pero tuvo actividad en el período de informe, se mostrará en la cuadrícula con eliminado establecido en true.</ul></li> <ul><li>**La fecha de** eliminación es la fecha en que se eliminó el usuario.</ul></li> <ul><li>**Producto asignado** es la lista de productos asignados al usuario.</ul></li>Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **¿Cómo ocultar los** detalles del nivel de usuario? en los Informes de actividades de la versión preliminar del Centro de administración [de Microsoft 365.](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)</ui> |
|**8**   |Haga clic o **pulse columnas** para agregar o quitar columnas de la tabla. |
|**9**   |Haga clic o **pulse Exportar** para exportar los datos del informe a un archivo .csv de Excel. De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el propio informe. Si tiene más de 2000 usuarios, tendrá que exportar los datos para filtrar y ordenar el informe. 

### <a name="microsoft-teams-device-usage-report"></a>Informe de uso de dispositivos de Microsoft Teams

El informe de uso de dispositivos de Teams proporciona información sobre cómo los usuarios se conectan a Teams, incluidas las aplicaciones móviles. El informe le ayuda a comprender qué dispositivos son populares en su organización y cuántos usuarios trabajan sobre la marcha.

![Captura de pantalla del informe de uso de dispositivos de Teams.](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretar el informe de uso de dispositivos de Microsoft Teams

Puede obtener una vista del uso de dispositivos de Teams consultando los **gráficos** Usuarios **y distribución.**

![Captura de pantalla del informe de uso de dispositivos de Teams con llamadas numeradas.](media/teams-device-usage-report-with-callouts.png)

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe de dispositivos de Teams para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si hace clic en un intervalo de tiempo determinado en el informe, la tabla (7) mostrará los datos de 30 días, hasta la fecha (2) en la que se generó el informe. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |La **vista** Usuarios muestra el número de usuarios diarios por tipo de dispositivo. |
|**4**   |La **vista** Distribución muestra el número de usuarios por dispositivo durante el período de tiempo seleccionado.  |
|**5**   | <ul><li>En el **gráfico Usuarios,** el eje X es el intervalo de fechas seleccionado para el informe y el eje Y es el número de usuarios por tipo de dispositivo.</ul></li> <ul><li>En el **gráfico de** distribución, el eje X muestra los distintos dispositivos usados para conectarse a Teams y el eje Y es el número de usuarios que usan el dispositivo.</ul></li> |
|**6**   |Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo,  en el Gráfico de distribución, haga clic o pulse **en Windows,** **Mac,** **Linux,** **Web,** **iOS** o **Android** para ver solo la información relacionada con cada uno de ellos. Cambiar esta selección no cambia la información de la tabla de cuadrícula. |
|**7**   |La lista de equipos activos a lo largo del plazo para los informes más amplio (180 días).  El recuento de actividades variará según la selección de fecha. <br><br> Para ver la siguiente información en la tabla, asegúrese de agregar las columnas a la tabla. <ul><li>**Nombre de** usuario es la dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.</ul></li> <ul><li>**Fecha de última actividad (UTC)** hace referencia a la última fecha en la que el usuario ha participado en una actividad de Teams.</ul></li> <ul><li>**"Eliminado"** indica si el equipo se ha eliminado. Si el equipo se elimina, pero tuvo actividad en el período de informe, se mostrará en la cuadrícula con eliminado establecido en true.</ul></li><ul><li>**La fecha de** eliminación es la fecha en que se eliminó el usuario.</ul></li> <ul><li>**Windows**  se selecciona si el usuario estuvo activo en el cliente de escritorio de Teams en un equipo basado en Windows.</ul></li> <ul><li>**Se** selecciona Mac si el usuario estuvo activo en el cliente de escritorio de Teams en un equipo macOS.</ul></li>  <ul><li>**Linux** se selecciona si el usuario estuvo activo en el cliente de escritorio de Teams en un equipo Linux.</ul></li>   <ul><li>**La** web se selecciona si el usuario estaba activo en el cliente web de Teams.</ul></li> <ul><li>**iOS** se selecciona si el usuario estaba activo en el cliente móvil de Teams para iOS.</ul></li> <ul><li>**El teléfono Android**  está seleccionado si el usuario estaba activo en el cliente móvil de Teams para Android.</ul></li></li> <ui>Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **¿Cómo ocultar los** detalles del nivel de usuario? en los Informes de actividades de la versión preliminar del Centro de administración [de Microsoft 365.](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)</ui> |
|**8**   |Haga clic o **pulse columnas** para agregar o quitar columnas de la tabla. |
|**9**   |Haga clic o **pulse Exportar** para exportar los datos del informe a un archivo .csv de Excel. De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el propio informe. Si tiene más de 2000 usuarios, tendrá que exportar los datos para filtrar y ordenar el informe. 

## <a name="who-can-access-the-teams-activity-reports"></a>Quién puede acceder a los informes de actividad de Teams

Los usuarios asignados pueden acceder a los informes de actividades:

- Rol de administrador global
- Rol de administrador específico del producto (Exchange, Skype Empresarial o SharePoint)
- Rol de lector de informes

### <a name="reports-reader-role"></a>Rol de lector de informes

Puede asignar el rol de lector de informes a personas que no tienen derechos de administrador pero que son responsables de impulsar la adopción o realizar un seguimiento del uso de la licencia de Teams. Para obtener información sobre cómo asignar roles, lea Asignar roles de administrador y [de administrador a usuarios con Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="other-information-on-the-reports-dashboard"></a>Otra información del panel Informes

### <a name="at-a-glance-activity-widget"></a>Widget actividad de un vistazo

El panel Informes incluye los datos de uso de Teams en el widget de actividad de un vistazo, que le proporciona una vista de producto cruzada de cómo los usuarios se comunican y colaboran con los otros servicios de Microsoft 365 u Office 365.

![Captura de pantalla del widget de actividad de Teams de un vistazo.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Tarjeta de actividad de Teams

La tarjeta de actividad de Teams en el panel Informes le proporciona una descripción general de la actividad de Teams, incluido el número de usuarios activos, para que pueda comprender rápidamente cuántos usuarios usan el servicio. Al hacer clic en la tarjeta de actividad del panel, se le lleva al informe de actividad de los usuarios de Teams. 

![Captura de pantalla de la tarjeta de actividad de Teams.](media/teams-activity-card.png)
