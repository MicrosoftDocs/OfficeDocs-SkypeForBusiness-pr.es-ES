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
description: Obtenga información sobre cómo comprar aplicaciones de terceros para Teams en el centro de administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 52cab02898a2fd187c60d2348a42c3ce97de2a3b
ms.sourcegitcommit: 836926a4914eb33fc3e0d8d6c84cee886cb1a5a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65137091"
---
# <a name="purchase-third-party-apps-for-teams"></a>Comprar aplicaciones de terceros para Teams

Teams aplicaciones son gratuitas de instalar y algunas pueden requerir la compra de suscripciones de servicio para experimentar la funcionalidad y el ámbito completos de la aplicación. Estas suscripciones de servicio se denominan ofertas de Software como servicio (SaaS), que están disponibles para su compra a través [de AppSource](https://appsource.microsoft.com/) y ahora a través del centro de administración de Microsoft Teams.

La página [Administrar aplicaciones](manage-apps.md) del centro de administración de Microsoft Teams es donde puede ver y administrar todas las aplicaciones Teams de su organización. Por ejemplo, puede ver el estado y las propiedades de nivel de organización de las aplicaciones, cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización, bloquear o permitir aplicaciones en el nivel de organización y administrar la configuración de aplicaciones para toda la organización.

Aquí, también puede comprar licencias para los servicios ofrecidos por aplicaciones de terceros para los usuarios de su organización. La columna **Licencias** de la tabla indica si una aplicación ofrece una suscripción SaaS para comprar.

![Captura de pantalla de la página de administración de aplicaciones de licencias de compra.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Comprar aplicaciones en el centro de administración de Teams

> [!IMPORTANT]
> Al habilitar la compra de aplicaciones, también se activará la compra desde la aplicación. Es posible que los usuarios vean ofertas de compra desde la aplicación controladas por el ISV para su aplicación. Si quieres impedir que los usuarios compren una aplicación, tienes que bloquear la aplicación. Para obtener más información sobre cómo bloquear una aplicación, consulta [Administrar directivas de aplicación](app-policies.md) o [aprende a bloquear una aplicación en el nivel de organización](manage-apps.md#allow-and-block-apps).

1. En el panel izquierdo del centro de administración de Microsoft Teams, vaya a **Teams** **aplicacionesAdministrar** >  aplicaciones. Para acceder a la página, debe ser administrador global o administrador de servicio de Teams.
1. Busca la aplicación que quieras. Para identificar las aplicaciones que tienen una suscripción SaaS de pago, busque en la columna **Licencias** . Cada aplicación tendrá uno de los siguientes valores:
    - **Compra**: la aplicación ofrece una suscripción SaaS y está disponible para comprar.  
    - **Comprado**: la aplicación ofrece una suscripción a SaaS y ha comprado licencias para ella.
    - **- -**: La aplicación no ofrece una suscripción SaaS.
1. Cuando encuentres la aplicación, selecciona **Comprar** para ir a la pestaña **Planes y precios** de la página de detalles de la aplicación. Revise la información de planes y precios de la oferta de SaaS para la aplicación. Si necesita más información, seleccione **Más información** para ir a la página de la aplicación en [AppSource](https://appsource.microsoft.com/).

   > [!NOTE]
   > Los planes privados también pueden aparecer para su compra, que incluyen precios especiales que su organización ha negociado previamente con un ISV. Estos planes tendrán la etiqueta **Plan privado** bajo el nombre del plan.

1. Para suscribirte a una aplicación, elige el plan que quieras y selecciona **Comprar**. El flujo de desprotección se abre directamente en el Teams centro de administración.

1. Seleccione el número de licencias de usuario que desea comprar.
1. Comprueba que la cuenta de facturación y la dirección del solicitante son correctas. Si aún no tiene una, agregue una nueva seleccionando **Agregar**. Para obtener más información sobre las cuentas de facturación, consulta [Comprender las cuentas de facturación](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Debes ser administrador global para agregar una nueva cuenta de facturación.

1. Comprueba que esté seleccionado el perfil de facturación correcto. Si aún no tiene una, agregue una nueva seleccionando **Agregar nuevo**. Tiene la opción de pagar con tarjeta de crédito, tarjeta de débito o con [facturación](#invoice-billing). El perfil de facturación también te permite agregar un número de pedido de compra para identificar tu pedido más adelante. Para obtener más información sobre los perfiles de facturación, consulta [Comprender los perfiles de facturación](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).
1. Selecciona **Realizar pedido**.
1. Seleccione **Configurar** para activar la suscripción en el sitio web del editor. Si no configura la suscripción después de la compra, puede hacerlo más adelante seleccionando **Administrar licencias**.

Después de comprar la oferta de SaaS asociada a la aplicación Teams, puede ver los siguientes detalles de compra en la pestaña **Planes y precios** de la página de detalles de la aplicación.

- **Fecha de activación de la licencia**: fecha en la que se activó la licencia. Si su cuenta aún no está configurada, se muestra como **Suscripción pendiente de activación**.
- **Licencias**: número de licencias que ha comprado.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Captura de pantalla de la pestaña Planes y precios de la página de detalles de la aplicación.":::

Seleccione **Administrar licencias** para ir a la Centro de administración de Microsoft 365 para ver y administrar las licencias que compró.

Los administradores globales pueden agregar más licencias, quitar licencias y cancelar las suscripciones para las compras realizadas por cualquier persona de la organización. Teams administradores de servicios pueden realizar las mismas acciones para las compras realizadas por ellos mismos. Sin embargo, si un administrador de servicio de Teams también tiene el rol de administrador de facturación, puede administrar las compras realizadas por cualquier persona de la organización.

> [!NOTE]
> Si un administrador global quiere administrar una suscripción comprada por otro administrador global, debe estar en la misma cuenta de facturación. Puede conceder a otro administrador global acceso a una suscripción que compró seleccionando la aplicación en el Centro de administración de Microsoft 365. Desde allí, vaya a **Ver perfil** >  de **facturaciónSeleccionar** roles  >  de cuenta  >  de **facturaciónAgregar otros administradores globales**.

### <a name="invoice-billing"></a>Facturación

- La facturación está disponible como opción de pago para algunas transacciones.
- La primera vez que use la facturación de facturación, se requiere una revisión de crédito, que puede tardar de 24 a 48 horas en aprobarse. La facturación no estará disponible hasta que se complete la comprobación de crédito. Puedes realizar el pedido con una tarjeta de crédito o volver a intentarlo más tarde después de que se apruebe la revisión de crédito.
- La facturación solo está disponible para los administradores globales o un administrador con permisos de administrador de Teams y de administrador de facturación.
- La facturación no está disponible al comprar un plan con una prueba gratuita de 30 días.

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>¿Tienes una oferta saas para una aplicación de Teams que quieras enumerar y vender en el centro de administración de Microsoft Teams y AppSource?

Los desarrolladores pueden crear ofertas SaaS asociadas a sus aplicaciones de Teams. Estas ofertas se publican a través del [Centro de partners](https://partner.microsoft.com) y están disponibles para que las organizaciones las compren a través [de AppSource](https://appsource.microsoft.com/) y el centro de administración de Microsoft Teams.

Los desarrolladores de aplicaciones de terceros pueden ir a [la oferta Crear un SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer) para obtener más información.

## <a name="related-topics"></a>Temas relacionados

- [Administrar las aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md)
- [Crear una oferta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
- [Azure AD roles integrados](/azure/active-directory/roles/permissions-reference)
- [roles de administrador Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles)
