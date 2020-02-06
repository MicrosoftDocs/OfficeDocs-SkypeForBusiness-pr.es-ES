---
title: Diseñar el tronco del SIP para E9-1-1 en Skype empresarial Server
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
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planificación de las topologías de Troncalización SIP para una implementación de E9-1-1 que use proveedores de Troncalización SIP, en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: bd310b39affbea9b4d9328c66b54712c0d388b8d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803080"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Diseñar el tronco del SIP para E9-1-1 en Skype empresarial Server
 
Planificación de las topologías de Troncalización SIP para una implementación de E9-1-1 que use proveedores de Troncalización SIP, en Skype empresarial Server Enterprise Voice.
  
Skype empresarial Server usa los troncos SIP para conectar una llamada de emergencia con el proveedor de servicios E9-1-1. Puedes configurar troncos SIP del servicio de emergencia para E9-1-1 en un sitio central, en varios sitios centrales o en cada sitio de sucursal. Sin embargo, si no está disponible el vínculo WAN entre el sitio de la persona que llama y el sitio que hospeda el tronco del SIP del servicio de emergencia, una llamada realizada por un usuario del sitio desconectado necesitará un registro especial de uso de teléfono en la política de voz del usuario que dirigirá la llamada al ECRC a través de la puerta de enlace de red de telefonía pública conmutada local (RTC). Lo mismo sucede si se aplican los límites de las llamadas simultáneas del servicio de control de admisión de llamadas.
  
Hay dos formas de implementar un tronco de SIP en un entorno de Skype empresarial Server:
  
- Use servidores de mediación multitarjeta que usen sus interfaces de enrutamiento público con el exterior para comunicarse con el proveedor de troncal de SIP.
    
- Use un controlador de borde de sesión (SBC) local para proporcionar un punto de delimitación seguro entre los servidores de mediación y los servicios del proveedor de troncal del SIP.
    
Si eliges el último método, asegúrate de que el modelo y la marca del SBC que elijas estén certificado y admitan el paso de datos de ubicación del objeto de localización del formato de datos de información de presencia (PIDF-LO) como parte de su SIP INVITE. De lo contrario, las llamadas llegarán al proveedor de los servicios de emergencia sin información de su ubicación. Para obtener más información sobre SBCs certificado, consulte ["infraestructura certificada para Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) y ["infraestructura de telefonía para Skype empresarial"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
Los proveedores de servicios E9-1-1 proporcionan acceso a un par de SBCs por redundancia. Debe tomar varias decisiones en relación con la topología de servidor de mediación y la configuración de enrutamiento de llamadas. ¿Tratará tanto SBCs como pares iguales y usará el enrutamiento de operación por turnos para las llamadas entre ellos, o se designará un SBC como principal y el otro como secundario?
  
Para obtener más información sobre la implementación de un tronco SIP en Skype empresarial Server, consulte el caso de [Troncalización SIP en Skype empresarial Server](sip-trunking.md). Las siguientes preguntas te ayudarán a decidir cómo implementar los troncos SIP para E9-1-1.
  
 **¿Tendría que implementar el tronco SIP a través de una conexión alquilada dedicada o de una conexión a Internet compartida?**
  
> Es importante que las llamadas de emergencia conecten siempre. Una línea dedicada proporciona una conexión que no tendrá que cambiarse por otro tráfico de la red y ofrece la posibilidad de implementar Calidad de servicio (QoS). Recuerda que si vas a conectar con proveedores de servicios de emergencia en la red de Internet pública y necesitas garantizar la confidencialidad de las llamadas de emergencia, es necesario el cifrado IPSec. 
    
 **¿Su implementación de E9-1-1 está diseñada para la tolerancia ante desastres?**
  
> Como se trata de una solución de emergencia, la resistencia es importante. Implementar los servidores de mediación y los troncos SIP principales y secundarios en ubicaciones con tolerancia ante desastres. Es buena idea implementar el servidor de mediación principal más cercano a los usuarios que es compatible y enrutar las llamadas de conmutación por error a través del servidor de mediación secundaria (que se encuentra en una ubicación geográfica diferente). 
    
 **¿Tendría que implementar un tronco SIP independiente para cada sucursal?**
  
> Skype empresarial Server ofrece varias estrategias para manejar la resistencia de voz en sucursales, entre las que se incluyen: tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o presionar las llamadas a la puerta de enlace local durante las interrupciones. Para obtener más información, consulte [SIP trunking in Skype for Business Server](sip-trunking.md).
    
 **¿Está habilitado el servicio de control de admisión de llamadas (CAC)?**
  
> Skype empresarial Server no maneja las llamadas de emergencia de ninguna otra forma. Por este motivo, la administración de ancho de banda o el servicio de control de admisión de llamadas (CAC) pueden afectar de forma negativa a una configuración de E9-1-1. Las llamadas de emergencia se pueden bloquear o redirigir a la puerta de enlace RTC local si hay un CAC habilitado y se supera el límite configurado en un vínculo al que se están redirigiendo las llamadas de emergencia. Como se ha indicado antes en este tema, dichas llamadas no tendrán datos de ubicación y se necesitan redirigir manualmente al ECRC.
    

