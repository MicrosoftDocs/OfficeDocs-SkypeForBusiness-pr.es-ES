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
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo actualizar aplicaciones en Microsoft Teams.
ms.openlocfilehash: e271af73800e87ddf5c0f83009fbd85002fc059e8da3f2479198de9ae64ea698
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288408"
---
# <a name="update-apps-in-microsoft-teams"></a>Actualizar aplicaciones en Microsoft Teams

En la mayoría de los casos, después de que los desarrolladores de aplicaciones publiquen una actualización de la aplicación, la nueva versión aparecerá automáticamente para los usuarios. Sin embargo, hay algunas actualizaciones del manifiesto <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams que</a> requieren la aceptación del usuario para completar:

* Se ha agregado o quitado un bot
* Se ha cambiado la propiedad "botId" de un bot existente
* Se ha cambiado la propiedad "isNotificationOnly" de un bot existente
* La propiedad "supportsFiles" del bot ha cambiado
* Se ha agregado o quitado una extensión de mensajería
* Se ha agregado un nuevo conector
* Se ha agregado una nueva pestaña estática
* Se ha agregado una nueva pestaña configurable
* Se han cambiado las propiedades dentro de "webApplicationInfo"

![nueva versión disponible](media/manage-your-custom-apps-update1.png)

![opción de actualización para una aplicación](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> El proceso de actualización se aplica a todas las actualizaciones de aplicaciones de Microsoft, aplicaciones personalizadas y aplicaciones de terceros. 

## <a name="related-topics"></a>Temas relacionados

[Administrar aplicaciones](manage-apps.md)