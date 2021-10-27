---
title: Microsoft Teams de uso de aplicaciones
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
description: Obtenga información sobre cómo usar el Teams de uso de aplicaciones en el centro Microsoft Teams administración.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7679652f0cb93e445e72af80307803b1e3197992
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2021
ms.locfileid: "60596217"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams de uso de aplicaciones

El Teams de uso de aplicaciones en el centro de administración de Microsoft Teams proporciona información sobre las aplicaciones que los usuarios usan en Teams.  

## <a name="view-the-app-usage-report"></a>Ver el informe uso de aplicaciones

1. En el panel de navegación izquierdo del centro de administración en , haga <https://admin.teams.microsoft.com> clic en Análisis & informes **de**  >  **uso.**<br><br>![Captura de pantalla del elemento de menú Informes de uso.](media/app-usage-report1.png "Captura de pantalla del elemento de menú Informes de uso.")
2. En la pestaña **Ver informes,** en **Informe,** seleccione **Uso de aplicaciones.**

3. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**. El Teams de uso de aplicaciones se puede ver para ver las tendencias de los últimos 7, 30 o 90 días.<br><br>![Captura de pantalla del informe Uso de aplicaciones.](media/app-usage-report2.png "Captura de pantalla del informe Uso de aplicaciones.")


## <a name="interpret-the-report"></a>Interpretar el informe

:::image type="content" alt-text="Captura de pantalla del Teams de uso de aplicaciones en el Teams de administración con llamadas." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

1. Cada informe tiene una fecha en la esquina superior izquierda que muestra cuándo se creó el informe. Los informes normalmente reflejan una latencia de 24 horas desde el momento en que se abrió una aplicación.

2. El eje Y del gráfico es el número de usuarios que para la fecha seleccionada al mantener el puntero sobre el gráfico se consideran usuarios activos porque han abierto una aplicación al menos una vez.

3. El eje X del gráfico es el intervalo de fechas que ha seleccionado para el informe.

4. Mantenga el puntero sobre el punto que representa el uso de una aplicación en cualquier fecha para ver el número total de usuarios activos de esa aplicación en esa fecha.

5. Para seleccionar otras aplicaciones, en  la esquina superior derecha, haga clic en el icono Filtro, seleccione o escriba nuevos criterios y, a continuación, haga clic en **Aplicar.**

6. La tabla de la parte inferior del informe muestra usuarios y equipos activos por nombre de aplicación.

   - **El nombre de** la aplicación es el nombre para mostrar de la aplicación que se usa en Teams.
   - **Usuarios activos** es el número de usuarios que abrieron la aplicación al menos una vez durante el período de tiempo especificado.
   - **El tipo de** aplicación es un valor estático de "Microsoft" o "Tercero".
   - **Equipos activos** es el número de equipos que han abierto la aplicación por al menos un miembro del equipo y durante los períodos de tiempo especificados.
   - **Publisher** es el editor de software de la aplicación.
   - **Versión** es la versión de software de la aplicación, del editor de aplicaciones.

   > [!NOTE]
   > **Los usuarios activos** y **los equipos activos** se calculan solo para las aplicaciones que se usan en los canales.

7. Para agregar o quitar columnas en la tabla,  en la esquina  superior derecha, haga clic en el icono Editar columnas, en la pestaña Editar columnas, seleccione nuevos criterios y, a continuación, haga clic en **Aplicar.**

8. Para exportar el informe a un archivo CSV para analizarlo sin conexión, en la esquina  superior derecha, seleccione el icono Exportar **Excel y, a continuación,** en la pestaña Descargas en **Estado,** haga clic en **Descargar.**

   :::image type="content" alt-text="Captura de pantalla del panel Descargas." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

9. Al ver el informe en Excel, también verá una columna **Id,** que representa el id. de la aplicación, normalmente una cadena alfanumérica. Si el **id.\n**, significa que un usuario solicitó que se eliminara su información. 

   ![Captura de pantalla del informe Excel descargado.](media/app-usage-report8.png "Captura de pantalla del informe Excel descargado.")

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
