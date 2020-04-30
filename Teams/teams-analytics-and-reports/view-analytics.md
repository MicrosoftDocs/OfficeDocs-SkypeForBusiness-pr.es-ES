---
title: Ver análisis en Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: rahulmi
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-collaboration
description: Obtenga más información sobre análisis entre equipos, análisis por equipo y análisis por canal en Teams, lo que permite a los usuarios ver los datos de uso de los equipos o canales de los que forman parte.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9261678848589028155d58449bf84d083ff756c2
ms.sourcegitcommit: 929c050c038a64216e38b0a67569a8f18ad4baf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43941017"
---
# <a name="view-analytics-in-teams"></a>Ver análisis en Teams

En Microsoft Teams, los usuarios pueden ver los análisis de los equipos y canales de los que forman parte. Esta información proporciona a los usuarios información sobre los patrones de uso y la actividad de sus equipos. Los usuarios pueden ver datos como, por ejemplo, el número de usuarios activos, publicaciones, respuestas y más en tres niveles.

- **Análisis entre equipos** proporciona a los usuarios una amplia visión general de los datos de uso de todos los equipos de los que son miembros o propietarios en una sola vista de lista.
- **Análisis por equipo** proporciona a los usuarios una vista más granular, que muestra los datos de uso de un equipo específico.
- El **análisis por canal** proporciona a los usuarios una vista aún más granular, que muestra los datos de uso de un canal específico.

Los usuarios pueden filtrar cualquiera de estas vistas para ver los datos durante un período de tiempo específico.

## <a name="view-cross-team-analytics"></a>Ver análisis de varios equipos

1. En Teams, en la parte inferior de la lista de equipos, junto a **unirse a un equipo o crear uno**, haga clic en **administrar equipos**.
2. Haga clic en la pestaña **Analytics** .
3. Seleccione un intervalo de fechas para mostrar los datos de uso de todos los equipos de los que es miembro o propietario.

    ![Captura de pantalla de la vista de análisis entre equipos](../media/view-analytics-cross-team.png)

    |Elemento |Descripción  |
    |--------|-------------|
    |**Nombre.**   |Nombre del equipo. |
    |**Usuarios activos**   |Número de usuarios activos en el equipo y línea de tendencia de actividad de equipo durante el período de tiempo especificado.
    |**Personas**   |Número total de personas en el equipo en el período de tiempo especificado. Esto incluye a los propietarios del equipo, los miembros del equipo y los invitados.|
    |**Guest**   |Número de invitados en el equipo durante el período de tiempo especificado. |
    |**Anuncio**   |Número de mensajes nuevos publicados en la conversación del equipo durante el período de tiempo especificado. |
    |**Las**   |Número de respuestas en la conversación del equipo durante el período de tiempo especificado. |
    |**Tipo**   |Si el equipo es un equipo privado o público.|

## <a name="view-per-team-analytics"></a>Ver análisis por equipo

1. En Teams, vaya al equipo que desee, haga clic en **más opciones (...)** y, a continuación, haga clic en **administrar equipo**.
2. Haga clic en la pestaña **Analytics** .
4. Seleccione un intervalo de fechas para mostrar los datos de uso del equipo.  

    ![Captura de pantalla de la vista de análisis por equipo](../media/view-analytics-per-team.png)

    |Elemento |Descripción  |
    |--------|-------------|
    |**Resumen**   |Resumen de actividad de equipo, incluidos los siguientes:<ul><li>**Usuarios**: número total de usuarios en el período de tiempo especificado. Esto incluye a los propietarios del equipo, los miembros del equipo y los invitados.</li> <li>**Publicaciones**: número de mensajes nuevos publicados en el chat del equipo durante el período de tiempo especificado.</li><li>**Respuestas**: número de respuestas en la conversación del equipo durante el período de tiempo especificado.</li> <li>**Aplicaciones**: número de aplicaciones agregadas al equipo.</li><li>**Reuniones**: número de reuniones de Teams organizadas en el nivel de equipo.</li> </ul> |
    |**Usuarios activos**   |Número de usuarios activos e inactivos.|
    |**Rol**   |Números de usuarios por función, incluidos los propietarios del equipo, los miembros del equipo y los invitados.|
    |Gráfico **usuarios activos**  |Número de días activos. Desplace el puntero sobre el punto en una fecha determinada para ver el número de usuarios activos en esa fecha.|
    |Gráfico de **mensajes**  |Número total de mensajes publicados en el chat del equipo por fecha. Desplace el puntero sobre el punto en una fecha determinada para ver el número de publicaciones nuevas y respuestas publicadas en esa fecha.|

> [!TIP]
> También puede ver los análisis por equipo haciendo clic en un equipo en la lista de la [vista de análisis entre equipos](#view-cross-team-analytics).

## <a name="view-per-channel-analytics"></a>Ver análisis por canal

1. En Teams, vaya al canal que desee, haga clic en **más opciones (...)** y, a continuación, haga clic en **administrar canal**.
2. Haga clic en la pestaña **Analytics** .
3. Seleccione un intervalo de fechas para mostrar los datos de uso para el canal.  

    ![Captura de pantalla de la vista analítica por canal](../media/view-analytics-per-channel.png)

    |Elemento |Descripción  |
    |--------|-------------|
    |**Resumen**   |Resumen de actividad de canal, entre los que se incluyen los siguientes:<ul><li>**Usuarios**: número total de usuarios en el período de tiempo especificado. Esto incluye a los propietarios del equipo, los miembros del equipo y los invitados.</li> <li>**Publicaciones**: número de mensajes nuevos que se han publicado en el canal durante el período de tiempo especificado.</li><li>**Respuestas**: número de respuestas del canal durante el período de tiempo especificado.</li> <li>**Aplicaciones**: número de aplicaciones agregadas al canal.</li> </ul> |
    |Gráfico de **mensajes**  |Número total de mensajes publicados en la conversación de canales por fecha. Desplace el puntero sobre el punto en una fecha determinada para ver el número de publicaciones nuevas y respuestas publicadas en esa fecha.|

> [!TIP]
> También puede ver los análisis por canal seleccionando un canal en el cuadro de lista desplegable en la vista de [análisis por equipo](#view-per-team-analytics).
    
> [!NOTE]
> Definimos usuarios activos como usuarios que realizan una acción intencional en el cliente de escritorio, el cliente móvil y el cliente web. Entre los ejemplos de una acción intencional se incluyen iniciar un chat, realizar una llamada, compartir un archivo, editar un documento de Teams, participar en una reunión, etc. Eliminamos las acciones pasivas, como el inicio automático, la minimización de una pantalla o la finalización de la aplicación. También desduplicamos todas las acciones en un único ID de usuario.

## <a name="related-topics"></a>Temas relacionados

- [Ver análisis de los equipos](https://support.office.com/article/view-analytics-for-your-teams-5b8ad4b1-af34-4217-aff4-cd11a820b56b)
- [Análisis e informes de Teams](teams-reporting-reference.md)