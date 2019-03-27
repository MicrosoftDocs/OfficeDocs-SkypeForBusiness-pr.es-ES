---
title: Definir el ámbito de la implementación de E9-1-1 de Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisiones necesarias para planear una implementación de E9-1-1 en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 014ef9a07679341a7d5eada4ecbad382a9576b61
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889143"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definir el ámbito de la implementación de E9-1-1 de Skype para Business Server

Decisiones necesarias para planear una implementación de E9-1-1 en Skype para Business Server Enterprise Voice.

Antes de configurar Skype para la empresa para E9-1-1, debe planear la implementación de E9-1-1. Algunas de las cuestiones que necesitas tener en cuenta son:

 **¿Cuáles son las obligaciones legales con respecto a E9-1-1 y la directiva de su organización?**

 Los requisitos legales de E9-1-1 para sistemas PBX (llamados sistemas telefónicos de varias líneas o MLTS, en la terminología de E9-1-1) difieren de un estado a otro. Debe consultar a su equipo legal para comprender las obligaciones que se pueden aplicar a la implementación de Skype para la empresa en sus ubicaciones geográficas relevantes.

 **¿Qué áreas de la empresa necesitan habilitarse para E9-1-1?**

 Puedes habilitar E9-1-1 para determinadas ubicaciones o para toda la empresa. Por ejemplo, puedes tener distintos requisitos de E9-1-1 para oficinas en diferentes estados o quizás desee excluir sitios fuera de EE. UU.

 **¿Cómo implementará E9-1-1 en las sucursales?**

 La resistencia de voz es un concepto que es importante tener en cuenta al implementar E9-1-1 en un sitio de sucursal. Si ha centralizado troncos SIP de E-9-1-1 y se produce una interrupción de la WAN, los clientes de inicio de sesión es posible que no pueda para obtener una ubicación de servicio de información de ubicación o para conectarse al proveedor de servicios de emergencia. Skype para la empresa proporciona varias estrategias para controlar la resistencia de voz en sucursales, incluidas: necesidad de redes de datos resistente, implementar un tronco SIP en cada sucursal o extraer las llamadas de emergencia a la puerta de enlace local durante las interrupciones. Para obtener más información, mira [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).

 **¿Se habilitará E9-1-1 para los usuarios que trabajan fuera de la red?**

 Adquisición de ubicación automática sólo está disponible para los clientes que se encuentra dentro de la red de la organización, por lo que la organización debe decidir si va a admitir E9-1-1 las llamadas realizadas desde Skype para clientes empresariales mientras se desactiva locales. Por ejemplo, ¿permitirás a los usuarios realizar llamadas de emergencia si trabajan desde casa o desde un sitio del cliente? Si un cliente se encuentra fuera de la red empresarial, puede configurarse para solicitar al usuario una ubicación. Pero como estas ubicaciones proporcionadas por el usuario no pueden validarse previamente con la Guía de calles maestra (MSAG), el distribuidor del proveedor de servicios de emergencia tendrá que confirmar la validez de la ubicación verbalmente con el autor de la llamada antes de redirigir la llamada al punto de respuesta de seguridad pública (PSAP).

> [!NOTE]
> Skype para clientes empresariales de los usuarios que se conectan a la red de su organización mediante el uso de VPN puede recoger información de la dirección IP interna, pero debido a que estas direcciones no se puede usar para identificar la ubicación del usuario real, es esencial que se excluyen subredes VPN desde el servicio de información de ubicación.

 **¿Desea proporcionar el enrutamiento de llamadas de emergencia a sitios de fuera de Estados Unidos?**

 Puede que quieras proporcionar el enrutamiento de emergencia en áreas de la compañía donde no sirve el proveedor de servicios de emergencia (por ejemplo, en ubicaciones internacionales). Para ello, crea un sitio y luego asigna directivas de voz a los sitios que hagan referencia a un uso de RTC que redirige la llamada a través de la puerta de enlace RTC local.


