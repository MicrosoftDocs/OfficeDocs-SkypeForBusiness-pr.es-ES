---
title: Comprar aplicaciones de terceros para Teams
author: KarliStites
ms.author: kastites
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
description: Obtenga información sobre cómo comprar aplicaciones de terceros para Teams en el Microsoft Teams de administración.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 19403d35ad2e7263ad6f0d5a2c7a2b22d4249664
ms.sourcegitcommit: c7a6079c9592c28d8b082ff92004ae4706cea76e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2021
ms.locfileid: "60600224"
---
# <a name="purchase-third-party-apps-for-teams"></a>Comprar aplicaciones de terceros para Teams

Teams aplicaciones son gratuitas y algunas pueden requerir la compra de suscripciones de servicio para experimentar la funcionalidad y el ámbito completos de la aplicación. Estas suscripciones de servicio se denominan ofertas de Software como servicio (SaaS), que están disponibles para su compra a través de [AppSource](https://appsource.microsoft.com/) y ahora a través del centro Microsoft Teams administración.

La [página Administrar aplicaciones](manage-apps.md) del centro Microsoft Teams administración es donde puede ver y administrar todas las Teams aplicaciones de su organización. Por ejemplo, puede ver el estado y las propiedades de las aplicaciones a nivel de organización, cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización, bloquear o permitir aplicaciones en el nivel de la organización y administrar la configuración de aplicaciones para toda la organización.

Aquí también puede comprar licencias para los servicios ofrecidos por aplicaciones de terceros para los usuarios de su organización. La **columna Licencias de** la tabla indica si una aplicación ofrece una suscripción saas para la compra.

![Captura de pantalla de la página administrar aplicaciones de licencias de compra.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Comprar aplicaciones en el centro Teams administración

> [!IMPORTANT]
> Si quiere bloquear a los usuarios para que no compren una aplicación a través Teams tienda de aplicaciones, tiene que bloquear la aplicación. Para obtener más información sobre cómo bloquear una aplicación, vea Administrar directivas de [aplicación](app-policies.md) o obtenga información sobre cómo bloquear una aplicación [a nivel de organización.](manage-apps.md#allow-and-block-apps)

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**. Debe ser administrador global o administrador Teams servicio para acceder a la página.
2. Busca la aplicación que quieras. Para identificar las aplicaciones que tienen una suscripción de SaaS de pago, busque en la **columna** Licencias. Cada aplicación tendrá uno de los siguientes valores:
    - **Compra:** La aplicación ofrece una suscripción SaaS y está disponible para comprar.  
    - **Comprado:** la aplicación ofrece una suscripción SaaS y ha comprado licencias para ella.
    - **- -**: La aplicación no ofrece una suscripción de SaaS.
3. Cuando encuentre la aplicación, haga clic en **Comprar** para ir a la **pestaña Planes y** precios de la página de detalles de la aplicación. Revise los planes y la información de precios de la oferta de SaaS para la aplicación. Si necesita más información, seleccione **Más información** para ir a la página de la aplicación en [AppSource.](https://appsource.microsoft.com/)

> [!NOTE]
> Los planes privados también pueden aparecer en la lista para la compra, que incluyen precios especiales que su organización ha negociado previamente con un ISV. Estos planes tendrán la etiqueta **Plan privado** bajo el nombre del plan.

4. Para suscribirse a una aplicación, elija el plan que desee y seleccione **Comprar.** El flujo de desprotección se abrirá directamente en el Teams de administración.
5. Seleccione el número de licencias de usuario que desea comprar.
6. Compruebe que la cuenta de facturación y la dirección de venta son correctas. Si aún no la tiene, agregue una nueva **seleccionando Agregar**. Para obtener más información sobre las cuentas de facturación, vea [Comprender cuentas de facturación.](/microsoft-365/commerce/manage-billing-accounts)

> [!NOTE]
> Debes ser administrador global para agregar una nueva cuenta de facturación.

7. Compruebe que el perfil de facturación correcto está seleccionado. Si aún no la tiene, agregue una nueva **seleccionando Agregar nuevo**. Tiene la opción de pagar con una tarjeta de crédito, tarjeta de débito o con [facturación de factura.](#invoice-billing) El perfil de facturación también le permite agregar un número de pedido de compra para identificar el pedido más adelante. Para obtener más información sobre los perfiles de facturación, vea [Comprender los perfiles de facturación.](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)
8. Seleccione **Realizar pedido.**
9. Seleccione **Configurar para** activar la suscripción en el sitio web del editor. Si no configura la suscripción después de la compra, puede hacerlo más adelante seleccionando Administrar **licencias.**

Después de comprar la oferta SaaS asociada Teams la aplicación Teams, puede ver  los siguientes detalles de compra en la pestaña Planes y precios de la página de detalles de la aplicación.

- **Fecha de activación de licencia:** fecha en la que se activó la licencia. Si su cuenta aún no está configurada, se muestra como **Suscripción pendiente de activación.**
- **Licencias:** Número de licencias que ha comprado.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Captura de pantalla de la pestaña Planes y precios de la página de detalles de la aplicación.":::

Seleccione **Administrar licencias para** ir al Centro de administración de Microsoft 365 para ver y administrar las licencias que compró.

Los administradores globales pueden agregar más licencias, quitar licencias y cancelar suscripciones para las compras realizadas por cualquier usuario de la organización. Teams administradores de servicios pueden realizar las mismas acciones para las compras realizadas por ellos mismos. Sin embargo, si un Teams de servicio de facturación también tiene el rol de administrador de facturación, puede administrar las compras realizadas por cualquier persona de la organización.

> [!NOTE]
> Si un administrador global quiere administrar una suscripción comprada por otro administrador global, debe estar en la misma cuenta de facturación. Puede dar a otro administrador global acceso a una suscripción que compró seleccionando la aplicación en el Centro de administración de Microsoft 365. Desde allí, vaya a Ver perfil **de facturación** Seleccionar cuenta  >  **de facturación Asignar**  >  **roles** Agregar  >  **otros administradores globales.**

### <a name="invoice-billing"></a>Facturación de facturas

- La facturación de facturas está disponible como opción de pago para algunas transacciones.
- Se requiere una revisión de crédito la primera vez que use la facturación de factura, que puede tardar hasta 24 o 48 horas en aprobarse. La facturación de factura no estará disponible hasta que se complete la comprobación de crédito. Puede realizar el pedido con una tarjeta de crédito o volver a intentarlo más tarde después de aprobar la revisión de crédito.
- La facturación solo está disponible para administradores globales o administradores con Teams de servicio y de administración de facturación.
- La facturación de facturas no está disponible al comprar un plan con una prueba gratuita de 30 días.

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>¿Tiene una oferta saas para una aplicación Teams que desea enumerar y vender en el centro de administración de Microsoft Teams y AppSource?

Los desarrolladores pueden crear ofertas saas asociadas a sus Teams aplicaciones. Estas ofertas se publican a través del Centro de [partners](https://partner.microsoft.com) y están disponibles para que las organizaciones compren a través de [AppSource](https://appsource.microsoft.com/) y Microsoft Teams centro de administración.

Los desarrolladores de aplicaciones de terceros pueden ir [a Crear una oferta saas](/azure/marketplace/partner-center-portal/create-new-saas-offer) para obtener más información.

## <a name="related-topics"></a>Temas relacionados

- [Administrar las aplicaciones en el centro Microsoft Teams administración](manage-apps.md)
- [Crear una oferta saas](/azure/marketplace/partner-center-portal/create-new-saas-offer)
- [Azure AD roles integrados](/azure/active-directory/roles/permissions-reference)
- [Microsoft 365 de administrador](/microsoft-365/admin/add-users/about-admin-roles)