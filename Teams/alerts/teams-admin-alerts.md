---
title: Supervisión y alertas de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: Obtenga más información sobre las capacidades de alertas y notificaciones de Teams disponibles en el Centro de administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 452bcbebeffa3936b9d05270626e11923caf5cda
ms.sourcegitcommit: 72b6f7ab2a44dec395622bfe64119a48094960bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2022
ms.locfileid: "67283091"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a>Supervisión y alertas de Microsoft Teams

En el Centro de administración de Teams hay disponibles nuevas capacidades de supervisión y alertas para Microsoft Teams. Use diferentes conjuntos de reglas disponibles en la sección **Alertas de & de notificaciones** del Centro de administración de Teams para supervisar las capacidades de Teams y recibir alertas. Por ejemplo, puede supervisar activamente el estado de los dispositivos de Teams, como teléfonos IP, barras de colaboración y otros, si se desconectan inesperadamente.  

Su organización puede usar la supervisión y las alertas de Teams para realizar los siguientes pasos:

- Administrar automáticamente las capacidades de Teams
- Recibir alertas si muestran algo inesperado.
- Realiza acciones correctivas para que todo vuelva a estar en el buen camino.

> [!NOTE]
> La funcionalidad de alertas dentro del centro de administración de Teams no está disponible en entornos GCC/GCC-High.

## <a name="how-to-manage-monitoring-and-alerting"></a>Cómo administrar la supervisión y las alertas

 Debe ser administrador global de Microsoft 365 o administrador del servicio de Teams para configurar las reglas de alertas. Consulte [Usar roles de administrador de Teams para administrar Teams para](../using-admin-roles.md) obtener más información sobre los roles de administrador de Teams y a qué informes puede acceder cada rol de administrador.

1. Inicie la sesión en el Centro de administración de Teams
2. En el panel de navegación izquierdo, seleccione **Notificaciones & alertas**.
3. Elija la regla que desea configurar desde **Reglas**.

## <a name="teams-monitoring-rules-reference"></a>Referencia de reglas de supervisión de Teams

Seguimos agregando y mejorando la experiencia de supervisión de Teams agregando diversas funcionalidades de supervisión y funcionalidades de configuración. Aquí tiene una lista de las reglas de supervisión de Teams disponibles actualmente en el Centro de administración de Teams.


|Regla  |Capacidad de supervisión|¿Qué se supervisa? |
|---------|---------|---------|
|Envíos de aplicaciones  |Aplicaciones de Teams | Supervise activamente las aplicaciones de Teams si se envían para su aprobación.|
|[Regla de estado de dispositivo](device-health-status.md)  |Dispositivos de Teams | Supervise de forma activa los dispositivos de Teams si se desconectan.|
