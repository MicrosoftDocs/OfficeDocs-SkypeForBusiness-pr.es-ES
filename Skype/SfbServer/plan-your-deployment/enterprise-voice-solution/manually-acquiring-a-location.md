---
title: Definir la experiencia de usuario para adquirir manualmente una ubicación en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planificación para usuarios móviles en una implementación de E9-1-1 mediante proveedores de Troncalización SIP, en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 6a22883fb5f028288ab3fab0246d6c2b3b693987
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server-2015"></a>Definir la experiencia de usuario para adquirir manualmente una ubicación en Skype Empresarial Server 2015
 
Planificación para usuarios móviles en una implementación de E9-1-1 mediante proveedores de Troncalización SIP, en Skype para Telefonía IP empresarial de Business Server.
  
Si un cliente está ubicado fuera de la red, o en una subred indefinida, puede introducir manualmente una ubicación. No obstante, durante una llamada de emergencia, la llamada se enrutará a un distribuidor del centro de respuesta de llamadas de emergencia (ECRC) E9-1-1 nacional y/o regional antes de enrutarla a un punto de respuesta de seguridad pública (PSAP). El distribuidor del ECRC preguntará la ubicación verbalmente a la persona que realice la llamada y, después, desviará la llamada al PSAP adecuado en función de la información proporcionada. 
  
**¿Deben pedirá a los usuarios introducir una ubicación cuando no se proporciona automáticamente por el servicio de información de ubicación?**
  
Por ejemplo, si un cliente se encuentra en una subred no definida, en casa, en una cafetería o en cualquier otro lugar fuera de la red, ¿se debe obligar al usuario a especificar una ubicación?
    
Puede configurar el valor de **Ubicación obligatoria** en la directiva de ubicación para definir el comportamiento del cliente. Si este valor se establece en No, no se pedirá al usuario una ubicación. Si se define en Sí, se pedirá al usuario una ubicación, pero este puede anular la solicitud. Si se define en Declinación de responsabilidades, se pedirá al usuario una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud. En todos los casos, el usuario puede continuar usando el cliente de la forma habitual.
    
Cuando un usuario introduce manualmente una ubicación, la ubicación está asignada a la dirección MAC de la puerta de enlace predeterminada de la red del cliente y se almacena en una tabla de usuario ubicada en el cliente. Cuando el usuario vuelve a cualquier ubicación almacenado previamente, el Skype para Business client se establece automáticamente a esa ubicación. 
  
> [!NOTE]
> Puede modificar sólo en la ubicación actual de su cliente, pero también puede eliminar cualquier ubicación almacenada en la tabla del usuario local. 
  

