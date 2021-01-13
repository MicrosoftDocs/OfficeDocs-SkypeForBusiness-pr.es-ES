---
title: Informe de actividad de usuario de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de actividad de los usuarios de Teams en el Centro de administración de Microsoft Teams para ver cómo usan teams los usuarios de su organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 85d907e527f8b957abf1a5f3b8b9f0d8c5f44443
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809200"
---
# <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe de actividad de los usuarios de Teams proporciona información sobre los tipos de actividades que los usuarios de su organización realizan en Teams. Por ejemplo, se puede ver cuántos usuarios se comunican de forma ad hoc a través de reuniones no programadas conocidas comúnmente como llamadas uno a uno o grupales, reuniones que ha organizado un usuario de Teams y reuniones en las que ha participado un usuario de Teams. Compartimos detalles sobre los minutos de audio, vídeo y pantalla, y las estadísticas de comunicación de chat, como cuántos usuarios responden y publican mensajes del canal, y cuántos usuarios participan en mensajes de chat grupales o uno a uno.

## <a name="view-the-user-activity-report"></a>Ver el informe de actividad de usuario

Debe ser administrador del servicio de Teams para realizar estos cambios. Consulte [Usar los roles de administrador de Teams para administrar Teams y](https://docs.microsoft.com/microsoftteams/using-admin-roles) obtener información sobre cómo obtener permisos y roles de administrador.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **& informes de**  >  **uso.** En la **pestaña Ver informes,** en **Informe,** seleccione Actividad **de usuario de Teams.**
2. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**.

    ![Captura de pantalla del informe de actividad de los usuarios de Teams en el centro de administración de Teams con llamadas](../media/teams-reports-user-activity-with-callouts.png "Captura de pantalla del informe de actividad de los usuarios de Teams en el centro de administración de Teams con llamadas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe de actividad de los usuarios de Teams para ver las tendencias de los últimos 7, 30 o 90 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, los informes reflejan una latencia de 24 horas desde el momento de actividad. |
|**3**   |<ul><li>El eje X de los gráficos es el intervalo de fechas seleccionado para el informe específico. </li><li>El eje Y es el número de usuarios que participan en la actividad.</li></ul>Mantenga el mouse sobre el punto que representa una actividad en una fecha determinada para ver el número de instancias de esa actividad en esa fecha. |
|**4**   |Puede filtrar lo que aparece en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, haga clic en  **llamadas uno a uno,** mensajes de canal o mensajes de **chat** para ver solo la información relacionada con cada uno de ellos. Cambiar la selección no cambia la información de la tabla. |
|**5**   |La tabla proporciona un desglose del uso por usuario.   <ul><li>**Nombre** de usuario es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Centro de administración de Microsoft Teams.</li><li>**Mensajes de canal** es el número de mensajes únicos que el usuario publicó en un chat de equipo durante el período de tiempo especificado.</li><li>**Mensajes de respuesta** es el número de mensajes de respuesta única que el usuario publicó en un canal de equipo durante el período de tiempo especificado.</li> <li>**Publicar mensajes** es el número de mensajes de publicación únicos que el usuario publicó en un canal de equipo durante el período de tiempo especificado.</li><li>**Mensajes de** chat es el número de mensajes únicos que el usuario publicó en un chat privado durante el período de tiempo especificado.</li><li>**Mensajes urgentes** es el número de mensajes urgentes que el usuario publicó en un chat durante el período de tiempo especificado.</li><li>**El total de** reuniones es el número total de reuniones programadas y ad hoc en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Las reuniones organizadas** es el número de reuniones programadas y ad hoc que ha organizado el usuario durante el período de tiempo especificado.</li><li>**Las reuniones organizadas es** el número de reuniones programadas que un usuario ha organizado durante el período de tiempo especificado.</li><li>**Reuniones organizadas es el** número de reuniones ad hoc que organizó un usuario durante el período de tiempo especificado.</li><li>**Las reuniones en las** que se ha participado es el número de reuniones programadas y las reuniones ad hoc en las que el usuario ha participado durante el período de tiempo especificado.</li><li>**Las reuniones en las que se ha** participado es el número de reuniones programadas en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Meetings participated adhoc** is the number of ad hoc meetings a user participated in during the specified time period.</li><li>**Las llamadas de 1:1** son el número de llamadas de 1:1 en las que el usuario ha participado durante el período de tiempo especificado.</li><li>**El tiempo de** audio es el tiempo total de audio en el que el usuario ha participado durante el período de tiempo especificado.</li><li>**El tiempo de** vídeo es el tiempo total de vídeo en el que el usuario ha participado durante el período de tiempo especificado.</li><li>**El tiempo de uso compartido** de la pantalla es el tiempo total de pantalla compartida en el que el usuario ha participado durante el período de tiempo especificado.</li>  <li>**La última** actividad es la última fecha (UTC) en la que el usuario ha participado en una actividad de Teams.</li><li>**Otra actividad** realiza un seguimiento cuando el usuario se considera activo, pero tiene un valor cero para los mensajes de chat, las llamadas uno a uno, los mensajes de canal, el total de reuniones y las reuniones organizadas. Algunos ejemplos de acciones son cuando un usuario abre una publicación de mensaje de canal pero no responde o cuando un usuario recibe un mensaje privado y lo lee pero no responde.</li> </ul>Tenga  en cuenta que las llamadas de grupo se han sustituido por reuniones **organizadas** y reuniones en las que se ha participado, en las que la suma de estos dos valores es igual **a** lo que se mide con las llamadas **de grupo.**
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**7**   |Puede exportar el informe a un archivo CSV para analizarlo sin conexión. Haga **clic en Exportar a Excel** y, a continuación, en la pestaña Descargas, haga clic en Descargar para descargar el informe cuando esté listo.  <br><br>![Captura de pantalla de la pestaña Descargas que muestra los informes exportados para descargar](../media/teams-reports-export-to-csv.png) <br>Cuando vea el informe en Excel, también  verá una columna Id., que representa el id. de equipo. Un id. de equipo suele ser una cadena alfanumérica. Si la **columna Id.** se **muestra como \n,** esto significa que un usuario solicitó que se eliminara su información. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
