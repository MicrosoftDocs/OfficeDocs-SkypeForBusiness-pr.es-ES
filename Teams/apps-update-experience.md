---
title: Experiencia de actualización de aplicaciones en Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: En este artículo, obtendrá información sobre cómo se actualizan las aplicaciones de Microsoft, las aplicaciones personalizadas y las aplicaciones de terceros en Microsoft Teams.
ms.openlocfilehash: bcd06b9814b03d917014d8136f51a280e30007d1
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272065"
---
# <a name="update-apps-in-microsoft-teams"></a>Actualizar aplicaciones en Microsoft Teams

En la mayoría de los casos, después de que los desarrolladores de aplicaciones publiquen una actualización de la aplicación, la nueva versión aparecerá automáticamente para los usuarios. Sin embargo, hay algunas actualizaciones del [manifiesto de Microsoft Teams](/microsoftteams/platform/resources/schema/manifest-schema) que requieren la aceptación del usuario para completarse:

* Se agregó o quitó un bot.
* Se cambió la propiedad "botId" de un bot existente.
* Se cambió la propiedad "isNotificationOnly" de un bot existente.
* Se agregó la funcionalidad SupportsCalling, SupportsVideo y SupportsFiles de un bot.
* Se agregó una extensión de mensajería.
* Se agregó un nuevo conector.
* S agregaron o cambiaron permisos dentro de "Authorization".

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="Nueva versión disponible." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Opción de actualización para una aplicación." lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> El proceso de actualización se aplica a todas las actualizaciones de aplicaciones de Microsoft, aplicaciones personalizadas y aplicaciones de terceros.
