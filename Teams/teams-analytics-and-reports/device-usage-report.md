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
description: Obtenga información sobre cómo usar el informe de uso de dispositivos de los equipos en el centro de administración de Microsoft Teams para ver el modo en que los usuarios de su organización se conectan a los equipos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1cd1ec97732b851246e03f6fcd56382ccdedf59
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401415"
---
# <a name="microsoft-teams-device-usage-report"></a>Informe de uso de dispositivos de Microsoft Teams

El informe de uso de dispositivos de los equipos en el centro de administración de Microsoft Teams proporciona información acerca de cómo los usuarios se conectan a los equipos. Puede usar el informe para ver los dispositivos que se usan en toda la organización, incluida la utilizan cuántos equipos desde sus dispositivos móviles cuando en Ir.  

![Captura de pantalla del informe de uso de dispositivos de los equipos en el centro de administración de equipos de Microsoft] (../media/teams-reports-device-usage.png "Captura de pantalla del informe de uso de dispositivos de los equipos en el centro de administración de equipos de Microsoft")

## <a name="view-the-report"></a>Ver el informe

1. Vaya al centro de administración de Microsoft Teams, en el panel de navegación izquierdo, haga clic en **informes de & de análisis**y, a continuación, en el **informe**, seleccione **uso de dispositivos de los equipos**. 
2. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**. 

## <a name="interpret-the-report"></a>Interpretar el informe

![Captura de pantalla del informe de uso de dispositivos de los equipos en el centro de administración de equipos de Microsoft] (../media/teams-reports-device-usage-with-callouts.png "Captura de pantalla del informe de uso de dispositivos de los equipos en el centro de administración de equipos de Microsoft con llamadas numerada")

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede verse el informe de uso de dispositivos de los equipos de tendencias a través de últimos 7 días o 28 días.  |
|**2**   |Cada informe tiene una fecha para cuando se generó el informe. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |<ul><li>El eje X del gráfico representa los distintos dispositivos (**Windows**, **Mac**, **iOS**, **Teléfono Android**) que usa para conectarse a los equipos. </li><li>El eje Y es el número de usuarios con el dispositivo durante el período de tiempo seleccionado.</li> </ul>Mantenga el mouse sobre la barra que representa un dispositivo para ver el número de usuarios con el dispositivo para conectarse a los equipos.|
|**4**   |La tabla proporciona un desglose de uso de dispositivos por usuario. <ul><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el centro de administración de Microsoft Teams. </li><li>**Windows** está seleccionada si el usuario estaba activo en el cliente de escritorio de los equipos en un equipo basado en Windows.</li><li>**Mac** se selecciona si el usuario estaba activo en el cliente de escritorio de los equipos en un equipo Mac OS. </li> <li>**iOS** se selecciona si el usuario estaba activo en el cliente móvil de los equipos para iOS.</li><li>**Teléfono Android** se selecciona si el usuario estaba activo en el cliente móvil de los equipos para Android. <li>**Última actividad** es la última fecha (UTC) que el usuario participó en una actividad de los equipos.</li> </ul> Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Seleccione **˙˙˙** y luego **Imprimir gráfico** para imprimir el gráfico. |

## <a name="related-topics"></a>Temas relacionados
- [Análisis e informes de Teams](teams-reporting-reference.md)
- [Informes de uso de Teams](teams-usage-report.md)
- [Informe de actividad de usuario de Teams](user-activity-report.md)