---
title: Informe de uso de aplicaciones de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.date: 09/27/2022
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de uso de aplicaciones de Teams en el Centro de administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9db5378a439061639298b8bc3b48f4d3ef26c50b
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68376968"
---
# <a name="microsoft-teams-app-usage-report"></a>Informe de uso de aplicaciones de Microsoft Teams

El informe de uso de aplicaciones de Teams en el Centro de administración de Microsoft Teams le proporciona información sobre qué aplicaciones usan los usuarios en Teams. Puede obtener información sobre la actividad de las aplicaciones de Teams en su organización. En este artículo se explica cómo acceder al informe y ver e interpretar las distintas métricas del informe. 

## <a name="view-the-app-usage-report"></a>Ver el informe de uso de aplicaciones

1. En el panel de navegación izquierdo del Centro de administración de Teams, seleccione **Análisis & informes****[de uso](https://admin.teams.microsoft.com/analytics/reports)** > .

   :::image type="content" source="media/app-usage-report1.png" alt-text="Captura de pantalla del elemento de menú Informes de uso.":::

1. En la pestaña **Ver informes** , en **Informe**, seleccione **Uso de aplicaciones**.

1. En **Intervalo de fechas**, seleccione un intervalo y, a continuación, seleccione **Ejecutar informe**. Puede ver el informe Uso de aplicaciones de Teams para ver las tendencias de los últimos 7, 30, 90 y 180 días.

   :::image type="content" source="media/app-usage-report2-trimmed.png" alt-text="Captura de pantalla de la interfaz del informe de uso de aplicaciones." lightbox="media/app-usage-report2.png":::

## <a name="interpret-the-report"></a>Interpretar el informe

:::image type="content" alt-text="Captura de pantalla del informe de uso de aplicaciones de Teams en el Centro de administración de Teams con globos." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

Cada informe tiene una fecha en la esquina superior izquierda que muestra cuándo se creó el informe. Los informes suelen reflejar una latencia de 24 a 48 horas desde el momento en que se abrió una aplicación.

Administración centro proporciona un gráfico de los usuarios activos y las fechas. Usuarios activos es el número de usuarios que han abierto una aplicación al menos una vez durante el período de tiempo seleccionado.

Desplace el puntero sobre el punto (4) que representa el uso de una aplicación en cualquier fecha para ver el número total de usuarios activos de esa aplicación en esa fecha.

Para seleccionar otras aplicaciones, en la esquina superior derecha, seleccione el icono **Filtro** (5), seleccione o escriba nuevos criterios y, después, seleccione **Aplicar**.

La tabla de la parte inferior del informe (6) muestra los usuarios activos y equipos por nombre de aplicación.

   - **Nombre de aplicación** es el nombre para mostrar de la aplicación que se usa en Teams.
   - **Usuarios activos** es el número de usuarios que han abierto la aplicación al menos una vez durante el período de tiempo especificado.
   - **El tipo de aplicación** es un valor estático de "Microsoft" o "Tercero".
   - **Equipos activos** es el número de equipos que han abierto la aplicación por al menos un miembro del equipo y durante los períodos de tiempo especificados.
   - **Publisher** es el desarrollador de software de la aplicación.
   - **Versión** es la versión de software de la aplicación, del desarrollador de la aplicación.

   > [!NOTE]
   > **Los usuarios activos** y **los equipos activos** se calculan solo para las aplicaciones que se usan en canales.

Para agregar o quitar columnas de la tabla, en la esquina superior derecha, seleccione el icono **Editar columnas** (7), en la pestaña **Editar columnas** , seleccione nuevos criterios y, después, seleccione **Aplicar**.

Para exportar el informe a un archivo CSV para analizarlo sin conexión, en la esquina superior derecha, seleccione el icono **Exportar a Excel** (8) y, a continuación, en la pestaña **Descargas** , en **Estado**, seleccione **Descargar**.

   :::image type="content" alt-text="Captura de pantalla del panel Descargas." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

Al ver el informe en Microsoft Excel, también verá una `Id` columna, que representa el id. de aplicación, normalmente una cadena alfanumérica. Si el valor del `Id` es **\n**, significa que un usuario pidió que se eliminara su información.

   :::image type="content" source="media/app-usage-report8.png" alt-text="Captura de pantalla del informe de Excel descargado.":::

## <a name="related-articles"></a>Artículos relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
