---
title: Definir la experiencia de usuario para la adquisición manual de una ubicación en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planificación de usuarios móviles en una implementación de E9-1-1 con proveedores de Troncalización SIP, Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 221c123c9630996d487644d0f5358b95d65fe1a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276722"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definir la experiencia de usuario para la adquisición manual de una ubicación en Skype empresarial Server
 
Planificación de usuarios móviles en una implementación de E9-1-1 con proveedores de Troncalización SIP, Skype empresarial Server Enterprise Voice.
  
Si un cliente está ubicado fuera de la red, o en una subred indefinida, puede introducir manualmente una ubicación. No obstante, durante una llamada de emergencia, la llamada se enrutará a un distribuidor del centro de respuesta de llamadas de emergencia (ECRC) E9-1-1 nacional y/o regional antes de enrutarla a un punto de respuesta de seguridad pública (PSAP). El distribuidor del ECRC preguntará la ubicación verbalmente a la persona que realice la llamada y, después, desviará la llamada al PSAP adecuado en función de la información proporcionada. 
  
**¿Se debe pedir a los usuarios que especifiquen una ubicación cuando el servicio de información de ubicación no los proporcione automáticamente?**
  
Por ejemplo, si un cliente se encuentra en una subred no definida, en casa, en una cafetería o en cualquier otro lugar fuera de la red, ¿se debe obligar al usuario a especificar una ubicación?
    
Puede configurar el valor de **Ubicación obligatoria** en la directiva de ubicación para definir el comportamiento del cliente. Si este valor se establece en No, no se pedirá al usuario una ubicación. Si se define en Sí, se pedirá al usuario una ubicación, pero este puede anular la solicitud. Si se define en Declinación de responsabilidades, se pedirá al usuario una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud. En todos los casos, el usuario puede continuar usando el cliente de la forma habitual.
    
Cuando un usuario escribe manualmente una ubicación, la ubicación se asigna a la dirección MAC de la puerta de enlace predeterminada de la red del cliente y se almacena en una tabla por usuario que se encuentra en el cliente. Cuando el usuario vuelve a una ubicación previamente almacenada, el cliente de Skype empresarial se ajusta automáticamente a esa ubicación. 
  
> [!NOTE]
> Solo puede modificar la ubicación actual del cliente, pero también puede eliminar cualquier ubicación almacenada en la tabla del usuario local. 
  

