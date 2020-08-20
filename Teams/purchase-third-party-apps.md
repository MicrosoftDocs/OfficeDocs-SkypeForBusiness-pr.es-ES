---
title: Servicios de compra para aplicaciones de terceros en el centro de administración de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava
search.appverid: MET150
f1keywords: ''
description: Aprenda a adquirir aplicaciones de terceros de servicios para equipos en la página Administrar aplicaciones del centro de administración de Microsoft Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: aeff6f363c1ae594a4a122055204d98b43d246e8
ms.sourcegitcommit: e0e089f0ab217d920e128377af653f7dbfdedacf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818159"
---
<a name="purchase-services-for-teams-third-party-apps-in-the-microsoft-teams-admin-center"></a>Servicios de compra para aplicaciones de terceros en el centro de administración de Microsoft Teams
======================================================

> [!NOTE]
> Actualmente, esta característica solo está disponible en los Estados Unidos.

Las aplicaciones de Teams son gratuitas de instalar y algunas pueden requerir la compra de suscripciones de servicio para experimentar la funcionalidad y el ámbito completo de la aplicación. Estas suscripciones de servicio se denominan ofertas de software como servicio (SaaS), que se encuentran disponibles para su compra a través de [AppSource](https://appsource.microsoft.com/) y ahora a través del centro de administración de Microsoft Teams.

La página [Manage apps](manage-apps.md) en el centro de administración de Microsoft Teams es donde se ven y administran todas las aplicaciones de Teams para su organización. Por ejemplo, puede ver el estado de organización y las propiedades de las aplicaciones, cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización, bloquear o permitir aplicaciones en el nivel de la organización y administrar la configuración de la aplicación en toda la organización.

Aquí también puede comprar licencias para los servicios ofrecidos por aplicaciones de terceros para los usuarios de su organización. La columna **licencias** de la tabla indica si una aplicación ofrece una suscripción de SaaS para la compra.

:::image type="content" source="media/purchase-third-party-apps-list.png" alt-text="Captura de pantalla que muestra aplicaciones de terceros que tienen suscripciones de SaaS":::

## <a name="search-for-and-purchase-services-for-a-third-party-app"></a>Buscar y comprar servicios para una aplicación de terceros

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**. Debe ser administrador global o administrador de servicios de equipo para poder acceder a la página.
2. Busque la aplicación que desee. Para identificar las aplicaciones que tienen una suscripción de SaaS de pagos, mire en la columna **licencias** . Cada aplicación tendrá uno de los siguientes valores:
    - **Comprar ahora**: la aplicación ofrece una suscripción de SaaS y está disponible para la compra.  
    - **Comprado**: la aplicación ofrece una suscripción de SaaS y ha comprado las licencias para él.
    - **--**: La aplicación no ofrece una suscripción de SaaS.
3. Cuando encuentre la aplicación, haga clic en **comprar ahora** para ir a la pestaña **planes y precios** de la página de detalles de la aplicación. Revise los planes y la información de precios de la oferta de SaaS para la aplicación. Si necesita más información, haga clic en **el vínculo más información para** ir a la página de la aplicación en [AppSource](https://appsource.microsoft.com/).  
4. Para comprar un plan, haga clic en **comprar ahora**. Será redirigido a la experiencia de compra de la oferta asociada con la aplicación de Teams. Aquí es donde completará la compra del servicio o la oferta de SaaS.
5. Elija el plan que desee. Si la oferta de SaaS incluye más de un plan, haga clic en **cambiar** para ver la lista de planes disponibles.
6. Seleccione el término de facturación ( **mensual** o **anual**) y, a continuación, escriba el número de licencias de usuario que desea comprar.
7. Escribe tu forma de pago.
8. Cuando esté listo, seleccione **realizar pedido**.
9. Haga clic en **configurar ahora** para activar su suscripción en el sitio web del editor.

Después de comprar la oferta de SaaS asociada con la aplicación de Teams, puede ver los siguientes detalles de la compra en la pestaña **planes y precios** de la página de detalles de la aplicación.

- **Fecha de activación**de la licencia: fecha en la que se activó su licencia. Si su cuenta aún no se ha configurado, se mostrará como **activación de suscripción pendiente**.
- **Licencias**: número de licencias compradas.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Captura de pantalla de la pestaña planes y precios de la página de detalles de la aplicación":::

Seleccione **administrar licencias** para ir al centro de administración de Microsoft 365 para ver y administrar las licencias que compró y para administrar las asignaciones de licencias de los usuarios.

Los administradores globales pueden ver las compras realizadas por cualquier persona de la organización, mientras que los administradores de servicios de equipos solo pueden ver las compras realizadas por sí mismos.  

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>¿Tiene una oferta de SaaS para una aplicación de teams que desee enumerar y vender en el centro de administración de Microsoft Teams y AppSource?

Los programadores pueden crear ofertas de SaaS asociadas con sus aplicaciones de Teams. Estas ofertas se publican a través del [centro de Partners](https://partner.microsoft.com) y están disponibles para que las organizaciones las compren a través de [AppSource](https://appsource.microsoft.com/) y el centro de administración de Microsoft Teams.
 
Los programadores de aplicaciones de terceros pueden ir a [crear una oferta de SaaS](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer) para obtener más información.

## <a name="related-topics"></a>Temas relacionados

- [Administrar las aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md)
- [Crear una oferta de SaaS](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer)
