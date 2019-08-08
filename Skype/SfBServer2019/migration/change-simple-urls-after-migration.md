---
title: Cambiar las direcciones URL simples tras la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype empresarial Server admite URL simples.
ms.openlocfilehash: 806003a2639d3861c066248657521ceb58a4e986
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239496"
---
# <a name="change-simple-urls-after-migration"></a>Cambiar las direcciones URL simples tras la migración

Skype empresarial Server admite tres direcciones URL simples:
  
- **Reunirse** se usa como la dirección URL base para todas las conferencias del sitio o la organización. Con la dirección URL simple, los vínculos a las reuniones de unirse son fáciles de comprender y se pueden comunicar y distribuir fácilmente. 
    
- El acceso **telefónico** permite el acceso a la Página Web de configuración de conferencias de acceso telefónico local. La dirección URL de acceso telefónico simple está incluida en todas las invitaciones a reuniones para que los usuarios que deseen llamar a la reunión puedan tener acceso a la información del número de teléfono y del PIN necesarios. 
    
- El **Administrador** permite acceder rápidamente al panel de control de Skype empresarial Server. La dirección URL simple de administración es interna de su organización. 
    
Después de migrar a Skype empresarial Server, debe tener en cuenta cómo afecta el cambio a los registros DNS y certificados para las direcciones URL simples. Si el director de Skype empresarial heredado sigue en uso en la topología, no es necesario realizar cambios en las direcciones URL simples. Si el director de Skype empresarial Server se quita de la topología después de la migración, los registros DNS de direcciones URL simples deben actualizarse para que apunten a uno de los grupos de servidores de Skype empresarial. Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar enable-CsComputer en cada director y en el servidor front-end para registrar el cambio.

## <a name="to-update-the-meet-simple-url"></a>Para actualizar la dirección URL simple de reunirse

1. En el generador de topología, haga clic con el botón derecho en el nodo superior **de Skype empresarial Server**y, a continuación, haga clic en **Editar propiedades**.
    
2. Seleccione **URL simples** en el panel izquierdo y, a continuación, debajo de **direcciones URL de reunión:** seleccione la dirección URL de la reunión y haga clic en **Editar URL**.
    
3. Actualice la dirección URL con el valor que quiera y haga clic en **Aceptar** para guardar la dirección URL modificada. 
    
## <a name="to-update-the-admin-simple-url"></a>Para actualizar la dirección URL simple de administración

1. En el generador de topología, haga clic con el botón derecho en el nodo superior **de Skype empresarial Server**y, a continuación, haga clic en **Editar propiedades**.
    
2. Seleccione **URL simples** en el panel izquierdo y, a continuación, en **dirección URL de acceso administrativo** , escriba la dirección URL simple que desee para el acceso administrativo al panel de control de Skype empresarial Server y, a continuación, haga clic en **Aceptar**.
    
   > [!TIP]
   > Recomendamos usar la dirección URL más simple posible como dirección URL sencilla de administración. La opción más sencilla es https://admin. <em> \<dominio\></em>. 
  
## <a name="see-also"></a>Vea también

[Requisitos de DNS para las direcciones URL simples en Skype empresarial Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
