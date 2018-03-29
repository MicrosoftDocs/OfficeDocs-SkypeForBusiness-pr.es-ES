---
title: Diseñar el tronco SIP para E9-1-1 en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planificación de las topologías de Troncalización SIP para una implementación de E9-1-1 que utiliza proveedores de Troncalización SIP, en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 588cd32d4c3c7f7aacc9a42d2a2ca8791d036dea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server-2015"></a>Diseñar el tronco SIP para E9-1-1 en Skype Empresarial Server 2015
 
Planificación de las topologías de Troncalización SIP para una implementación de E9-1-1 que utiliza proveedores de Troncalización SIP, en Skype para Telefonía IP empresarial de Business Server.
  
Skype para Business Server utiliza los troncos SIP para conectar una llamada de emergencia al proveedor de servicios E9-1-1. Puedes configurar troncos SIP del servicio de emergencia para E9-1-1 en un sitio central, en varios sitios centrales o en cada sitio de sucursal. Sin embargo, si el vínculo WAN entre los sitios del llamador y el sitio que aloja el tronco SIP de servicio de emergencia no está disponible, entonces una llamada realizada por un usuario en el sitio desconectado tendrá un registro de uso de teléfono especial en la directiva de voz del usuario que se usará para enrutar la llamada a la ECRC a través de la puerta de enlace de local telefónica pública conmutada (PSTN) de la red. Lo mismo sucede si se aplican los límites de las llamadas simultáneas del servicio de control de admisión de llamadas.
  
Hay dos maneras de implementar un troncal SIP en un Skype para entorno Business Server:
  
- Utilizar servidores de mediación multitarjeta que utilizan sus interfaces de públicamente enruta hacia el exterior para comunicarse con el proveedor de tronco SIP.
    
- Utilice un controlador de borde de sesión local (SBC) para proporcionar un punto de demarcación segura entre los servidores de mediación y la troncal SIP servicios del proveedor.
    
Si eliges el último método, asegúrate de que el modelo y la marca del SBC que elijas estén certificado y admitan el paso de datos de ubicación del objeto de localización del formato de datos de información de presencia (PIDF-LO) como parte de su SIP INVITE. De lo contrario, las llamadas llegarán al proveedor de los servicios de emergencia sin información de su ubicación. Para obtener más información acerca de certificados SBCs, vea ["la infraestructura calificados para Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) y ["telefonía infraestructura de Skype para el negocio"](https://technet.microsoft.com/en-us/office/dn947483).
  
Proveedores de servicios de E9-1-1 proporcionan acceso a un par de SBCs para redundancia. Debe tomar varias decisiones con respecto a la topología de servidor de mediación y llamar a la configuración de enrutamiento. ¿Tratar ambas SBCs como iguales del mismo nivel y utilizar el enrutamiento de turnos para las llamadas entre ellos o se designará un SBC como principal y el otro como secundario?
  
Para obtener más información acerca de cómo implementar un troncal SIP en Skype para Business Server, consulte [SIP trunking en Skype para Business Server 2015](sip-trunking.md). Las siguientes preguntas te ayudarán a decidir cómo implementar los troncos SIP para E9-1-1.
  
 **¿Tendría que implementar el tronco SIP a través de una conexión alquilada dedicada o de una conexión a Internet compartida?**
  
> Es importante que las llamadas de emergencia conecten siempre. Una línea dedicada proporciona una conexión que no tendrá que cambiarse por otro tráfico de la red y ofrece la posibilidad de implementar Calidad de servicio (QoS). Recuerda que si vas a conectar con proveedores de servicios de emergencia en la red de Internet pública y necesitas garantizar la confidencialidad de las llamadas de emergencia, es necesario el cifrado IPSec. 
    
 **¿La implementación E9-1-1 está diseñada para tolerancia ante desastres?**
  
> Como se trata de una solución de emergencia, la resistencia es importante. Implementar los troncos de servidores de mediación y SIP primarios y secundarios en ubicaciones tolerante ante desastres. Es una buena idea implementar el servidor de mediación principal más cercano a los usuarios que ya tiene y conmutación por error de ruta llama a través del servidor de mediación secundaria (que se encuentra en una ubicación geográfica diferente). 
    
 **¿Tendría que implementar un tronco SIP independiente para cada sucursal?**
  
> Skype para Business Server proporciona varias estrategias para controlar la resistencia de voz en las sucursales, incluyendo: necesidad de redes de datos adaptable, implementar un troncal SIP en cada sucursal o extraer las llamadas a la puerta de enlace local durante las interrupciones. Para obtener información detallada, vea [SIP trunking en Skype para Business Server 2015](sip-trunking.md).
    
 **¿Está habilitado el servicio de control de admisión de llamadas (CAC)?**
  
> Skype para Business Server hace no identificador de llamadas de emergencia alguna forma diferente que una llamada normal. Por este motivo, la administración de ancho de banda o el servicio de control de admisión de llamadas (CAC) pueden afectar de forma negativa a una configuración de E9-1-1. Las llamadas de emergencia se pueden bloquear o redirigir a la puerta de enlace RTC local si hay un CAC habilitado y se supera el límite configurado en un vínculo al que se están redirigiendo las llamadas de emergencia. Como se ha indicado antes en este tema, dichas llamadas no tendrán datos de ubicación y se necesitan redirigir manualmente al ECRC.
    

