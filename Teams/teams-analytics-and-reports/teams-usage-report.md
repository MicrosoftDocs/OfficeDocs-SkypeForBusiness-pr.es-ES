---
title: Informe de uso de Microsoft Teams
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
description: Aprenda a usar el informe de uso de Teams en el centro de administración de Microsoft Teams para obtener información general sobre la actividad de Teams en su organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63193b6540a40e9ad4a2171c95f638dfb7c1d112
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809270"
---
# <a name="microsoft-teams-usage-report"></a>Informe de uso de Microsoft Teams

El informe de uso de Teams en el centro de administración de Microsoft Teams proporciona información general sobre la actividad de uso en Teams, como el número de usuarios y canales activos, para que pueda ver rápidamente cuántos usuarios en su organización usan Teams para comunicarse y colaborar. Puede ver información sobre el uso para equipos, como el número de canales y usuarios activos, invitados y mensajes en cada equipo.

## <a name="view-the-usage-report"></a>Ver el informe de uso

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **& informes de**  >  **uso.** En la **pestaña Ver informes,** en **Informe,** seleccione **Uso de Teams.**
2. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**.

    ![Captura de pantalla del informe de uso de Teams en el Centro de administración de Teams con llamadas](../media/teams-reports-teams-usage-with-callouts.png "Captura de pantalla del informe de uso de Teams en el Centro de administración de Teams con llamadas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe de actividad de uso de Teams para ver las tendencias de los últimos 7, 30 o 90 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |<ul><li>En el gráfico, el eje X es el intervalo de fechas seleccionado para el informe específico.</li> <li> El eje Y es el número de elementos activos o actividad.</li> </ul>Mueva el puntero sobre el punto que representa un elemento o actividad en una fecha determinada para ver el número de instancias de ese elemento o actividad en esa fecha.|
|**4**   |Puede filtrar lo que aparece en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, haga **clic** en Total de usuarios activos,  Equipos **& Canales** **activos,** Canales activos o Mensajes para ver solo la información relacionada con cada uno de ellos. Al cambiar esta selección no se cambia la información de la tabla. |
|**5**   |La tabla le proporciona un desglose del uso por equipo. <ul><li>**El nombre del** equipo es el nombre para mostrar del equipo. Puede hacer clic en el nombre del equipo para ir a la página de configuración del equipo en el Centro de administración de Microsoft Teams. </li> <li>**Privacidad** hace referencia a si es un equipo privado o público.</li> <li>**Usuarios activos** es el número de usuarios activos en el equipo en el período de tiempo especificado.</li><li>**Invitados** es el número de invitados en el equipo en el período de tiempo especificado.</li> <li>**Los canales** activos son el número de canales que tienen al menos un usuario activo en el período de tiempo especificado.</li> <li>**Publicar mensajes** es el número de todos los mensajes publicados en canales en el período de tiempo especificado.</li> <li>**Los mensajes de** respuesta son el número de todos los mensajes de respuesta de los canales durante el período de tiempo especificado.</li> <li>**Las reuniones organizadas** es el número de reuniones programadas y ad hoc que ha organizado el usuario durante el período de tiempo especificado. </li><li>**Mensajes urgentes** es el número de todos los mensajes urgentes en el período de tiempo especificado.</li><li>**Reacciones** es el número de todas las reacciones a los mensajes durante el período de tiempo especificado.</li><li>**Menciones** es el número de todas las menciones usadas en los mensajes en el período de tiempo especificado.</li><li>**Mensajes de** canal es el número de mensajes únicos que los usuarios del equipo han publicado en los chats del equipo durante el período de tiempo especificado.</li> </li> </ul>Tenga en cuenta que si una cuenta de usuario ya no existe en Azure AD, el nombre de usuario se muestra como "--" en la tabla. <br><br>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|
|**7**   |Puede exportar el informe a un archivo CSV para analizarlo sin conexión. Haga **clic en Exportar a Excel** y, a continuación, en la pestaña Descargas, haga clic en Descargar para descargar el informe cuando esté listo.  <br><br>![Captura de pantalla de la pestaña Descargas que muestra los informes exportados para descargar](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
