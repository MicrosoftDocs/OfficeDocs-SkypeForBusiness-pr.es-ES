---
title: Obtener números de teléfono de Skype Empresarial para los usuarios
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Obtenga información sobre cómo obtener números nuevos, transferirlos o transferirlos a Teams y cómo mostrar los cambios a los usuarios.
ms.openlocfilehash: b0ed990cd16a7e4878c2819a95fac29f46a9d770
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156548"
---
# <a name="getting-phone-numbers-for-your-users"></a>Obtener números de teléfono de Skype Empresarial para los usuarios

[] Para poder configurar los usuarios de su organización para que puedan recibir y realizar llamadas telefónicas, debe usar el Centro de administración de Skype Empresarial para obtener los números de teléfono.
  
Hay tres maneras de obtener números de usuario:

- **Use el Centro de administración de Microsoft Teams.** En algunos países y regiones, puede obtener números para los usuarios mediante el Centro de administración de Microsoft Teams. Vea [Obtener números de teléfono nuevos para los usuarios](#get-new-phone-numbers-for-your-users).

- **Portar los números existentes.** Puede transferir números existentes desde su proveedor de servicios u operador de telefonía actual. Consulte [Transferir números de teléfono a Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o [Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization) para obtener más información que le ayude a hacer esto.  
  
- **Usar un formulario de solicitud para números nuevos.** A veces (en función de su país o región) no podrá obtener los nuevos números de teléfono con el Centro de Administración de Microsoft Teams o necesitará números de teléfono o códigos de área específicos. Para obtener más información, vea [Administrar los números de teléfono de su organización](/microsoftteams/manage-phone-numbers-for-your-organization).
  
> [!NOTE]
> Si necesita ayuda para configurar los números de teléfono de su organización, póngase [en contacto con el servicio de soporte técnico de productos Administración ayuda](/microsoft-365/admin/contact-support-for-business-products).

## <a name="get-new-phone-numbers-for-your-users"></a>Get new phone numbers for your users

**Usar el Centro de administración de Microsoft Teams**

Debe ser administrador de servicio de Teams para poder realizar estos cambios. Consulte [Usar los roles de administrador de Teams para administrar Teams](./using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.

1. Vaya al Centro de Administración de Microsoft Teams.

2. En el panel de navegación izquierdo, vaya a **Números de teléfono** **de voz** >  y, después, seleccione **Agregar**.

3. Escriba un nombre para el pedido y agregue una descripción.

4. En la página Ubicación y cantidad, haga lo siguiente:
    1. En **País o región**, selecciona un país o región.
    2. En **Tipo de número**, seleccione **Usuario (suscriptor).**.
    3. En **Ubicación**, selecciona una ubicación. Si necesitas crear una nueva ubicación, selecciona **Agregar una ubicación**.
    4. En **Código de área**, selecciona un código de área.
    5. En **Cantidad**, escriba el número de números que desea para su organización y, a continuación, seleccione **Siguiente** para seleccionar los números.

5. Seleccione los números que desee. Tienes 10 minutos para seleccionar tus números de teléfono y realizar el pedido. Si tarda más de 10 minutos, los números de teléfono se devolverán al grupo de números.

6. Cuando estés listo para realizar el pedido, selecciona **Realizar pedido**.

    > [!IMPORTANT]
    > El número de números de teléfono de los usuarios (suscriptores) es igual al número total de licencias de **Plan de llamadas nacionales** y **Plan de llamadas internacionales** que ha asignado multiplicado por 1,1, más 10 números de teléfono adicionales. Por ejemplo, si tiene 50 usuarios en total con un plan de llamadas nacionales o un plan de llamadas internacionales, puede adquirir **65** números de teléfono **(50 x 1,1 + 10)**. Tenga en cuenta que si tiene un plan de llamadas de pago por uso, solo puede adquirir 1 número de teléfono por licencia asignada.
    >
    > Para obtener más información, consulte [¿Cuántos números de teléfono puede obtener?](./how-many-phone-numbers-can-you-get.md). Si necesita obtener más números de teléfono, [póngase en contacto con el contacto de soporte técnico para productos de la empresa Administración ayuda](/microsoft-365/admin/contact-support-for-business-products).
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Port or transfer phone numbers from your service provider or phone carrier
  
- Si necesita 999 números de teléfono o menos para los usuarios, use el asistente para portabilidad en el Centro de Administración de Microsoft Teams. Siga los pasos de [Transferir números de teléfono a Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md). Si su país o región no aparece en el asistente para portabilidad, puede [enviar manualmente una solicitud de portabilidad](phone-number-calling-plans/manually-submit-port-order.md) o ver [Administrar los números de teléfono de su organización para](/microsoftteams/manage-phone-numbers-for-your-organization) descargar la Carta de autorización (LOA) correcta.

- Si necesita realizar la portabilidad de más de 999 números de teléfono, puede [enviar manualmente una solicitud de portabilidad](phone-number-calling-plans/manually-submit-port-order.md) o ver [Administrar los números de teléfono de su organización para](/microsoftteams/manage-phone-numbers-for-your-organization) descargar la Carta de autorización (LOA) correcta y, a continuación, enviarla al [servicio de asistencia de TNS](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) para que se transfieran todos los números.

## <a name="view-the-phone-numbers-for-your-organization"></a>Ver los números de teléfono de la organización

**Usar el Centro de administración de Microsoft Teams**

En el panel de navegación izquierdo del centro de administración, vaya a **Números de teléfono** de **voz** >  para ver los números de su organización, incluida la ubicación, el tipo de número y la información de estado.
  
## <a name="assign-phone-numbers-to-users"></a>Asignar números de teléfono a los usuarios

Después de obtener los números de teléfono, tendrá que asignar un número a cada uno de los usuarios. Vea [Asignar, cambiar o quitar un número de teléfono a un usuario](./assign-change-or-remove-a-phone-number-for-a-user.md) para obtener más información.

> [!NOTE]
> Si necesita obtener más números de teléfono, [póngase en contacto con el contacto de soporte técnico para productos de la empresa Administración ayuda](/microsoft-365/admin/contact-support-for-business-products).

## <a name="related-articles"></a>Artículos relacionados

[Preguntas comunes sobre la transferencia de números de teléfono](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)

[Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
