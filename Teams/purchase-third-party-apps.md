---
title: Comprar aplicaciones de terceros para Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: Obtenga información sobre cómo comprar aplicaciones de terceros en la tienda de Teams con una tarjeta de crédito, una tarjeta de débito o mediante facturación.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 8627d94fc384064b484019ecc17b2e4701e945e8
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880244"
---
# <a name="purchase-third-party-apps-for-teams"></a>Comprar aplicaciones de terceros para Teams

Las aplicaciones de Teams son gratuitas de instalar y algunas pueden requerir la compra de suscripciones de servicio para experimentar la funcionalidad y el ámbito completos de la aplicación. Estas suscripciones de servicio se denominan ofertas de Software como servicio (SaaS), que están disponibles para su compra a través [de AppSource](https://appsource.microsoft.com/) y ahora a través del [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com).

La página [Administrar aplicaciones](manage-apps.md) del Centro de administración de Microsoft Teams es donde puede ver y administrar todas las aplicaciones de Teams para su organización. Por ejemplo, puede ver el estado y las propiedades de nivel de organización de las aplicaciones, cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización, bloquear o permitir aplicaciones en el nivel de organización y administrar la configuración de aplicaciones para toda la organización.

Aquí, también puede comprar licencias para los servicios ofrecidos por aplicaciones de terceros para los usuarios de su organización. La columna **Licencias** de la tabla indica si una aplicación ofrece una suscripción SaaS para comprar.

![Captura de pantalla de la página de administración de aplicaciones de licencias de compra.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Comprar aplicaciones en el Centro de administración de Teams

> [!IMPORTANT]
> Al habilitar la compra de aplicaciones, también se activará la compra desde la aplicación. Es posible que los usuarios vean ofertas de compra desde la aplicación controladas por el ISV para su aplicación. Si quieres impedir que los usuarios compren una aplicación, tienes que bloquear la aplicación. Para obtener más información sobre cómo bloquear una aplicación, consulta [Administrar directivas de aplicación](app-policies.md) o [aprende a bloquear una aplicación en el nivel de organización](manage-apps.md#allow-and-block-apps).

1. En el panel izquierdo del Centro de administración de Microsoft Teams, vaya a Aplicaciones  > **de Teams****[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**. Debe ser administrador global o administrador de servicios de Teams para poder acceder a la página.

1. Busca la aplicación que quieras por su nombre. Para identificar las aplicaciones que tienen una suscripción SaaS de pago, busque en la columna **Licencias** . Cada aplicación tiene uno de los siguientes valores:
    * **Compra**: la aplicación ofrece una suscripción SaaS y está disponible para comprar.  
    * **Comprado**: la aplicación ofrece una suscripción a SaaS y ha comprado licencias para ella.
    * **- -**: La aplicación no ofrece una suscripción SaaS.

1. Cuando encuentres la aplicación, selecciona **Comprar** para ir a la pestaña **Planes y precios** de la página de detalles de la aplicación. Revise la información de planes y precios de la oferta de SaaS para la aplicación. Si necesita más información, seleccione **Más información** para ir a la página de la aplicación en [AppSource](https://appsource.microsoft.com/).

   > [!NOTE]
   > Los planes privados también pueden aparecer para su compra, que incluyen precios especiales que su organización ha negociado previamente con un ISV. Estos planes tendrán la etiqueta **Plan privado** bajo el nombre del plan.

1. Para suscribirte a una aplicación, elige el plan que quieras y selecciona **Comprar**. El flujo de finalización de la compra se abre directamente en el Centro de administración de Teams.

1. Seleccione el número de licencias de usuario que desea comprar.

1. Comprueba que la cuenta de facturación y la dirección del solicitante sean correctas. Si aún no tiene una, seleccione **Agregar**. Para obtener más información sobre las cuentas de facturación, consulta [Comprender las cuentas de facturación](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Solo un Administración global puede agregar una nueva cuenta de facturación.

1. Comprueba que esté seleccionado el perfil de facturación correcto. Si aún no tiene una, seleccione **Agregar nuevo**. Tiene la opción de pagar con tarjeta de crédito, tarjeta de débito o con [facturación](#invoice-billing). El perfil de facturación también te permite agregar un número de pedido de compra para identificar tu pedido más adelante. Para obtener más información sobre los perfiles de facturación, consulta [Comprender los perfiles de facturación](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).

1. Selecciona **Realizar pedido**.

1. Seleccione **Configurar** para activar la suscripción en el sitio web del editor. Si no configura la suscripción después de la compra, puede hacerlo más adelante seleccionando **Administrar licencias**.

Después de comprar la oferta de SaaS asociada a la aplicación Teams, puede ver los siguientes detalles de compra en la pestaña **Planes y precios** de la página de detalles de la aplicación.

* **Fecha de activación de la licencia**: fecha en la que se activó la licencia. Si su cuenta aún no está configurada, se muestra como **Suscripción pendiente de activación**.
* **Licencias**: número de licencias que compró.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Captura de pantalla de la pestaña Planes y precios en la página de detalles de la aplicación en el Centro de administración de Teams.":::

Para ver y administrar las licencias que compró, seleccione **Administrar licencias** para acceder a la Centro de administración de Microsoft 365.

Los administradores globales pueden agregar más licencias, quitar licencias y cancelar las suscripciones para las compras realizadas por cualquier persona de la organización. Los administradores de servicios de Teams pueden realizar las mismas acciones para las compras realizadas por ellos mismos. Sin embargo, si un administrador de servicios de Teams también tiene el rol de administrador de facturación, puede administrar las compras realizadas por cualquier persona de la organización.

> [!NOTE]
> Si un Administración global quiere administrar una suscripción adquirida por otro Administración global, debe estar en la misma cuenta de facturación. Puede conceder acceso a otra Administración global a una suscripción que compró seleccionando la aplicación en el [Centro de administración de Microsoft 365](https://admin.microsoft.com). Desde allí, vaya a **Ver perfil** >  de **facturación Seleccione la cuenta** >  de facturación **Asignar roles** > **Agregar otros administradores globales**.

### <a name="invoice-billing"></a>Facturación

* La facturación está disponible como opción de pago para algunas transacciones.
* La primera vez que use la facturación de facturación, se requiere una revisión de crédito, que puede tardar de 24 a 48 horas en aprobarse. La facturación no estará disponible hasta que se complete la comprobación de crédito. Puedes realizar el pedido con una tarjeta de crédito o volver a intentarlo más tarde después de que se apruebe la revisión de crédito.
* La facturación de facturas solo está disponible para los administradores globales o para un administrador con permisos de administrador de servicios de Teams y de administrador de facturación.
* La facturación no está disponible al comprar un plan con una prueba gratuita de 30 días.

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Enumerar y vender una oferta de SaaS para una aplicación de Teams

Los desarrolladores pueden crear ofertas SaaS asociadas a sus aplicaciones de Teams. Estas ofertas se publican a través del [Centro de partners](https://partner.microsoft.com) y están disponibles para que las organizaciones las compren a través [de AppSource](https://appsource.microsoft.com/) y del Centro de administración de Microsoft Teams.

Para obtener más información para desarrolladores de aplicaciones de terceros, consulta [Crear una oferta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer).

## <a name="related-articles"></a>Artículos relacionados

* [Administrar las aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
* [Crear una oferta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Roles integrados de Azure Active Directory](/azure/active-directory/roles/permissions-reference)
* [Roles de administrador de Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles)
