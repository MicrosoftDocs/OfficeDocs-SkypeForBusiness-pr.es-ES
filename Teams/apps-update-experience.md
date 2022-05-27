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
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtén información sobre cómo actualizar aplicaciones en Microsoft Teams.
ms.openlocfilehash: ed9a1de2e182088a20721758c63f8b6d83cc36df
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675002"
---
# <a name="update-apps-in-microsoft-teams"></a>Actualizar aplicaciones en Microsoft Teams

En la mayoría de los casos, después de que los desarrolladores de aplicaciones publiquen una actualización de la aplicación, la nueva versión aparece automáticamente para los usuarios. Sin embargo, hay algunas actualizaciones en el [manifiesto de Microsoft Teams](/microsoftteams/platform/resources/schema/manifest-schema) que requieren la aceptación del usuario para completar:

* Se ha agregado o quitado un bot
* Propiedad "botId" de un bot existente cambiada
* Propiedad "isNotificationOnly" de un bot existente cambiada
* Se ha agregado la funcionalidad SupportsCalling, SupportsVideo y SupportsFiles de un bot
* Se ha agregado una extensión de mensajería
* Se ha agregado un conector nuevo
* Se agregaron o cambiaron los permisos dentro de "Autorización"

![nueva versión disponible.](media/manage-your-custom-apps-update1.png)

![opción de actualización para una aplicación.](media/manage-your-custom-apps-update2.png)

> [!NOTE]
> El proceso de actualización se aplica a todas las actualizaciones de aplicaciones de Microsoft, aplicaciones personalizadas y aplicaciones de terceros.

## <a name="related-topics"></a>Temas relacionados

[Administrar aplicaciones](manage-apps.md)
