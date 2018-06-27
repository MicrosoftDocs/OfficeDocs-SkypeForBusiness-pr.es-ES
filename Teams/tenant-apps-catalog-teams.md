---
title: Publicar aplicaciones en el catálogo de aplicaciones del inquilino de equipos de Microsoft
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Instrucciones para la publicación de aplicaciones en el catálogo de aplicaciones de inquilino de los equipos de Microsoft.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 298caf3cee6fe6af38f22ef9ac7dd85991fd6dba
ms.sourcegitcommit: b42a6a56a0e1e4be1239174c1c3b4ab86517d043
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "20050462"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a>Publicar aplicaciones en el catálogo de aplicaciones del inquilino de equipos de Microsoft
=======================================================

> [!IMPORTANT]
> Esta página describe una característica de la versión preliminar y contiene contenido preliminar que puede cambiar considerablemente antes de que se libere. Las capturas de pantalla son marcadores de posición y podrían ser diferentes de lo que se ve.

Puede usar el catálogo de aplicaciones de inquilino de los equipos de Microsoft para probar y distribuir aplicaciones de línea de negocio para su organización. 

El catálogo de aplicaciones de los equipos de inquilino permite distribuir las aplicaciones de línea de negocio que han sido creadas específicamente para su organización y que se basan en para completan las funciones empresariales fundamentales para los usuarios. 
 
Puede publicar aplicaciones en el catálogo de aplicaciones del inquilino de equipos directamente desde el cliente de los equipos.

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a>Publicar una aplicación en el catálogo de aplicaciones de inquilino desde el cliente de los equipos

### <a name="get-a-teams-app-package"></a>Obtener un paquete de la aplicación de los equipos

Se crea un paquete de aplicación de los equipos mediante el uso de [Los equipos de aplicación Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio). Una vez que el paquete de la aplicación, puede agregarlo al catálogo de aplicaciones de empresa. Si bien todos los usuarios en el inquilino pueden ver el catálogo de aplicaciones, sólo los administradores tienen la capacidad de administrar.

### <a name="go-to-the-tenant-apps-catalog"></a>Vaya al catálogo de aplicaciones de inquilinos

De Microsoft Teams Store, seleccione la nueva sección con nombre para su organización específica (en este ejemplo, Contoso). Los usuarios de su organización pueden ver aplicaciones en el catálogo y los instale en los equipos de los cuales son miembros. 

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>Agregar una aplicación para el catálogo de aplicaciones de inquilinos

En el almacén, seleccione **carga una aplicación personalizada** > **Cargar para Contoso**.

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image02.png)

(También puede **Cargar para mí o a Mis equipos**, que se denomina sideloading, que hace que la aplicación esté disponible únicamente para los o los equipos seleccionados.) 

Navegue hasta el paquete de la aplicación y selecciónelo.

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image03.png)

Cuando vuelva a su catálogo de aplicaciones del inquilino, será la nueva aplicación de empresa no existe. Recuerde que sólo usted y los miembros de la organización tienen acceso a este catálogo de aplicaciones.

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>Actualizar una aplicación en el catálogo de aplicaciones de inquilinos

1. En el catálogo de aplicaciones inquilino, seleccione "**...**" en esquina superior derecha de la aplicación que desea actualizar.
2. Navegue al paquete de la aplicación actualizada y selecciónelo.

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image04.png)

La aplicación se revisará a la versión 2.0. También se elimina la aplicación para toda la empresa desde este menú.

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>Usar el portal de administración de Office 365 para administrar el catálogo de aplicaciones de inquilinos

Si tiene aplicaciones que necesitan correcciones de errores, puede deshabilitar temporalmente aplicaciones a través del portal de administración de Office 365. Además de la configuración anterior, ahora hay una sección dedicada a las aplicaciones de su empresa. Puede elegir qué aplicaciones que desea habilitar o deshabilitar.

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image05.png)

Esto impide que los usuarios interactuar con la aplicación, sin eliminar por completo la aplicación. Estos controles dar a los administradores más flexibilidad y control cuando gobierno de aplicaciones en la empresa. 


