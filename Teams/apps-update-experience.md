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
description: En este artículo, obtendrá información sobre cómo se actualizan las aplicaciones de Microsoft, las aplicaciones personalizadas y las aplicaciones de terceros en Microsoft Teams.
ms.openlocfilehash: 27d51a487af918e6fcee2b7806c81d31506bd1af
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958045"
---
# <a name="update-apps-in-microsoft-teams"></a>Actualizar aplicaciones en Microsoft Teams

En la mayoría de los casos, después de que los desarrolladores de aplicaciones publiquen una actualización de la aplicación, la nueva versión aparece automáticamente para los usuarios. Sin embargo, hay algunas actualizaciones en el [manifiesto de Microsoft Teams](/microsoftteams/platform/resources/schema/manifest-schema) que requieren la aceptación del usuario para completar:

* Se ha agregado o quitado un bot.
* Se cambió la propiedad "botId" de un bot existente.
* Se cambió la propiedad "isNotificationOnly" de un bot existente.
* Se ha agregado la funcionalidad SupportsCalling, SupportsVideo y SupportsFiles de un bot.
* Se ha agregado una extensión de mensajería.
* Se ha agregado un conector nuevo.
* Se agregaron o cambiaron los permisos dentro de "Autorización".

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="Nueva versión disponible." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Opción de actualización para una aplicación." lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> El proceso de actualización se aplica a todas las actualizaciones de aplicaciones de Microsoft, aplicaciones personalizadas y aplicaciones de terceros.
