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
description: Obtenga más información sobre cómo usar los informes de actividad para ver cómo los usuarios de su organización usan Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff2c013f286e6a6e64b88f74dc0685e3876f517e
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460640"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Use los informes de actividades de Microsoft Teams 
========================================

Puede usar los informes de actividad en el Centro de administración de Microsoft 365 para ver cómo los usuarios de su organización usan Microsoft Teams. Por ejemplo, si algunos aún no usan Microsoft Teams, puede que no sepan cómo empezar o no entiendan cómo pueden usar Teams para ser más productivos y mejorar la colaboración. Su organización puede usar los informes de actividad para decidir dónde debe dar prioridad a los esfuerzos de aprendizaje y comunicación.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Cómo ver los informes de Teams en el panel de informes

1. En el [Centro de administración de Microsoft 365](https://portal.office.com/adminportal/home), seleccione **Uso** > **de informes**.
 
2. En la página **Uso**, elija **Seleccionar un informe** y, después, en la lista de informes de **Microsoft Teams**, elija el informe que desea ver.

## <a name="teams-activity-reports-that-are-available"></a>Informes de actividad de Teams están disponibles

Actualmente hay dos informes de actividad que puede ver:

- [Informe de actividad de usuario de Microsoft Teams](#microsoft-teams-user-activity-report) 
- [Informe de uso de dispositivos de Microsoft Teams](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe de actividad de usuario de Teams le proporciona una vista de las actividades más comunes que realizan los usuarios en Teams. Esto incluye cuántos usuarios interactúan en un chat de un canal, cuántos se comunican a través de mensajes de chat privados y cuántos participan en llamadas o reuniones. Puede ver esta información para toda la organización, así como para cada usuario individual.

![Captura de pantalla del informe de actividad de usuario en el centro de administración.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar el informe de actividad de los usuarios de Microsoft Teams

Puede consultar la actividad de los usuarios en Teams mediante los gráficos **Actividad** y **Usuarios**.

![Captura de pantalla del informe de actividad de usuario con llamadas numeradas.](media/teams-user-activity-report-with-callouts.png)

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe de actividad de usuario de Teams para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si hace clic en un intervalo de tiempo concreto en el informe, la tabla (7) mostrará los datos de 30 días, hasta la fecha (2) en la que se generó el informe. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |La vista **Actividad** muestra el número de actividades de Microsoft Teams por tipo. Los tipos de actividad son el número de mensajes de chat de equipo, mensajes privados de chat, llamadas y reuniones. |
|**4**   |La vista **Usuarios** muestra el número de usuarios por tipo de actividad. Los tipos de actividad son el número de mensajes de chat de equipo, mensajes privados de chat, llamadas y reuniones. |
|**5**   |En los dos gráficos, el eje X es el intervalo de fechas seleccionado para el informe específico. <ul><li>En el gráfico **Actividad**, el eje Y es el recuento para la actividad especificada.</ul></li> <ul><li>En el gráfico **Usuarios**, el eje Y es el número de usuarios que participan en chats de equipo o privados, llamadas o reuniones.</ul></li> |
|**6**   |Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, en el gráfico **Actividad**, haga clic o pulse en **Mensajes de canal**, **Mensajes de chat**, **Llamadas** o **Reuniones** para ver solamente la información relacionada con cada uno. Cambiar esta selección no cambia la información en la tabla de cuadrícula. |
|**7**   |La lista de equipos activos durante el período de tiempo de informes más amplio (180 días).  El recuento de actividades variará según la selección de fecha. <br><br> Para ver la siguiente información en la tabla, asegúrese de agregar las columnas a la tabla. <ul><li>**Nombre de usuario** es la dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.</ul></li> <ul><li>**Última fecha de actividad (UTC)** hace referencia a la última fecha en la que el usuario haya participado en una actividad de Microsoft Teams.</ul></li> <ul><li>**Mensajes de canal** es el número de mensajes únicos que el usuario ha publicado en un chat de grupo durante el período de tiempo especificado.</ul></li> <ul><li>**Mensajes de chat** es el número de mensajes únicos que el usuario ha publicado en un chat privado durante el período de tiempo especificado.</ul></li> <ul><li>**Llamadas** es el número de llamadas en las que el usuario ha participado durante el período de tiempo especificado.</ul></li> <ul><li>**Reuniones** es el número de reuniones en línea en las que el usuario ha participado durante el período de tiempo especificado.</ul></li> <ul><li>**Otra actividad** es el número de otras actividades del equipo del usuario, entre las que se incluyen: mensajes que le gustan, aplicaciones, trabajo con archivos, búsqueda, equipos y canales que sigue y marca como favoritos.</ul></li> <ul><li>**Eliminado** indica si se eliminó el equipo. Si el equipo se elimina, pero tuvo actividad durante el período de presentación de informes, se mostrará en la cuadrícula con eliminado establecido en true.</ul></li> <ul><li>**Fecha de eliminación** es la fecha en que se eliminó el usuario.</ul></li> <ul><li>**Producto asignado** es la lista de productos asignados al usuario.</ul></li>Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **¿Cómo oculto detalles del nivel de usuario?** en [Informes de actividad en la versión preliminar del Centro de administración de Microsoft 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Haga clic o pulse en **Editar columnas** para agregar o quitar columnas en la tabla. |
|**9**   |Haga clic o pulse en **Exportar** para exportar datos del informe a un archivo .csv de Excel. De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el mismo informe. Si tiene más de 2000 usuarios, tendrá que exportar los datos para filtrar y ordenar el informe. 

### <a name="microsoft-teams-device-usage-report"></a>Informe de uso de dispositivos de Microsoft Teams

El informe de uso de dispositivos de Teams proporciona información sobre cómo se conectan los usuarios a Teams, incluidas las aplicaciones móviles. El informe le ayudará a comprender qué dispositivos son populares en su organización y cuántos usuarios trabajan desde fuera de la oficina.

![Captura de pantalla de un informe de uso de dispositivo en Teams](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretar el informe de uso de dispositivos de Microsoft Teams

Para obtener información sobre el uso de dispositivos de Teams, consulte los gráficos **Usuarios** y **Distribución**.

![Captura de pantalla de un informe de uso de dispositivo en Teams con llamadas numeradas.](media/teams-device-usage-report-with-callouts.png)

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe de dispositivo de Teams para ver las tendencias de los últimos 7, 30, 90 o 180 días. Sin embargo, si hace clic en un intervalo de tiempo concreto en el informe, la tabla (7) mostrará los datos de 30 días, hasta la fecha (2) en la que se generó el informe. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |La vista **Usuarios** muestra el número de usuarios diarios por tipo de dispositivo. |
|**4**   |La vista **Distribución** muestra el número de usuarios por dispositivo durante el período de tiempo seleccionado.  |
|**5**   | <ul><li>En el gráfico **Usuarios**, el eje X es el intervalo de fechas seleccionado para el informe y el eje Y es el número de usuarios por tipo de dispositivo.</ul></li> <ul><li>En el gráfico **Distribución**, el eje X muestra los distintos dispositivos usados para conectarse a Teams y el eje Y es el número de usuarios que usan el dispositivo.</ul></li> |
|**6**   |Puede filtrar las series que aparecen en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, en el gráfico **Distribución**, haga clic o pulse **Windows**, **Mac**, **Linux**, **Web**, **iOS** o **Android** para ver solo la información relacionada con cada uno. Cambiar esta selección no cambia la información en la tabla de cuadrícula. |
|**7**   |La lista de equipos activos durante el período de tiempo de informes más amplio (180 días).  El recuento de actividades variará según la selección de fecha. <br><br> Para ver la siguiente información en la tabla, asegúrese de agregar las columnas a la tabla. <ul><li>**Nombre de usuario** es la dirección de correo electrónico del usuario. Puede mostrar la dirección de correo electrónico real o hacer que este campo sea anónimo.</ul></li> <ul><li>**Última fecha de actividad (UTC)** hace referencia a la última fecha en la que el usuario haya participado en una actividad de Teams.</ul></li> <ul><li>**Eliminado** indica si se eliminó el equipo. Si el equipo se elimina, pero tuvo actividad durante el período de presentación de informes, se mostrará en la cuadrícula con eliminado establecido en true.</ul></li><ul><li>**Fecha de eliminación** es la fecha en que se eliminó el usuario.</ul></li> <ul><li>**Windows** está seleccionado si el usuario estaba activo en el cliente de escritorio de Teams en un equipo basado en Windows.</ul></li> <ul><li>**Mac** está seleccionado si el usuario estaba activo en el cliente de escritorio de Teams en un equipo macOS.</ul></li>  <ul><li>**Linux** está seleccionado si el usuario estaba activo en el cliente de escritorio de Teams en un equipo Linux.</ul></li>   <ul><li>**Web** está seleccionado si el usuario estaba activo en el cliente web de Teams.</ul></li> <ul><li>**iOS** está seleccionado si el usuario estaba activo en el cliente móvil e Teams para iOS.</ul></li> <ul><li>**Teléfono Android** está seleccionado si el usuario estaba activo en el cliente móvil e Teams para Android.</ul></li></li> <ui>Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **Cómo ocultar los detalles del nivel de usuario** en [Informes de actividad en la vista previa del Centro de administración de Office 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Haga clic o pulse en **Editar columnas** para agregar o quitar columnas en la tabla. |
|**9**   |Haga clic o pulse en **Exportar** para exportar datos del informe a un archivo .csv de Excel. De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el mismo informe. Si tiene más de 2000 usuarios, tendrá que exportar los datos para filtrar y ordenar el informe. 

## <a name="who-can-access-the-teams-activity-reports"></a>Quién tiene acceso a los informes de actividades de Teams

Los usuarios asignados pueden tener acceso a los informes de actividades:

- Rol de administrador global
- Rol de administrador específico del producto (Exchange, Skype Empresarial o SharePoint)
- Rol de lector de informes

### <a name="reports-reader-role"></a>Rol de lector de informes

Puede asignar el rol de lector de informes a personas que no tienen derechos de administrador, pero que sean responsables de impulsar la adopción o el seguimiento del uso de licencias de Teams. Para obtener información sobre cómo asignar roles, lea [Asignar roles de administrador y de no administrador a los usuarios con Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="other-information-on-the-reports-dashboard"></a>Otra información en el panel de informes

### <a name="at-a-glance-activity-widget"></a>Widget de actividad de un vistazo

El panel Informes incluye los datos de uso de Teams en el widget de actividad de un vistazo, que le proporciona una vista entre productos de cómo los usuarios se comunican y colaboran mediante el resto de los servicios de Microsoft 365 u Office 365.

![Captura de pantalla del widget de actividad de Teams de un vistazo.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Tarjeta de actividad de Teams

La tarjeta de actividad de Teams en el panel Informes le proporciona información general de la actividad en Teams, incluido el número de usuarios activos, para que pueda comprender rápidamente cuántos usuarios usan el servicio. Hacer clic en la tarjeta de actividad en el panel le llevará al informe de actividad de usuario de Teams. 

![Captura de pantalla de la tarjeta de actividad de Teams.](media/teams-activity-card.png)
