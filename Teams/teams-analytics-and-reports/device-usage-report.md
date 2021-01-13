---
title: Informe de uso de dispositivos de Microsoft Teams
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
description: Obtenga información sobre cómo usar el informe de uso de dispositivos de Teams en el Centro de administración de Microsoft Teams para ver cómo los usuarios de su organización se conectan a Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 292632972396f5d4300fa2526f01e69a5555ff45
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815650"
---
# <a name="microsoft-teams-device-usage-report"></a>Informe de uso de dispositivos de Microsoft Teams

El informe de uso de dispositivos de Teams en el Centro de administración de Microsoft Teams le proporciona información sobre cómo los usuarios se conectan a Teams. Puede usar el informe para ver los dispositivos que se usan en toda la organización, incluido cuántos usan Teams desde sus dispositivos móviles cuando están fuera.  

## <a name="view-the-device-usage-report"></a>Ver el informe de uso de dispositivos

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **& informes de**  >  **uso.** En la **pestaña Ver informes,** en **Informe,** seleccione Uso de **dispositivos de Teams.**
2. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**.

    ![Captura de pantalla del informe de uso de dispositivos de Teams en el Centro de administración de Teams con llamadas](../media/teams-reports-device-usage-with-callouts.png "Captura de pantalla del informe de uso de dispositivos de Teams en el Centro de administración de Teams con llamadas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe de uso de dispositivos de Teams para ver las tendencias de los últimos 7 o 30 días.  |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, los informes reflejan una latencia de 24 horas desde el momento de actividad. |
|**3**   |<ul><li>El eje X del gráfico representa los distintos dispositivos **(Windows,** **Mac,** **Linux,** **iOS,** **Android Phone,** **Web)** usados para conectarse a Teams. </li><li>El eje Y es el número de usuarios que usan el dispositivo durante el período de tiempo seleccionado.</li> </ul>Mantenga el mouse sobre la barra que representa un dispositivo para ver el número de usuarios que usan el dispositivo para conectarse a Teams.|
|**4**   |La tabla proporciona un desglose del uso del dispositivo por usuario. <ul><li>**Nombre** de usuario es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Centro de administración de Microsoft Teams. </li><li>**Windows** se selecciona si el usuario estuvo activo en el cliente de escritorio de Teams en un equipo basado en Windows.</li><li>**Se** selecciona Mac si el usuario estuvo activo en el cliente de escritorio de Teams en un equipo macOS. </li> <li>**Linux** se selecciona si el usuario estuvo activo en el cliente de escritorio de Teams en un equipo Linux. </li> <li>**iOS** se selecciona si el usuario estaba activo en el cliente móvil de Teams para iOS.</li><li>**El teléfono Android** está seleccionado si el usuario estaba activo en el cliente móvil de Teams para Android. <li><li>**La** web se selecciona si el usuario estaba activo en el cliente web de Teams. <li>**La última** actividad es la última fecha (UTC) en la que el usuario ha participado en una actividad de Teams.</li> </ul> Tenga en cuenta que si una cuenta de usuario ya no existe en Azure AD, el nombre de usuario se muestra como "--" en la tabla. <br><br>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Puede exportar el informe a un archivo CSV para analizarlo sin conexión. Haga **clic en Exportar a Excel** y, a continuación, en la pestaña Descargas, haga clic en Descargar para descargar el informe cuando esté listo.  <br><br>![Captura de pantalla de la pestaña Descargas que muestra los informes exportados](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
