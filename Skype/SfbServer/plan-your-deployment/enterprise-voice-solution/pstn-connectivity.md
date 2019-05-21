---
title: Componentes de conectividad RTC en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Obtenga más información sobre la Troncalización SIP y las puertas de enlace RTC para telefonía IP empresarial en Skype empresarial Server.
ms.openlocfilehash: 6d11ea3204c9b924c9e700194ee04beb9a0df56c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276486"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>Componentes de conectividad RTC en Skype empresarial Server
 
Obtenga más información sobre la Troncalización SIP y las puertas de enlace RTC para telefonía IP empresarial en Skype empresarial Server.
  
Una solución VoIP empresarial necesita proporcionar llamadas entrantes y salientes a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada. Además, los usuarios no tienen por qué conocer la tecnología subyacente cuando realizan o reciben llamadas. Desde el punto de vista del usuario, una llamada entre la infraestructura de telefonía IP empresarial y la RTC debe parecer simplemente otra sesión de SIP.
  
En las conexiones de RTC, puedes implementar un tronco SIP o una puerta de enlace RTC (también denominada vínculo SIP directo, con una PBX o sin ella).
  
## <a name="sip-trunking"></a>Enlace troncal SIP

Como alternativa al uso de puertas de enlace RTC, puede conectar su solución de telefonía empresarial a la RTC mediante el uso de troncales SIP. El enlace troncal SIP habilita los siguientes escenarios:
  
- Un usuario de la empresa dentro o fuera del firewall corporativo puede realizar una llamada local o de larga distancia especificada por un número conforme a E.164 con terminación en la RTC como un servicio del proveedor de servicios correspondiente.
    
- Cualquier suscriptor de RTC pueda ponerse en contacto con un usuario de la empresa dentro o fuera del firewall corporativo marcando un número de llamada directa a la extensión (DID) asociado a ese usuario de la empresa.
    
El uso de esta solución de implementación requiere un proveedor de servicios de enlace troncal SIP. 
  
## <a name="pstn-gateways"></a>Puertas de enlace RTC

Las puertas de enlace RTC son dispositivos de terceros que traducen la señalización y los medios entre la infraestructura de voz empresarial y una RTC o un sistema PBX. Las puertas de enlace RTC funcionan con el servidor de mediación para presentar una llamada RTC o PBX a un cliente de telefonía empresarial. El servidor de mediación también presenta llamadas de clientes de telefonía de empresa a la puerta de enlace RTC para el enrutamiento a la RTC o a la PBX. Para obtener una lista de los socios que trabajan con Microsoft para proporcionar dispositivos que funcionen con Skype empresarial Server, consulte [el sitio web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Centrales de conmutación

 Si ya tiene una infraestructura de voz que usa una central de conmutación (PBX), puede usar su PBX con telefonía IP empresarial.
  
Los escenarios de integración de la telefonía IP empresarial compatibles son los siguientes:
  
- IP-PBX que admite omisión de medios, con un servidor de mediación.
    
- IP-PBX que requiere una puerta de enlace RTC independiente.
    
- PBX de multiplexación por división de tiempo (TDM), con una puerta de enlace RTC independiente.
    
> [!NOTE]
> La omisión de medios no interactuará con todas las puertas de enlace RTC, las IP-PBX y los SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con las IP-PBX de Cisco. La omisión de contenido multimedia solo se admite con productos y versiones que se muestran en [el programa de interoperabilidad abierto de comunicaciones unificadas: Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Para obtener más información sobre los partners que ofrecen soluciones de telefonía IP empresarial, consulte el [sitio web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Para obtener más información sobre los partners que ofrecen soluciones de hardware de voz empresarial, incluidas las puertas de enlace RTC, consulte el [sitio web de socios de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).
  

