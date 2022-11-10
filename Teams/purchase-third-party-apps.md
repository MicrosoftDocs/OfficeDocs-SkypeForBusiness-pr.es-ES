---
title: Comprar aplicaciones de terceros y administrar suscripciones
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 10/04/2022
ms.collection:
- M365-collaboration
ms.reviewer: chhavib, nsuter
search.appverid: MET150
f1keywords: ''
description: Obtenga información sobre cómo comprar licencias de aplicación de pago en la tienda de Teams con una tarjeta de crédito, una tarjeta de débito o mediante facturación.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 82364d5659009e067a6884551266c6fabf93dc04
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912429"
---
# <a name="purchase-third-party-teams-apps-and-manage-subscriptions"></a>Comprar aplicaciones de Teams de terceros y administrar suscripciones

Algunas aplicaciones de Teams pueden requerir la compra de una suscripción de servicio para experimentar la funcionalidad y el ámbito completos de la aplicación. Estas suscripciones de servicio se denominan ofertas de Software como servicio (SaaS). Se puede comprar una licencia a través [de AppSource](https://appsource.microsoft.com/) y del [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com).

Las aplicaciones de pago se administran con los mismos controles de gobierno que para cualquier otra aplicación. Puede ver y administrar todas las aplicaciones de Teams desde la página [Administrar aplicaciones](manage-apps.md) del Centro de administración de Teams.

En la página Administrar aplicaciones, también puede comprar licencias para los servicios ofrecidos por aplicaciones de terceros para los usuarios de su organización. La columna **Licencias** de la tabla indica si una aplicación ofrece una suscripción SaaS para comprar. Los usuarios finales pueden comprar aplicaciones con tarjeta de crédito, tarjeta de débito o con facturación.

:::image type="content" source="media/manage-apps-new-page.png" alt-text="Captura de pantalla que muestra la opción de compra de licencias en la página administrar aplicaciones del Centro de administración de Teams." lightbox="media/manage-apps-new-page-large.png":::

## <a name="purchase-apps-in-the-teams-admin-center"></a>Comprar aplicaciones en el centro de administración de Teams

Para comprar aplicaciones en el centro de administración de Teams, siga estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** > **[de Teams Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**. Debe ser Administrador global o Administrador de servicio de Teams para acceder a la página.

1. Busque la aplicación que quiera por su nombre. Para comprobar si la aplicación ofrece una suscripción SaaS de pago, consulte la columna **Licencias** . Cada aplicación tiene uno de los siguientes valores:
    * **Comprar**: la aplicación ofrece una suscripción SaaS y está disponible para comprar.
    * **Comprado**: la aplicación ofrece una suscripción SaaS y has comprado licencias para ella.
    * **- -**: La aplicación no ofrece una suscripción SaaS.

1. Selecciona **Comprar** para ir a la pestaña **Planes y precios** de la página de detalles de la aplicación. Puede revisar la información de planes y precios disponible en el Centro de administración. Puede seleccionar **el vínculo Más información** para ir a la página de la aplicación en [AppSource](https://appsource.microsoft.com/).

1. Para suscribirse a una aplicación, elija el plan que desee y seleccione **Comprar**. El flujo de finalización de la compra se abre directamente en el centro de administración de Teams.

> [!NOTE]
> También se puede incluir la compra de planes privados, que incluyen precios especiales que la organización puede negociar por separado con algún desarrollador de aplicaciones. Estos planes tendrán la etiqueta **Plan privado** bajo el nombre del plan.

1. Seleccione el número de licencias de usuario que desea comprar.

1. Compruebe que la cuenta de facturación y la dirección de venta son correctas. Si aún no tiene una, seleccione **Agregar**. Para obtener más información sobre las cuentas de facturación, consulte [Descripción de las cuentas de facturación](/microsoft-365/commerce/manage-billing-accounts). Solo un Administrador global puede agregar una nueva cuenta de facturación.

1. Compruebe que está seleccionado el perfil de facturación correcto. Si aún no tiene uno, seleccione **Agregar nuevo**. Puedes pagar con una tarjeta de crédito, una tarjeta de débito o con [facturación](#invoice-billing). El perfil de facturación también le permite agregar un número de pedido de compra para identificar el pedido más adelante. Para obtener más información sobre los perfiles de facturación, consulte [Descripción de los perfiles de facturación](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).

1. Seleccione **Realizar pedido**.

1. Seleccione **Configurar** para activar la suscripción en el sitio web del desarrollador de la aplicación. Si no configuras la suscripción después de la compra, puedes hacerlo más adelante seleccionando **Administrar suscripciones**.

Después de comprar la oferta de SaaS asociada a la aplicación Teams, puede ver los siguientes detalles de compra en la pestaña **Planes y suscripciones** de la página de detalles de la aplicación.

* **Fecha de activación de licencia**: fecha en la que se activó la licencia.
* **Licencias**: número de licencias que ha comprado.

  :::image type="content" source="media/manage-apps-plans-and-subscription.png" alt-text="Captura de pantalla de la pestaña Planes y precios en la página de detalles de la aplicación en el Centro de administración de Teams." lightbox="media/purchase-third-party-apps-details-page.png":::

Seleccione **Administrar suscripciones** para ver y administrar las licencias que compró.

Los administradores globales pueden ver las suscripciones compradas por cualquier persona de la organización, pero solo pueden agregar más licencias, quitar licencias y cancelar suscripciones para las compras realizadas por cualquier persona de su cuenta de facturación. Los administradores de servicios de Teams pueden realizar las mismas acciones para las compras realizadas por ellos mismos.

> [!NOTE]
> Si un Administrador global quiere administrar una suscripción comprada por otro Administrador global, debe estar en la misma cuenta de facturación. Puede conceder a otro Administrador global acceso a una suscripción que haya adquirido seleccionando la aplicación en el [Centro de administración de Microsoft 365](https://admin.microsoft.com). En el centro de administración, acceda a **Ver perfil de facturación** > **Seleccione la cuenta de facturación** > **Asignar roles** > **Agregar otros administradores globales**.

> [!IMPORTANT]
> Al habilitar la compra de aplicaciones, también se activa la compra desde la aplicación. Los usuarios pueden ver ofertas de compra desde la aplicación que el desarrollador de la aplicación controla para su aplicación. Para evitar que los usuarios compren una aplicación, debe bloquearla.

### <a name="invoice-billing"></a>Facturación con envío de factura

* La facturación con envío de facturas está disponible como opción de pago para algunas transacciones.
* Se requiere una revisión de crédito la primera vez que use la facturación de facturas, lo que puede tardar de 24 a 48 horas en aprobarse. La facturación con envío de facturas no estará disponible hasta que se complete la comprobación de crédito. Puede realizar el pedido con una tarjeta de crédito o volver a intentarlo más tarde una vez aprobada la revisión de crédito.
* La facturación con envío de facturas solo está disponible para Administradores globales o administradores con permisos de administrador de servicios de Teams y administrador de facturación.
* La facturación con envío de facturas no está disponible al comprar un plan con una prueba gratuita de 30 días.

## <a name="manage-subscriptions-in-teams-admin-center"></a>Administrar suscripciones en el Centro de administración de Teams

En el Centro de administradores de Teams, puede administrar las suscripciones y licencias de aplicaciones que compró. Puede ver la lista de suscripciones de aplicaciones y sus detalles y realizar las siguientes acciones:

* Cambiar un plan
* Comprar o quitar licencia
* Actualizar un método de pago
* Cancelar una suscripción
* Ver la factura

  :::image type="content" source="media/manage-existing-subscriptions-actions.png" alt-text="Captura de pantalla de los detalles de suscripción de una aplicación." lightbox="media/manage-existing-subscriptions-all.png":::

Para administrar las suscripciones, sigue estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** > [**de Teams Administrar aplicaciones**](https://admin.teams.microsoft.com/policies/manage-apps) .

1. Selecciona la pestaña **Suscripciones** para ver las suscripciones que has comprado.

   :::image type="content" source="media/subscription-options-in-manage-apps.png" alt-text="Captura de pantalla de la opción de suscripción de una aplicación en la página administrar aplicaciones." lightbox="media/manage-app-subscriptions-manage-apps.png":::

> [!NOTE]
> En el Centro de administración de Teams, puede administrar las suscripciones de aplicación adquiridas por usted u otros administradores que forman parte de la misma cuenta de facturación. Para ver todas las suscripciones de aplicación compradas para el mismo inquilino por otros administradores o adquiridas con cuentas de facturación diferentes, visite la [Centro de administración de Microsoft 365](https://admin.microsoft.com/adminportal/home#/homepage).

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Enumerar y vender una oferta de SaaS para una aplicación de Teams

Los desarrolladores pueden crear ofertas de SaaS asociadas a sus aplicaciones de Teams. Estas ofertas se publican a través del [Centro de partners](https://partner.microsoft.com) y están disponibles para que las organizaciones las compren a través de [AppSource](https://appsource.microsoft.com/) y el Centro de administración de Microsoft Teams.

Para obtener más información para desarrolladores de aplicaciones de terceros, consulte [Crear una oferta de SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer).

## <a name="related-articles"></a>Artículos relacionados

* [Administrar aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
* [Crear una oferta de SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Roles integrados de Azure Active Directory](/azure/active-directory/roles/permissions-reference)
* [Roles de administración de Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles)
