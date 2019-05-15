---
title: Definir la experiencia del usuario para adquirir manualmente una ubicación en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planeación para usuarios móviles en una implementación de E9-1-1 mediante proveedores de enlace troncal SIP, en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 503d1cb55afcf23809db851751db0b126504e4f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924167"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definir la experiencia del usuario para adquirir manualmente una ubicación en Skype para Business Server
 
Planeación para usuarios móviles en una implementación de E9-1-1 mediante proveedores de enlace troncal SIP, en Skype para Business Server Enterprise Voice.
  
Si un cliente está ubicado fuera de la red, o en una subred indefinida, puede introducir manualmente una ubicación. No obstante, durante una llamada de emergencia, la llamada se enrutará a un distribuidor del centro de respuesta de llamadas de emergencia (ECRC) E9-1-1 nacional y/o regional antes de enrutarla a un punto de respuesta de seguridad pública (PSAP). El distribuidor del ECRC preguntará la ubicación verbalmente a la persona que realice la llamada y, después, desviará la llamada al PSAP adecuado en función de la información proporcionada. 
  
**¿Los usuarios se deben pedir para especificar una ubicación cuando no se proporciona automáticamente por el servicio de información de ubicación?**
  
Por ejemplo, si un cliente se encuentra en una subred no definida, en casa, en una cafetería o en cualquier otro lugar fuera de la red, ¿se debe obligar al usuario a especificar una ubicación?
    
Puede configurar el valor de **Ubicación obligatoria** en la directiva de ubicación para definir el comportamiento del cliente. Si este valor se establece en No, no se pedirá al usuario una ubicación. Si se define en Sí, se pedirá al usuario una ubicación, pero este puede anular la solicitud. Si se define en Declinación de responsabilidades, se pedirá al usuario una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud. En todos los casos, el usuario puede continuar usando el cliente de la forma habitual.
    
Cuando un usuario escribe manualmente una ubicación, la ubicación está asignada a la dirección MAC de la puerta de enlace predeterminada de la red del cliente y se almacena en una tabla por usuario que se encuentra en el cliente. Cuando el usuario vuelve a cualquier ubicación previamente almacenado, el Skype para clientes empresariales se establece automáticamente a esa ubicación. 
  
> [!NOTE]
> Puede modificar sólo en la ubicación actual del cliente, pero también puede eliminar cualquier ubicación almacenada en la tabla del usuario local. 
  

