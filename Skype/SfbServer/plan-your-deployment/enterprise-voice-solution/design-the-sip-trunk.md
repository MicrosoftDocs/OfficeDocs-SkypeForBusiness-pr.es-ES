---
title: Diseñar el tronco SIP para E9-1-1 en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Planear las topologías de enlace troncal SIP para una implementación E9-1-1 que usa proveedores de enlace troncal SIP, en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 8685b3263b9e3b6f98bc94e190ac9dd8207348df
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112696"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Diseñar el tronco SIP para E9-1-1 en Skype Empresarial Server
 
Planear las topologías de enlace troncal SIP para una implementación E9-1-1 que usa proveedores de enlace troncal SIP, en Skype Empresarial Server Telefonía IP empresarial.
  
Skype Empresarial Server usa troncos SIP para conectar una llamada de emergencia al proveedor de servicios E9-1-1. Puede configurar un tronco SIP de servicio de emergencia para E9-1-1 en un sitio central, en varios sitios centrales o en cada sitio de sucursal. Sin embargo, si el vínculo WAN entre el sitio del autor de la llamada y el sitio que hospeda el tronco SIP del servicio de emergencia no está disponible, una llamada realizada por un usuario en el sitio desconectado necesitará un registro de uso de teléfono especial en la directiva de voz del usuario que enruta la llamada al ECRC a través de la puerta de enlace de la red telefónica conmutada (RTC) local. Lo mismo sucede si se aplica un control de admisión de llamadas a la llamada.
  
Hay dos formas de implementar un tronco SIP en un entorno de Skype Empresarial Server:
  
- Use servidores de mediación multihomed que usen sus interfaces enrutadas públicamente para comunicarse con el proveedor de troncos SIP.
    
- Use un controlador de borde de sesión (SBC) local para proporcionar un punto de demarcación seguro entre los servidores de mediación y los servicios del proveedor troncal SIP.
    
Si elige el último método, asegúrese de que el modelo y la marca SBC que elija admite el paso de datos de ubicación PIDF-LO (Presence Information Data Format Location Object, en inglés) como parte de su SIP INVITE. De lo contrario, las llamadas llegarán al proveedor de los servicios de emergencia sin información de su ubicación. Para obtener más información acerca de los SBC certificados, vea "Infraestructura calificada para [Microsoft Lync"](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) y ["Infraestructura de telefonía para Skype Empresarial".](../../../SfbPartnerCertification/certification/infra-gateways.md) 
  
Los proveedores de servicios E9-1-1 le proporcionan acceso a un par de SBC para redundancia. Debe tomar varias decisiones con respecto a la topología del servidor de mediación y la configuración de enrutamiento de llamadas. ¿Tratará a ambos SBC como pares iguales y usará el enrutamiento por turnos para llamadas entre ellos, o designará un SBC como principal y el otro como secundario?
  
Para obtener más información sobre cómo implementar un tronco SIP en Skype Empresarial Server, vea Enlace troncal [SIP en Skype Empresarial Server](sip-trunking.md). Las siguientes preguntas le ayudarán a decidir cómo implementar troncos SIP para E9-1-1.
  
 **¿Tendrá que implementar el tronco SIP a través de una conexión alquilada dedicada o de una conexión a Internet compartida?**
  
> Es importante que las llamadas de emergencia conecten siempre. Una línea dedicada proporciona una conexión que no tendrá que reemplazarse por otro tráfico de la red y ofrece la posibilidad de implementar Calidad de servicio (QoS). Recuerde que si va a conectar con proveedores de servicios de emergencia en Internet público y debe garantizar la confidencialidad de las llamas de emergencia, es necesario el cifrado IPSec. 
    
 **¿La implementación de E9-1-1 está diseñada para la tolerancia ante desastres?**
  
> Como se trata de una solución de emergencia, la resistencia es importante. Implemente los servidores de mediación principales y secundarios y los troncos SIP en ubicaciones tolerantes a desastres. Es una buena idea implementar el servidor de mediación principal más cercano a los usuarios que admite y enrutar llamadas de conmutación por error a través del servidor de mediación secundario (ubicado en una ubicación geográfica diferente). 
    
 **¿Deberá implementar un tronco SIP independiente para cada sucursal?**
  
> Skype Empresarial Server proporciona varias estrategias para controlar la resistencia de voz en las sucursales, como tener redes de datos resistentes, implementar un tronco SIP en cada rama o insertar llamadas a la puerta de enlace local durante las interrupciones. Para obtener más información, [vea Enlace troncal SIP en Skype Empresarial Server](sip-trunking.md).
    
 **¿Está habilitado el servicio de control de admisión de llamadas (CAC)?**
  
> Skype Empresarial Server no controla las llamadas de emergencia de forma diferente a una llamada normal. Por este motivo, la administración de ancho de banda o el servicio de control de admisión de llamadas (CAC) puede afectar de forma negativa a una configuración de E9-1-1. Las llamadas de emergencia se pueden bloquear o enrutar a la puerta de enlace RTC local si hay un CAC habilitado y se supera el límite configurado en un vínculo al que se están enrutando las llamadas de emergencia. Como se ha indicado antes en este tema, dichas llamadas no tendrán datos de ubicación y se deben enrutar manualmente al ECRC.
