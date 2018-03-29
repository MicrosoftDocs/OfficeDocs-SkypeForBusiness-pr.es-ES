---
title: Componentes de conectividad con RTC en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Conozca SIP trunking y puertas de enlace PSTN para Telefonía IP empresarial en Skype para Business Server.
ms.openlocfilehash: 051066643649f9f8f872f4a2795e5ea71417d810
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="pstn-connectivity-components-in-skype-for-business-server-2015"></a>Componentes de conectividad con RTC en Skype Empresarial Server 2015
 
Conozca SIP trunking y puertas de enlace PSTN para Telefonía IP empresarial en Skype para Business Server.
  
Una solución VoIP empresarial necesita proporcionar llamadas entrantes y salientes a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada. Además, los usuarios no tienen por qué conocer la tecnología subyacente cuando realizan o reciben llamadas. Desde la perspectiva del usuario, una llamada entre la infraestructura de Telefonía IP empresarial y PSTN debe parecer otra sesión SIP.
  
En las conexiones de RTC, puedes implementar un tronco SIP o una puerta de enlace RTC (también denominada vínculo SIP directo, con una PBX o sin ella).
  
## <a name="sip-trunking"></a>Enlace troncal SIP

Como alternativa al uso de puertas de enlace PSTN, puede conectar su solución de Telefonía IP empresarial a la RTC mediante SIP trunking. El enlace troncal SIP habilita los siguientes escenarios:
  
- Un usuario de la empresa dentro o fuera del firewall corporativo puede realizar una llamada local o de larga distancia especificada por un número conforme a E.164 con terminación en la RTC como un servicio del proveedor de servicios correspondiente.
    
- Cualquier suscriptor de RTC pueda ponerse en contacto con un usuario de la empresa dentro o fuera del firewall corporativo marcando un número de llamada directa a la extensión (DID) asociado a ese usuario de la empresa.
    
El uso de esta solución de implementación requiere un proveedor de servicios de enlace troncal SIP. 
  
## <a name="pstn-gateways"></a>Puertas de enlace RTC

Puertas de enlace PSTN son dispositivos de otros fabricantes que traducen la señalización y los medios de comunicación entre la infraestructura de Telefonía IP empresarial y un PSTN o PBX. Puertas de enlace PSTN trabajan con el servidor de mediación para presentar una llamada PSTN o PBX a un cliente de Telefonía IP empresarial. El servidor de mediación presenta también llamadas de clientes de Telefonía IP empresarial a la puerta de enlace PSTN para enrutar a la PSTN o PBX. Para obtener una lista de los socios que trabajan con Microsoft para proporcionar dispositivos que funcionan con Skype para Business Server, consulte [el sitio Web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Centrales de conmutación

 Si tiene una infraestructura de voz existente que utiliza una central de conmutación (PBX), puede utilizar su PBX con la Telefonía IP empresarial.
  
Los escenarios de integración de Telefonía IP empresarial-PBX compatibles son los siguientes:
  
- IP-PBX compatible con omisión de medios, con un servidor de mediación.
    
- IP-PBX que requiere una puerta de enlace RTC independiente.
    
- PBX de multiplexación por división de tiempo (TDM), con una puerta de enlace RTC independiente.
    
> [!NOTE]
> La omisión de medios no interactuará con todas las puertas de enlace RTC, las IP-PBX y los SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. Omisión de medios es compatible sólo con los productos y versiones que se enumeran en [Unified Communications interoperabilidad programa abierto - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Para obtener más información acerca de los asociados que ofrecen soluciones de Telefonía IP empresarial, consulte el [sitio Web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Para obtener más información acerca de los asociados que ofrecen soluciones de hardware de Telefonía IP empresarial, incluidas las puertas de enlace PSTN, consulte el [sitio Web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).
  

