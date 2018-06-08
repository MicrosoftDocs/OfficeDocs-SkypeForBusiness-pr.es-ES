---
title: Administración de la tienda de aplicaciones de Microsoft los equipos privados
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Instrucciones para la administración de aplicaciones en la tienda de aplicaciones privada de Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6aaa763c423d7756808856706375f96f99224b9e
ms.sourcegitcommit: d979aecf73da0ba493a0b3be1db4d8b997c6ce2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "19694892"
---
<a name="publish-apps-to-the-microsoft-teams-private-app-store"></a>Publicar aplicaciones en la tienda de aplicaciones de Microsoft los equipos privados
============================================

> [!IMPORTANT]
> Esta página describe una característica de la versión preliminar y contiene contenido preliminar que puede cambiar considerablemente antes de que se libere. Las capturas de pantalla son marcadores de posición y podrían ser diferentes de lo que se ve.

Puede usar Microsoft Teams Private App Store para probar y distribuir aplicaciones de línea de negocio para su organización. 

Microsoft Teams Private App Store permite distribuir las aplicaciones de línea de negocio que han sido creadas específicamente para su organización y que se basan en para completan las funciones empresariales fundamentales para los usuarios. 
 
Existen dos métodos para publicar aplicaciones en la tienda de aplicaciones privada de los equipos:
- Directamente desde el cliente de los equipos 
- Cmdlets que aprovechan las API de gráfico de Microsoft (este método no está todavía disponible para vista previa.)

## <a name="publish-an-app-to-the-teams-private-app-store-from-the-teams-client"></a>Publicar una aplicación en la tienda de aplicaciones privada de los equipos desde el cliente de los equipos

### <a name="get-a-teams-app-package"></a>Obtener un paquete de la aplicación de los equipos

Se crea un paquete de aplicación de los equipos mediante el uso de [Los equipos de aplicación Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio). Una vez que el paquete de la aplicación, puede agregarlo al catálogo de aplicaciones de empresa. Si bien todos los usuarios en el inquilino pueden ver el catálogo de aplicaciones, sólo los administradores tienen la capacidad de administrar.

### <a name="go-to-the-teams-private-app-store"></a>Vaya a la tienda de aplicaciones privada de los equipos

De Microsoft Teams Store, seleccione la nueva sección con nombre para su organización específica (en este ejemplo, Contoso). Los usuarios de su organización pueden ver aplicaciones en el catálogo y los instale en los equipos de los cuales son miembros. 

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-teams-private-app-store"></a>Agregar una aplicación a la tienda de aplicaciones privada de los equipos

En el almacén, seleccione **carga una aplicación personalizada** > **Cargar para Contoso**.

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image02.png)

(También puede **Cargar para mí o a Mis equipos**, que se denomina sideloading, que hace que la aplicación esté disponible únicamente para los o los equipos seleccionados.) 

Navegue hasta el paquete de la aplicación y selecciónelo.

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image03.png)

Cuando vuelva a su catálogo de aplicaciones, la nueva aplicación de empresa va a estar allí. Recuerde que sólo usted y los miembros de la organización tienen acceso a este catálogo de aplicaciones.

### <a name="update-an-app-in-the-teams-private-app-store"></a>Actualizar una aplicación en la tienda de aplicaciones privada de los equipos

1. En el catálogo de aplicaciones, seleccione "**...**" en esquina superior derecha de la aplicación que desea actualizar.
2. Navegue al paquete de la aplicación actualizada y selecciónelo.

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image04.png)

La aplicación se revisará a la versión 2.0. También se elimina la aplicación para toda la empresa desde este menú.

## <a name="manage-the-teams-private-app-store-by-using-cmdlets-and-microsoft-graph-apis"></a>Administración de la tienda de aplicaciones privada de los equipos mediante el uso de los cmdlets y las API de Microsoft Graph

Este método aún no está disponible para vista previa.

## <a name="use-the-office-365-admin-portal-to-manage-private-apps"></a>Usar el portal de administración de Office 365 para administrar aplicaciones de privado

Si tiene aplicaciones que necesitan correcciones de errores, puede deshabilitar temporalmente aplicaciones a través del portal de administración de Office 365. Además de la configuración anterior, ahora hay una sección dedicada a las aplicaciones de su empresa. Puede elegir qué aplicaciones que desea habilitar o deshabilitar.

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image05.png)

Esto impide que los usuarios interactuar con la aplicación, sin eliminar por completo la aplicación. Estos controles dar a los administradores más flexibilidad y control cuando gobierno de aplicaciones en la empresa. 


