---
title: Administrar directivas de permisos de aplicación en Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Obtenga información sobre las directivas de permisos de aplicación en Microsoft Teams y cómo controlar la disponibilidad de las aplicaciones para los usuarios finales.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 24c4b85bb1c4b97597bad6a38e6a67c35dc1abb0
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377048"
---
# <a name="manage-access-to-teams-apps-using-app-permission-policies"></a>Administrar el acceso a las aplicaciones de Teams mediante directivas de permisos de aplicaciones

Como administrador, puede usar directivas de permisos de aplicaciones para controlar las aplicaciones que están disponibles para cada usuario de su organización. Los permisos que establezca para permitir o bloquear todas las aplicaciones o aplicaciones específicas son aplicables a todos los [tipos de aplicaciones en Teams](deploy-apps-microsoft-teams-landing-page.md). Para administrar estas directivas, debe ser administrador global de Administración o teams.

Para permitir una aplicación, debe permitirla en la [configuración de aplicaciones de toda la organización](manage-apps.md#manage-org-wide-app-settings), la [configuración de aplicaciones individuales](manage-apps.md#allow-and-block-apps) y la directiva de permisos de las aplicaciones. Mientras que los otros dos métodos solo permiten que una aplicación se use en su organización, las directivas de permisos le permiten controlar qué usuarios pueden usar una aplicación específica. Puede controlar el acceso por usuario y por aplicación creando y aplicando la directiva a usuarios específicos.

El Centro de administración de Teams le permite crear dos tipos de directivas de permisos:

* `Global (Org-wide default)` existe de forma predeterminada y se aplica a todos los usuarios. Los cambios realizados en esta directiva afectan a todos los usuarios, ya que esta directiva se aplica a todos los usuarios de forma predeterminada.
* Una directiva creada por el administrador solo se aplica a los usuarios a los que se aplica. Cree una nueva directiva para permitir aplicaciones para usuarios específicos o grupos de usuarios.

   :::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Captura de pantalla que muestra una nueva directiva de permisos de aplicación que se está creando." lightbox="media/app-permission-policy.png":::

Si su organización ya está en Teams, la configuración de aplicaciones que configuró en **Configuración de inquilinos** en el Centro de administración de Microsoft 365 se refleja en la configuración de aplicaciones para toda la organización en la página [Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps) del Centro de administración de Teams. Si no está familiarizado con Teams y acaba de empezar, de forma predeterminada, todas las aplicaciones se permiten en la configuración global de toda la organización. Incluye aplicaciones publicadas por Microsoft, proveedores de software de terceros y su organización.

> [!NOTE]
> Para obtener información sobre la configuración de aplicaciones de terceros en Microsoft 365 Government Community Cloud High (GCCH) y el entorno del Departamento de defensa (DoD), consulta [Administrar la configuración de aplicaciones de toda la organización para Microsoft 365 Administración pública](manage-apps.md#manage-org-wide-app-settings-for-microsoft-365-government).

## <a name="create-an-app-permission-policy"></a>Crear una directiva de permisos de aplicación

Use una o varias directivas de permisos de aplicación personalizadas si desea controlar las aplicaciones que están disponibles para distintos grupos de usuarios. Puede crear y asignar directivas personalizadas en función de si las aplicaciones se publican por Microsoft, terceros o su organización. Debe de crear una directiva personalizada, no podrá cambiarla si las aplicaciones de terceros están deshabilitadas en la configuración de la aplicación para toda la organización.

1. Inicie sesión en el Centro de administración de Teams y acceda a las directivas **[de permisos](https://admin.teams.microsoft.com/policies/app-permission)** de **las aplicaciones** >  de Teams.
1. Seleccione **Agregar**.
1. Proporcione un nombre y una descripción para la directiva.
1. En **Aplicaciones de Microsoft**, **Aplicaciones de terceros** y **Aplicaciones personalizadas**, selecciona una de las siguientes opciones:

    * `Allow all apps`
    * `Allow specific apps and block all others`
    * `Block specific apps and allow all others`
    * `Block all apps`

1. Si ha seleccionado **Permitir aplicaciones específicas y bloquear todas las demás**, agregue las aplicaciones que desea permitir:

    1. Seleccione **Permitir aplicaciones**.
    1. Busque las aplicaciones que desea permitir, y luego seleccione **Agregar**. Los resultados de búsqueda se filtran en función de quién haya desarrollado la aplicación (**Aplicaciones de Microsoft**, **Aplicaciones de terceros** y **Aplicaciones personalizadas**).
    1. Después de elegir una o más aplicaciones, selecciona **Permitir**.

1. Si has seleccionado **Bloquear aplicaciones específicas y permitir a todas las demás**, busca y elige de forma similar las aplicaciones que quieras bloquear y, a continuación, selecciona **Bloquear**.

1. Seleccione **Guardar**.

## <a name="edit-an-app-permission-policy"></a>Editar una directiva de permisos de aplicación

Puede usar el Centro de administración de Teams para editar la directiva global o cualquier directiva personalizada que haya creado.

1. Inicie sesión en el Centro de administración de Teams y acceda a las directivas **[de permisos](https://admin.teams.microsoft.com/policies/app-permission)** de **las aplicaciones** >  de Teams.
1. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, seleccione **Editar**.
1. Realiza los cambios para permitir o bloquear aplicaciones específicas en cada una de las tres categorías.
1. Seleccione **Guardar**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Asignar una directiva de permisos de aplicación personalizada a los usuarios

Las directivas de permisos de aplicación surtan efecto solo cuando se aplica una directiva a un usuario o a un grupo de usuarios. Vea las diferentes formas de [asignar la directiva a los usuarios](policy-assignment-overview.md#ways-to-assign-policies).

## <a name="considerations-when-using-app-permission-policies"></a>Consideraciones al usar directivas de permisos de aplicaciones

A continuación se indican algunas consideraciones al usar directivas de permisos de aplicación para conceder acceso o no permitir el acceso a las aplicaciones:

* Las directivas de permisos de aplicación surtan efecto solo cuando se aplica una directiva a un usuario o a un grupo de usuarios.

* Después de editar o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.

* Un usuario final no puede interactuar con ninguna funcionalidad de una aplicación que el usuario no pueda usar.

* Los usuarios pueden buscar aplicaciones bloqueadas y solicitar la aprobación del administrador. Los administradores conservan el control completo para [aprobar o ignorar solicitudes de usuario](user-requests-approve-apps.md).

* Las directivas de configuración de aplicaciones funcionan conjuntamente con las directivas de permisos de aplicaciones. Selecciona las aplicaciones que quieres anclar en la directiva de configuración de un conjunto de aplicaciones permitidas. Sin embargo, si un usuario tiene una directiva de permisos de aplicación que bloquea el uso de una aplicación anclada, el usuario no podrá usar la aplicación.

* Las directivas de aplicación se aplican a los usuarios que usan cualquier Equipo en la web, móvil o escritorio.

## <a name="related-articles"></a>Artículos relacionados

* [Configurar la administración para aplicaciones en Teams](admin-settings.md)
* [Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)
* [La comparación de disponibilidad de características de Teams](/office365/servicedescriptions/teams-service-description#feature-availability)
