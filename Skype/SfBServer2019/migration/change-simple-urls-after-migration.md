---
title: Direcciones URL sencillas de cambio después de la migración
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server es compatible con las direcciones URL sencillas.
ms.openlocfilehash: 71935aab09de1598b355d2a7b27dfa02fd169216
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374993"
---
# <a name="change-simple-urls-after-migration"></a>Direcciones URL sencillas de cambio después de la migración

Skype para Business Server admite tres direcciones URL sencillas:
  
- **Cumplir** se usa como la dirección URL base para todas las conferencias en el sitio o la organización. Con la URL simples de reunión, vínculos a unirse a reuniones son fáciles de comprender y fácil de comunicarse y distribuir. 
    
- **Dial-in** habilita el acceso a la página Web de configuración de conferencia de acceso telefónico. La dirección URL sencilla de marcado se incluye en todas las invitaciones a reuniones para que los usuarios que deseen conectarse a la reunión pueden tener acceso a la información de PIN y número de teléfono es necesario. 
    
- **Admin** permite el acceso rápido a la Skype para el Panel de Control de servidor empresarial. La dirección URL de administración simple es interna a la organización. 
    
Después de migrar a Skype para Business Server, debe tener en cuenta cómo afecta el cambio a sus registros DNS y los certificados para las direcciones URL sencillas. Si el Director del servidor para profesionales de Skype heredado permanece en uso en la topología, se requiere ningún cambio en las direcciones URL sencillas. Si el Director del servidor para profesionales de Skype se ha quitado de la topología de después de la migración, se deben actualizar los registros DNS de la dirección URL simples para que apunte a uno de los Skype para grupos de servidores de negocio. Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar Enable-CsComputer en cada Director y el servidor Front-End para registrar el cambio.

## <a name="to-update-the-meet-simple-url"></a>Para actualizar la URL simples de reunión

1. En el generador, haga clic en el nodo superior **Skype para Business Server**y, a continuación, haga clic en **Editar propiedades**.
    
2. Seleccione **Direcciones URL simples** en el panel izquierdo, a continuación, debajo de **direcciones URL de reunión:** seleccione la dirección URL de la reunión y, a continuación, haga clic en **Editar dirección URL**.
    
3. Actualice la dirección URL con el valor que quiera y haga clic en **Aceptar** para guardar la dirección URL modificada. 
    
## <a name="to-update-the-admin-simple-url"></a>Para actualizar la dirección URL de administración simple

1. En el generador, haga clic en el nodo superior **Skype para Business Server**y, a continuación, haga clic en **Editar propiedades**.
    
2. Seleccione **Direcciones URL simples** en el panel izquierdo, a continuación, debajo de cuadro de **dirección URL de acceso administrativo** , escriba la dirección URL sencilla que desee para el acceso administrativo a Skype para el Panel de Control de servidor empresarial y, a continuación, haga clic en **Aceptar**.
    
   > [!TIP]
   > Recomendamos usar la dirección URL más simple posible como dirección URL sencilla de administración. La opción más sencilla es https://admin. <em> \<dominio\></em>. 
  
## <a name="see-also"></a>Vea también

[Requisitos de DNS para direcciones URL simples en Skype para Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
