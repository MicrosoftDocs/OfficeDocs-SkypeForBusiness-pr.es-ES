---
title: Definir el ámbito de la implementación de E9-1-1 en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisiones necesarias para planear una implementación de E9-1-1 en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: fa300ac2f4ba1c0d847abec138b6882e4f240831
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802470"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definir el ámbito de la implementación de E9-1-1 en Skype empresarial Server

Decisiones necesarias para planear una implementación de E9-1-1 en Skype empresarial Server Enterprise Voice.

Antes de configurar Skype empresarial para E9-1-1, necesita planear la implementación de E9-1-1. Algunas de las cuestiones que necesitas tener en cuenta son:

 **¿Cuáles son las obligaciones legales y directivas de la organización en relación con el E9-1-1?**

 Los requisitos legales de E9-1-1 para sistemas PBX (llamados sistemas telefónicos de varias líneas o MLTS, en la terminología de E9-1-1) difieren de un estado a otro. Debe consultar a su equipo legal para comprender las obligaciones que se pueden aplicar a su implementación de Skype empresarial en sus aspectos geográficos relevantes.

 **¿Qué áreas de la empresa necesitan habilitarse para E9-1-1?**

 Puedes habilitar E9-1-1 para determinadas ubicaciones o para toda la empresa. Por ejemplo, puedes tener distintos requisitos de E9-1-1 para oficinas en diferentes estados o quizás desee excluir sitios fuera de EE. UU.

 **¿Cómo implementará E9-1-1 en las sucursales?**

 La resistencia de voz es un concepto que es importante tener en cuenta al implementar E9-1-1 en un sitio de sucursal. Si tienes troncos de E-9-1-1 SIP centralizados y se produce una interrupción de la WAN, es posible que los clientes que inicien sesión no puedan obtener una ubicación del servicio de información de ubicación o para conectar con el proveedor de servicios de servicios de emergencias. Skype empresarial ofrece varias estrategias para manejar la resistencia de voz en sucursales, entre las que se incluyen: tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o presionar llamadas de emergencia a la puerta de enlace local durante las interrupciones. Para obtener más información, mira [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).

 **¿Se habilitará E9-1-1 para los usuarios que trabajan fuera de la red?**

 La adquisición de ubicación automática solo está disponible para los clientes que se encuentran dentro de la red de la organización, por lo que su organización debe decidir si será compatible con las llamadas de E9 de Skype empresarial cuando no estén locales. Por ejemplo, ¿permitirás a los usuarios realizar llamadas de emergencia si trabajan desde casa o desde un sitio del cliente? Si un cliente se encuentra fuera de la red empresarial, puede configurarse para solicitar al usuario una ubicación. Pero como estas ubicaciones proporcionadas por el usuario no pueden validarse previamente con la Guía de calles maestra (MSAG), el distribuidor del proveedor de servicios de emergencia tendrá que confirmar la validez de la ubicación verbalmente con el autor de la llamada antes de redirigir la llamada al punto de respuesta de seguridad pública (PSAP).

> [!NOTE]
> Los clientes de Skype empresarial que se conectan a la red de la organización mediante VPN pueden retomar información interna de la dirección IP, pero estas direcciones no se pueden usar para identificar la ubicación real del usuario, por lo que es esencial que se excluyan las subredes VPN desde el servicio de información de ubicación.

 **¿Desea proporcionar el enrutamiento de llamadas de emergencia a sitios de fuera de Estados Unidos?**

 Puede que quieras proporcionar el enrutamiento de emergencia en áreas de la compañía donde no sirve el proveedor de servicios de emergencia (por ejemplo, en ubicaciones internacionales). Para ello, crea un sitio y luego asigna directivas de voz a los sitios que hagan referencia a un uso de RTC que redirige la llamada a través de la puerta de enlace RTC local.


