---
title: Informe de usuarios bloqueados de RTC de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Obtenga información sobre cómo usar el informe de usuarios bloqueados de RTC en el centro de administración de Microsoft Teams para obtener información general de los usuarios de su organización que no pueden realizar llamadas RTC.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ef4dfbab2b32b088c8e2f8b38b55c15a66eb32
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827348"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Informe de usuarios bloqueados de RTC de Microsoft Teams

El informe de usuarios bloqueados de RTC en el centro de administración de Microsoft Teams le muestra los usuarios de su organización que no pueden realizar llamadas RTC en Teams. Puede ver más información sobre los usuarios bloqueados, incluidos su número de teléfono asignado y el motivo por el que fueron bloqueados para realizar llamadas.

## <a name="view-the-report"></a>Ver el informe

En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en > **informes de uso**de **informes &**. En la pestaña **ver informes** , en **Informe**, seleccione **usuarios bloqueados con RTC**y, a continuación, haga clic en **Ejecutar Informe**.

![Captura de pantalla del informe de informe usuarios bloqueados de RTC en el centro de administración](../media/teams-reports-pstn-blocked-users-with-callouts.png "Captura de pantalla del informe de usuarios bloqueados de RTC en el centro de administración de Microsoft Teams con llamadas numeradas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha en la que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**2**   |El eje X es la fecha. El eje Y es el número de usuarios. <br>Desplace el puntero sobre el punto en una fecha determinada para ver el número de usuarios bloqueados en esa fecha. |
|**3**   |La tabla muestra un desglose de todos los usuarios que están bloqueados para realizar llamadas RTC.  Muestra todos los usuarios que tienen asignada una conferencia de audio o de sistema telefónico y le proporcionan más información acerca de cada usuario. <ul><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el centro de administración de Microsoft Teams. </li> <li>**Teléfono** es el número que está asignado al usuario.</li> <li>**Motivo de bloqueo** es el motivo por el que el usuario está bloqueado para hacer llamadas.</li><li>La **acción bloqueada** indica si el usuario está bloqueado o desbloqueado para hacer llamadas RTC en Teams.</li> <li>**Tiempo bloqueado** es la fecha y hora (UTC) en las que el usuario no pudo realizar llamadas.</li></li> </ul>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**4**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|
|**5**   |Seleccione **pantalla completa** para ver el informe en modo de pantalla completa.|

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)