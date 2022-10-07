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
ms.date: 09/25/2022
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
ms.openlocfilehash: 42c970f3b354ac1f5b490359f0df9bcc01e97019
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494773"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>Comprender y administrar aplicaciones personalizadas y de instalación de prueba

Microsoft Teams permite a los desarrolladores de su organización crear, probar e implementar aplicaciones personalizadas para los usuarios internos de la organización. Estas aplicaciones se denominan aplicaciones personalizadas o aplicaciones de Línea de negocio. Su organización puede encargar la creación de aplicaciones personalizadas para los requisitos específicos de la organización. Los administradores controlan la implementación de y los permisos de las aplicaciones personalizadas mediante diversas configuraciones y directivas.

:::image type="content" source="media/custom-app-orgwide-setting-trimmed.png" alt-text="Recorte de pantalla que muestra cómo permitir aplicaciones personalizadas en la organización en el panel de configuración de toda la organización." lightbox="media/custom-app-orgwide-setting.png":::

Después de permitir el uso de una aplicación personalizada, los usuarios finales pueden encontrarla seleccionando **Creado para su organización** en el panel de navegación izquierdo de la tienda de Teams.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Captura de pantalla de aplicaciones personalizadas en la tienda de Teams en la aplicación de escritorio de Teams." lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>Descripción de la instalación de prueba de aplicaciones personalizadas

Al desarrollar aplicaciones personalizadas y antes de distribuirlas a los usuarios finales, los desarrolladores prueban las aplicaciones agregándolas a la Tienda Teams para probarlas. Los desarrolladores pueden realizar pruebas por su cuenta o con un grupo específico de usuarios, pero la aplicación no está disponible para otros usuarios finales de la organización a través de store. Este método se denomina instalación de prueba de aplicaciones y solo se aplica a aplicaciones personalizadas.

Los desarrolladores pueden transferir localmente una aplicación para que esté disponible para los miembros de un equipo específico, normalmente cuando se prueba una aplicación en desarrollo. Cuando se usa una aplicación de esta forma, se limita el uso a los desarrolladores de aplicaciones y no se requiere la aprobación de un administrador, siempre y cuando el administrador permita la instalación de prueba en Teams.

Los desarrolladores pueden compartir una aplicación con instalación de prueba con un equipo específico sin enviarla al catálogo de aplicaciones de Teams. Hace que la aplicación personalizada de instalación de prueba esté disponible para un grupo limitado de usuarios finales, pero no está disponible en la tienda de aplicaciones de su organización para todos los usuarios finales.

Como administrador, se puede denegar la instalación de prueba de aplicaciones para todos los desarrolladores. Si no se permite la instalación de prueba, los desarrolladores podrán probar sus aplicaciones al [crear un inquilino de prueba independiente](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Una vez completado el desarrollo de aplicaciones personalizadas, los desarrolladores solicitan a los administradores que distribuyan su aplicación personalizada a los usuarios finales. Para obtener más información, consulte [cómo publicar una aplicación personalizada](/microsoftteams/upload-custom-apps). Como administrador, permite (o bloquea) el uso de una aplicación personalizada para todos los usuarios o para usuarios específicos.

## <a name="allow-developers-to-upload-custom-apps"></a>Permitir que los desarrolladores carguen aplicaciones personalizadas

En la directiva de configuración de aplicaciones, puede crear una directiva personalizada o editar la directiva global para permitir la carga de aplicaciones personalizadas. Para crear una directiva personalizada y aplicarla a usuarios específicos, siga estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **Aplicaciones de Teams** > **[ Directivas de instalación](https://admin.teams.microsoft.com/policies/app-setup)**.
1. Seleccione **Agregar**.
1. Proporcione un nombre y una descripción para la directiva.
1. Active o desactive **Cargar aplicaciones personalizadas**.
1. [Aplique la directiva a los usuarios](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users) que desarrollan aplicaciones personalizadas y tienen permiso para cargarlas.

> [!NOTE]
> Para cambiar esta configuración, permita las aplicaciones personalizadas en la [configuración de aplicaciones de toda la organización](manage-apps.md#manage-org-wide-app-settings).

## <a name="related-articles"></a>Artículos relacionados

* [Administrar directivas y configuraciones de aplicaciones personalizadas](teams-custom-app-policies-and-settings.md)
* [Comprender las directivas para gobernar las aplicaciones](app-policies.md)
* [Comprender las aplicaciones de terceros](overview-third-party-apps.md)
