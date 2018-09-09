---
title: Diseñar el tronco SIP para E9-1-1 en Skype para Business Server
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
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planeación de las topologías de enlace troncal SIP para una implementación de E9-1-1 que usa los proveedores de enlace troncal SIP, en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 7640cbd78dadaac999327becce360bf5ea865ef5
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885541"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Diseñar el tronco SIP para E9-1-1 en Skype para Business Server
 
Planeación de las topologías de enlace troncal SIP para una implementación de E9-1-1 que usa los proveedores de enlace troncal SIP, en Skype para Business Server Enterprise Voice.
  
Skype para Business Server usa troncos SIP para conectarse a una llamada de emergencia al proveedor de servicios E9-1-1. Puedes configurar troncos SIP del servicio de emergencia para E9-1-1 en un sitio central, en varios sitios centrales o en cada sitio de sucursal. Sin embargo, si el vínculo WAN entre sitios el autor de la llamada y el sitio que hospeda el tronco SIP de servicio de emergencia no está disponible, a continuación, una llamada realizada por un usuario en el sitio desconectado necesitará un registro de uso de teléfono especial en la directiva de voz del usuario que se usará para enrutar la llamada a la ECRC a través de la puerta de enlace de local telefónica conmutada (RTC). Lo mismo sucede si se aplican los límites de las llamadas simultáneas del servicio de control de admisión de llamadas.
  
Hay dos formas de implementar un tronco SIP en un Skype para entorno Business Server:
  
- Usar los servidores de mediación de host múltiple que usan sus interfaces de enrutadas públicamente y orientadas hacia fuera para comunicarse con el proveedor de troncos SIP.
    
- Use un controlador de borde de sesión (SBC) local para proporcionar un punto de demarcación segura entre los servidores de mediación y el tronco SIP servicios del proveedor.
    
Si eliges el último método, asegúrate de que el modelo y la marca del SBC que elijas estén certificado y admitan el paso de datos de ubicación del objeto de localización del formato de datos de información de presencia (PIDF-LO) como parte de su SIP INVITE. De lo contrario, las llamadas llegarán al proveedor de los servicios de emergencia sin información de su ubicación. Para obtener información detallada acerca de SBCs certificadas, vea ["la infraestructura completa para Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) y ["telefonía infraestructura de Skype para profesionales"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
Proveedores de servicios E9-1-1 de proporcionan acceso a un par de SBCs para conseguir redundancia. Debe tomar varias decisiones con respecto a la topología de servidor de mediación y la configuración de enrutamiento de llamadas. ¿Tratar ambas SBCs como igual del mismo nivel y usar el enrutamiento round-robin para las llamadas entre ellas, o se designa una SBC como principal y el otro como secundaria?
  
Para obtener información detallada sobre la implementación de un tronco SIP en Skype para Business Server, consulte el [enlace troncal SIP en Skype para Business Server](sip-trunking.md). Las siguientes preguntas te ayudarán a decidir cómo implementar los troncos SIP para E9-1-1.
  
 **¿Tendría que implementar el tronco SIP a través de una conexión alquilada dedicada o de una conexión a Internet compartida?**
  
> Es importante que las llamadas de emergencia conecten siempre. Una línea dedicada proporciona una conexión que no tendrá que cambiarse por otro tráfico de la red y ofrece la posibilidad de implementar Calidad de servicio (QoS). Recuerda que si vas a conectar con proveedores de servicios de emergencia en la red de Internet pública y necesitas garantizar la confidencialidad de las llamadas de emergencia, es necesario el cifrado IPSec. 
    
 **¿La implementación de E9-1-1 está diseñada para tolerar desastres?**
  
> Como se trata de una solución de emergencia, la resistencia es importante. Implementar los troncos de los servidores de mediación y SIP principales y secundarios en ubicaciones tolerante ante desastres. Es una buena idea para implementar el servidor de mediación principal más cercano a los usuarios que esté ofreciendo compatibilidad y conmutación por error de ruta llama a través del servidor de mediación secundario (que se encuentra en una ubicación geográfica diferente). 
    
 **¿Tendría que implementar un tronco SIP independiente para cada sucursal?**
  
> Skype para Business Server proporciona varias estrategias para controlar la resistencia de voz en sucursales, incluidas: necesidad de redes de datos resistente, implementar un tronco SIP en cada sucursal o extraer las llamadas a la puerta de enlace local durante las interrupciones. Para obtener información detallada, vea [enlace troncal SIP en Skype para Business Server](sip-trunking.md).
    
 **¿Está habilitado el servicio de control de admisión de llamadas (CAC)?**
  
> Skype para Business Server hace no controlar las llamadas de emergencia cualquiera diferente de una llamada normal. Por este motivo, la administración de ancho de banda o el servicio de control de admisión de llamadas (CAC) pueden afectar de forma negativa a una configuración de E9-1-1. Las llamadas de emergencia se pueden bloquear o redirigir a la puerta de enlace RTC local si hay un CAC habilitado y se supera el límite configurado en un vínculo al que se están redirigiendo las llamadas de emergencia. Como se ha indicado antes en este tema, dichas llamadas no tendrán datos de ubicación y se necesitan redirigir manualmente al ECRC.
    

