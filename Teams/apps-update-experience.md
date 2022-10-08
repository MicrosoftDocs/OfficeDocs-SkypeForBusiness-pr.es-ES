---
title: Experiencia de actualización de aplicaciones en Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/04/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: En este artículo, aprenderá cómo se actualizan las aplicaciones de Microsoft, las aplicaciones personalizadas y las aplicaciones de terceros en Microsoft Teams y cómo los administradores facilitan esto.
ms.openlocfilehash: 14c327c2a24536f5441b318767e301ffe9a3196d
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68376818"
---
# <a name="teams-app-updates-and-admin-role"></a>Actualizaciones de aplicaciones de Teams y rol de administrador

Los administradores de Teams pueden ayudar a los usuarios finales a obtener la última versión de las aplicaciones. Para ello, realizan una o ambas de las siguientes tareas:

* [Actualice las aplicaciones de terceros](#updates-to-third-party-apps) que están disponibles en la tienda de Teams cuando el desarrollador o proveedor de la aplicación proporcione una nueva versión.
* [Actualiza las aplicaciones personalizadas](#updates-to-custom-apps) que solo están disponibles en tu organización cuando el desarrollador envíe una nueva versión.

## <a name="updates-to-third-party-apps"></a>Novedades a aplicaciones de terceros

Para que los usuarios instalen y usen una aplicación, deben conceder permisos a la aplicación para acceder a los servicios e información necesarios. En la mayoría de los casos, cuando una nueva versión de una aplicación instalada está disponible en la tienda de Teams, la aplicación se actualiza automáticamente para todos los usuarios. Sin embargo, algunos cambios específicos en la nueva versión de la aplicación requieren un permiso de usuario de nuevo. Esta aceptación repetida por parte del usuario garantiza el conocimiento de los cambios, como la funcionalidad o el acceso a la información personal. Los administradores de Teams pueden [proporcionar permisos a una aplicación en nombre de los usuarios](app-permissions-admin-center.md).

Si los desarrolladores de aplicaciones realizan uno o varios de los siguientes cambios en sus aplicaciones, los usuarios finales deben aprobar la actualización de la aplicación.

* Agregar o quitar un bot. Cambie el id. del bot con la `botId` propiedad.
* Cambie la `isNotificationOnly` propiedad de un bot existente que pueda cambiar las notificaciones del bot.
* Cambie `SupportsCalling`, `SupportsVideo`y las `SupportsFiles` propiedades de un bot existente para agregar la capacidad de llamar, reproducir vídeo y cargar o descargar archivos.
* Agregar o quitar permisos en autorización.
* Agregue o quite una extensión de mensajería, agregue una pestaña de grupo, agregue un conector o un canal.
* Cambie los parámetros en el [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) archivo de manifiesto.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>Novedades a aplicaciones personalizadas

Las aplicaciones personalizadas que se crean e implementan en la organización están disponibles para los usuarios de su inquilino u organización. Los administradores de Teams actualizan las aplicaciones personalizadas a las nuevas versiones proporcionadas por los desarrolladores de la organización. Para obtener más información, vea [cómo administran los administradores las aplicaciones personalizadas](custom-app-overview.md).

## <a name="related-article"></a>Artículo relacionado

* [Comprender el esquema del manifiesto para las actualizaciones realizadas en las aplicaciones](/microsoftteams/platform/resources/schema/manifest-schema).
* [Información sobre la administración de aplicaciones personalizadas](custom-app-overview.md).
