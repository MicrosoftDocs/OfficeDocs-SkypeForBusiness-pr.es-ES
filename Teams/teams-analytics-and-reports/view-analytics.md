---
title: Ver análisis en Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: rahulmi
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga más información sobre análisis entre equipos, análisis por equipo y análisis por canal en Teams, que permiten a los usuarios ver los datos de uso de equipos o canales de los que forman parte.
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 9755eca1c6f6f1afb57b615dfa7e96fd0cbefe64
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267395"
---
# <a name="view-analytics-in-teams"></a>Ver análisis en Teams

En Microsoft Teams, los usuarios pueden ver análisis de equipos y canales de los que forman parte. Esta información proporciona a los usuarios información sobre los patrones de uso y la actividad en sus equipos. Los usuarios pueden ver datos como el número de usuarios activos, publicaciones, respuestas y mucho más a tres niveles.

- **El análisis entre** equipos ofrece a los usuarios una visión general de los datos de uso de todos los equipos de los que son miembros o propietarios en una sola vista de lista.
- **El análisis por equipo** ofrece a los usuarios una vista más pormenorizada que muestra los datos de uso de un equipo específico.
- **El análisis por canal** ofrece a los usuarios una vista aún más granular, que muestra los datos de uso de un canal específico.

Los usuarios pueden filtrar cualquiera de estas vistas para ver los datos de un período de tiempo especificado.

## <a name="view-cross-team-analytics"></a>Ver análisis entre equipos

1. En Teams, en la parte inferior de la lista de equipos, junto a **Unirse a un equipo o crear uno**, haga clic en **Administrar equipos**.
2. Haga clic en la pestaña **Análisis** .
3. Seleccione un intervalo de fechas para mostrar los datos de uso de todos los equipos de los que es miembro o propietario.

    ![Captura de pantalla de la vista de análisis entre equipos.](../media/view-analytics-cross-team.png)

    |Elemento |Descripción  |
    |--------|-------------|
    |**Nombre.**   |Nombre del equipo. |
    |**Usuarios activos**   |Número de usuarios activos en el equipo y línea de tendencia de la actividad del equipo durante el período de tiempo especificado.
    |**Personas**   |Número total de personas del equipo en el período de tiempo especificado. Esto incluye los propietarios del equipo, los miembros del equipo y los invitados.|
    |**Invitados**   |Número de invitados en el equipo durante el período de tiempo especificado. |
    |**Mensajes**   |Número de mensajes nuevos publicados en el chat de equipo durante el período de tiempo especificado. |
    |**Respuestas**   |Número de respuestas en el chat de equipo durante el período de tiempo especificado. |
    |**Tipo**   |Si el equipo es un equipo privado o público.|

## <a name="view-per-team-analytics"></a>Ver análisis por equipo

1. En Teams, vaya al equipo que desee, haga clic en **Más opciones (...)** y, a continuación, haga clic en **Administrar equipo**.
2. Haga clic en la pestaña **Análisis** .
4. Seleccione un intervalo de fechas para mostrar los datos de uso del equipo.  

    ![Captura de pantalla de la vista de análisis por equipo.](../media/view-analytics-per-team.png)

    |Elemento |Descripción  |
    |--------|-------------|
    |**Resumen**   |Resumen de la actividad del equipo, incluidas las siguientes:<ul><li>**Usuarios**: número total de usuarios en el período de tiempo especificado. Esto incluye los propietarios del equipo, los miembros del equipo y los invitados.</li> <li>**Publicaciones**: Número de mensajes nuevos publicados en el chat de equipo durante el período de tiempo especificado.</li><li>**Respuestas**: Número de respuestas en el chat de equipo durante el período de tiempo especificado.</li> <li>**Aplicaciones**: número de aplicaciones agregadas al equipo.</li><li>**Reuniones**: Número de reuniones de Teams organizadas a nivel de equipo.</li> </ul> |
    |**Usuarios activos**   |Número de usuarios activos e inactivos.|
    |**Rol**   |Número de usuarios por rol, incluidos los propietarios del equipo, los miembros del equipo y los invitados.|
    |**Gráfico de usuarios activos**  |Número de activos diarios. Desplace el puntero sobre el punto de una fecha determinada para ver el número de usuarios activos en esa fecha.|
    |**Gráfico de mensajes**  |Número total de mensajes publicados en el chat del equipo por fecha. Desplace el puntero sobre el punto de una fecha determinada para ver el número de nuevas publicaciones y respuestas publicadas en esa fecha.|

> [!TIP]
> También puede ver el análisis por equipo haciendo clic en un equipo en la lista en la [vista de análisis entre equipos](#view-cross-team-analytics).

## <a name="view-per-channel-analytics"></a>Ver análisis por canal

1. En Teams, vaya al canal que desee, haga clic en **Más opciones (...)** y, a continuación, haga clic en **Administrar canal**.
2. Haga clic en la pestaña **Análisis** .
3. Seleccione un intervalo de fechas para mostrar los datos de uso del canal.  

    ![Captura de pantalla de la vista de análisis por canal.](../media/view-analytics-per-channel.png)

    |Elemento |Descripción  |
    |--------|-------------|
    |**Resumen**   |Resumen de la actividad de canal, incluidas las siguientes:<ul><li>**Usuarios**: número total de usuarios en el período de tiempo especificado. Esto incluye los propietarios del equipo, los miembros del equipo y los invitados.</li> <li>**Publicaciones**: número de mensajes nuevos publicados en el canal durante el período de tiempo especificado.</li><li>**Respuestas**: número de respuestas en el canal durante el período de tiempo especificado.</li> <li>**Aplicaciones**: número de aplicaciones agregadas al canal.</li> </ul> |
    |**Gráfico de mensajes**  |Número total de mensajes publicados en el chat del canal por fecha. Desplace el puntero sobre el punto de una fecha determinada para ver el número de nuevas publicaciones y respuestas publicadas en esa fecha.|

> [!TIP]
> También puede ver análisis por canal seleccionando un canal en el cuadro de lista desplegable de la [vista de análisis por equipo](#view-per-team-analytics).
    
> [!NOTE]
> Definimos usuarios activos como usuarios que realizan una acción intencionada en el cliente de escritorio, el cliente móvil y el cliente web. Como ejemplos de una acción intencionada se incluyen iniciar un chat, realizar una llamada, compartir un archivo, editar un documento dentro de los equipos, participar en una reunión, etc. Eliminamos las acciones pasivas, como el arranque automático, minimizando una pantalla o cerrando la aplicación. También anulamos todas las acciones en un único id. de usuario.

## <a name="related-topics"></a>Temas relacionados

- [Ver análisis para sus equipos](https://support.office.com/article/view-analytics-for-your-teams-5b8ad4b1-af34-4217-aff4-cd11a820b56b)
- [Análisis e informes de Teams](teams-reporting-reference.md)