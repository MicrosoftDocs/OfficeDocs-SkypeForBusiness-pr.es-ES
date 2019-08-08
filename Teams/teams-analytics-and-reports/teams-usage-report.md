---
title: Informe de uso de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Aprenda a usar el informe de uso de Teams en el centro de administración de Microsoft Teams para obtener información general sobre la actividad de Teams en su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5fdee65771f2ac23e2cea78e54752786357405
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234775"
---
# <a name="microsoft-teams-usage-report"></a>Informe de uso de Microsoft Teams

El informe de uso de Teams en el centro de administración de Microsoft Teams proporciona información general sobre la actividad de uso en Teams, como el número de usuarios y canales activos, para que pueda ver rápidamente cuántos usuarios en su organización usan Teams para comunicarse y colaborar. Puede ver información sobre el uso para equipos, como el número de canales y usuarios activos, invitados y mensajes en cada equipo.

![Captura de pantalla del informe de uso de equipos en el centro de administración] (../media/teams-reports-teams-usage.png "Captura de pantalla del informe de uso de equipos en el centro de administración de Microsoft Teams")

## <a name="view-the-report"></a>Ver el informe

1.In el centro de administración de Microsoft Teams, en la barra de navegación izquierda, haga clic en **análisis & informes**y, a continuación, en **Informe**, seleccione **uso de equipos**.
2. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**.

## <a name="interpret-the-report"></a>Interpretar el informe

![Captura de pantalla del informe de uso de equipos en el centro de administración] (../media/teams-reports-teams-usage-with-callouts.png "Captura de pantalla del informe de uso de equipos en el centro de administración de Microsoft Teams con llamadas numeradas")

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe de actividad de uso de Teams se puede visualizar para ver las tendencias de los últimos 7 o 28 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |<ul><li>En el gráfico, el eje X es el intervalo de fechas seleccionado para el informe específico.</li> <li> El eje Y es el número de elementos activos o actividad.</li> </ul>Mueva el puntero sobre el punto que representa un elemento o actividad en una fecha determinada para ver el número de instancias de ese elemento o actividad en esa fecha.|
|**4**   |Puede filtrar lo que aparece en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, haga clic en **total de usuarios activos**, **equipos & canales usuarios activos**, **canales activos**o **mensajes** para ver solo la información relacionada con cada uno de ellos. Al cambiar esta selección no se cambia la información de la tabla. |
|**5**   |La tabla le proporciona un desglose del uso por equipo. <ul><li>**Nombre del equipo** es el nombre para mostrar del equipo. Puede hacer clic en el nombre del equipo para ir a la página de configuración del equipo en el centro de administración de Microsoft Teams. </li> <li>**Privacidad** hace referencia a si es un equipo privado o público.</li> <li>**Usuarios activos** es el número de usuarios activos en el equipo en el período de tiempo especificado.</li><li>**Invitados** es el número de invitados en el equipo en el período de tiempo especificado.</li> </li> </ul>Tenga en cuenta que si ya no existe una cuenta de usuario en Azure AD, el nombre de usuario se muestra como "--" en la tabla. <br><br>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|
|**7**   |Puede exportar el informe a un archivo CSV para analizarlos sin conexión. Haga clic en **exportar a Excel**y, a continuación, en la pestaña **descargas** , haga clic en **Descargar** para descargar el informe cuando esté listo.<br>![Captura de pantalla de la pestaña descargas que muestra los informes exportados para descargar](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Temas relacionados
- [Análisis e informes de Teams](teams-reporting-reference.md)
