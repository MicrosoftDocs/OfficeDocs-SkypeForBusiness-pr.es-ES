---
title: Definir la experiencia del usuario para adquirir manualmente una ubicación en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planeación de usuarios móviles en una implementación de E9-1-1 con proveedores de enlace troncal SIP, en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: d412c3368dc6f3e302ab8f589aaed1585ea0b233
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855287"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definir la experiencia del usuario para adquirir manualmente una ubicación en Skype Empresarial Server
 
Planeación de usuarios móviles en una implementación de E9-1-1 con proveedores de enlace troncal SIP, en Skype Empresarial Server Telefonía IP empresarial.
  
Si un cliente está ubicado fuera de la red, o en una subred indefinida, puede introducir manualmente una ubicación. No obstante, durante una llamada de emergencia, se enrutará la llamada a un distribuidor del centro de respuesta de llamadas de emergencia (ECRC) E9-1-1 nacional y/o regional antes de enrutarla a un punto de respuesta de seguridad pública (PSAP). El distribuidor del ECRC preguntará la ubicación verbalmente a la persona que realice la llamada y después desviará la llamada al PSAP adecuado en función de la información proporcionada. 
  
**¿Se debe pedir a los usuarios que escriban una ubicación cuando el servicio de información de ubicación no proporciona una automáticamente?**
  
Por ejemplo, ¿si un cliente se encuentra en una subred no definida, en casa, en una cafetería o en cualquier otro lugar fuera de la red, se debe obligar al usuario a introducir una ubicación?
    
Puede configurar la configuración **Ubicación requerida** en la directiva de ubicación para definir el comportamiento del cliente. Establecer este valor en No significa que no se pedirá al usuario una ubicación. Establecer este valor en Sí significa que se pedirá al usuario una ubicación, pero puede descartar el mensaje. Establecer este valor en Aviso de declinación de responsabilidades significa que se pedirá al usuario una ubicación y se mostrará un aviso de declinación de responsabilidades si intenta descartar el mensaje. En todos los casos, el usuario puede seguir usando el cliente como de costumbre.
    
Cuando un usuario escribe manualmente una ubicación, la ubicación se asigna a la dirección MAC de la puerta de enlace predeterminada de la red del cliente y se almacena en una tabla por usuario ubicada en el cliente. Cuando el usuario vuelve a cualquier ubicación almacenada anteriormente, Skype Empresarial cliente se establece automáticamente en esa ubicación. 
  
> [!NOTE]
> Solo puede modificar la ubicación actual del cliente, pero también puede eliminar cualquier ubicación almacenada en la tabla del usuario local. 
  

