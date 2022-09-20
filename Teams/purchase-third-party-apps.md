---
title: Comprar aplicaciones de terceros para Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: Obtenga información sobre cómo comprar aplicaciones de terceros en la tienda de Teams con una tarjeta de crédito, una tarjeta de débito o mediante facturación.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 5c3137815ea8e4d02ac987ec0a2b0e50c32c3fcb
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837410"
---
# <a name="purchase-third-party-apps-for-teams"></a>Comprar aplicaciones de terceros para Microsoft Teams

La instalación de las aplicaciones de Teams es gratuita y algunas pueden requerir suscripciones de servicio de compra para experimentar la funcionalidad y el ámbito completos de la aplicación. Estas suscripciones de servicio se denominan ofertas de software como servicio (SaaS), que están disponibles para su compra a través de [AppSource](https://appsource.microsoft.com/) y ahora a través del [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com).

La página [Administrar aplicaciones](manage-apps.md) del Centro de administración de Microsoft Teams es donde puede ver y administrar todas las aplicaciones de Teams para su organización. Por ejemplo, puede ver el estado y las propiedades de las aplicaciones a nivel de organización, cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización, bloquear o permitir aplicaciones en el nivel de organización y administrar la configuración de aplicaciones de toda la organización.

Aquí, también puede comprar licencias de servicios ofrecidos por aplicaciones de terceros para los usuarios de su organización. La columna **Licencias** de la tabla indica si una aplicación ofrece una suscripción SaaS para su compra. Los usuarios finales pueden comprar aplicaciones con tarjeta de crédito, tarjeta de débito o con facturación.

![Captura de pantalla de la página de administración de licencias de compra de aplicaciones.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Comprar aplicaciones en el centro de administración de Teams

Para comprar aplicaciones en el centro de administración de Teams, siga estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** > **[de Teams Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**. Debe ser Administrador global o Administrador de servicio de Teams para acceder a la página.

1. Busque la aplicación que quiera por su nombre. Para identificar las aplicaciones que tienen una suscripción SaaS de pago, consulte la columna **Licencias**. Cada aplicación tiene uno de los siguientes valores:
    * **Comprar**: la aplicación ofrece una suscripción SaaS y está disponible para comprar.  
    * **Comprado**: la aplicación ofrece una suscripción SaaS y has comprado licencias para ella.
    * **- -**: La aplicación no ofrece una suscripción SaaS.

1. Cuando encuentre la aplicación, seleccione **Comprar** para ir a la pestaña **Planes y precios** de la página de detalles de la aplicación. Revise los planes y la información de precios de la oferta de SaaS para la aplicación. Si necesita más información, seleccione **Más información** para ir a la página de la aplicación en [AppSource](https://appsource.microsoft.com/).

   > [!NOTE]
   > También se puede incluir la compra de planes privados, que incluyen precios especiales que la organización puede negociar por separado con algún desarrollador de aplicaciones. Estos planes tendrán la etiqueta **Plan privado** bajo el nombre del plan.

1. Para suscribirse a una aplicación, elija el plan que desee y seleccione **Comprar**. El flujo de finalización de la compra se abre directamente en el centro de administración de Teams.

1. Seleccione el número de licencias de usuario que desea comprar.

1. Compruebe que la cuenta de facturación y la dirección de venta son correctas. Si aún no tiene una, seleccione **Agregar**. Para obtener más información sobre las cuentas de facturación, consulte [Descripción de las cuentas de facturación](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Solo un Administrador global puede agregar una nueva cuenta de facturación.

1. Compruebe que está seleccionado el perfil de facturación correcto. Si aún no tiene uno, seleccione **Agregar nuevo**. Tiene la opción de pagar con una tarjeta de crédito, una tarjeta de débito o mediante [facturación](#invoice-billing). El perfil de facturación también le permite agregar un número de pedido de compra para identificar el pedido más adelante. Para obtener más información sobre los perfiles de facturación, consulte [Descripción de los perfiles de facturación](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).

1. Seleccione **Realizar pedido**.

1. Seleccione **Configurar** para activar la suscripción en el sitio web del desarrollador de la aplicación. Si no configura la suscripción después de la compra, puede hacerlo más adelante seleccionando **Administrar licencias**.

Después de comprar la oferta SaaS asociada a la aplicación Teams, puede ver los siguientes detalles de compra en la pestaña **Planes y precios** de la página de detalles de la aplicación.

* **Fecha de activación de licencia**: fecha en la que se activó la licencia. Si su cuenta aún no está configurada, se muestra como **Suscripción pendiente de activación**.
* **Licencias**: número de licencias que compró.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Captura de pantalla de la pestaña Planes y precios en la página de detalles de la aplicación en el Centro de administración de Teams.":::

Para ver y administrar las licencias compradas, seleccione **Administrar licencias** para acceder al Centro de administración de Microsoft 365.

Los Administradores globales pueden agregar más licencias, quitar licencias y cancelar suscripciones para las compras realizadas por cualquier usuario de la organización. Los administradores de servicios de Teams pueden realizar las mismas acciones para las compras realizadas por ellos mismos. Sin embargo, si un administrador de servicios de Teams también tiene el rol de administrador de facturación, puede administrar las compras realizadas por cualquier usuario de la organización.

> [!NOTE]
> Si un Administrador global quiere administrar una suscripción comprada por otro Administrador global, debe estar en la misma cuenta de facturación. Puede conceder a otro Administrador global acceso a una suscripción que haya adquirido seleccionando la aplicación en el [Centro de administración de Microsoft 365](https://admin.microsoft.com). En el centro de administración, acceda a **Ver perfil de facturación** > **Seleccione la cuenta de facturación** > **Asignar roles** > **Agregar otros administradores globales**.

> [!IMPORTANT]
> Al habilitar la compra de aplicaciones, también se activa la compra desde la aplicación. Los usuarios pueden ver ofertas de compra desde la aplicación que el desarrollador de la aplicación controla para su aplicación. Para evitar que los usuarios compren una aplicación, debe bloquearla.

### <a name="invoice-billing"></a>Facturación con envío de factura

* La facturación con envío de facturas está disponible como opción de pago para algunas transacciones.
* Se requiere una revisión de crédito la primera vez que use la facturación de facturas, lo que puede tardar de 24 a 48 horas en aprobarse. La facturación con envío de facturas no estará disponible hasta que se complete la comprobación de crédito. Puede realizar el pedido con una tarjeta de crédito o volver a intentarlo más tarde una vez aprobada la revisión de crédito.
* La facturación con envío de facturas solo está disponible para Administradores globales o administradores con permisos de administrador de servicios de Teams y administrador de facturación.
* La facturación con envío de facturas no está disponible al comprar un plan con una prueba gratuita de 30 días.

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Enumerar y vender una oferta de SaaS para una aplicación de Teams

Los desarrolladores pueden crear ofertas de SaaS asociadas a sus aplicaciones de Teams. Estas ofertas se publican a través del [Centro de partners](https://partner.microsoft.com) y están disponibles para que las organizaciones las compren a través de [AppSource](https://appsource.microsoft.com/) y el Centro de administración de Microsoft Teams.

Para obtener más información para desarrolladores de aplicaciones de terceros, consulte [Crear una oferta de SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer).

## <a name="related-articles"></a>Artículos relacionados

* [Administrar aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
* [Crear una oferta de SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Roles integrados de Azure Active Directory](/azure/active-directory/roles/permissions-reference)
* [Roles de administración de Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles)
