---
title: Experiencia de actualización de aplicaciones en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo actualizar aplicaciones en Microsoft Teams.
ms.openlocfilehash: 0755c505a25d4c858afd104331d193edd8b2b27c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726209"
---
# <a name="update-apps-in-microsoft-teams"></a>Actualizar aplicaciones en Microsoft Teams

En la mayoría de los casos, después de que los desarrolladores de aplicaciones publiquen una actualización de la aplicación, la nueva versión aparecerá automáticamente para los usuarios. Sin embargo, hay algunas actualizaciones del manifiesto <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams que</a> requieren la aceptación del usuario para completar:

* Se ha agregado o quitado un bot
* Se ha cambiado la propiedad "botId" de un bot existente
* Se ha cambiado la propiedad "isNotificationOnly" de un bot existente
* Se ha agregado la funcionalidad SupportsCalling, SupportsVideo y SupportsFiles de un bot
* Se ha agregado una extensión de mensajería
* Se ha agregado un nuevo conector
* Se han cambiado las propiedades dentro de "webApplicationInfo"

![nueva versión disponible.](media/manage-your-custom-apps-update1.png)

![opción de actualización para una aplicación.](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> El proceso de actualización se aplica a todas las actualizaciones de aplicaciones de Microsoft, aplicaciones personalizadas y aplicaciones de terceros. 

## <a name="related-topics"></a>Temas relacionados

[Administrar aplicaciones](manage-apps.md)
