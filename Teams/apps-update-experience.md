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
ms.openlocfilehash: 7139fb1f1788ff0e9fe093a17fbe08842f47bfd9
ms.sourcegitcommit: b8098d6ea36f10ee3a630a230ebd84bc2d96e37a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2022
ms.locfileid: "65780616"
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
