---
title: Información general sobre las directivas de aplicación para administrar aplicaciones en Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
search.appverid: ''
description: Obtenga información sobre las directivas de permisos de aplicación, las directivas de configuración de aplicaciones y las directivas de aplicación personalizadas usadas para administrar aplicaciones en Microsoft Teams.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 5a377923412ad1835e4a0a3c099d31adf283267b
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299039"
---
# <a name="overview-of-app-policies-used-to-manage-access-to-apps"></a>Información general sobre las directivas de aplicación usadas para administrar aplicaciones

Microsoft Teams usa directivas para controlar el comportamiento de acceso e instalación. Las directivas ayudan a los administradores de Teams a controlar el siguiente comportamiento de la aplicación:

* Configurar el acceso de las aplicaciones para los usuarios al detalle. Ayuda a cada usuario final a usar solo las aplicaciones que un administrador les ha permitido.

* Anclar las aplicaciones pertinentes para un usuario específico. Ayuda a los usuarios finales a empezar a trabajar fácilmente y acceder rápidamente a las aplicaciones pertinentes, ya que las aplicaciones ancladas se instalan automáticamente sin intervención.

## <a name="app-permission-policies"></a>Directivas de permisos de aplicación

Con las directivas de permisos de aplicación, el administrador de Teams puede controlar qué aplicaciones están disponibles para cada usuario específico de su organización. Puede definir una asignación de acceso exacta entre la aplicación y el usuario, o cualquier combinación de los dos. Por ejemplo, puede permitir el acceso a algunas aplicaciones para todos los usuarios, algunas aplicaciones para un grupo específico de usuarios o una aplicación específica para un usuario específico.

Las directivas de permisos de aplicación se aplican a todos los tipos de aplicaciones disponibles en Teams. Por ejemplo, puede usar directivas de permisos de aplicación para implementar gradualmente una aplicación de terceros o una aplicación personalizada al permitir el acceso a usuarios específicos.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Captura de pantalla de la directiva de protección de aplicaciones." lightbox="media/app-permission-policy.png":::

Para obtener más información, consulte [Cómo administrar la configuración y las directivas de aplicación personalizadas](teams-app-permission-policies.md).

## <a name="app-setup-policies"></a>Directivas de configuración de la aplicación

Las directivas de configuración de aplicaciones permiten personalizar la experiencia de la aplicación para los usuarios. Usted elige las aplicaciones que quiere anclar a la barra de aplicaciones en los clientes de Teams y el orden en el que aparecen en los clientes web, de escritorio y móviles.

Estos son algunos ejemplos de cómo puede usar las directivas de configuración de aplicaciones:

* Instalar aplicaciones para los usuarios finales en su entorno personal de Teams. Ayuda a incrementar el reconocimiento y la adopción de las aplicaciones deseadas. Por ejemplo, ancle una aplicación personalizada de reclutamiento y administración de talento para los usuarios de su equipo de RR. HH.
* Ancle de forma selectiva las aplicaciones principales, como Chat, Teams y Llamadas.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Captura de pantalla de la directiva de configuración de la aplicación en el Centro de administración de Teams." lightbox="media/app-setup-policy.png":::

Para obtener más información, consulte [Cómo administrar las directivas de configuración de aplicaciones](teams-app-setup-policies.md).

## <a name="custom-app-policies"></a>Directivas de aplicación personalizadas

Teams permite a los desarrolladores de su organización compilar, probar e implementar aplicaciones personalizadas para los usuarios internos de la organización. Los desarrolladores pueden enviar sus aplicaciones personalizadas a través de Teams para su aprobación por parte de los administradores de Teams. Puede usar directivas de configuración de aplicaciones para controlar qué usuarios de la organización pueden cargar aplicaciones personalizadas. Los administradores pueden permitir que los usuarios finales de su organización usen aplicaciones personalizadas y que los desarrolladores carguen aplicaciones personalizadas mediante la configuración de aplicaciones de toda la organización.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Recorte de pantalla que muestra cómo permitir aplicaciones personalizadas en la organización en el panel de configuración de toda la organización." lightbox="media/custom-app-policy.png":::

Para obtener más información, consulte [Cómo administrar la configuración y las directivas de aplicaciones personalizadas](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>Artículos relacionados

* [Administrar Teams con directivas](manage-teams-with-policies.md)
