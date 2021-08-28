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
ms.localizationpriority: medium
description: Skype Empresarial Server admite direcciones URL sencillas.
ms.openlocfilehash: 8bbbb55262e353ff66adeaca194e7060e3ff7ca5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618316"
---
# <a name="change-simple-urls-after-migration"></a>Cambiar las direcciones URL simples tras la migración

Skype Empresarial Server admite tres direcciones URL sencillas:
  
- **Reunión** sirve como dirección URL base de todas las conferencias del sitio o la organización. Con una dirección URL simple de reunión, los vínculos para unirse a reuniones son fáciles de identificar, comunicar y distribuir. 
    
- **Acceso telefónico** permite el acceso a la página web Configuración de conferencia de acceso telefónico local. La dirección URL simple de acceso telefónico aparece en todas las invitaciones a reuniones para que los usuarios que marquen para unirse a la reunión puedan tener acceso al número de teléfono e información de PIN necesarios. 
    
- **El** administrador habilita el acceso rápido al panel Skype Empresarial Server control. La dirección URL simple de administración es de uso interno para la organización. 
    
Después de migrar a Skype Empresarial Server, debe ser consciente de cómo el cambio afecta a los registros DNS y los certificados de las direcciones URL sencillas. Si el director de Skype Empresarial Server permanece en uso en la topología, no se requieren cambios en las direcciones URL sencillas. Si el director Skype Empresarial Server se quita de la topología después de la migración, los registros DNS de dirección URL simples deben actualizarse para que apunten a uno de los Skype Empresarial Server servidores. Sin embargo, cuando modifique el nombre de una dirección URL simple, deberá ejecutar Enable-CsComputer en cada director y servidor front-end para registrar el cambio.

## <a name="to-update-the-meet-simple-url"></a>Para actualizar las direcciones URL simples de reunión

1. En el Generador de topologías, haga clic con el botón secundario en el nodo superior **Skype Empresarial Server** y, a continuación, haga clic **en Editar propiedades**.
    
2. Seleccione **Direcciones URL sencillas** en el panel izquierdo y, a continuación, debajo de Direcciones URL de **reunión:** seleccione la dirección URL de reunión y, a continuación, haga clic **en Editar dirección URL**.
    
3. Actualice la dirección URL al valor deseado y haga clic en **Aceptar** para guardar la dirección URL modificada. 
    
## <a name="to-update-the-admin-simple-url"></a>Para actualizar las direcciones URL simples de administración

1. En el Generador de topologías, haga clic con el botón secundario en el nodo superior **Skype Empresarial Server** y, a continuación, haga clic **en Editar propiedades**.
    
2. Seleccione **Direcciones URL** sencillas en el panel izquierdo y, a continuación, debajo del cuadro Dirección **URL** de acceso administrativo, escriba la dirección URL sencilla que desea para el acceso administrativo Skype Empresarial Server Panel de control y, a continuación, haga clic en **Aceptar**.
    
   > [!TIP]
   > Recomendamos usar la dirección URL más simple posible para la dirección URL de administración. La opción más sencilla es https://admin . <em>\<domain\></em> . 
  
## <a name="see-also"></a>Consulte también

[Requisitos dns para direcciones URL sencillas en Skype Empresarial Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
