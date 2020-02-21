---
title: Publicar aplicaciones en el catálogo de aplicaciones de inquilino de Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Instrucciones para la publicación de aplicaciones en el catálogo de aplicaciones de inquilino de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161619"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a>Publicar aplicaciones en el catálogo de aplicaciones de inquilino de Microsoft Teams
=======================================================

Puede usar el catálogo de aplicaciones de inquilino de Microsoft Teams para probar y distribuir aplicaciones de línea de negocio a su organización.

El catálogo de aplicaciones de inquilino de Teams le permite distribuir aplicaciones de línea de negocio que se han creado específicamente para su organización y en las que confía para completar las funciones críticas de la empresa.

Para publicar aplicaciones para su organización, inicie sesión en el cliente de Teams mediante una cuenta con el rol de administrador global o de administrador de servicios de equipo y, a continuación, siga los pasos que se indican a continuación.

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a>Publicar una aplicación en el catálogo de aplicaciones de inquilino del cliente de Teams

> [!NOTE]
> Estos pasos describen cómo publicar una aplicación con el cliente de Teams. También puede publicar una aplicación en la página **Manage apps** en el centro de administración de Microsoft Teams. Para obtener más información, consulte [Administrar aplicaciones en Teams](manage-apps.md).

### <a name="get-a-teams-app-package"></a>Obtener un paquete de la aplicación Teams

Un paquete de la aplicación de Teams se crea con [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Una vez que tenga el paquete de la aplicación, puede agregarlo al catálogo de aplicaciones del inquilino. Mientras todos los usuarios de su organización pueden ver el catálogo de aplicaciones, solo los administradores globales y los administradores de servicios de equipos tienen la capacidad de publicarlos y administrarlos.

### <a name="go-to-the-tenant-app-catalog"></a>Ir al catálogo de aplicaciones de inquilino

Inicie Teams e inicie sesión con sus credenciales de administrador de servicio global o Teams. Seleccione **aplicaciones** en la parte izquierda de la aplicación y, a continuación, seleccione la nueva sección nombrada para su organización específica (en este ejemplo, contoso). Los usuarios de su organización pueden ver las aplicaciones en el catálogo e instalarlas para los equipos de los que son miembros.

![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a>Agregar una aplicación al catálogo de aplicaciones de inquilino

1. En la página **aplicaciones** , seleccione **cargar una aplicación** > **de carga personalizada para contoso**.

    ![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image02.png)

    (También puede elegir **cargar por mí o mis equipos**, que se denomina *transferencia local*. La transferencia local hace que la aplicación esté disponible solo para los equipos o los equipos que seleccione.)

2. Navegue hasta el paquete de la aplicación, selecciónelo y, a continuación, haga clic en **abrir**.

    ![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image03.png)

Cuando vuelva al catálogo de aplicaciones de inquilino, la nueva aplicación de empresa estará allí. Recuerde que solo usted y los miembros de su organización tienen acceso a este catálogo de aplicaciones.

### <a name="update-an-app-in-the-tenant-app-catalog"></a>Actualizar una aplicación en el catálogo de aplicaciones de inquilino

1. Desde el catálogo de aplicaciones de inquilino, seleccione "**...**" en la parte superior derecha de la aplicación que desea actualizar.

2. Navegue hasta el paquete de la aplicación actualizado, selecciónelo y, a continuación, haga clic en **abrir**.

    ![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image04.png)

La aplicación se revisará como versión 2,0. También puede eliminar la aplicación de toda la empresa desde este menú.

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a>Usar el centro de administración de Microsoft Teams para administrar el catálogo de aplicaciones de inquilino

Si tiene aplicaciones que necesitan correcciones de errores, puede deshabilitar temporalmente las aplicaciones para los usuarios en una directiva de permisos de la aplicación.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a > **directivas de permisos**de las **aplicaciones de Teams**.
2. Seleccione la Directiva de permisos de la aplicación que desea editar y, a continuación, haga clic en **Editar**.
3. En **aplicaciones de inquilino**, seleccione **bloquear aplicaciones específicas y permitir a todos los demás**y, a continuación, agregue las aplicaciones que quiera bloquear.

Deshabilitar una aplicación impide que los usuarios interactúen con la aplicación, sin eliminarla por completo. Estos controles ofrecen flexibilidad y control adicionales al administrar aplicaciones de su organización.

Para obtener más información, vea [Administrar directivas de permisos de aplicaciones en Teams](teams-app-permission-policies.md).