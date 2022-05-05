---
title: Microsoft Teams informe de uso de aplicaciones
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de uso de aplicaciones Teams en el Centro de administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8ef86a0387c3966b795c323d1c28d0e1ca788e1
ms.sourcegitcommit: e102d72e67ab1c440c29ae6a048fc2cf8545fe01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "65217954"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams informe de uso de aplicaciones

El informe de uso de aplicaciones Teams del Centro de administración de Microsoft Teams le proporciona información sobre las aplicaciones que los usuarios usan en Teams.  

## <a name="view-the-app-usage-report"></a>Ver el informe de uso de aplicaciones

1. En el panel de navegación izquierdo del centro de administración, en , haga clic en <https://admin.teams.microsoft.com>**Análisis &** **informesAdministrar** >  informes.<br><br>![Captura de pantalla del elemento de menú Informes de uso.](media/app-usage-report1.png "Captura de pantalla del elemento de menú Informes de uso.")
2. En la pestaña **Ver informes** , en **Informe**, seleccione **Uso de aplicaciones**.

3. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**. El informe uso de aplicaciones Teams puede visualizarse para ver las tendencias de los últimos 7, 30 o 90 días.<br><br>![Captura de pantalla del informe Uso de aplicaciones.](media/app-usage-report2.png "Captura de pantalla del informe Uso de aplicaciones.")


## <a name="interpret-the-report"></a>Interpretar el informe

:::image type="content" alt-text="Captura de pantalla del informe de uso de aplicaciones de Teams en el centro de administración de Teams con globos." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

Cada informe tiene una fecha en la esquina superior izquierda que muestra cuándo se creó el informe. Los informes suelen reflejar una latencia de 24 horas desde el momento en que se abrió una aplicación.

El eje Y del gráfico es el número de usuarios que para la fecha que ha seleccionado manteniendo el mouse sobre el gráfico se consideran usuarios activos porque han abierto una aplicación al menos una vez.

El eje X del gráfico es el intervalo de fechas seleccionado para el informe.

Desplace el puntero sobre el punto (4) que representa el uso de una aplicación en cualquier fecha para ver el número total de usuarios activos de esa aplicación en esa fecha.

Para seleccionar otras aplicaciones, en la esquina superior derecha, haga clic en el icono **Filtro** (5), seleccione o escriba nuevos criterios y, a continuación, haga clic en **Aplicar**.

La tabla de la parte inferior del informe (6) muestra los usuarios activos y equipos por nombre de aplicación.

   - **Nombre de aplicación** es el nombre para mostrar de la aplicación que se usa en Teams.
   - **Usuarios activos** es el número de usuarios que han abierto la aplicación al menos una vez durante el período de tiempo especificado.
   - **El tipo de aplicación** es un valor estático de "Microsoft" o "Tercero".
   - **Equipos activos** es el número de equipos que han abierto la aplicación por al menos un miembro del equipo y durante los períodos de tiempo especificados.
   - **Publisher** es el editor de software de la aplicación.
   - **Versión** es la versión de software de la aplicación, del editor de la aplicación.

   > [!NOTE]
   > **Los usuarios activos** y **los equipos activos** se calculan solo para las aplicaciones que se usan en canales.

Para agregar o quitar columnas en la tabla, en la esquina superior derecha, haga clic en el icono **Editar columnas** (7), en la pestaña **Editar columnas** , seleccione nuevos criterios y, a continuación, haga clic en **Aplicar**.

Para exportar el informe a un archivo CSV para analizarlo sin conexión, en la esquina superior derecha, seleccione el icono **Exportar a Excel** (8) y, a continuación, en la pestaña **Descargas** en **Estado**, haga clic en **Descargar**.

   :::image type="content" alt-text="Captura de pantalla del panel Descargas." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

Al ver el informe en Excel, también verá una columna **Id**. que representa el id. de aplicación, normalmente una cadena alfanumérica. Si el **Id** **. está\n**, esto significa que un usuario solicitó que se eliminara su información.

   ![Captura de pantalla del informe de Excel descargado.](media/app-usage-report8.png "Captura de pantalla del informe de Excel descargado.")

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
