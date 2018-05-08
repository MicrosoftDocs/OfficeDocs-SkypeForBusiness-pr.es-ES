---
title: Componentes de conectividad con RTC en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Obtenga información sobre el enlace troncal SIP y puertas de enlace RTC para Enterprise Voice en Skype para Business Server.
ms.openlocfilehash: 4f346209b483a3d469beba233bd22ee39e45745a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="pstn-connectivity-components-in-skype-for-business-server-2015"></a>Componentes de conectividad con RTC en Skype Empresarial Server 2015
 
Obtenga información sobre el enlace troncal SIP y puertas de enlace RTC para Enterprise Voice en Skype para Business Server.
  
Una solución VoIP empresarial necesita proporcionar llamadas entrantes y salientes a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada. Además, los usuarios no tienen por qué conocer la tecnología subyacente cuando realizan o reciben llamadas. Desde la perspectiva del usuario, una llamada entre la infraestructura de Enterprise Voice y la RTC debe parecer exactamente igual que otra sesión SIP.
  
En las conexiones de RTC, puedes implementar un tronco SIP o una puerta de enlace RTC (también denominada vínculo SIP directo, con una PBX o sin ella).
  
## <a name="sip-trunking"></a>Enlace troncal SIP

Como alternativa al uso de puertas de enlace RTC, puede conectar la solución de Enterprise Voice a la RTC mediante el enlace troncal SIP. El enlace troncal SIP habilita los siguientes escenarios:
  
- Un usuario de la empresa dentro o fuera del firewall corporativo puede realizar una llamada local o de larga distancia especificada por un número conforme a E.164 con terminación en la RTC como un servicio del proveedor de servicios correspondiente.
    
- Cualquier suscriptor de RTC pueda ponerse en contacto con un usuario de la empresa dentro o fuera del firewall corporativo marcando un número de llamada directa a la extensión (DID) asociado a ese usuario de la empresa.
    
El uso de esta solución de implementación requiere un proveedor de servicios de enlace troncal SIP. 
  
## <a name="pstn-gateways"></a>Puertas de enlace RTC

Puertas de enlace RTC son dispositivos de otro fabricante que convierten la señalización y los medios entre la infraestructura de Enterprise Voice y una RTC o un PBX. Puertas de enlace RTC trabajen con el servidor de mediación para presentar una llamada de RTC o PBX a un cliente de Enterprise Voice. El servidor de mediación también presenta llamadas desde clientes de Enterprise Voice a la puerta de enlace de RTC para el enrutamiento a la RTC o PBX. Para obtener una lista de los socios que trabajan con Microsoft para proporcionar dispositivos que funcionan con Skype para Business Server, vea [el sitio Web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Centrales de conmutación

 Si tiene una infraestructura de voz existente que usa una central de conmutación (PBX), puede usar su PBX con Enterprise Voice.
  
Escenarios de integración de Enterprise Voice y PBX admitidos son los siguientes:
  
- IP-PBX que admite el desvío de medios, con un servidor de mediación.
    
- IP-PBX que requiere una puerta de enlace RTC independiente.
    
- PBX de multiplexación por división de tiempo (TDM), con una puerta de enlace RTC independiente.
    
> [!NOTE]
> La omisión de medios no interactuará con todas las puertas de enlace RTC, las IP-PBX y los SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. Desvío de medios es compatible solo con productos y versiones que aparece al [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Para obtener información detallada acerca de los socios que ofrecen soluciones de Enterprise Voice, consulte el [sitio Web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Para obtener información detallada acerca de los socios que ofrecen soluciones de hardware de Enterprise Voice, incluidas las puertas de enlace RTC, consulte el [sitio Web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).
  

