---
title: Ver análisis en Teams
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre análisis entre equipos, análisis por equipo y análisis por canal en Teams, que permiten a los usuarios ver los datos de uso de equipos o canales de los que forman parte.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 00ac44638a3f1b79ba98d1b2ebc6cf3645ef44bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809180"
---
# <a name="view-analytics-in-teams"></a>Ver análisis en Teams

En Microsoft Teams, los usuarios pueden ver análisis de equipos y canales de los que forman parte. Esta información proporciona a los usuarios información sobre los patrones de uso y la actividad de sus equipos. Los usuarios pueden ver datos como el número de usuarios activos, publicaciones, respuestas y mucho más en tres niveles.

- **El análisis entre** equipos ofrece a los usuarios una amplia descripción general de los datos de uso de todos los equipos de los que son miembros o propietarios en una única vista de lista.
- **El análisis por equipo ofrece** a los usuarios una vista más granular, que muestra los datos de uso de un equipo específico.
- **El análisis por canal ofrece** a los usuarios una vista aún más granular, que muestra los datos de uso de un canal específico.

Los usuarios pueden filtrar cualquiera de estas vistas para ver los datos de un período de tiempo especificado.

## <a name="view-cross-team-analytics"></a>Ver análisis entre equipos

1. En Teams, en la parte inferior de la lista de equipos, junto a Unirse **o crear un** equipo, haga clic en Administrar **equipos.**
2. Haga clic en **la pestaña Análisis.**
3. Seleccione un intervalo de fechas para mostrar los datos de uso de todos los equipos de los que es miembro o propietario.

    ![Captura de pantalla de la vista de análisis entre equipos](../media/view-analytics-cross-team.png)

    |Elemento |Descripción  |
    |--------|-------------|
    |**Nombre.**   |Nombre del equipo. |
    |**Usuarios activos**   |Número de usuarios activos en el equipo y la línea de tendencia de la actividad del equipo durante el período de tiempo especificado.
    |**Personas**   |Número total de personas del equipo en el período de tiempo especificado. Esto incluye propietarios de equipos, miembros del equipo e invitados.|
    |**Invitados**   |Número de invitados del equipo durante el período de tiempo especificado. |
    |**Publicaciones**   |Número de mensajes nuevos publicados en el chat de grupo durante el período de tiempo especificado. |
    |**Respuestas**   |Número de respuestas en el chat de grupo durante el período de tiempo especificado. |
    |**Tipo**   |Si el equipo es un equipo privado o un equipo público.|

## <a name="view-per-team-analytics"></a>Ver análisis por equipo

1. En Teams, vaya al equipo que desee, haga clic en Más opciones **(...)** y, a continuación, haga clic **en Administrar equipo.**
2. Haga clic en **la pestaña Análisis.**
4. Seleccione un intervalo de fechas para mostrar los datos de uso del equipo.  

    ![Captura de pantalla de la vista de análisis por equipo](../media/view-analytics-per-team.png)

    |Elemento |Descripción  |
    |--------|-------------|
    |**Resumen**   |Resumen de la actividad del equipo, que incluye lo siguiente:<ul><li>**Usuarios:** número total de usuarios en el período de tiempo especificado. Esto incluye propietarios de equipos, miembros del equipo e invitados.</li> <li>**Publicaciones:** Número de mensajes nuevos publicados en el chat de grupo durante el período de tiempo especificado.</li><li>**Respuestas:** Número de respuestas en el chat de grupo durante el período de tiempo especificado.</li> <li>**Aplicaciones:** Número de aplicaciones agregadas al equipo.</li><li>**Reuniones:** número de Teams reuniones organizadas en el nivel de equipo.</li> </ul> |
    |**Usuarios activos**   |Número de usuarios activos e inactivos.|
    |**Rol**   |Número de usuarios por rol, incluidos los propietarios del equipo, los miembros del equipo e invitados.|
    |**Gráfico de usuarios activos**  |Número de activos diarios. Mantenga el puntero sobre el punto en una fecha determinada para ver el número de usuarios activos en esa fecha.|
    |**Gráfico de** mensajes  |Número total de mensajes publicados en el chat de grupo por fecha. Mantenga el puntero sobre el punto en una fecha determinada para ver el número de nuevas publicaciones y respuestas publicadas en esa fecha.|

> [!TIP]
> También puede ver análisis por equipo haciendo clic en un equipo de la lista en la vista análisis [entre equipos.](#view-cross-team-analytics)

## <a name="view-per-channel-analytics"></a>Ver análisis por canal

1. En Teams, vaya al canal que desee, haga clic en Más opciones **(...)** y, a continuación, haga clic **en Administrar canal.**
2. Haga clic en **la pestaña Análisis.**
3. Seleccione un intervalo de fechas para mostrar los datos de uso del canal.  

    ![Captura de pantalla de la vista de análisis por canal](../media/view-analytics-per-channel.png)

    |Elemento |Descripción  |
    |--------|-------------|
    |**Resumen**   |Resumen de la actividad del canal, que incluye lo siguiente:<ul><li>**Usuarios:** número total de usuarios en el período de tiempo especificado. Esto incluye propietarios de equipos, miembros del equipo e invitados.</li> <li>**Publicaciones:** Número de mensajes nuevos publicados en el canal durante el período de tiempo especificado.</li><li>**Respuestas:** Número de respuestas en el canal durante el período de tiempo especificado.</li> <li>**Aplicaciones:** Número de aplicaciones agregadas al canal.</li> </ul> |
    |**Gráfico de** mensajes  |Número total de mensajes publicados en el chat del canal por fecha. Mantenga el puntero sobre el punto en una fecha determinada para ver el número de nuevas publicaciones y respuestas publicadas en esa fecha.|

> [!TIP]
> También puede ver análisis por canal seleccionando un canal en el cuadro de lista desplegable de la vista de análisis [por equipo.](#view-per-team-analytics)
    
> [!NOTE]
> Definimos usuarios activos como usuarios que realizan una acción intencionada en el cliente de escritorio, el cliente móvil y el cliente web. Ejemplos de una acción intencionada incluyen iniciar un chat, realizar una llamada, compartir un archivo, editar un documento dentro de los equipos, participar en una reunión, y así sucesivamente. Eliminamos acciones pasivas como el inicio automático, minimizar una pantalla o cerrar la aplicación. También desapetemos todas las acciones en un único id. de usuario.

## <a name="related-topics"></a>Temas relacionados

- [Ver análisis para sus equipos](https://support.office.com/article/view-analytics-for-your-teams-5b8ad4b1-af34-4217-aff4-cd11a820b56b)
- [Análisis e informes de Teams](teams-reporting-reference.md)