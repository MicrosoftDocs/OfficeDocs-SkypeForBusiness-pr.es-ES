---
title: Salas de Microsoft Teams información general sobre licencias en el Centro de administración de Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Obtenga información y compare Salas de Teams la disponibilidad de licencias y características en el Centro de administración de Teams.
ms.openlocfilehash: 0e4a3d4fc15f5e978731254e3344ee6e413ff682
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999635"
---
# <a name="microsoft-teams-rooms-license-overview-in-teams-admin-center"></a>Salas de Microsoft Teams información general sobre licencias en el Centro de administración de Teams

El Centro de administración de Teams le permite ver y administrar Salas de Teams dispositivos y sus periféricos desde una ubicación central. Este artículo muestra [qué capacidades de administración](#comparison-of-teams-rooms-feature-availability-by-license) tienes, en función de si a un dispositivo Salas de Teams se le asigna una licencia de Salas de Microsoft Teams Basic o Salas de Microsoft Teams Pro.

Para obtener más información sobre las licencias de Salas de Microsoft Teams, consulte [licencias de Salas de Microsoft Teams](rooms-licensing.md).

> [!NOTE]
> Si tienes licencias heredadas de Salas de Teams Standard o Salas de Teams Premium, tendrás que cambiar a Salas de Teams Pro cuando expiren las licencias heredadas. Si tienes una Enterprise Agreement, tendrás que cambiar a las licencias de Salas de Teams Pro en el siguiente período de renovación. Para obtener más información, vea [Cambiar de Salas de Teams Estándar y Salas de Teams Premium](rooms-licensing.md#switching-from-teams-rooms-standard-and-teams-rooms-premium).

## <a name="see-which-licenses-are-assigned-to-teams-rooms-devices"></a>Ver qué licencias están asignadas a Salas de Teams dispositivos

Para ver qué licencias tienen los dispositivos, vaya a Dispositivos de Teams en el Centro de administración de Teams y, a continuación, seleccione la categoría de dispositivo (Salas de Teams en Windows, Salas de Teams en Android y Surface Hub) que desee ver. Por ejemplo, si selecciona **dispositivos** >  Teams **Salas de Teams en Windows**, verá algo similar a la imagen siguiente. La columna **Licencia** muestra la licencia de Salas de Teams asignada a cada dispositivo.

:::image type="content" source="../media/mtr-device-inventory-license-focus.png" alt-text="Salas de Teams lista de inventario con el foco en las licencias Standard, Pro y Pro (de prueba).":::

Los dispositivos que tienen la licencia **Pro** pueden acceder a todas las características del Centro de administración de Teams. Los dispositivos con otras licencias pueden acceder a un subconjunto de esas características. Puede ver qué características están disponibles para cada licencia en [Comparación de Salas de Teams disponibilidad de características por licencia](#comparison-of-teams-rooms-feature-availability-by-license).

> [!IMPORTANT]
> Si seleccionas varios dispositivos que incluyen licencias de Salas de Microsoft Teams Basic y Salas de Microsoft Teams Pro, las acciones que requieran una licencia de Salas de Microsoft Teams Pro solo se realizarán en dispositivos que tengan asignada esa licencia. La acción no se realizará en dispositivos asignados a la licencia Salas de Microsoft Teams Basic.

## <a name="see-which-features-require-a-microsoft-teams-rooms-pro-license"></a>Ver qué características requieren una licencia de Salas de Microsoft Teams Pro

Las funciones que requieren una licencia de Salas de Microsoft Teams Pro se pueden identificar buscando el icono en la :::image type="icon" source="../media/mtr-pro-icon.png" border="false"::: página de detalles de un dispositivo. Si el dispositivo seleccionado actualmente no tiene asignada una licencia de Salas de Microsoft Teams Pro, no podrás realizar la acción y verás un aviso para actualizar.

:::image type="content" source="../media/mtr-restart-device-dialog.png" alt-text="Salas de Teams cuadro de diálogo de reinicio del dispositivo que muestra el icono Pro.":::

## <a name="comparison-of-teams-rooms-feature-availability-by-license"></a>Comparación de Salas de Teams disponibilidad de características por licencia

En la tabla siguiente se muestran las capacidades de administración disponibles en el Centro de administración de Teams para cada licencia de Salas de Microsoft Teams.

|                                               | Salas de Microsoft Teams Básicos | Salas de Microsoft Teams Pro |
|:----------------------------------------------|:---------------------------:|:-------------------------:|
| **Actualizaciones automáticas de dispositivos**                  | &#x2714;                    | &#x2714;                  |
| **Análisis básicos de dispositivos**                    | &#x2714;                    | &#x2714;                  |
| **Estado básico del dispositivo**                       | &#x2714;                    | &#x2714;                  |
| **Panel de calidad de llamadas**                    | &#x2714;                    | &#x2714;                  |
| **Crear y ver áreas de trabajo**                | &#x2714;                    | &#x2714;                  |
| **Telemetría en tiempo real**                       | &#x2714;                    | &#x2714;                  |
| **Actualizaciones de características periódicas**                   | &#x2714;                    | &#x2714;                  |
| **Inicio y cierre de sesión remotos**               | &#x2714;                    | &#x2714;                  |
| **Configuraciones de dispositivos Android**             |                             | &#x2714;                  |
| **Alertas de dispositivo**                             |                             | &#x2714;                  |
| **Análisis de dispositivos: estado y uso** |                             | &#x2714;                  |
| **Vista de detalles del dispositivo**                        |                             | &#x2714;                  |
| **Detalles del estado del dispositivo**                     |                             | &#x2714;                  |
| **Etiquetas de dispositivo**                               |                             | &#x2714;                  |
| **API de Graph**                                |                             | &#x2714;                  |
| **Reinicio remoto**                            |                             | &#x2714;                  |
| **Administración de periféricos de dispositivos Windows**     |                             | &#x2714;                  |
| **Configuración del dispositivo Windows**                   |                             | &#x2714;                  |
