---
title: Informe de actividad de usuario de Microsoft Teams
author: LanaChin
ms.author: v-lanac
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
description: Obtenga información sobre cómo usar el informe actividad de usuarios de Teams en el centro de administración de Microsoft Teams para ver cómo los usuarios de su organización usan Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 907491aab660bacd0b619b385aaef3a9309cc121
ms.sourcegitcommit: 9d60f403b42d2fdef91cdfa3caf50179a49561df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2020
ms.locfileid: "46536842"
---
# <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe actividad de usuarios de Teams ofrece información sobre los tipos de actividades que los usuarios de la organización realizan en Teams. Por ejemplo, puede ver cuántos usuarios se comunican de manera ad hoc a través de reuniones no programadas comúnmente conocidas como 1:1 y llamadas grupales, reuniones que ha organizado un usuario de Teams y reuniones en las que participó un usuario de Teams. Compartimos detalles sobre los minutos de audio, vídeo y pantalla, y estadísticas de comunicación de chats, como cuántos usuarios responden y envían mensajes de canal y cuántos usuarios participan en 1:1 o mensajes de chat grupal.

## <a name="view-the-user-activity-report"></a>Ver el informe de actividad del usuario

Para realizar estos cambios, debe ser administrador del servicio de Teams. Consulte [usar los roles de administrador de Teams para administrar los equipos](https://docs.microsoft.com/microsoftteams/using-admin-roles) para obtener información sobre cómo obtener roles y permisos de administrador.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en informes de uso de **informes &**  >  **Usage reports**. En la pestaña **ver informes** , en **Informe**, seleccione **actividad de usuario de Teams**.
2. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**.

    ![Captura de pantalla del informe actividad de usuarios de Teams en el centro de administración de Teams con llamadas](../media/teams-reports-user-activity-with-callouts.png "Captura de pantalla del informe actividad de usuarios de Teams en el centro de administración de Teams con llamadas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe actividad de usuarios de Teams se puede visualizar para las tendencias de los últimos 7 días, 30 ó 90 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Por lo general, los informes reflejan una latencia de 24 horas de actividad. |
|**3**   |<ul><li>El eje X de los gráficos es el intervalo de fechas seleccionado para el informe específico. </li><li>El eje Y es el número de usuarios que participan en la actividad.</li></ul>Mantenga el mouse sobre el punto que representa una actividad en una fecha determinada para ver el número de instancias de esa actividad en esa fecha determinada. |
|**4**   |Puede filtrar lo que aparece en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, haz clic en **llamadas de 1:1**, **mensajes de canal**o **mensajes** instantáneos para ver solo la información relacionada con cada uno de ellos. Cambiar la selección no cambia la información de la tabla. |
|**5**   |La tabla ofrece un desglose del uso por parte del usuario.   <ul><li>**Username** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el centro de administración de Microsoft Teams.</li><li>**Mensajes de canal** es el número de mensajes únicos que el usuario ha publicado en un chat de equipo durante el período de tiempo especificado.</li><li>**Mensajes de respuesta** es el número de mensajes de respuesta únicos que el usuario ha publicado en un canal de equipo durante el período de tiempo especificado.</li> <li>**Mensajes publicados** es el número de mensajes post únicos que el usuario ha publicado en un canal de equipo durante el período de tiempo especificado.</li><li>**Mensajes de chat** es el número de mensajes únicos que el usuario ha publicado en una conversación privada durante el período de tiempo especificado.</li><li>**Mensajes urgentes** es el número de mensajes urgentes que el usuario ha publicado en una conversación durante el período de tiempo especificado.</li><li>**Reuniones totales** es el número total de reuniones programadas y ad hoc en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Reuniones organizadas** es el número de reuniones programadas y ad hoc que un usuario organizó durante el período de tiempo especificado.</li><li>**Reuniones organizadas organizadas** es el número de reuniones programadas que un usuario organizó durante el período de tiempo especificado.</li><li>**Reuniones organizadas** por el Adhoc es el número de reuniones ad hoc organizadas por un usuario durante el período de tiempo especificado.</li><li>**Participaciones en reuniones** es el número de reuniones programadas y ad hoc en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**Participación de reuniones programadas** es el número de las reuniones programadas en las que participó un usuario durante el período de tiempo especificado.</li><li>**Reuniones que participaron** en el Adhoc es el número de reuniones ad hoc en las que ha participado un usuario durante el período de tiempo especificado.</li><li>**llamadas de 1:1** es el número de llamadas de 1:1 en las que el usuario ha participado durante el período de tiempo especificado.</li><li>**Tiempo de audio** es el tiempo total de audio en el que el usuario participó durante el período de tiempo especificado.</li><li>**Tiempo de video** es el tiempo total de video en el que el usuario participó durante el período de tiempo especificado.</li><li>**Tiempo compartido de pantalla** es el tiempo total compartido de pantalla en el que participó el usuario durante el período de tiempo especificado.</li>  <li>**Última actividad** es la última fecha (UTC) en la que el usuario participó en una actividad de Teams.</li><li>**Otras actividades** hacen que el usuario se considere activo pero tiene un valor de cero para los mensajes instantáneos, las llamadas de 1:1, los mensajes de canal, las reuniones totales y las reuniones organizadas. Ejemplos de acciones son cuando un usuario abre un mensaje de canal, pero no responde a él, o cuando un usuario recibe un mensaje privado y lo lee pero no responde a él.</li> </ul>Tenga en cuenta que las **llamadas a grupos** se han sustituido por las **reuniones organizadas en ad hoc** y las **reuniones que participaron en ad**, en las que la suma de estos dos valores es igual a lo que midieron las **llamadas grupales**.
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**7**   |Puede exportar el informe a un archivo CSV para analizarlos sin conexión. Haga clic en **exportar a Excel**y, a continuación, en la pestaña **descargas** , haga clic en **Descargar** para descargar el informe cuando esté listo.<br><br>![Captura de pantalla de la pestaña descargas que muestra los informes exportados para descargar](../media/teams-reports-export-to-csv.png) <br>Al ver el informe en Excel, también verá una columna **ID** , que representa el identificador del equipo. Un identificador de equipo suele ser una cadena alfanumérica. Si la columna **ID** muestra el nombre **\n**, significa que un usuario ha solicitado que se elimine su información. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
