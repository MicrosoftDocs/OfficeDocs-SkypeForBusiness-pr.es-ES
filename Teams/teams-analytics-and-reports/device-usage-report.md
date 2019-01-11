---
title: Informe de uso de dispositivos de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 01/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
description: Obtenga información sobre cómo usar el informe de uso de dispositivos de los equipos en el Microsoft Teams & Skype para el centro de administración de negocio para ver el modo en que los usuarios de su organización se conectan a los equipos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d8c6153970d5b8be9fd10336d0388f6e7a92ca0c
ms.sourcegitcommit: 768c7b5f0aaa4b38a0b98c7c9ff904ffedd2e9b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2019
ms.locfileid: "27893296"
---
# <a name="microsoft-teams-device-usage-report"></a>Informe de uso de dispositivos de Microsoft Teams

El informe de uso de dispositivos de los equipos en el Microsoft Teams & Skype para el centro de administración de negocio proporciona información acerca de cómo los usuarios se conectan a los equipos. Puede usar el informe para ver los dispositivos que se usan en toda la organización, incluida la utilizan cuántos equipos desde sus dispositivos móviles cuando en Ir.  

![Captura de pantalla del informe de uso de dispositivos de los equipos en los equipos de Microsoft & Skype para el centro de administración de negocio] (../media/teams-reports-device-usage.png "Captura de pantalla del informe de uso de dispositivos de los equipos en los equipos de Microsoft & Skype para el centro de administración de negocio")

## <a name="view-the-report"></a>Ver el informe

1. Vaya a la Teams Microsoft & Skype para el centro de administración de negocio, en el panel de navegación izquierdo, haga clic en **análisis e informes**y, a continuación, en el **informe**, seleccione **uso de dispositivos de los equipos**. 
2. En **intervalo de fechas**, seleccione un intervalo y, a continuación, haga clic en **Ejecutar informe**. 

## <a name="interpret-the-report"></a>Interpretación del informe

![Captura de pantalla del informe de uso de dispositivos de los equipos en los equipos de Microsoft & Skype para el centro de administración de negocio] (../media/teams-reports-device-usage-with-callouts.png "Captura de pantalla del informe de uso de dispositivos de los equipos en los equipos de Microsoft & Skype para el centro de administración de negocio con llamadas numerada")

|Llamada |Descripción  |
|--------|-------------|
|**1**   |Puede verse el informe de uso de dispositivos de los equipos de tendencias a través de últimos 7 días o 28 días.  |
|**2**   |Cada informe tiene una fecha para cuando se generó el informe. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |<ul><li>El eje X del gráfico representa los distintos dispositivos (**Windows**, **Mac**, **iOS**, **Teléfono Android**) que usa para conectarse a los equipos. </li><li>El eje Y es el número de usuarios con el dispositivo durante el período de tiempo seleccionado.</li> </ul>Mantenga el mouse sobre la barra que representa un dispositivo para ver el número de usuarios con el dispositivo para conectarse a los equipos.|
|**4**   |La tabla proporciona un desglose de uso de dispositivos por usuario. <ul><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Microsoft Teams & Skype para el centro de administración de negocio. </li><li>**Windows** está seleccionada si el usuario estaba activo en el cliente de escritorio de los equipos en un equipo basado en Windows.</li><li>**Mac** se selecciona si el usuario estaba activo en el cliente de escritorio de los equipos en un equipo Mac OS. </li> <li>**iOS** se selecciona si el usuario estaba activo en el cliente móvil de los equipos para iOS.</li><li>**Teléfono Android** se selecciona si el usuario estaba activo en el cliente móvil de los equipos para Android. <li>**Última actividad** es la última fecha (UTC) que el usuario participó en una actividad de los equipos.</li> </ul> Para ver la información que desee incluir en la tabla, asegúrese de agregar las columnas a la tabla. |
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas de la tabla. |
|**6**   |Seleccione **˙˙˙**y, a continuación, el **gráfico de impresión** para imprimir el gráfico. |

## <a name="related-topics"></a>Temas relacionados
- [Informes y análisis de los equipos](teams-reporting-reference.md)
- [Informe de uso de los equipos](teams-usage-report.md)
- [Informe de actividad de usuario de los equipos](user-activity-report.md)