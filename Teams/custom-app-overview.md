---
title: Administrar aplicaciones personalizadas y de instalación de prueba
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Comprenda qué son las aplicaciones personalizadas y las aplicaciones de instalación de prueba en Microsoft Teams y administre las aplicaciones para gobernar su comportamiento, implementación y permisos.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 4ba559d605f1465fda7caf9b253c18864c8b4c20
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837380"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>Comprender y administrar aplicaciones personalizadas y de instalación de prueba

Microsoft Teams permite a los desarrolladores de su organización crear, probar e implementar aplicaciones personalizadas para los usuarios internos de la organización. Estas aplicaciones se denominan aplicaciones personalizadas o aplicaciones de Línea de negocio. Su organización puede encargar la creación de aplicaciones personalizadas para los requisitos específicos de la organización.

Usted como administrador tiene el control para permitir o bloquear dichas aplicaciones para toda la organización o para usuarios específicos. Los desarrolladores de su organización pueden crear rápidamente soluciones personalizadas de bajo código mediante la integración de Teams con [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Los desarrolladores pueden enviar sus aplicaciones personalizadas a través de Teams para su aprobación por parte del administrador. Puede usar las directivas de configuración de aplicaciones para controlar la implementación, la distribución y los permisos de las aplicaciones personalizadas.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Recorte de pantalla que muestra cómo permitir aplicaciones personalizadas en la organización en el panel de configuración de toda la organización." lightbox="media/custom-app-policy.png":::

Después de permitir el uso de una aplicación personalizada, los usuarios finales pueden encontrarla seleccionando **Creado para su organización** en el panel de navegación izquierdo de la tienda de Teams.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Captura de pantalla de aplicaciones personalizadas en la tienda de Teams en la aplicación de escritorio de Teams." lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>Descripción de la instalación de prueba de aplicaciones personalizadas

Al desarrollar aplicaciones personalizadas y antes de distribuirlas a los usuarios finales, los desarrolladores prueban las aplicaciones agregándolas a la Tienda Teams para probarlas. Los desarrolladores pueden realizar pruebas por su cuenta o con un grupo específico de usuarios, pero la aplicación no está disponible para otros usuarios finales de la organización a través de store. Este método se denomina instalación de prueba de aplicaciones y solo se aplica a aplicaciones personalizadas.

Los desarrolladores pueden transferir localmente una aplicación para que esté disponible para los miembros de un equipo específico, normalmente cuando se prueba una aplicación en desarrollo. Cuando se usa una aplicación de esta forma, se limita el uso a los desarrolladores de aplicaciones y no se requiere la aprobación de un administrador, siempre y cuando el administrador permita la instalación de prueba en Teams.

Los desarrolladores pueden compartir una aplicación con instalación de prueba con un equipo específico sin enviarla al catálogo de aplicaciones de Teams. Hace que la aplicación personalizada de instalación de prueba esté disponible para un grupo limitado de usuarios finales, pero no está disponible en la tienda de aplicaciones de su organización para todos los usuarios finales.

Como administrador, se puede denegar la instalación de prueba de aplicaciones para todos los desarrolladores. Si no se permite la instalación de prueba, los desarrolladores podrán probar sus aplicaciones al [crear un inquilino de prueba independiente](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Una vez completado el desarrollo de aplicaciones personalizadas, los desarrolladores solicitan a los administradores que distribuyan su aplicación personalizada a los usuarios finales. Para obtener más información, consulte [cómo publicar una aplicación personalizada](/microsoftteams/upload-custom-apps). Como administrador, puede permitir o denegar el uso de una aplicación personalizada para usuarios específicos.

## <a name="allow-developers-to-upload-custom-apps"></a>Permitir que los desarrolladores carguen aplicaciones personalizadas

Puede crear una directiva personalizada o editar la directiva global para permitir o bloquear aplicaciones personalizadas según las necesidades de su organización. Para crear una directiva personalizada que permita a los desarrolladores de la organización cargar aplicaciones personalizadas, siga estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **Aplicaciones de Teams** > **[ Directivas de instalación](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Seleccione **Agregar**.

1. Proporcione un nombre y una descripción para la directiva.

1. Active o desactive **Cargar aplicaciones personalizadas**.

> [!NOTE]
> Para cambiar esta configuración, permite las aplicaciones de terceros en la configuración de [aplicaciones de toda la organización](manage-apps.md#manage-org-wide-app-settings) de tu inquilino.

## <a name="related-articles"></a>Artículos relacionados

* [Administrar directivas de aplicación personalizadas](teams-custom-app-policies-and-settings.md)
* [Comprender las directivas para gobernar las aplicaciones](app-policies.md)
* [Comprender las aplicaciones de terceros](overview-third-party-apps.md)
