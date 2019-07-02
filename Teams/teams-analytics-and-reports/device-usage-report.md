---
title: Informe de uso de dispositivos de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/24/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de uso de dispositivos de Teams en el centro de administración de Microsoft Teams para ver cómo los usuarios de su organización se conectan a teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86d8e2dc145aa8538326b42f5110de69542e8453
ms.sourcegitcommit: 5791b98589e64df2e2bcd96f05fd2f869a65861f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "35420015"
---
# <a name="microsoft-teams-device-usage-report"></a>Informe de uso de dispositivos de Microsoft Teams

El informe de uso de dispositivos de Teams en el centro de administración de Microsoft Teams le proporciona información sobre cómo los usuarios se conectan a teams. Puede usar el informe para ver los dispositivos que se usan en toda la organización, incluido el número de equipos que usan sus dispositivos móviles cuando está en la marcha.  

![Captura de pantalla del informe de uso de dispositivos de Teams en el centro de administración] (../media/teams-reports-device-usage.png "Captura de pantalla del informe de uso de dispositivos de Teams en el centro de administración de Microsoft Teams")

## <a name="view-the-report"></a>Ver el informe

1. Vaya al centro de administración de Microsoft Teams, en la barra de navegación izquierda, haga clic en **análisis & informes**y, a continuación, en **Informe**, seleccione **uso de dispositivos**de Teams. 
2. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**. 

## <a name="interpret-the-report"></a>Interpretar el informe

![Captura de pantalla del informe de uso de dispositivos de Teams en el centro de administración] (../media/teams-reports-device-usage-with-callouts.png "Captura de pantalla del informe de uso de dispositivos de Teams en el centro de administración de Microsoft Teams con llamadas numeradas")

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe de uso de dispositivos de Teams se puede visualizar para las tendencias de los últimos 7 días o 28 días.  |
|**2**   |Cada informe tiene una fecha en la que se generó el informe. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |<ul><li>El eje X del gráfico representa los diferentes dispositivos (**Windows**, **Mac**, **iOS**, **teléfono Android**) que se usan para conectarse a teams. </li><li>El eje Y es el número de usuarios que usan el dispositivo durante el período de tiempo seleccionado.</li> </ul>Desplace el puntero sobre la barra que representa un dispositivo para ver el número de usuarios que usan el dispositivo para conectarse a teams.|
|**4**   |La tabla ofrece un desglose del uso del dispositivo por parte del usuario. <ul><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el centro de administración de Microsoft Teams. </li><li>**Windows** se selecciona si el usuario ha estado activo en el cliente de escritorio de Teams en un equipo basado en Windows.</li><li>**Mac** está seleccionado si el usuario ha estado activo en el cliente de escritorio de Teams en un equipo Mac OS. </li> <li>**iOS** está seleccionado si el usuario ha estado activo en el cliente móvil de Teams para iOS.</li><li>**Teléfono Android** está seleccionado si el usuario ha estado activo en el cliente móvil de Teams para Android. <li>**Última actividad** es la última fecha (UTC) en la que el usuario participó en una actividad de Teams.</li> </ul> Tenga en cuenta que si ya no existe una cuenta de usuario en Azure AD, el nombre de usuario se muestra como "--" en la tabla. <br><br>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Puede exportar el informe a un archivo CSV para analizarlos sin conexión. Haga clic en **exportar a Excel**y, a continuación, en la pestaña **descargas** , haga clic en **Descargar** para descargar el informe cuando esté listo.<br>![Captura de pantalla de la pestaña descargas que muestra los informes exportados](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Temas relacionados
- [Análisis e informes de Teams](teams-reporting-reference.md)