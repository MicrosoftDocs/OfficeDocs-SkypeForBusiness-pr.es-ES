---
title: Publicar aplicaciones en el catálogo de aplicaciones de inquilino de Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Guía para la publicación de aplicaciones en el catálogo de aplicaciones de inquilino de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 35f15986fa5977a08cd91ce8cc5ca40ace0daca9
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "36484075"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a>Publicar aplicaciones en el catálogo de aplicaciones de inquilino de Microsoft Teams
=======================================================

Puede usar el catálogo de aplicaciones de inquilino de Microsoft Teams para probar y distribuir aplicaciones de línea de negocio a su organización.

El catálogo de aplicaciones de inquilino de Teams le permite distribuir aplicaciones de línea de negocio que se han creado específicamente para su organización y en las que confía para completar las funciones críticas de la empresa.

Para publicar aplicaciones para su organización, inicie sesión en el cliente de Teams mediante una cuenta con los roles de administrador global o de servicio de Teams y, a continuación, siga las instrucciones a continuación.

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a>Publicar una aplicación en el catálogo de aplicaciones de inquilino del cliente de Teams

> [!NOTE]
> Debe haber iniciado sesión en el cliente de Microsoft Teams con una cuenta que tenga habilitada la función de administrador global o de administrador de servicios de equipo para publicar aplicaciones para su organización. Obtenga más información sobre el [uso de roles de administrador para administrar equipos](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).

### <a name="get-a-teams-app-package"></a>Obtener un paquete de la aplicación Teams

Un paquete de la aplicación de Teams se crea con [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Una vez que tenga el paquete de la aplicación, puede agregarlo al catálogo de aplicaciones empresarial. Mientras todos los usuarios del inquilino pueden ver el catálogo de aplicaciones, solo los administradores globales y los administradores de servicios de equipos tienen la capacidad de publicarlos y administrarlos.

### <a name="go-to-the-tenant-apps-catalog"></a>Ir al catálogo de aplicaciones de inquilino

Inicie el cliente de Microsoft Teams e inicie sesión con las credenciales de administrador del servicio global o de Teams. En la tienda Microsoft Teams, seleccione la nueva sección nombrada para su organización específica (en este ejemplo, contoso). Los usuarios de su organización pueden ver las aplicaciones en el catálogo e instalarlas para los equipos de los que son miembros.

![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>Agregar una aplicación al catálogo de aplicaciones de inquilino

1. En la tienda, seleccione **cargar una** > **carga de aplicaciones personalizada para contoso**.

    ![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image02.png)

    (También puede elegir **cargar por mí o mis equipos**, que se denomina *transferencia local*. La transferencia local hace que la aplicación esté disponible solo para los equipos o los equipos que seleccione.)

2. Navegue hasta el paquete de la aplicación, selecciónelo y, a continuación, haga clic en **abrir**.

    ![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image03.png)

Cuando vuelva al catálogo de aplicaciones de inquilino, la nueva aplicación de empresa estará allí. Recuerde que solo usted y los miembros de su organización tienen acceso a este catálogo de aplicaciones.

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>Actualizar una aplicación en el catálogo de aplicaciones de inquilino

1. Desde el catálogo de aplicaciones de inquilino, seleccione "**...**" en la parte superior derecha de la aplicación que desea actualizar.

2. Navegue hasta el paquete de la aplicación actualizado, selecciónelo y, a continuación, haga clic en **abrir**.

    ![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image04.png)

La aplicación se revisará como versión 2,0. También puede eliminar la aplicación de toda la empresa desde este menú.

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>Usar el portal de administración de Office 365 para administrar el catálogo de aplicaciones de inquilino

Si tiene aplicaciones que necesitan correcciones de errores, puede deshabilitar temporalmente las aplicaciones a través del portal de administración de Office 365. Seleccione **Settings** > **Services & complementos** > **Microsoft Teams**. Además de la configuración anterior, ahora hay una sección dedicada a las aplicaciones de su empresa. Puede elegir qué aplicaciones quiere habilitar o deshabilitar.

![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image05.png)

Deshabilitar una aplicación evitará que los usuarios interactúen con la aplicación, sin eliminarla por completo. Estos controles ofrecen flexibilidad y control adicionales al administrar aplicaciones de su empresa.
