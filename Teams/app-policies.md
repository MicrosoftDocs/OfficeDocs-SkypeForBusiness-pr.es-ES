---
title: Información general sobre las directivas de aplicación para administrar aplicaciones en Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/25/2022
search.appverid: ''
description: Obtenga más información sobre las directivas de permisos de las aplicaciones y las directivas de configuración que se usan para administrar aplicaciones en Microsoft Teams.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 8e059199d4963004e287b456c98bb80717f849b3
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912439"
---
# <a name="know-about-policies-to-manage-access-and-installation-of-teams-apps"></a>Información sobre directivas para administrar el acceso y la instalación de aplicaciones de Teams

Microsoft Teams usa directivas de aplicaciones para controlar el comportamiento de acceso e instalación de las aplicaciones. Las directivas de aplicación ayudan a los administradores de Teams a controlar el comportamiento de la aplicación siguiente:

* Configurar el acceso de aplicaciones para cada usuario individual o para un grupo de usuarios. Ayuda a los administradores a controlar las aplicaciones que se permiten para cada usuario final.

* Ancle esas aplicaciones para los usuarios finales que sean relevantes para las necesidades de su organización. Además, los administradores pueden instalar aplicaciones para los usuarios finales sin la intervención del usuario. Ayuda a los usuarios finales a empezar fácilmente con las aplicaciones relevantes.

* Controlar qué desarrolladores de la organización pueden enviar aplicaciones personalizadas para la aprobación del administrador. Le ayuda a controlar el acceso a la funcionalidad de carga de aplicaciones personalizadas.

## <a name="app-permission-policies"></a>Directivas de permisos de aplicación

Con las directivas de permisos de aplicaciones, los administradores de Teams controlan qué aplicaciones están disponibles para cada usuario de su organización. Puedes permitir algunas aplicaciones para todos los usuarios, puedes permitir algunas aplicaciones para un grupo específico de usuarios o puedes permitir aplicaciones específicas para usuarios específicos. Las directivas de permisos de aplicaciones funcionan en conjunto con la configuración de toda la organización y permiten o bloquean el estado de cada aplicación individual.

Las directivas de permisos de aplicaciones se aplican a todos los [tipos de aplicaciones disponibles en Teams](deploy-apps-microsoft-teams-landing-page.md). Algunos escenarios de ejemplo en los que se usan directivas de permisos de aplicaciones son:

* Implemente gradualmente una aplicación para algunos usuarios inicialmente y para todos los usuarios finalmente.
* Permita una aplicación personalizada para la contratación y la gestión de talentos solo para los miembros de su departamento de RRHH y bloquee para el resto de usuarios de la organización.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Captura de pantalla de la directiva de protección de aplicaciones." lightbox="media/app-permission-policy.png":::

Para obtener más información, consulte [cómo administrar directivas de permisos de aplicaciones](teams-app-permission-policies.md).

## <a name="app-setup-policies"></a>Directivas de configuración de la aplicación

Las directivas de configuración de aplicaciones le permiten configurar cómo y dónde están disponibles las aplicaciones para los usuarios de su cliente de Teams. Elija las aplicaciones que desea anclar a la barra de aplicaciones en los clientes de Teams y defina el orden en que se muestran las aplicaciones.

Anclar o instalar aplicaciones ayuda a concienciar y adoptar las aplicaciones deseadas en tu organización. Los cambios se aplican a los clientes de Teams web, de escritorio y móviles.

Algunos escenarios de ejemplo en los que usa directivas de configuración de aplicaciones son:

* Ancle una aplicación personalizada de contratación y gestión de talentos para los miembros de su equipo de RRHH.
* Cambiar el orden de las [aplicaciones principales](deploy-apps-microsoft-teams-landing-page.md#core-apps) mediante el anclaje de los usuarios de la organización.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Captura de pantalla de la directiva de configuración de la aplicación en el Centro de administración de Teams." lightbox="media/app-setup-policy.png":::

Para obtener más información, consulte [Cómo administrar las directivas de configuración de aplicaciones](teams-app-setup-policies.md).

### <a name="option-to-upload-custom-apps"></a>Opción para cargar aplicaciones personalizadas

Su organización puede encargar la creación de aplicaciones personalizadas para los requisitos específicos de la organización. Los desarrolladores de su organización pueden crear, probar e implementar aplicaciones personalizadas para los usuarios internos de Teams de la organización. Puede usar la directiva de configuración de aplicaciones para controlar quién en su organización puede cargar aplicaciones personalizadas. Puede usar la configuración de toda la organización para permitir que los usuarios finales usen aplicaciones personalizadas. Las directivas de permisos se usan para permitir que solo usuarios finales específicos usen una aplicación personalizada.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Recorte de pantalla que muestra cómo permitir aplicaciones personalizadas en la organización en el panel de configuración de toda la organización." lightbox="media/custom-app-policy.png":::

Para obtener más información, consulta [cómo administrar las directivas y la configuración de las aplicaciones personalizadas](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>Artículos relacionados

* [Administrar Teams con directivas](manage-teams-with-policies.md)
* [Administrar directivas de permisos de aplicación](teams-app-permission-policies.md)
* [Administrar directivas de configuración de aplicaciones](teams-app-setup-policies.md)
* [Administrar directivas y configuraciones de aplicaciones personalizadas](teams-custom-app-policies-and-settings.md)
