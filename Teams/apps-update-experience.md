---
title: Experiencia de actualización de aplicaciones en Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: En este artículo, aprenderá cómo se actualizan las aplicaciones de Microsoft, las aplicaciones personalizadas y las aplicaciones de terceros en Microsoft Teams y cómo los administradores facilitan esto.
ms.openlocfilehash: ed91ad441b773833838796d9ea8c71038c842b88
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299049"
---
# <a name="update-apps-in-microsoft-teams"></a>Actualizar aplicaciones en Microsoft Teams

En la mayoría de los casos, cuando una nueva versión de una aplicación está disponible en la Tienda Teams, la aplicación se actualiza automáticamente para los usuarios. Sin embargo, algunos cambios específicos en la nueva versión de la aplicación requieren la aceptación del usuario para que la aplicación se actualice. La aceptación del usuario garantiza el conocimiento de los cambios, como la funcionalidad o el acceso. Si los desarrolladores de aplicaciones realizan los siguientes cambios específicos en las aplicaciones de Microsoft Teams, los usuarios finales deben aprobar la actualización de la aplicación:

* Se agrega un bot.
* Se cambia la propiedad `botId` o la propiedad `isNotificationOnly` de un bot existente.
* Se agrega la funcionalidad `SupportsCalling`, `SupportsVideo`y `SupportsFiles` de un bot.
* Se agregó una extensión de mensajería.
* Los permisos dentro de la autorización se agregan o cambian.
* `Id` o `ApplicationPermissionsHash` o ambos se cambian dentro de la `webApplicationInfo`.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="related-articles"></a>Artículos relacionados

* [Comprender el esquema del manifiesto para las actualizaciones realizadas en las aplicaciones](/microsoftteams/platform/resources/schema/manifest-schema).
