---
title: Informe de actividad de usuario de Microsoft Teams
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
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de actividad de usuario de los equipos en el centro de administración de Microsoft Teams para ver cómo usa los equipos de los usuarios de su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa13ee11b9a622461e501a1b004be5ff54e8cf0b
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459967"
---
# <a name="microsoft-teams-user-activity-report"></a>Informe de actividad de usuario de Microsoft Teams

El informe de actividad de usuario de los equipos proporciona información sobre los tipos de actividades que llevar a cabo en los equipos de los usuarios de su organización. Por ejemplo, puede ver cuántos usuarios comunican a través de llamadas de 1:1, ¿cuántos usuarios comunican a través de mensajes de canal y cuántos usuarios integrarse en los mensajes de chat privado.

![Captura de pantalla del informe de actividad de usuario de los equipos en el centro de administración de equipos de Microsoft] (../media/teams-reports-user-activity.png "Captura de pantalla del informe de actividad de usuario de los equipos en el centro de administración de equipos de Microsoft")

## <a name="view-the-report"></a>Ver el informe

1. Vaya al centro de administración de Microsoft Teams, en el panel de navegación izquierdo, haga clic en **informes de análisis &** y, a continuación, en el **informe**, seleccione **actividad de usuario de los equipos**. 
2. En **intervalo de fechas**, seleccione un intervalo y, a continuación, haga clic en **Ejecutar informe**. 

## <a name="interpret-the-report"></a>Interpretación del informe

![Captura de pantalla del informe de actividad de usuario de los equipos en el centro de administración de equipos de Microsoft con llamadas numerada] (../media/teams-reports-user-activity-with-callouts.png "Captura de pantalla del informe de actividad de usuario de los equipos en el centro de administración de equipos de Microsoft con llamadas numerada")

|Llamada |Descripción  |
|--------|-------------|
|**1**   |Puede verse el informe de actividad de usuario de los equipos de tendencias a través de últimos 7 días o 28 días. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**3**   |<ul><li>El eje X en los gráficos es el intervalo de fechas seleccionado para el informe específico. </li><li>El eje Y es el número de usuarios que participan en la actividad.</li></ul>Mantenga el mouse sobre el punto que representa una actividad en una fecha determinada para ver el número de instancias de la actividad en esa fecha determinada. |
|**4**   |Puede filtrar lo que se ve en el gráfico haciendo clic en un elemento de la leyenda. Por ejemplo, haga clic en **llamadas de 1:1**, **los mensajes del canal**o **conversaciones de mensajes** para ver sólo la información relacionada con cada uno de ellos. Cambiar la selección no cambia la información de la tabla. |
|**5**   |La tabla proporciona un desglose de uso por usuario.   <ul><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el centro de administración de Microsoft Teams.</li><li>**las llamadas de 1:1** es el número de llamadas de 1:1 que el usuario participó en durante el período de tiempo especificado.</li><li>**Mensajes del canal** es el número de mensajes únicos que el usuario ha realizado en una charla de equipo durante el período de tiempo especificado.</li> <li>**Mensajes de chat** es el número de mensajes únicos que el usuario registrado en privado chat durante el período de tiempo especificado.</li>  <li>**Última actividad** es la última fecha (UTC) que el usuario participó en una actividad de los equipos.</li> </ul>Para ver la información que desee incluir en la tabla, asegúrese de agregar las columnas a la tabla.
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas de la tabla. |
|**7**   |Seleccione **˙˙˙**y, a continuación, el **gráfico de impresión** para imprimir el gráfico. |

## <a name="related-topics"></a>Temas relacionados
- [Informes y análisis de los equipos](teams-reporting-reference.md)
- [Informe de uso de los equipos](teams-usage-report.md)
- [Informe de uso de dispositivos de los equipos](device-usage-report.md)