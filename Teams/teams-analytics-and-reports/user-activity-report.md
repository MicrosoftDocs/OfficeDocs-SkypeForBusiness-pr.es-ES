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
ms.openlocfilehash: 8d6fb204cbfeece1df063f9b17f2912fad69f910
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825798"
---
# <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe actividad de usuarios de Teams le proporciona información sobre los tipos de actividades que los usuarios de su organización realizan en Teams. Por ejemplo, puede ver cuántos usuarios se comunican a través de las llamadas de 1:1, cuántos usuarios se comunican a través de los mensajes de canal y cuántos usuarios participan en los mensajes instantáneos.

## <a name="view-the-report"></a>Ver el informe

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en > **informes de uso**de **informes &**. En la pestaña **ver informes** , en **Informe**, seleccione **actividad de usuario de Teams**.
2. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**.

    ![Captura de pantalla del informe actividad de usuarios de Teams en el centro de administración de Teams con llamadas](../media/teams-reports-user-activity-with-callouts.png "Captura de pantalla del informe actividad de usuarios de Teams en el centro de administración de Teams con llamadas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe actividad de usuarios de Teams se puede visualizar para las tendencias de los últimos 7 días o 28 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |<ul><li>El eje X de los gráficos es el intervalo de fechas seleccionado para el informe específico. </li><li>El eje Y es el número de usuarios que participan en la actividad.</li></ul>Mantenga el mouse sobre el punto que representa una actividad en una fecha determinada para ver el número de instancias de esa actividad en esa fecha determinada. |
|**4**   |Puede filtrar lo que aparece en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, haz clic en **llamadas de 1:1**, **mensajes de canal**o **mensajes** instantáneos para ver solo la información relacionada con cada uno de ellos. Cambiar la selección no cambia la información de la tabla. |
|**5**   |La tabla ofrece un desglose del uso por parte del usuario.   <ul><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el centro de administración de Microsoft Teams.</li><li>**llamadas de 1:1** es el número de llamadas de 1:1 en las que el usuario ha participado durante el período de tiempo especificado.</li><li>**Mensajes de canal** es el número de mensajes únicos que el usuario ha publicado en un chat de equipo durante el período de tiempo especificado.</li> <li>**Mensajes de chat** es el número de mensajes únicos que el usuario ha publicado en una conversación privada durante el período de tiempo especificado.</li>  <li>**Última actividad** es la última fecha (UTC) en la que el usuario participó en una actividad de Teams.</li> </ul>Tenga en cuenta que si ya no existe una cuenta de usuario en Azure AD, el nombre de usuario se muestra como "--" en la tabla. <br><br>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**7**   |Puede exportar el informe a un archivo CSV para analizarlos sin conexión. Haga clic en **exportar a Excel**y, a continuación, en la pestaña **descargas** , haga clic en **Descargar** para descargar el informe cuando esté listo.<br><br>![Captura de pantalla de la pestaña descargas que muestra los informes exportados para descargar](../media/teams-reports-export-to-csv.png) <br>Al ver el informe en Excel, también verá una columna **ID** , que representa el identificador del equipo. Un identificador de equipo suele ser una cadena alfanumérica. Si la columna **ID** muestra el nombre **\n**, significa que un usuario ha solicitado que se elimine su información. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)