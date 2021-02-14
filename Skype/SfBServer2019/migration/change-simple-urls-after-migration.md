---
title: Cambiar las direcciones URL simples tras la migración
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype Empresarial Server admite direcciones URL sencillas.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753910"
---
# <a name="change-simple-urls-after-migration"></a>Cambiar las direcciones URL simples tras la migración

Skype Empresarial Server admite tres direcciones URL sencillas:
  
- **Reunión** sirve como dirección URL base de todas las conferencias del sitio o la organización. Con una dirección URL simple de reunión, los vínculos para unirse a reuniones son fáciles de identificar, comunicar y distribuir. 
    
- **Acceso telefónico** permite el acceso a la página web Configuración de conferencia de acceso telefónico local. La dirección URL simple de acceso telefónico aparece en todas las invitaciones a reuniones para que los usuarios que marquen para unirse a la reunión puedan tener acceso al número de teléfono e información de PIN necesarios. 
    
- **La** administración permite el acceso rápido al Panel de control de Skype Empresarial Server. La dirección URL simple de administración es de uso interno para la organización. 
    
Después de migrar a Skype Empresarial Server, debe conocer cómo afecta el cambio a los certificados y registros DNS para direcciones URL sencillas. Si el director heredado de Skype Empresarial Server permanece en uso en la topología, no es necesario realizar cambios en las direcciones URL sencillas. Si el director de Skype Empresarial Server se quita de la topología después de la migración, los registros DNS de la dirección URL sencilla deben actualizarse para que apunten a uno de los grupos de servidores de Skype Empresarial Server. Sin embargo, cuando modifique el nombre de una dirección URL simple, deberá ejecutar Enable-CsComputer en cada director y servidor front-end para registrar el cambio.

## <a name="to-update-the-meet-simple-url"></a>Para actualizar las direcciones URL simples de reunión

1. En el Generador de topologías, haga clic con el botón secundario en el nodo superior **de Skype Empresarial Server** y, a continuación, haga clic en Editar **propiedades.**
    
2. Seleccione **Direcciones URL sencillas** en el panel izquierdo y, a continuación, debajo de Direcciones URL de **reunión:** seleccione la dirección URL de reunión y, a continuación, haga clic **en Editar dirección URL.**
    
3. Actualice la dirección URL al valor deseado y haga clic en **Aceptar** para guardar la dirección URL modificada. 
    
## <a name="to-update-the-admin-simple-url"></a>Para actualizar las direcciones URL simples de administración

1. En el Generador de topologías, haga clic con el botón secundario en el nodo superior **de Skype Empresarial Server** y, a continuación, haga clic en Editar **propiedades.**
    
2. Seleccione **Direcciones URL** sencillas en el panel izquierdo y, a continuación, debajo del cuadro Dirección **URL** de acceso administrativo, escriba la dirección URL sencilla que desea para el acceso administrativo al Panel de control de Skype Empresarial Server y, a continuación, haga clic en **Aceptar.**
    
   > [!TIP]
   > Recomendamos usar la dirección URL más simple posible para la dirección URL de administración. La opción más sencilla es https://admin ... <em>\<domain\></em> 
  
## <a name="see-also"></a>Vea también

[Requisitos de DNS para direcciones URL sencillas en Skype Empresarial Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
