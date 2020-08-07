---
title: Informe de uso de aplicaciones de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Aprenda a usar el informe de uso de la aplicación de Teams en el centro de administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91af37ed9c19a1d3e8d32cdf296cf32e90818564
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583799"
---
# <a name="microsoft-teams-app-usage-report"></a>Informe de uso de aplicaciones de Microsoft Teams

El informe de uso de aplicaciones de Teams en el centro de administración de Microsoft Teams le proporciona información sobre qué aplicaciones usan los usuarios en Teams.  

## <a name="view-the-app-usage-report"></a>Ver el informe de uso de aplicaciones

1.  En el centro de navegación izquierdo del centro de administración de <https://admin.teams.microsoft.com> , haga clic en **análisis &** informes de \> **uso**de informes. En la pestaña **ver informes** , en **Informe**, seleccione **uso de aplicaciones**.

     :::image type="content" source="media/app-usage-report1.png" alt-text="Captura de pantalla del elemento de menú informes de uso":::

2.  En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**.

      :::image type="content" source="media/app-usage-report2.png" alt-text="Captura de pantalla del informe de uso de aplicaciones":::

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe de uso de las aplicaciones de Teams se puede visualizar para las tendencias de los últimos 7, 30 o 90 días. |
|**2**   |Cada informe tiene una fecha en la que se generó el informe. Los informes suelen reflejar una latencia de 24 horas desde el momento en que se abrió una aplicación. <br><br>![Captura de pantalla del informe de uso de aplicaciones que muestra intervalos de fechas](media/app-usage-report3.png)|
|**3**    | <ul><li>El eje X de los gráficos es el intervalo de fechas seleccionado para el informe específico.</li><li>El eje Y es el número de usuarios que, durante el día dado, se desplazan sobre el gráfico, esos usuarios han abierto una aplicación al menos una vez y al hacerlo se les considera un usuario activo y se acumula el total visto por el ratón.</li></ul>|
|**4**   |Desplace el puntero sobre el punto que representa el uso de una aplicación en una fecha determinada para ver el número de instancias de usuarios activos de esa aplicación en esa fecha determinada.  |
|**5**   |Se incluirán todas las aplicaciones pero seleccionando el icono de filtro, estarán disponibles filtros adicionales.  |
|**6**   |La tabla ofrece un desglose de los usuarios activos y de los equipos por nombre de aplicación.<br><ul><li>**Nombre** de la aplicación es el nombre para mostrar de la aplicación que se usa en Teams.</li><li>**Usuarios activos** es el número de usuarios que abrieron la aplicación al menos una vez durante el período de tiempo especificado.</li><li>**Tipo de aplicación** es un valor estático de "Microsoft" o "de terceros".</li><li>**Equipos activos** es el número de equipos que han abierto la aplicación al menos por un miembro del equipo y durante los períodos de tiempo especificados.</li><li>**Publisher** es el editor de software de la aplicación.</li><li>**Versión** es la versión de software de la aplicación, de la aplicación Publisher.</li></ul><br>![Captura de pantalla de un informe de uso de aplicaciones](media/app-usage-report4.png)  |
|**7**  |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.<br><br>![Captura de pantalla de la página Editar columnas](media/app-usage-report5.png)  |
|**4,8**  |Puede exportar el informe a un archivo CSV para analizarlos sin conexión. Haga clic en **exportar a Excel**y, a continuación, en la pestaña **descargas** , haga clic en **Descargar** para descargar el informe cuando esté listo.<br>![Captura de pantalla de la página de descargas](media/app-usage-report7.png)  |
|**99,999**   |Al ver el informe en Excel, también verá una columna **identificador** , que representa el identificador de la aplicación. Un identificador de equipo suele ser una cadena alfanumérica. Si la columna **ID** se muestra como * * \n * * * *, significa que un usuario ha solicitado la eliminación de su información.<br>![Captura de pantalla del informe de Excel descargado](media/app-usage-report8.png)  |

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)