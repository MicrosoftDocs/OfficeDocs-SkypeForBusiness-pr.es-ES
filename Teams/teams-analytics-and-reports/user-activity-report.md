---
title: Informe de actividad de usuario de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/22/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre cómo usar el informe actividad de usuarios de Teams en el centro de administración de Microsoft Teams para ver cómo los usuarios de su organización usan Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c217ae2d1344c8998e9dd8035f8c96d48a110a6d
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433011"
---
# <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe actividad de usuarios de Teams le proporciona información sobre los tipos de actividades que los usuarios de su organización realizan en Teams. Por ejemplo, puede ver cuántos usuarios se comunican a través de las llamadas de 1:1, cuántos usuarios se comunican a través de los mensajes de canal y cuántos usuarios participan en los mensajes instantáneos.

![Captura de pantalla del informe actividad de usuario de Teams] (../media/teams-reports-user-activity.png "Captura de pantalla del informe actividad de usuarios de Teams en el centro de administración de Microsoft Teams")

## <a name="view-the-report"></a>Ver el informe

1. Vaya al centro de administración de Microsoft Teams, en el navegación de la izquierda, haga clic en **Analytics & informes**y, a continuación, en **Informe**, seleccione **actividad de usuario**de Teams. 
2. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**. 

## <a name="interpret-the-report"></a>Interpretar el informe

![Captura de pantalla del informe de actividad de usuario de Teams con rótulos numerados] (../media/teams-reports-user-activity-with-callouts.png "Captura de pantalla del informe actividad de usuarios de Teams en el centro de administración de Microsoft Teams con llamadas numeradas")

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe actividad de usuarios de Teams se puede visualizar para las tendencias de los últimos 7 días o 28 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |<ul><li>El eje X de los gráficos es el intervalo de fechas seleccionado para el informe específico. </li><li>El eje Y es el número de usuarios que participan en la actividad.</li></ul>Mantenga el mouse sobre el punto que representa una actividad en una fecha determinada para ver el número de instancias de esa actividad en esa fecha determinada. |
|**4**   |Puede filtrar lo que aparece en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, haz clic en **llamadas de 1:1**, **mensajes de canal**o **mensajes** instantáneos para ver solo la información relacionada con cada uno de ellos. Cambiar la selección no cambia la información de la tabla. |
|**5**   |La tabla ofrece un desglose del uso por parte del usuario.   <ul><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el centro de administración de Microsoft Teams.</li><li>**llamadas de 1:1** es el número de llamadas de 1:1 en las que el usuario ha participado durante el período de tiempo especificado.</li><li>**Mensajes de canal** es el número de mensajes únicos que el usuario ha publicado en un chat de equipo durante el período de tiempo especificado.</li> <li>**Mensajes de chat** es el número de mensajes únicos que el usuario ha publicado en una conversación privada durante el período de tiempo especificado.</li>  <li>**Última actividad** es la última fecha (UTC) en la que el usuario participó en una actividad de Teams.</li> </ul>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**7**   |Puede exportar el informe a un archivo CSV para analizarlos sin conexión. Haga clic en **exportar a Excel**y, a continuación, en la pestaña **descargas** , haga clic en **Descargar** para descargar el informe cuando esté listo.<br>![Captura de pantalla de la pestaña descargas que muestra los informes exportados para descargar](../media/teams-reports-export-to-csv.png)||

## <a name="related-topics"></a>Temas relacionados
- [Análisis e informes de Teams](teams-reporting-reference.md)
- [Informes de uso de Teams](teams-usage-report.md)
- [Informe de uso de dispositivos de Teams](device-usage-report.md)