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
description: Obtenga información sobre cómo usar el informe de uso de aplicaciones de Teams en el Centro de administración de Microsoft Teams.
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

El informe de uso de aplicaciones de Teams en el Centro de administración de Microsoft Teams le proporciona información sobre las aplicaciones que usan los usuarios en Teams.  

## <a name="view-the-app-usage-report"></a>Ver el informe Uso de aplicaciones

1.  En el panel de navegación izquierdo del centro de administración, haga clic en <https://admin.teams.microsoft.com> **& informes** \> **de uso.** En la **pestaña Ver informes,** en **Informe,** seleccione **Uso de aplicaciones.**

     :::image type="content" source="media/app-usage-report1.png" alt-text="Captura de pantalla del elemento de menú Informes de uso":::

2.  En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**.

      :::image type="content" source="media/app-usage-report2.png" alt-text="Captura de pantalla del informe Uso de aplicaciones":::

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe de uso de aplicaciones de Teams para ver las tendencias de los últimos 7, 30 o 90 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, los informes reflejan una latencia de 24 horas desde el momento en que se abrió una aplicación. <br><br>![Captura de pantalla del informe Uso de aplicaciones que muestra intervalos de fechas](media/app-usage-report3.png)|
|**3**    | <ul><li>En los gráficos, el eje X es el intervalo de fechas seleccionado para el informe específico.</li><li>El eje Y es el número de usuarios que para un día determinado se desplazan por el gráfico, los usuarios han abierto una aplicación al menos una vez y al hacerlo se consideran usuarios activos y se acumulan hacia el total visto al pasar el mouse por encima.</li></ul>|
|**4**   |Mantenga el mouse sobre el punto que representa un Uso de aplicaciones en una fecha determinada para ver el número de instancias del total de usuarios activos de esa aplicación en esa fecha determinada.  |
|**5**   |Se incluirán todas las aplicaciones, pero si elige el icono Filtro, habrá disponibles filtros adicionales.  |
|**6**   |La tabla proporciona un desglose de los usuarios y equipos activos por nombre de aplicación.<br><ul><li>**El nombre de** la aplicación es el nombre para mostrar de la aplicación que se usa en Teams.</li><li>**Usuarios activos** es el número de usuarios que han abierto la aplicación al menos una vez durante el período de tiempo especificado.</li><li>**El tipo** de aplicación es un valor estático de "Microsoft" o "Terceros".</li><li>**Equipos activos** es el número de equipos que han abierto la aplicación por al menos un miembro del equipo y durante los períodos de tiempo especificados.</li><li>**Publisher** es el editor de software de la aplicación.</li><li>**La** versión es la versión de software de la aplicación, del editor de la aplicación.</li></ul><br>![Captura de pantalla de un informe de uso de aplicaciones](media/app-usage-report4.png)  |
|**7**  |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.<br><br>![Captura de pantalla de la página Editar columnas](media/app-usage-report5.png)  |
|**8**  |Puede exportar el informe a un archivo CSV para analizarlo sin conexión. Haga **clic en Exportar a Excel** y, a continuación, en la pestaña Descargas, haga clic en Descargar para descargar el informe cuando esté listo.  <br>![Captura de pantalla de la página Descargas](media/app-usage-report7.png)  |
|**9**   |Cuando vea el informe en Excel, también  verá una columna Id., que representa el id. de aplicación. Un id. de equipo suele ser una cadena alfanumérica. Si la **columna Id.** se muestra como **\n****, esto significa que un usuario solicitó que se eliminara su información.<br>![Captura de pantalla del informe de Excel descargado](media/app-usage-report8.png)  |

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)